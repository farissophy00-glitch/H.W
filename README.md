[index.html](https://github.com/user-attachments/files/25640681/index.html)
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Math Empire · Triangle Geometry Challenge</title>
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
                <i class="fas fa-crown empire-logo"></i> MATH EMPIRE
            </div>
            <div class="subtitle">Triangle Geometry Challenge</div>
            <div class="instructors">
                <strong>Instructors:</strong>
                <span class="instructor-name">Eng. Youseef Mehanna</span> &
                <span class="instructor-name">Eng. Eyad Hefny</span>
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
                    <h2>Triangle Geometry Challenge</h2>
                    <span id="answered-count">0/8 answered</span>
                </div>
                <div class="test-instructions">
                    <i class="fas fa-info-circle"></i> <strong>Instructions:</strong> Solve each problem without a calculator. Use exact numbers (radicals allowed). Choose the correct option.
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
                    <i class="fas fa-crown"></i> Score: <span id="current-score">0</span>/8
                </div>
                <p id="score-message">Complete the challenge to see your score</p>
            </div>
        </div>
       
        <!-- Footer -->
        <div class="footer">
            <p>© 2023 Math Empire | Conquer Mathematics, Rule the Empire</p>
            <p>Triangle Geometry Challenge designed by Eng. Youseef Mehanna & Eng. Eyad Hefny</p>
        </div>
    </div>

    <script>
        // Exam data – 8 triangle geometry questions with exact answers
        const examQuestions = [
            {
                id: 1,
                question: `Triangle ABC is a 30-60-90 triangle. Angle B is a right angle. The measure of Angle A is 30°. The length of side AC is 24 inches. What is the length of side BC and the perimeter of the triangle? (Use exact numbers)`,
                options: [
                    "BC = 12 in, perimeter = 36 + 12√3 in",
                    "BC = 12√3 in, perimeter = 36 + 12√3 in",
                    "BC = 12 in, perimeter = 24 + 12√3 in",
                    "BC = 24 in, perimeter = 48 + 12√3 in"
                ],
                correct: 0,
                explanation: "In a 30-60-90 triangle, sides are in ratio 1 : √3 : 2 opposite 30°, 60°, 90°. Angle A = 30°, so BC (opposite A) = half the hypotenuse AC = 12. AB (opposite 60°) = 12√3. Perimeter = 12 + 12√3 + 24 = 36 + 12√3."
            },
            {
                id: 2,
                question: `Triangle ABC is an isosceles right triangle. Angle B is a right angle. The length of one leg is 9√2 inches. What are the length of the hypotenuse and the area? (Use exact numbers)`,
                options: [
                    "Hypotenuse = 18 in, Area = 81 sq in",
                    "Hypotenuse = 9√2 in, Area = 81 sq in",
                    "Hypotenuse = 18 in, Area = 162 sq in",
                    "Hypotenuse = 9√2 in, Area = 162 sq in"
                ],
                correct: 0,
                explanation: "Isosceles right triangle: legs equal. Hypotenuse = leg × √2 = 9√2 × √2 = 18. Area = ½ × leg² = ½ × (9√2)² = ½ × 162 = 81."
            },
            {
                id: 3,
                question: `Triangle ABC is an isosceles right triangle. Angle B is a right angle. The length of the hypotenuse is 41√2 inches. What is the perimeter? (Use exact numbers)`,
                options: [
                    "82 + 41√2 in",
                    "41 + 41√2 in",
                    "82 + 82√2 in",
                    "41 + 82√2 in"
                ],
                correct: 0,
                explanation: "Leg = hypotenuse / √2 = 41√2 / √2 = 41. Perimeter = 2×leg + hypotenuse = 82 + 41√2."
            },
            {
                id: 4,
                question: `Triangle ABC is a right triangle where angle B is a right angle. The measure of Angle C is 30°. Side BC has a length of 57 inches. What is the perimeter? (Use exact numbers)`,
                options: [
                    "57 + 57√3 in",
                    "57 + 38√3 in",
                    "114 + 57√3 in",
                    "57 + 19√3 in"
                ],
                correct: 0,
                explanation: "Angle C = 30°, so side opposite C (AB) is short leg. BC is opposite 60°, so BC = √3 × short leg. Short leg = BC/√3 = 57/√3 = 19√3. Hypotenuse = 2 × short leg = 38√3. Perimeter = 19√3 + 57 + 38√3 = 57 + 57√3."
            },
            {
                id: 5,
                question: `An isosceles right triangle has a perimeter of 98 + 98√2 inches. What is the length of one leg? (Use exact numbers)`,
                options: [
                    "49√2 in",
                    "49 in",
                    "98 in",
                    "98√2 in"
                ],
                correct: 0,
                explanation: "Let leg = L, then hypotenuse = L√2, perimeter = 2L + L√2 = L(2+√2). Given perimeter = 98(1+√2). Since 2+√2 = √2(1+√2), we have L√2 = 98 → L = 98/√2 = 49√2."
            },
            {
                id: 6,
                question: `A 30-60-90 triangle has a perimeter of 15 + 15√3 inches. What is the length of the longer leg? (Use exact numbers)`,
                options: [
                    "15 in",
                    "5√3 in",
                    "10 in",
                    "15√3 in"
                ],
                correct: 0,
                explanation: "Let short leg = x, then long leg = x√3, hypo = 2x. Perimeter = 3x + x√3 = x(3+√3) = 15(1+√3). Since 3+√3 = √3(1+√3), we get x√3 = 15 → x = 5√3. Longer leg = x√3 = 15."
            },
            {
                id: 7,
                question: `A 30-60-90 triangle has an area of 8√3 square inches. What is the perimeter? (Use exact numbers)`,
                options: [
                    "12 + 4√3 in",
                    "8 + 8√3 in",
                    "16 + 8√3 in",
                    "4 + 4√3 in"
                ],
                correct: 0,
                explanation: "Area = ½ × short × long = ½ × x × x√3 = (x²√3)/2 = 8√3 → x² = 16 → x = 4. Sides: short = 4, long = 4√3, hypo = 8. Perimeter = 4 + 4√3 + 8 = 12 + 4√3."
            },
            {
                id: 8,
                question: `An equilateral triangle has an altitude of 11√3 inches. What is the perimeter? (Use exact numbers)`,
                options: [
                    "66 in",
                    "33 in",
                    "22√3 in",
                    "66√3 in"
                ],
                correct: 0,
                explanation: "Altitude of equilateral triangle = (s√3)/2 = 11√3 → s/2 = 11 → s = 22. Perimeter = 3s = 66."
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
            const storageKey = 'math_empire_geometry_start_time';
           
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
                    message += "👑 <strong>EMPEROR STATUS:</strong> You rule the Math Empire! Your geometry mastery is absolute.";
                } else if (percentage >= 80) {
                    message += "⚔️ <strong>ROYAL KNIGHT:</strong> Excellent command of triangles! You're a valued defender.";
                } else if (percentage >= 70) {
                    message += "🛡️ <strong>NOBLE LORD:</strong> Strong performance! Continue honing your skills.";
                } else if (percentage >= 60) {
                    message += "🏰 <strong>LOYAL VASSAL:</strong> Good effort! Study the explanations to strengthen your geometry.";
                } else {
                    message += "📚 <strong>APPRENTICE MAGE:</strong> The path to mastery begins here. Review each solution carefully.";
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
            let resultContent = `MATH EMPIRE - TRIANGLE GEOMETRY CHALLENGE RESULTS\n`;
            resultContent += `===================================================\n\n`;
            resultContent += `Instructors: Eng. Youseef Mehanna & Eng. Eyad Hefny\n`;
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
            a.download = `Math_Empire_Geometry_${endTime.toISOString().split('T')[0]}.txt`;
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
