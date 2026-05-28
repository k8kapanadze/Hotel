აქ მოცემულია სრული, ერთიანი ფაილი, სადაც გაერთიანებულია ტიპები, დამხმარე მექანიზმები და მთავარი აპლიკაციის კომპონენტი. ეს კოდი შეგიძლიათ პირდაპირ ჩასვათ თქვენს პროექტში (მაგალითად, `MedicalPlatform.tsx` ფაილში).

იგი აწყობილია **React + TypeScript + Tailwind CSS**-ზე, იყენებს **Lucide React** ხატულებს და სრულიად თავისუფალია ყოველგვარი გარე ხელოვნური ინტელექტის კვალისგან.

```tsx
import React, { useState, useEffect } from 'react';
import { Upload, Star, AlertCircle, Play, Save, Download, RefreshCw, FileText, CheckCircle2, Moon, Sun, ChevronRight, ListFilter } from 'lucide-react';

// ============================================================================
// 1. ტიპების დეკლარაცია (TYPES)
// ============================================================================
export interface Question {
  id: string;
  text: string;
  correctAnswer: string;
  incorrectAnswers: string[];
  allAnswers: string[]; // ორმაგი არევის (Double Shuffle) შემდგომი მასივი
  sourceFile: string;
}

export interface FileData {
  id: string;
  name: string;
  questions: Question[];
}

export interface SavedMistakeSet {
  id: string;
  timestamp: number;
  name: string;
  sourceFile: string;
  questions: Question[];
}

export type AppMode = 'setup' | 'quiz' | 'review_mistakes' | 'review_starred' | 'results';
export type QuizType = 'standard' | 'multi_exam';

// ============================================================================
// 2. დამხმარე მოდულები (UTILS)
// ============================================================================
export const shuffleArray = <T>(array: T[]): T[] => {
  const arr = [...array];
  for (let i = arr.length - 1; i > 0; i--) {
    const j = Math.floor(Math.random() * (i + 1));
    [arr[i], arr[j]] = [arr[j], arr[i]];
  }
  return arr;
};

export const parseMedicalFile = (text: string, fileName: string): Question[] => {
  const lines = text.split('\n').map(l => l.trim()).filter(l => l.length > 0);
  const questions: Question[] = [];
  
  let currentQuestionText = '';
  let correct: string = '';
  let incorrects: string[] = [];
  
  const pushCurrent = () => {
    if (currentQuestionText && correct && incorrects.length > 0) {
      const allAnswers = shuffleArray([correct, ...incorrects]);
      questions.push({
        id: `${fileName}_${Date.now()}_${Math.random().toString(36).substr(2, 5)}`,
        text: currentQuestionText,
        correctAnswer: correct,
        incorrectAnswers: incorrects,
        allAnswers,
        sourceFile: fileName
      });
    }
  };

  lines.forEach(line => {
    if (line.startsWith('////')) {
      pushCurrent();
      currentQuestionText = line.replace('////', '').trim();
      correct = '';
      incorrects = [];
    } else if (line.startsWith('//')) {
      correct = line.replace('//', '').trim();
    } else if (line.startsWith('///')) {
      incorrects.push(line.replace('///', '').trim());
    }
  });
  pushCurrent();
  return questions;
};

// ============================================================================
// 3. მთავარი კომპონენტი (MAIN PLATFORM COMPONENT)
// ============================================================================
export const MedicalPlatform: React.FC = () => {
  // ვიზუალური თემები და ძირითადი რეჟიმები
  const [darkMode, setDarkMode] = useState<boolean>(true);
  const [appMode, setAppMode] = useState<AppMode>('setup');
  const [quizType, setQuizType] = useState<QuizType>('standard');
  const [nightAlert, setNightAlert] = useState<boolean>(false);

  // მონაცემთა ბაზები
  const [uploadedFiles, setUploadedFiles] = useState<FileData[]>([]);
  const [selectedFileId, setSelectedFileId] = useState<string>('');
  const [multiConfig, setMultiConfig] = useState<{ [fileId: string]: number }>({});
  
  // აქტიური ტესტირების მენეჯმენტი
  const [activeQuestions, setActiveQuestions] = useState<Question[]>([]);
  const [currentIndex, setCurrentIndex] = useState<number>(0);
  const [selectedAnswer, setSelectedAnswer] = useState<string | null>(null);
  const [isAnswered, setIsAnswered] = useState<boolean>(false);
  const [isAutoMode, setIsAutoMode] = useState<boolean>(true);
  
  // დინამიკური ფილტრები და ამოჭრის სისტემა
  const [rangeStart, setRangeStart] = useState<string>('');
  const [rangeEnd, setRangeEnd] = useState<string>('');
  const [cutStart, setCutStart] = useState<string>('');
  const [cutEnd, setCutEnd] = useState<string>('');
  const [jumpIndex, setJumpIndex] = useState<string>('');

  // მომხმარებლის პროგრესის ჩანაწერები
  const [starredIds, setStarredIds] = useState<string[]>([]);
  const [sessionMistakes, setSessionMistakes] = useState<Question[]>([]);
  const [savedMistakeSets, setSavedMistakeSets] = useState<SavedMistakeSet[]>([]);
  const [quizStats, setQuizStats] = useState({ correct: 0, totalPassed: 0, initialTotal: 0 });
  const [pausedPosition, setPausedPosition] = useState<number | null>(null);

  // ღამის 12 საათის შემოწმების ლოგიკა
  useEffect(() => {
    const hours = new Date().getHours();
    if (hours === 0 || hours === 24) setNightAlert(true);
  }, [appMode]);

  // კლავიატურით მართვის მხარდაჭერა (Hotkeys)
  useEffect(() => {
    const handleKeyDown = (e: KeyboardEvent) => {
      if (appMode !== 'quiz' && appMode !== 'review_mistakes' && appMode !== 'review_starred') return;
      
      if (['1', '2', '3', '4'].includes(e.key) && !isAnswered) {
        const idx = parseInt(e.key) - 1;
        const currentQ = activeQuestions[currentIndex];
        if (currentQ && currentQ.allAnswers[idx]) handleAnswerSelection(currentQ.allAnswers[idx]);
      } else if (e.key === 'Enter' && isAnswered) {
        handleNextQuestion();
      } else if (e.key === 'f' || e.key === 'F') {
        if (activeQuestions[currentIndex]) toggleStar(activeQuestions[currentIndex].id);
      }
    };
    window.addEventListener('keydown', handleKeyDown);
    return () => window.removeEventListener('keydown', handleKeyDown);
  }, [appMode, currentIndex, isAnswered, activeQuestions]);

  // ფაილების ატვირთვა და დამუშავება
  const handleFileUpload = (e: React.ChangeEvent<HTMLInputElement>) => {
    const files = e.target.files;
    if (!files) return;
    Array.from(files).forEach(file => {
      const reader = new FileReader();
      reader.onload = (evt) => {
        const text = evt.target?.result as string;
        const parsed = parseMedicalFile(text, file.name);
        if (parsed.length > 0) {
          const newFile: FileData = { id: `file_${Date.now()}_${Math.random().toString(36).substr(2, 5)}`, name: file.name, questions: parsed };
          setUploadedFiles(prev => [...prev, newFile]);
          if (!selectedFileId) setSelectedFileId(newFile.id);
        }
      };
      reader.readAsText(file);
    });
  };

  // ტესტის ინიციალიზაცია (ორმაგი შაფლი და ფილტრაცია)
  const initStandardQuiz = () => {
    const sourceFile = uploadedFiles.find(f => f.id === selectedFileId);
    if (!sourceFile) return;
    let baseQuestions = [...sourceFile.questions];

    // დიაპაზონის ამოჭრა
    if (rangeStart || rangeEnd) {
      const start = rangeStart ? Math.max(1, parseInt(rangeStart)) - 1 : 0;
      const end = rangeEnd ? Math.min(baseQuestions.length, parseInt(rangeEnd)) : baseQuestions.length;
      baseQuestions = baseQuestions.slice(start, end);
    }

    // კონკრეტული მონაკვეთის სრული ამოშლა ბაზიდან
    if (cutStart && cutEnd) {
      const cStart = Math.max(1, parseInt(cutStart)) - 1;
      const cEnd = Math.min(baseQuestions.length, parseInt(cutEnd));
      baseQuestions.splice(cStart, cEnd - cStart);
    }

    if (baseQuestions.length === 0) return alert('არჩეულ დიაპაზონში კითხვები არ არის!');

    // ორმაგი არევის (Double Shuffle) მექანიზმი
    let prepared = shuffleArray(baseQuestions).map(q => ({ 
      ...q, 
      allAnswers: shuffleArray([q.correctAnswer, ...q.incorrectAnswers]) 
    }));

    // კონკრეტული კითხვიდან დაწყება / გაგრძელება
    if (jumpIndex) {
      const target = Math.max(1, Math.min(prepared.length, parseInt(jumpIndex))) - 1;
      setCurrentIndex(target);
    } else {
      setCurrentIndex(0);
    }

    setActiveQuestions(prepared);
    setQuizStats({ correct: 0, totalPassed: 0, initialTotal: prepared.length });
    setSessionMistakes([]);
    setIsAnswered(false);
    setSelectedAnswer(null);
    setAppMode('quiz');
  };

  // მულტი-ფაილური კომბინირებული გამოცდის რეჟიმი
  const initMultiExamQuiz = () => {
    let combined: Question[] = [];
    for (const fileId in multiConfig) {
      const file = uploadedFiles.find(f => f.id === fileId);
      const requestedQty = multiConfig[fileId];
      if (!file || !requestedQty) continue;
      
      if (file.questions.length < requestedQty) {
        alert(`ფაილში ${file.name} არ არის საკმარისი კითხვები (მოთხოვნილია: ${requestedQty}, არსებობს: ${file.questions.length})`);
        return;
      }
      const sampled = shuffleArray([...file.questions]).slice(0, requestedQty);
      combined = [...combined, ...sampled];
    }
    if (combined.length === 0) return;
    
    let prepared = shuffleArray(combined).map(q => ({ 
      ...q, 
      allAnswers: shuffleArray([q.correctAnswer, ...q.incorrectAnswers]) 
    }));
    
    setCurrentIndex(0);
    setActiveQuestions(prepared);
    setQuizStats({ correct: 0, totalPassed: 0, initialTotal: prepared.length });
    setSessionMistakes([]);
    setIsAnswered(false);
    setSelectedAnswer(null);
    setAppMode('quiz');
  };

  // პასუხის მონიშვნა და შეფასება
  const handleAnswerSelection = (answer: string) => {
    if (isAnswered) return;
    setSelectedAnswer(answer);
    setIsAnswered(true);
    const currentQ = activeQuestions[currentIndex];
    const isCorrect = answer === currentQ.correctAnswer;

    if (isCorrect) {
      setQuizStats(prev => ({ ...prev, correct: prev.correct + 1, totalPassed: prev.totalPassed + 1 }));
      if (isAutoMode && appMode === 'quiz') {
        setTimeout(() => { forwardToNext(); }, 800);
      }
    } else {
      setQuizStats(prev => ({ ...prev, totalPassed: prev.totalPassed + 1 }));
      if (!sessionMistakes.some(m => m.id === currentQ.id)) {
        setSessionMistakes(prev => [...prev, currentQ]);
      }
    }
  };

  const forwardToNext = () => {
    if (currentIndex + 1 < activeQuestions.length) {
      setCurrentIndex(prev => prev + 1);
      setSelectedAnswer(null);
      setIsAnswered(false);
    } else {
      setAppMode('results');
    }
  };

  const handleNextQuestion = () => { forwardToNext(); };

  // შეცდომების მუშაობის რეჟიმი რეალურ დროში (Instant Interruption)
  const triggerInstantMistakeReview = () => {
    if (sessionMistakes.length === 0) return;
    setPausedPosition(currentIndex);
    const preparedMistakes = shuffleArray([...sessionMistakes]).map(q => ({ 
      ...q, 
      allAnswers: shuffleArray([q.correctAnswer, ...q.incorrectAnswers]) 
    }));
    setActiveQuestions(preparedMistakes);
    setCurrentIndex(0);
    setSelectedAnswer(null);
    setIsAnswered(false);
    setAppMode('review_mistakes');
  };

  const terminateMistakeReview = () => {
    if (pausedPosition !== null) {
      initStandardQuiz();
      setCurrentIndex(pausedPosition);
      setPausedPosition(null);
    } else {
      setAppMode('setup');
    }
  };

  // ვარსკვლავით მონიშვნის სისტემა (Flagging)
  const toggleStar = (id: string) => {
    setStarredIds(prev => prev.includes(id) ? prev.filter(i => i !== id) : [...prev, id]);
  };

  const initStarredReview = () => {
    const allUploadedQuestions = uploadedFiles.flatMap(f => f.questions);
    const targets = allUploadedQuestions.filter(q => starredIds.includes(q.id));
    if (targets.length === 0) return;
    
    let prepared = shuffleArray(targets).map(q => ({ 
      ...q, 
      allAnswers: shuffleArray([q.correctAnswer, ...q.incorrectAnswers]) 
    }));
    setActiveQuestions(prepared);
    setCurrentIndex(0);
    setSelectedAnswer(null);
    setIsAnswered(false);
    setAppMode('review_starred');
  };

  // შეცდომების ექსპორტი და შენახვა
  const exportMistakesAsJSON = () => {
    if (sessionMistakes.length === 0) return;
    const dataStr = "data:text/json;charset=utf-8," + encodeURIComponent(JSON.stringify(sessionMistakes, null, 2));
    const dlAnchor = document.createElement('a');
    dlAnchor.setAttribute("href", dataStr);
    dlAnchor.setAttribute("download", `Mistakes_Session_${Date.now()}.json`);
    dlAnchor.click();
  };

  const saveMistakesToState = () => {
    if (sessionMistakes.length === 0) return;
    const currentFile = uploadedFiles.find(f => f.id === selectedFileId);
    const newSet: SavedMistakeSet = {
      id: `mistake_${Date.now()}`,
      timestamp: Date.now(),
      name: `შეცდომები - ${currentFile?.name || 'სიმულატორი'}`,
      sourceFile: currentFile?.name || 'Mixed Exam',
      questions: [...sessionMistakes]
    };
    setSavedMistakeSets(prev => [newSet, ...prev]);
    alert('შეცდომების ბაზა წარმატებით შეინახა პლატფორმაზე!');
  };

  const runSavedMistakeSet = (set: SavedMistakeSet) => {
    let prepared = shuffleArray([...set.questions]).map(q => ({ 
      ...q, 
      allAnswers: shuffleArray([q.correctAnswer, ...q.incorrectAnswers]) 
    }));
    setActiveQuestions(prepared);
    setCurrentIndex(0);
    setSelectedAnswer(null);
    setIsAnswered(false);
    setAppMode('review_mistakes');
  };

  // მოტივაციური შეტყობინებების ლოგიკა ტესტის ბოლოს
  const renderMotivationalFeedback = () => {
    const total = quizStats.initialTotal;
    if (total === 0) return null;
    const errorRatio = (sessionMistakes.length / total) * 100;
    
    if (errorRatio < 10) {
      return (
        <div className="p-5 border-l-4 border-emerald-500 bg-emerald-500/10 rounded-r-xl mt-4 text-left">
          <p className="text-emerald-400 font-bold text-lg">🧠 შენი ჰიპოკამპი პიკზე მუშაობს!</p>
          <p className="text-slate-300 text-sm mt-1">ბაზა უბრალოდ გაანადგურე. ამ შედეგით გამოცდაზე მხოლოდ ფორმალობისთვის თუ მიხვალ!</p>
        </div>
      );
    } else {
      return (
        <div className="p-5 border-l-4 border-amber-500 bg-amber-500/10 rounded-r-xl mt-4 text-left">
          <p className="text-amber-400 font-bold text-lg">⚡ მე ვარსებობ შენი წარმატებისთვის.</p>
          <p className="text-slate-300 text-sm mt-1">ახლა მთავარია დოფამინის დონე აიმაღლო, ცოტა დაისვენო და კვლავ თავიდან ვცადოთ.</p>
        </div>
      );
    }
  };

  const selectedFile = uploadedFiles.find(f => f.id === selectedFileId);
  const currentQuestion = activeQuestions[currentIndex];

  return (
    <div className={`min-h-screen font-sans transition-colors duration-200 ${darkMode ? 'bg-slate-950 text-slate-100' : 'bg-slate-50 text-slate-900'}`}>
      
      {/* ჰედერი */}
      <header className={`border-b px-6 py-4 flex items-center justify-between sticky top-0 z-50 backdrop-blur-md ${darkMode ? 'bg-slate-950/80 border-slate-800' : 'bg-white/80 border-slate-200'}`}>
        <div className="flex items-center gap-3">
          <div className="bg-blue-600 text-white p-2 rounded-xl shadow-md">
            <CheckCircle2 className="w-6 h-6" />
          </div>
          <div>
            <h1 className="font-extrabold text-lg tracking-tight uppercase">MEDTEST</h1>
            <p className="text-xs text-slate-400 font-medium">სპეციალიზებული სამედიცინო ტესტირება</p>
          </div>
        </div>
        <div className="flex items-center gap-4">
          <button onClick={() => setDarkMode(!darkMode)} className={`p-2 rounded-xl border transition-all ${darkMode ? 'bg-slate-900 border-slate-800 text-yellow-400 hover:bg-slate-800' : 'bg-slate-100 border-slate-200 text-slate-700 hover:bg-slate-200'}`}>
            {darkMode ? <Sun className="w-5 h-5" /> : <Moon className="w-5 h-5" />}
          </button>
        </div>
      </header>

      <main className="max-w-5xl mx-auto p-4 sm:p-6 lg:p-8">
        
        {/* შუაღამის შეტყობინება */}
        {nightAlert && (
          <div className="mb-6 p-4 bg-purple-600/20 border border-purple-500/50 rounded-2xl flex items-center justify-between animate-pulse">
            <span className="text-purple-300 text-sm font-semibold">🕒 შეხედე საათს! უკვე გვიანია, ძილის დროა ორგანიზმის რეგენერაციისთვის!</span>
            <button onClick={() => setNightAlert(false)} className="text-xs text-purple-300 underline hover:text-purple-100">დახურვა</button>
          </div>
        )}

        {/* 1. SETUP ეკრანი */}
        {appMode === 'setup' && (
          <div className="grid grid-cols-1 lg:grid-cols-3 gap-8">
            <div className="lg:col-span-2 space-y-6">
              
              {/* ფაილის ატვირთვის ზონა */}
              <div className={`p-6 rounded-3xl border-2 border-dashed transition-all relative ${darkMode ? 'border-slate-800 bg-slate-900/40 hover:border-blue-500/50' : 'border-slate-200 bg-white hover:border-blue-500/50'}`}>
                <input type="file" accept=".txt" multiple onChange={handleFileUpload} className="absolute inset-0 opacity-0 cursor-pointer" />
                <div className="text-center py-6">
                  <div className="mx-auto w-12 h-12 bg-blue-600/10 rounded-2xl flex items-center justify-center text-blue-500 mb-4"><Upload className="w-6 h-6" /></div>
                  <h3 className="font-bold text-base">ატვირთეთ სამედიცინო ტესტის ბაზა</h3>
                  <p className="text-xs text-slate-400 mt-1">დაშვებული ფორმატი: .txt (////, ///, //)</p>
                </div>
              </div>

              {/* ატვირთული ფაილების სია */}
              {uploadedFiles.length > 0 && (
                <div className={`p-6 rounded-3xl border ${darkMode ? 'bg-slate-900/50 border-slate-800' : 'bg-white border-slate-200'}`}>
                  <h4 className="font-bold text-sm tracking-wide text-slate-400 mb-4 uppercase">ჩატვირთული ფაილები</h4>
                  <div className="space-y-2">
                    {uploadedFiles.map(file => (
                      <div key={file.id} onClick={() => { setSelectedFileId(file.id); setQuizType('standard'); }} className={`p-4 rounded-2xl border cursor-pointer flex items-center justify-between transition-all ${selectedFileId === file.id && quizType === 'standard' ? 'border-blue-500 bg-blue-500/5' : darkMode ? 'border-slate-800 bg-slate-900 hover:bg-slate-800/50' : 'border-slate-200 bg-slate-50 hover:bg-slate-100'}`}>
                        <div className="flex items-center gap-3">
                          <FileText className="w-5 h-5 text-blue-500" />
                          <span className="font-semibold text-sm truncate max-w-[220px]">{file.name}</span>
                        </div>
                        <span className="text-xs font-bold px-3 py-1 bg-slate-800 text-slate-300 rounded-lg">ნაპოვნია {file.questions.length} კითხვა</span>
                      </div>
                    ))}
                  </div>
                </div>
              )}

              {/* ფილტრების და მოდულების მართვა */}
              {uploadedFiles.length > 0 && (
                <div className={`rounded-3xl border overflow-hidden ${darkMode ? 'bg-slate-900/30 border-slate-800' : 'bg-white border-slate-200'}`}>
                  <div className="flex border-b border-slate-800 bg-slate-900/60">
                    <button onClick={() => setQuizType('standard')} className={`flex-1 py-4 text-sm font-bold transition-all ${quizType === 'standard' ? 'border-b-2 border-blue-500 text-blue-500 bg-blue-500/5' : 'text-slate-400'}`}>სტანდარტული ფილტრაცია</button>
                    <button onClick={() => setQuizType('multi_exam')} className={`flex-1 py-4 text-sm font-bold transition-all ${quizType === 'multi_exam' ? 'border-b-2 border-blue-500 text-blue-500 bg-blue-500/5' : 'text-slate-400'}`}>Multi-File გამოცდის სიმულატორი</button>
                  </div>

                  <div className="p-6">
                    {quizType === 'standard' && selectedFile && (
                      <div className="space-y-6">
                        <div className="grid grid-cols-2 gap-4">
                          <div>
                            <label className="block text-xs font-bold uppercase text-slate-400 mb-2">დიაპაზონის ფილტრი (1 - {selectedFile.questions.length})</label>
                            <div className="flex gap-2">
                              <input type="number" placeholder="დან" value={rangeStart} onChange={e => setRangeStart(e.target.value)} className={`w-full p-3 rounded-xl border text-sm ${darkMode ? 'bg-slate-900 border-slate-800' : 'bg-white border-slate-200'}`} />
                              <input type="number" placeholder="მდე" value={rangeEnd} onChange={e => setRangeEnd(e.target.value)} className={`w-full p-3 rounded-xl border text-sm ${darkMode ? 'bg-slate-900 border-slate-800' : 'bg-white border-slate-200'}`} />
                            </div>
                          </div>
                          <div>
                            <label className="block text-xs font-bold uppercase text-slate-400 mb-2">კითხვების ამოჭრა ბაზიდან</label>
                            <div className="flex gap-2">
                              <input type="number" placeholder="დან" value={cutStart} onChange={e => setCutStart(e.target.value)} className={`w-full p-3 rounded-xl border text-sm ${darkMode ? 'bg-slate-900 border-slate-800' : 'bg-white border-slate-200'}`} />
                              <input type="number" placeholder="მდე" value={cutEnd} onChange={e => setCutEnd(e.target.value)} className={`w-full p-3 rounded-xl border text-sm ${darkMode ? 'bg-slate-900 border-slate-800' : 'bg-white border-slate-200'}`} />
                            </div>
                          </div>
                        </div>

                        <div>
                          <label className="block text-xs font-bold uppercase text-slate-400 mb-2">კონკრეტული კითხვიდან გაგრძელება</label>
                          <input type="number" placeholder="მაგალითად: 100" value={jumpIndex} onChange={e => setJumpIndex(e.target.value)} className={`w-1/2 p-3 rounded-xl border text-sm ${darkMode ? 'bg-slate-900 border-slate-800' : 'bg-white border-slate-200'}`} />
                        </div>

                        <div className="flex items-center justify-between p-4 bg-blue-500/5 rounded-2xl border border-blue-500/20">
                          <div className="flex items-center gap-3">
                            <input type="checkbox" id="autoModeCheck" checked={isAutoMode} onChange={e => setIsAutoMode(e.target.checked)} className="w-4 h-4 text-blue-600 rounded focus:ring-blue-500" />
                            <label htmlFor="autoModeCheck" className="text-sm font-semibold cursor-pointer select-none">ავტომატური რეჟიმი (სწორ პასუხზე მყისიერი გადასვლა)</label>
                          </div>
                        </div>

                        <button onClick={initStandardQuiz} className="w-full bg-blue-600 hover:bg-blue-700 text-white font-bold py-4 rounded-2xl flex items-center justify-center gap-2 transition-all"><Play className="w-5 h-5" /> ტესტირების დაწყება</button>
                      </div>
                    )}

                    {quizType === 'multi_exam' && (
                      <div className="space-y-6">
                        <p className="text-xs text-slate-400">მიუთითეთ თითოეული საგნიდან/ფაილიდან ამოსაღები კითხვების ზუსტი რაოდენობა გამოცდის სიმულატორის ასაწყობად.</p>
                        <div className="space-y-3">
                          {uploadedFiles.map(file => (
                            <div key={file.id} className="flex items-center justify-between p-3 border rounded-xl border-slate-800 bg-slate-900/40">
                              <span className="text-sm font-semibold truncate max-w-[300px]">{file.name}</span>
                              <div className="flex items-center gap-2">
                                <input type="number" min="0" max={file.questions.length} placeholder="რაოდენობა" value={multiConfig[file.id] || ''} onChange={e => setMultiConfig({ ...multiConfig, [file.id]: parseInt(e.target.value) || 0 })} className={`w-28 p-2 rounded-lg text-center text-sm border ${darkMode ? 'bg-slate-900 border-slate-800' : 'bg-white border-slate-200'}`} />
                                <span className="text-xs text-slate-500">/ {file.questions.length}</span>
                              </div>
                            </div>
                          ))}
                        </div>
                        <button onClick={initMultiExamQuiz} className="w-full bg-indigo-600 hover:bg-indigo-700 text-white font-bold py-4 rounded-2xl flex items-center justify-center gap-2 transition-all"><RefreshCw className="w-5 h-5" /> სიმულატორის გენერაცია და დაწყება</button>
                      </div>
                    )}
                  </div>
                </div>
              )}
            </div>

            {/* გვერდითა პანელი (სესიები და მონიშვნები) */}
            <div className="space-y-6">
              <div className={`p-6 rounded-3xl border ${darkMode ? 'bg-slate-900/50 border-slate-800' : 'bg-white border-slate-200'}`}>
                <h4 className="font-bold text-sm tracking-wide text-slate-400 mb-3 uppercase flex items-center gap-2"><Star className="w-4 h-4 text-amber-400" /> მონიშნული კრებულები</h4>
                <p className="text-xs text-slate-400 mb-4">მექანიკური რევიზიისთვის შენახული კითხვების პირადი ბაზა.</p>
                <button onClick={initStarredReview} disabled={starredIds.length === 0} className="w-full bg-slate-800 hover:bg-slate-700 disabled:opacity-50 text-white font-bold py-3 rounded-xl text-sm transition-all flex items-center justify-center gap-2"><ListFilter className="w-4 h-4" /> გადახედვა ({starredIds.length})</button>
              </div>

              <div className={`p-6 rounded-3xl border ${darkMode ? 'bg-slate-900/50 border-slate-800' : 'bg-white border-slate-200'}`}>
                <h4 className="font-bold text-sm tracking-wide text-slate-400 mb-3 uppercase flex items-center gap-2"><AlertCircle className="w-4 h-4 text-red-400" /> შენახული შეცდომები</h4>
                <div className="space-y-3 max-h-[300px] overflow-y-auto pr-1">
                  {savedMistakeSets.length === 0 ? (
                    <p className="text-xs text-slate-500 italic">არცერთი ბაზა არ არის შენახული</p>
                  ) : (
                    savedMistakeSets.map(set => (
                      <div key={set.id} onClick={() => runSavedMistakeSet(set)} className="p-3 rounded-xl border border-slate-800 bg-slate-900 hover:bg-slate-800 cursor-pointer flex items-center justify-between group transition-all">
                        <div className="truncate max-w-[180px]">
                          <p className="text-xs font-bold truncate">{set.name}</p>
                          <p className="text-[10px] text-slate-500">{new Date(set.timestamp).toLocaleDateString()}</p>
                        </div>
                        <span className="text-[11px] font-bold bg-red-950 text-red-400 px-2 py-0.5 rounded border border-red-900/40">{set.questions.length} შეცდომა</span>
                      </div>
                    ))
                  )}
                </div>
              </div>
            </div>
          </div>
        )}

        {/* 2. აქტიური ტესტირების გარემო */}
        {(appMode === 'quiz' || appMode === 'review_mistakes' || appMode === 'review_starred') && currentQuestion && (
          <div className="max-w-3xl mx-auto space-y-6">
            
            <div className="flex items-center justify-between">
              <div className="flex items-center gap-3">
                <span className="text-xs font-bold tracking-widest px-3 py-1.5 rounded-xl bg-blue-600/10 text-blue-400 uppercase border border-blue-500/20">
                  {appMode === 'quiz' ? 'მთავარი ტესტი' : appMode === 'review_mistakes' ? 'შეცდომების ანალიზი' : 'მონიშნული კითხვები'}
                </span>
                <span className="text-xs font-medium text-slate-400">წყარო: {currentQuestion.sourceFile}</span>
              </div>
              <div className="flex items-center gap-2">
                {appMode === 'quiz' && (
                  <button onClick={triggerInstantMistakeReview} disabled={sessionMistakes.length === 0} className="px-3 py-1.5 bg-red-600/10 hover:bg-red-600/20 text-red-400 rounded-xl border border-red-500/20 text-xs font-bold transition-all disabled:opacity-40">შეცდომების გავლა ახლავე ({sessionMistakes.length})</button>
                )}
                {appMode === 'review_mistakes' && (
                  <button onClick={terminateMistakeReview} className="px-3 py-1.5 bg-slate-800 hover:bg-slate-700 text-white rounded-xl text-xs font-bold transition-all">ტესტზე დაბრუნება</button>
                )}
                <button onClick={() => setAppMode('setup')} className="px-3 py-1.5 bg-slate-800 hover:bg-slate-700 text-white rounded-xl text-xs font-bold transition-all">შეწყვეტა</button>
              </div>
            </div>

            {/* პროგრეს ბარი */}
            <div className="space-y-2">
              <div className="flex justify-between text-xs font-bold text-slate-400">
                <span>კითხვა: {currentIndex + 1} / {activeQuestions.length}</span>
                {appMode === 'quiz' && <span>სწორი პასუხები: {quizStats.correct}</span>}
              </div>
              <div className={`h-2 rounded-full overflow-hidden ${darkMode ? 'bg-slate-900' : 'bg-slate-200'}`}>
                <div className="h-full bg-gradient-to-r from-blue-500 to-indigo-500 transition-all duration-300" style={{ width: `${((currentIndex + 1) / activeQuestions.length) * 100}%` }}></div>
              </div>
            </div>

            {/* კითხვის ინტერფეისი */}
            <div className={`p-8 rounded-3xl border shadow-xl relative ${darkMode ? 'bg-slate-900/60 border-slate-800' : 'bg-white border-slate-200'}`}>
              <button onClick={() => toggleStar(currentQuestion.id)} className="absolute top-6 right-6 p-2 rounded-xl transition-all hover:scale-105">
                <Star className={`w-6 h-6 transition-colors ${starredIds.includes(currentQuestion.id) ? 'fill-amber-400 text-amber-400' : 'text-slate-500'}`} />
              </button>

              <div className="pr-8">
                <h2 className="text-xl font-bold leading-relaxed tracking-wide">{currentQuestion.text}</h2>
              </div>

              {/* პასუხების გრიდი */}
              <div className="mt-8 space-y-3">
                {currentQuestion.allAnswers.map((answer, idx) => {
                  let btnStyle = darkMode ? 'bg-slate-900/80 border-slate-800 hover:bg-slate-800' : 'bg-slate-50 border-slate-200 hover:bg-slate-100';
                  
                  if (isAnswered) {
                    if (answer === currentQuestion.correctAnswer) {
                      btnStyle = 'border-emerald-500 bg-emerald-500/10 text-emerald-400 font-bold';
                    } else if (selectedAnswer === answer) {
                      btnStyle = 'border-red-500 bg-red-500/10 text-red-400';
                    } else {
                      btnStyle = 'opacity-40 border-slate-800';
                    }
                  }

                  return (
                    <button key={idx} onClick={() => handleAnswerSelection(answer)} disabled={isAnswered} className={`w-full p-5 rounded-2xl border text-left text-base transition-all duration-150 flex items-start gap-4 group ${btnStyle}`}>
                      <span className={`w-6 h-6 rounded-lg border flex items-center justify-center text-xs font-bold shrink-0 mt-0.5 ${isAnswered && answer === currentQuestion.correctAnswer ? 'bg-emerald-500 border-emerald-500 text-white' : 'border-slate-700 bg-slate-950 text-slate-400'}`}>{idx + 1}</span>
                      <span className="flex-1 leading-normal font-medium">{answer}</span>
                    </button>
                  );
                })}
              </div>

              {isAnswered && (!isAutoMode || selectedAnswer !== currentQuestion.correctAnswer || appMode !== 'quiz') && (
                <div className="mt-6 pt-6 border-t border-slate-800 flex justify-end">
                  <button onClick={handleNextQuestion} className="px-6 py-3 bg-blue-600 hover:bg-blue-700 text-white font-bold rounded-xl text-sm flex items-center gap-2 transition-all">შემდეგი კითხვა <ChevronRight className="w-4 h-4" /></button>
                </div>
              )}
            </div>
          </div>
        )}

        {/* 3. შედეგების შეჯამების ეკრანი */}
        {appMode === 'results' && (
          <div className="max-w-2xl mx-auto space-y-6">
            <div className={`p-8 rounded-3xl border text-center shadow-2xl ${darkMode ? 'bg-slate-900/60 border-slate-800' : 'bg-white border-slate-200'}`}>
              <h2 className="text-2xl font-extrabold tracking-tight">ტესტირების შედეგები</h2>
              <p className="text-sm text-slate-400 mt-1">ბაზის ანალიტიკური შეჯამება</p>

              {/* სტატისტიკური მატრიცა */}
              <div className="grid grid-cols-2 sm:grid-cols-4 gap-4 my-8">
                <div className="p-4 bg-slate-950 rounded-2xl border border-slate-800">
                  <p className="text-2xl font-black text-blue-500">{quizStats.initialTotal}</p>
                  <p className="text-[10px] uppercase font-bold text-slate-400 mt-1">მთლიანი კითხვა</p>
                </div>
                <div className="p-4 bg-slate-950 rounded-2xl border border-slate-800">
                  <p className="text-2xl font-black text-emerald-500">{quizStats.correct}</p>
                  <p className="text-[10px] uppercase font-bold text-slate-400 mt-1">სწორი პასუხი</p>
                </div>
                <div className="p-4 bg-slate-950 rounded-2xl border border-slate-800">
                  <p className="text-2xl font-black text-red-500">{sessionMistakes.length}</p>
                  <p className="text-[10px] uppercase font-bold text-slate-400 mt-1">შეცდომები</p>
                </div>
                <div className="p-4 bg-slate-950 rounded-2xl border border-slate-800">
                  <p className="text-2xl font-black text-indigo-500">{quizStats.initialTotal > 0 ? Math.round((quizStats.correct / quizStats.initialTotal) * 100) : 0}%</p>
                  <p className="text-[10px] uppercase font-bold text-slate-400 mt-1">სიზუსტე</p>
                </div>
              </div>

              {/* ინექცირებული მოტივაციური შეტყობინება პირობის მიხედვით */}
              {renderMotivationalFeedback()}

              {/* მენეჯმენტის ღილაკები */}
              <div className="mt-8 grid grid-cols-1 sm:grid-cols-2 gap-3">
                <button onClick={saveMistakesToState} disabled={sessionMistakes.length === 0} className="w-full bg-slate-800 hover:bg-slate-700 disabled:opacity-40 text-white font-bold py-3.5 rounded-xl text-sm transition-all flex items-center justify-center gap-2"><Save className="w-4 h-4" /> შეცდომების შენახვა საიტზე</button>
                <button onClick={exportMistakesAsJSON} disabled={sessionMistakes.length === 0} className="w-full bg-slate-800 hover:bg-slate-700 disabled:opacity-40 text-white font-bold py-3.5 rounded-xl text-sm transition-all flex items-center justify-center gap-2"><Download className="w-4 h-4" /> შეცდომების ჩამოტვირთვა (.json)</button>
              </div>

              <div className="mt-3 pt-4 border-t border-slate-800/60">
                <button onClick={() => setAppMode('setup')} className="w-full bg-blue-600 hover:bg-blue-700 text-white font-bold py-4 rounded-xl text-sm transition-all">ახალი სესიის დაწყება</button>
              </div>
            </div>
          </div>
        )}

      </main>
    </div>
  );
};

```
