[index.html](https://github.com/user-attachments/files/25722337/index.html)
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>D/Asharf elsaqa - Advanced Algebra</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
       
        body {
            background-color: #f5f7fa;
            color: #333;
            line-height: 1.6;
            padding: 20px;
            min-height: 100vh;
        }
       
        .container {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: 1fr 300px;
            gap: 20px;
        }
       
        /* Header styling */
        .header {
            grid-column: 1 / -1;
            background: linear-gradient(135deg, #8B0000, #B22222, #DC143C);
            color: white;
            padding: 25px;
            border-radius: 10px;
            box-shadow: 0 4px 15px rgba(139, 0, 0, 0.2);
            margin-bottom: 20px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
       
        .header::before {
            content: "";
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent 30%, rgba(255,255,255,0.1) 50%, transparent 70%);
            transform: rotate(30deg);
            animation: shine 3s infinite linear;
        }
       
        @keyframes shine {
            0% { transform: rotate(30deg) translateX(-100%); }
            100% { transform: rotate(30deg) translateX(100%); }
        }
       
        .main-title {
            font-size: 2.8rem;
            font-weight: 900;
            letter-spacing: 1px;
            margin-bottom: 5px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
            position: relative;
            z-index: 1;
        }
       
        .subtitle {
            font-size: 1.4rem;
            font-weight: 300;
            margin-bottom: 15px;
            opacity: 0.9;
            position: relative;
            z-index: 1;
        }
       
        .instructors {
            font-size: 1rem;
            background: rgba(0, 0, 0, 0.2);
            padding: 10px 20px;
            border-radius: 20px;
            display: inline-block;
            position: relative;
            z-index: 1;
            margin-top: 10px;
        }
       
        .timer-container {
            background: rgba(0, 0, 0, 0.3);
            padding: 12px 25px;
            border-radius: 50px;
            display: inline-flex;
            align-items: center;
            gap: 12px;
            font-weight: bold;
            font-size: 1.5rem;
            margin-top: 15px;
            position: relative;
            z-index: 1;
            border: 2px solid rgba(255, 255, 255, 0.2);
        }
       
        .timer-container.warning {
            background: rgba(255, 165, 0, 0.3);
            border-color: rgba(255, 165, 0, 0.5);
            color: #FFD700;
        }
       
        .timer-container.danger {
            background: rgba(255, 0, 0, 0.3);
            border-color: rgba(255, 0, 0, 0.5);
            color: #FF6666;
            animation: pulse 1s infinite;
        }
       
        @keyframes pulse {
            0% { opacity: 1; }
            50% { opacity: 0.7; }
            100% { opacity: 1; }
        }
       
        /* Exam section styling */
        .exam-section {
            background: white;
            border-radius: 10px;
            padding: 30px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
            margin-bottom: 20px;
            border-top: 5px solid #8B0000;
        }
       
        .section-title {
            color: #8B0000;
            border-bottom: 2px solid #eaeaea;
            padding-bottom: 10px;
            margin-bottom: 25px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
       
        .question {
            margin-bottom: 30px;
            padding-bottom: 20px;
            border-bottom: 1px solid #eaeaea;
        }
       
        .question:last-child {
            border-bottom: none;
        }
       
        .question-number {
            display: inline-block;
            background: #8B0000;
            color: white;
            width: 36px;
            height: 36px;
            border-radius: 50%;
            text-align: center;
            line-height: 36px;
            margin-right: 15px;
            font-weight: bold;
            font-size: 1.1rem;
            box-shadow: 0 2px 4px rgba(139, 0, 0, 0.3);
        }
       
        .question-text {
            font-size: 1.1rem;
            margin: 15px 0;
            line-height: 1.8;
        }
       
        .math-expr {
            font-family: 'Cambria Math', 'Times New Roman', serif;
            font-size: 1.3rem;
            padding: 15px;
            background-color: #fff5f5;
            border-radius: 8px;
            margin: 15px 0;
            border-left: 4px solid #8B0000;
            text-align: center;
            box-shadow: 0 2px 4px rgba(0,0,0,0.05);
        }
       
        .options {
            margin: 25px 0;
        }
       
        .option {
            margin: 12px 0;
            padding: 14px 18px;
            border: 2px solid #ddd;
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.3s;
            font-size: 1.05rem;
        }
       
        .option:hover {
            background: #f9f9f9;
            border-color: #8B0000;
            transform: translateX(5px);
        }
       
        .option.selected {
            background: #ffeaea;
            border-color: #8B0000;
            font-weight: bold;
            box-shadow: 0 2px 8px rgba(139, 0, 0, 0.1);
        }
       
        .option.correct {
            background: #e7f7e7;
            border-color: #27ae60;
            box-shadow: 0 2px 8px rgba(39, 174, 96, 0.1);
        }
       
        .option.incorrect {
            background: #fdeaea;
            border-color: #e74c3c;
            box-shadow: 0 2px 8px rgba(231, 76, 60, 0.1);
        }
       
        /* Sidebar styling */
        .sidebar {
            background: white;
            border-radius: 10px;
            padding: 20px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
            height: fit-content;
            position: sticky;
            top: 20px;
            border-top: 5px solid #8B0000;
        }
       
        .question-nav {
            display: grid;
            grid-template-columns: repeat(5, 1fr);
            gap: 10px;
            margin: 20px 0;
        }
       
        .nav-btn {
            width: 42px;
            height: 42px;
            border-radius: 8px;
            border: 2px solid #eaeaea;
            background: white;
            cursor: pointer;
            font-weight: bold;
            transition: all 0.3s;
            font-size: 1rem;
        }
       
        .nav-btn:hover {
            background: #ffeaea;
            border-color: #8B0000;
            transform: scale(1.05);
        }
       
        .nav-btn.active {
            background: #8B0000;
            color: white;
            border-color: #8B0000;
            transform: scale(1.1);
        }
       
        .nav-btn.answered {
            background: #ffeaea;
            border-color: #8B0000;
        }
       
        .exam-controls {
            margin-top: 25px;
            display: flex;
            flex-direction: column;
            gap: 15px;
        }
       
        .control-btn {
            padding: 14px;
            border-radius: 8px;
            border: none;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s;
            font-size: 1.1rem;
        }
       
        .submit-btn {
            background: linear-gradient(to right, #27ae60, #219653);
            color: white;
            box-shadow: 0 4px 8px rgba(39, 174, 96, 0.3);
        }
       
        .submit-btn:hover {
            background: linear-gradient(to right, #219653, #1e8449);
            transform: translateY(-2px);
            box-shadow: 0 6px 12px rgba(39, 174, 96, 0.4);
        }
       
        .download-btn {
            background: linear-gradient(to right, #3498db, #2980b9);
            color: white;
            box-shadow: 0 4px 8px rgba(52, 152, 219, 0.3);
        }
       
        .download-btn:hover {
            background: linear-gradient(to right, #2980b9, #2573a7);
            transform: translateY(-2px);
            box-shadow: 0 6px 12px rgba(52, 152, 219, 0.4);
        }
       
        .results-panel {
            background: #f8f9fa;
            border-radius: 8px;
            padding: 20px;
            margin-top: 20px;
            border-left: 4px solid #8B0000;
        }
       
        .score-display {
            font-size: 1.3rem;
            font-weight: bold;
            color: #8B0000;
            margin: 10px 0;
        }
       
        .progress-bar {
            height: 12px;
            background: #eaeaea;
            border-radius: 6px;
            margin: 15px 0;
            overflow: hidden;
        }
       
        .progress {
            height: 100%;
            background: linear-gradient(to right, #8B0000, #B22222);
            width: 0%;
            transition: width 0.5s;
        }
       
        /* Footer styling */
        .footer {
            grid-column: 1 / -1;
            text-align: center;
            margin-top: 30px;
            color: #777;
            font-size: 0.9rem;
            padding-top: 20px;
            border-top: 1px solid #ddd;
        }
       
        /* Superscript and subscript styling */
        sup, .sup {
            vertical-align: super;
            font-size: 0.8em;
            line-height: 0;
        }
       
        sub, .sub {
            vertical-align: sub;
            font-size: 0.8em;
            line-height: 0;
        }
       
        .math-symbol {
            font-family: 'Cambria Math', 'Times New Roman', serif;
        }
       
        .sqrt {
            text-decoration: overline;
            text-decoration-thickness: 1px;
            padding: 0 2px;
        }
       
        .root-index {
            font-size: 0.7em;
            position: relative;
            top: -0.2em;
        }
       
        .fraction {
            display: inline-block;
            text-align: center;
            vertical-align: middle;
        }
       
        .fraction span {
            display: block;
        }
       
        .fraction .numerator {
            border-bottom: 1px solid black;
            padding: 0 5px;
        }
       
        .fraction .denominator {
            padding: 0 5px;
        }
       
        .test-instructions {
            background-color: #fff5f5;
            padding: 15px;
            border-radius: 8px;
            margin-bottom: 20px;
            border-left: 4px solid #8B0000;
            font-size: 0.95rem;
        }
       
        .difficulty-badge {
            display: inline-block;
            background: #8B0000;
            color: white;
            padding: 3px 10px;
            border-radius: 12px;
            font-size: 0.75rem;
            margin-left: 10px;
            vertical-align: middle;
        }
       
        @media (max-width: 992px) {
            .container {
                grid-template-columns: 1fr;
            }
           
            .sidebar {
                position: static;
            }
           
            .header {
                padding: 20px 15px;
            }
           
            .main-title {
                font-size: 2.2rem;
            }
           
            .subtitle {
                font-size: 1.2rem;
            }
        }
       
        .empire-logo {
            font-size: 1.2rem;
            color: #FFD700;
            margin-right: 10px;
        }
       
        .instructor-name {
            font-weight: bold;
            color: #FFD700;
        }
       
        .math-format {
            font-family: 'Cambria Math', 'Times New Roman', serif;
            font-size: 1.15rem;
        }
       
        .power {
            font-size: 0.75em;
            vertical-align: super;
            line-height: 0;
        }
       
        .subscript {
            font-size: 0.75em;
            vertical-align: sub;
            line-height: 0;
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Header with title and timer -->
        <div class="header">
            <div class="main-title">
                <i class="fas fa-crown empire-logo"></i> D/Asharf elsaqa
            </div>
            <div class="subtitle">Advanced Algebra Challenge</div>
            <div class="instructors">
                <strong>Instructor:</strong>
                <span class="instructor-name">D/Asharf elsaqa</span>
            </div>
            <div class="timer-container" id="timer">
                <i class="fas fa-clock"></i>
                <span id="time-display">60:00</span>
            </div>
        </div>
       
        <!-- Main exam content -->
        <div class="exam-content">
            <div class="exam-section">
                <div class="section-title">
                    <h2>Advanced Algebra Challenge</h2>
                    <span id="answered-count">0/20 answered</span>
                </div>
                <div class="test-instructions">
                    <i class="fas fa-info-circle"></i> <strong>Instructions:</strong> Solve each problem without a calculator. Show your mastery of exponents, roots, and factorization techniques.
                </div>
               
                <!-- Questions will be dynamically inserted here -->
                <div id="questions-container"></div>
            </div>
        </div>
       
        <!-- Sidebar with navigation and controls -->
        <div class="sidebar">
            <h3><i class="fas fa-compass"></i> Question Navigation</h3>
            <div class="question-nav" id="question-nav">
                <!-- Navigation buttons will be dynamically inserted here -->
            </div>
           
            <div class="exam-controls">
                <button class="control-btn submit-btn" id="submit-exam">
                    <i class="fas fa-flag-checkered"></i> Complete Challenge
                </button>
                <button class="control-btn download-btn" id="download-results" style="display: none;">
                    <i class="fas fa-trophy"></i> Download Results
                </button>
            </div>
           
            <div class="results-panel">
                <h4><i class="fas fa-chart-line"></i> Challenge Progress</h4>
                <div class="start-time" id="start-time-display">
                    <i class="fas fa-hourglass-start"></i> Started: <span id="start-time-text">Loading...</span>
                </div>
                <div class="progress-bar">
                    <div class="progress" id="exam-progress"></div>
                </div>
                <div class="score-display">
                    <i class="fas fa-crown"></i> Score: <span id="current-score">0</span>/20
                </div>
                <p id="score-message">Complete the challenge to see your score</p>
            </div>
        </div>
       
        <!-- Footer -->
        <div class="footer">
            <p>© 2023 D/Asharf elsaqa | Conquer Mathematics</p>
            <p>Advanced Algebra Challenge prepared by D/Asharf elsaqa</p>
        </div>
    </div>

    <script>
        // Exam data - 20 challenging algebra problems from Exponent.pdf pages 2-5
        const examQuestions = [
            {
                id: 1,
                question: `What is the value of 3<sup>-1</sup>? <span class="difficulty-badge">Easy</span>`,
                options: ["1/3", "-3", "3", "-1/3"],
                correct: 0,
                explanation: "3<sup>-1</sup> = 1/3."
            },
            {
                id: 2,
                question: `Simplify (16/x<sup>2</sup>)<sup>-3</sup>. <span class="difficulty-badge">Medium</span>`,
                options: ["x<sup>6</sup>/4096", "4096/x<sup>6</sup>", "x<sup>6</sup>/16", "16/x<sup>6</sup>"],
                correct: 0,
                explanation: "(16/x<sup>2</sup>)<sup>-3</sup> = (x<sup>2</sup>/16)<sup>3</sup> = x<sup>6</sup>/4096."
            },
            {
                id: 3,
                question: `What is the value of 5<sup>0</sup>? <span class="difficulty-badge">Easy</span>`,
                options: ["0", "1", "5", "undefined"],
                correct: 1,
                explanation: "Any nonzero number raised to the power 0 equals 1."
            },
            {
                id: 4,
                question: `What is (-2)<sup>2</sup>? <span class="difficulty-badge">Easy</span>`,
                options: ["4", "-4", "2", "-2"],
                correct: 0,
                explanation: "(-2)<sup>2</sup> = (-2) × (-2) = 4."
            },
            {
                id: 5,
                question: `If x = -3, what is x<sup>2</sup>? <span class="difficulty-badge">Easy</span>`,
                options: ["9", "-9", "6", "-6"],
                correct: 0,
                explanation: "(-3)<sup>2</sup> = 9."
            },
            {
                id: 6,
                question: `If x = -3, what is -x<sup>2</sup>? <span class="difficulty-badge">Easy</span>`,
                options: ["-9", "9", "6", "-6"],
                correct: 0,
                explanation: "-x<sup>2</sup> = -((-3)<sup>2</sup>) = -9."
            },
            {
                id: 7,
                question: `If 2<sup>x+6</sup> = 2<sup>5</sup>, what is 2<sup>x</sup>? <span class="difficulty-badge">Medium</span>`,
                options: ["2<sup>-1</sup>", "2", "1/2", "4"],
                correct: 2,
                explanation: "x+6 = 5 ⇒ x = -1, so 2<sup>x</sup> = 2<sup>-1</sup> = 1/2."
            },
            {
                id: 8,
                question: `If 3<sup>a+1</sup> = 3<sup>-a+7</sup>, what is a+2? <span class="difficulty-badge">Medium</span>`,
                options: ["5", "4", "6", "3"],
                correct: 0,
                explanation: "a+1 = -a+7 ⇒ 2a = 6 ⇒ a = 3, so a+2 = 5."
            },
            {
                id: 9,
                question: `If 2<sup>y</sup> × (9<sup>x-3</sup>)<sup>1/2</sup> = 36, what is xy? <span class="difficulty-badge">Hard</span>`,
                options: ["2", "15", "10", "20"],
                correct: 2,
                explanation: "2<sup>y</sup> × 3<sup>x-3</sup> = 2<sup>2</sup> × 3<sup>2</sup> ⇒ y=2, x-3=2 ⇒ x=5, xy=10."
            },
            {
                id: 10,
                question: `If 4<sup>2n+3</sup> = 8<sup>n+5</sup>, what is 2n+1? <span class="difficulty-badge">Hard</span>`,
                options: ["19", "9", "10", "20"],
                correct: 0,
                explanation: "2<sup>2(2n+3)</sup> = 2<sup>3(n+5)</sup> ⇒ 4n+6 = 3n+15 ⇒ n=9, so 2n+1=19."
            },
            {
                id: 11,
                question: `If (16x)<sup>a</sup> = 2x<sup>a</sup>, what is a? <span class="difficulty-badge">Hard</span>`,
                options: ["1/4", "1/2", "2", "4"],
                correct: 0,
                explanation: "16<sup>a</sup> x<sup>a</sup> = 2 x<sup>a</sup> ⇒ 16<sup>a</sup> = 2 ⇒ (2<sup>4</sup>)<sup>a</sup> = 2<sup>1</sup> ⇒ 4a=1 ⇒ a=1/4."
            },
            {
                id: 12,
                question: `If 2(16<sup>x</sup>) = 64, what is 2x? <span class="difficulty-badge">Medium</span>`,
                options: ["2.5", "2", "3", "4"],
                correct: 0,
                explanation: "2 × 16<sup>x</sup> = 64 ⇒ 16<sup>x</sup> = 32 ⇒ 2<sup>4x</sup> = 2<sup>5</sup> ⇒ 4x=5 ⇒ x=5/4, so 2x=5/2=2.5."
            },
            {
                id: 13,
                question: `If (3<sup>9</sup>)<sup>3<sup>12</sup></sup> = 3<sup>3<sup>x</sup></sup>, what is x? <span class="difficulty-badge">Challenging</span>`,
                options: ["14", "12", "9", "3"],
                correct: 0,
                explanation: "(3<sup>9</sup>)<sup>3<sup>12</sup></sup> = 3<sup>9·3<sup>12</sup></sup> = 3<sup>3<sup>2</sup>·3<sup>12</sup></sup> = 3<sup>3<sup>14</sup></sup> ⇒ 3<sup>x</sup> = 3<sup>14</sup> ⇒ x=14."
            },
            {
                id: 14,
                question: `If 2a - b = 4, what is (4<sup>a</sup>)/(2<sup>b</sup>)? <span class="difficulty-badge">Medium</span>`,
                options: ["16", "8", "4", "2"],
                correct: 0,
                explanation: "4<sup>a</sup>/2<sup>b</sup> = 2<sup>2a</sup>/2<sup>b</sup> = 2<sup>2a-b</sup> = 2<sup>4</sup> = 16."
            },
            {
                id: 15,
                question: `If 2a - b = 3, what is (9<sup>a</sup>)/(3<sup>b</sup>)? <span class="difficulty-badge">Medium</span>`,
                options: ["27", "9", "3", "1"],
                correct: 0,
                explanation: "9<sup>a</sup>/3<sup>b</sup> = 3<sup>2a</sup>/3<sup>b</sup> = 3<sup>2a-b</sup> = 3<sup>3</sup> = 27."
            },
            {
                id: 16,
                question: `If 2x = 3 + y, what is (9<sup>x</sup>)/(3<sup>y</sup>)? <span class="difficulty-badge">Medium</span>`,
                options: ["27", "9", "3", "1"],
                correct: 0,
                explanation: "9<sup>x</sup>/3<sup>y</sup> = 3<sup>2x</sup>/3<sup>y</sup> = 3<sup>2x-y</sup> = 3<sup>(3+y)-y</sup> = 3<sup>3</sup> = 27."
            },
            {
                id: 17,
                question: `If 4x - 2y = 20, what is (16<sup>x</sup>)/(4<sup>y</sup>)? <span class="difficulty-badge">Medium</span>`,
                options: ["2<sup>20</sup>", "2<sup>10</sup>", "16<sup>5</sup>", "4<sup>5</sup>"],
                correct: 0,
                explanation: "16<sup>x</sup>/4<sup>y</sup> = 2<sup>4x</sup>/2<sup>2y</sup> = 2<sup>4x-2y</sup> = 2<sup>20</sup>."
            },
            {
                id: 18,
                question: `If 3x - y = 1 and (8<sup>2x</sup>/4<sup>y</sup>) + t = 7, what is t? <span class="difficulty-badge">Hard</span>`,
                options: ["3", "4", "5", "6"],
                correct: 0,
                explanation: "8<sup>2x</sup>/4<sup>y</sup> = 2<sup>6x</sup>/2<sup>2y</sup> = 2<sup>2(3x-y)</sup> = 2<sup>2</sup> = 4, so 4 + t = 7 ⇒ t = 3."
            },
            {
                id: 19,
                question: `If 12x - 2y = 1, what is (216<sup>2x</sup>)/(6<sup>y</sup>)? <span class="difficulty-badge">Hard</span>`,
                options: ["√6", "6", "1/6", "36"],
                correct: 0,
                explanation: "216 = 6<sup>3</sup>, so 216<sup>2x</sup> = 6<sup>6x</sup>, then divided by 6<sup>y</sup> = 6<sup>6x-y</sup> = 6<sup>(12x-2y)/2</sup> = 6<sup>1/2</sup> = √6."
            },
            {
                id: 20,
                question: `If x = -5, what is x<sup>3</sup>? <span class="difficulty-badge">Easy</span>`,
                options: ["-125", "125", "-25", "25"],
                correct: 0,
                explanation: "(-5)<sup>3</sup> = -125."
            }
        ];

        // State variables
        let userAnswers = new Array(examQuestions.length).fill(null);
        let examStarted = false;
        let timeRemaining = 60 * 60; // 60 minutes in seconds
        let timerInterval;
        let currentQuestionIndex = 0;
        let examSubmitted = false;
        let examStartTime = null;

        // DOM elements
        const timerDisplay = document.getElementById('time-display');
        const timerContainer = document.getElementById('timer');
        const questionsContainer = document.getElementById('questions-container');
        const questionNav = document.getElementById('question-nav');
        const answeredCount = document.getElementById('answered-count');
        const examProgress = document.getElementById('exam-progress');
        const currentScore = document.getElementById('current-score');
        const scoreMessage = document.getElementById('score-message');
        const submitExamBtn = document.getElementById('submit-exam');
        const downloadResultsBtn = document.getElementById('download-results');
        const startTimeText = document.getElementById('start-time-text');

        // Initialize the exam
        function initExam() {
            // Record start time if not already recorded
            recordStartTime();
           
            renderQuestions();
            renderNavigation();
            updateProgress();
            startTimer();
           
            // Set up event listeners
            submitExamBtn.addEventListener('click', submitExam);
            downloadResultsBtn.addEventListener('click', downloadResults);
        }

        // Record the start time in localStorage
        function recordStartTime() {
            const storageKey = 'math_empire_challenge_start_time';
           
            // Check if we already have a start time
            const storedTime = localStorage.getItem(storageKey);
           
            if (storedTime) {
                examStartTime = new Date(storedTime);
            } else {
                // First time opening - record current time
                examStartTime = new Date();
                localStorage.setItem(storageKey, examStartTime.toISOString());
            }
           
            // Display the start time
            startTimeText.textContent = examStartTime.toLocaleTimeString([], {hour: '2-digit', minute:'2-digit'});
        }

        // Render all questions
        function renderQuestions() {
            questionsContainer.innerHTML = '';
           
            examQuestions.forEach((q, index) => {
                const questionEl = document.createElement('div');
                questionEl.className = 'question';
                questionEl.id = `question-${index}`;
               
                let optionsHtml = '';
                q.options.forEach((option, optIndex) => {
                    const isSelected = userAnswers[index] === optIndex;
                    const optionClass = `option ${isSelected ? 'selected' : ''}`;
                   
                    optionsHtml += `
                        <div class="${optionClass}" data-question="${index}" data-option="${optIndex}">
                            ${String.fromCharCode(65 + optIndex)}. <span class="math-format">${option}</span>
                        </div>
                    `;
                });
               
                questionEl.innerHTML = `
                    <div class="question-header">
                        <span class="question-number">${q.id}</span>
                        <strong>Challenge ${q.id}</strong>
                    </div>
                    <div class="question-text math-format">
                        ${q.question}
                    </div>
                    <div class="options">${optionsHtml}</div>
                `;
               
                questionsContainer.appendChild(questionEl);
            });
           
            // Add event listeners to options
            document.querySelectorAll('.option').forEach(option => {
                option.addEventListener('click', handleOptionClick);
            });
           
            // Show first question
            showQuestion(currentQuestionIndex);
        }

        // Render navigation buttons
        function renderNavigation() {
            questionNav.innerHTML = '';
           
            examQuestions.forEach((q, index) => {
                const button = document.createElement('button');
                button.className = 'nav-btn';
                if (index === currentQuestionIndex) button.classList.add('active');
                if (userAnswers[index] !== null) button.classList.add('answered');
                button.textContent = q.id;
                button.addEventListener('click', () => showQuestion(index));
                questionNav.appendChild(button);
            });
        }

        // Show a specific question
        function showQuestion(index) {
            // Hide all questions
            document.querySelectorAll('.question').forEach(q => {
                q.style.display = 'none';
            });
           
            // Show selected question
            document.getElementById(`question-${index}`).style.display = 'block';
           
            // Update navigation buttons
            document.querySelectorAll('.nav-btn').forEach((btn, i) => {
                btn.classList.remove('active');
                if (i === index) btn.classList.add('active');
            });
           
            currentQuestionIndex = index;
        }

        // Handle option selection
        function handleOptionClick(e) {
            if (examSubmitted) return;
           
            const questionIndex = parseInt(e.target.dataset.question);
            const optionIndex = parseInt(e.target.dataset.option);
           
            // Update user answer
            userAnswers[questionIndex] = optionIndex;
           
            // Update UI for this question
            const questionEl = document.getElementById(`question-${questionIndex}`);
            questionEl.querySelectorAll('.option').forEach((opt, idx) => {
                opt.classList.remove('selected');
                if (idx === optionIndex) {
                    opt.classList.add('selected');
                }
            });
           
            // Update navigation button
            document.querySelectorAll('.nav-btn')[questionIndex].classList.add('answered');
           
            updateProgress();
        }

        // Update progress bar and answered count
        function updateProgress() {
            const answered = userAnswers.filter(answer => answer !== null).length;
            const total = examQuestions.length;
            const progressPercent = (answered / total) * 100;
           
            answeredCount.textContent = `${answered}/${total} answered`;
            examProgress.style.width = `${progressPercent}%`;
           
            // Update score if exam is submitted
            if (examSubmitted) {
                let score = 0;
                userAnswers.forEach((answer, index) => {
                    if (answer === examQuestions[index].correct) {
                        score++;
                    }
                });
                currentScore.textContent = score;
               
                // Show score message with empire theme
                const percentage = (score / total * 100).toFixed(1);
                let message = `You scored ${score}/${total} (${percentage}%). `;
               
                if (percentage >= 90) {
                    message += "👑 <strong>EMPEROR STATUS:</strong> You rule the Math Empire! Your algebra mastery is absolute.";
                } else if (percentage >= 80) {
                    message += "⚔️ <strong>ROYAL KNIGHT:</strong> Excellent command of algebra! You're a valued defender of the Math Empire.";
                } else if (percentage >= 70) {
                    message += "🛡️ <strong>NOBLE LORD:</strong> Strong performance! Continue honing your skills to ascend the ranks.";
                } else if (percentage >= 60) {
                    message += "🏰 <strong>LOYAL VASSAL:</strong> Good effort! Study the explanations to strengthen your mathematical kingdom.";
                } else {
                    message += "📚 <strong>APPRENTICE MAGE:</strong> The path to mastery begins here. Review each solution carefully to build your empire.";
                }
               
                scoreMessage.innerHTML = message;
               
                // Show download button
                downloadResultsBtn.style.display = 'block';
            }
        }

        // Start the timer
        function startTimer() {
            if (examStarted) return;
           
            examStarted = true;
            updateTimerDisplay();
           
            timerInterval = setInterval(() => {
                timeRemaining--;
                updateTimerDisplay();
               
                if (timeRemaining <= 0) {
                    clearInterval(timerInterval);
                    submitExam();
                }
            }, 1000);
        }

        // Update timer display
        function updateTimerDisplay() {
            const minutes = Math.floor(timeRemaining / 60);
            const seconds = timeRemaining % 60;
           
            timerDisplay.textContent = `${minutes.toString().padStart(2, '0')}:${seconds.toString().padStart(2, '0')}`;
           
            // Update timer color based on remaining time
            timerContainer.classList.remove('warning', 'danger');
            if (timeRemaining < 20 * 60) { // Less than 20 minutes
                timerContainer.classList.add('warning');
            }
            if (timeRemaining < 10 * 60) { // Less than 10 minutes
                timerContainer.classList.add('danger');
            }
        }

        // Submit the exam
        function submitExam() {
            if (examSubmitted) return;
           
            clearInterval(timerInterval);
            examSubmitted = true;
           
            // Show correct/incorrect answers
            examQuestions.forEach((q, index) => {
                const questionEl = document.getElementById(`question-${index}`);
                const options = questionEl.querySelectorAll('.option');
               
                options.forEach((opt, optIndex) => {
                    if (optIndex === q.correct) {
                        opt.classList.add('correct');
                    } else if (userAnswers[index] === optIndex && userAnswers[index] !== q.correct) {
                        opt.classList.add('incorrect');
                    }
                });
               
                // Add explanation
                const explanationEl = document.createElement('div');
                explanationEl.className = 'explanation';
                explanationEl.style.marginTop = '15px';
                explanationEl.style.padding = '12px';
                explanationEl.style.backgroundColor = '#f8f9fa';
                explanationEl.style.borderRadius = '8px';
                explanationEl.style.fontSize = '0.95rem';
                explanationEl.innerHTML = `<strong><i class="fas fa-lightbulb"></i> Solution:</strong> <span class="math-format">${q.explanation}</span>`;
                questionEl.appendChild(explanationEl);
            });
           
            updateProgress();
            submitExamBtn.disabled = true;
            submitExamBtn.innerHTML = '<i class="fas fa-crown"></i> Challenge Conquered';
            submitExamBtn.style.background = 'linear-gradient(to right, #8B0000, #B22222)';
           
            // Scroll to top
            window.scrollTo({top: 0, behavior: 'smooth'});
        }

        // Download results as a text file
        function downloadResults() {
            if (!examSubmitted) return;
           
            // Calculate score
            let score = 0;
            userAnswers.forEach((answer, index) => {
                if (answer === examQuestions[index].correct) {
                    score++;
                }
            });
           
            // Format current time
            const endTime = new Date();
            const timeTaken = 60 * 60 - timeRemaining; // in seconds
            const minutesTaken = Math.floor(timeTaken / 60);
            const secondsTaken = timeTaken % 60;
           
            // Create result content
            let resultContent = `D/Asharf elsaqa - ADVANCED ALGEBRA RESULTS\n`;
            resultContent += `===================================================\n\n`;
            resultContent += `Instructor: D/Asharf elsaqa\n`;
            resultContent += `Challenge started at: ${examStartTime.toLocaleString()}\n`;
            resultContent += `Challenge completed at: ${endTime.toLocaleString()}\n`;
            resultContent += `Time taken: ${minutesTaken} minutes, ${secondsTaken} seconds\n\n`;
            resultContent += `FINAL SCORE: ${score}/${examQuestions.length} (${((score/examQuestions.length)*100).toFixed(1)}%)\n\n`;
           
            // Add rank based on score
            const percentage = (score / examQuestions.length * 100);
            let rank = "";
            if (percentage >= 90) rank = "🏆 EMPEROR STATUS";
            else if (percentage >= 80) rank = "⚔️ ROYAL KNIGHT";
            else if (percentage >= 70) rank = "🛡️ NOBLE LORD";
            else if (percentage >= 60) rank = "🏰 LOYAL VASSAL";
            else rank = "📚 APPRENTICE MAGE";
           
            resultContent += `YOUR RANK: ${rank}\n\n`;
            resultContent += `ANSWER DETAILS:\n`;
            resultContent += `================\n\n`;
           
            // Add each question with user's answer and correct answer
            examQuestions.forEach((q, index) => {
                resultContent += `Question ${q.id}: ${q.question.replace(/<[^>]*>/g, '')}\n`;
                resultContent += `Your answer: ${userAnswers[index] !== null ? q.options[userAnswers[index]].replace(/<[^>]*>/g, '') : 'Not answered'}\n`;
                resultContent += `Correct answer: ${q.options[q.correct].replace(/<[^>]*>/g, '')}\n`;
                resultContent += `Status: ${userAnswers[index] === q.correct ? '✓ CORRECT' : '✗ INCORRECT'}\n`;
                resultContent += `Explanation: ${q.explanation.replace(/<[^>]*>/g, '')}\n`;
                resultContent += `---\n\n`;
            });
           
            // Create and download the file
            const blob = new Blob([resultContent], { type: 'text/plain' });
            const url = URL.createObjectURL(blob);
            const a = document.createElement('a');
            a.href = url;
            a.download = `Asharf_elsaqa_Results_${endTime.toISOString().split('T')[0]}.txt`;
            document.body.appendChild(a);
            a.click();
            document.body.removeChild(a);
            URL.revokeObjectURL(url);
        }

        // Initialize the exam when page loads
        document.addEventListener('DOMContentLoaded', initExam);
    </script>
</body>
</html>
