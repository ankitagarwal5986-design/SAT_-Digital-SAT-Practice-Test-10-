<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Brain and Mind Academy - Digital SAT Practice Test 10 Math (All 27 Questions)</title>
    <!-- Desmos API Script -->
    <script src="https://www.desmos.com/api/v1.8/calculator.js?apiKey=d2822b107a6c49f6a00a221957776319"></script>
    <style>
        :root {
            --primary-header: #1e3a8a;
            --header-gradient: linear-gradient(135deg, #0f172a 0%, #1e3a8a 100%);
            --accent-gold: #d97706;
            --accent-gold-light: #fcd34d;
            --correct-green: #059669;
            --correct-bg: #d1fae5;
            --incorrect-red: #dc2626;
            --incorrect-bg: #fee2e2;
            --skipped-orange: #f59e0b;
            --skipped-bg: #fef3c7;
            --bg-body: #f8fafc;
            --text-dark: #1e293b;
            --text-muted: #64748b;
            --border-color: #e2e8f0;
            --card-bg: #ffffff;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: var(--bg-body);
            color: var(--text-dark);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
        }

        header {
            background: var(--header-gradient);
            color: white;
            padding: 1.1rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
        }

        .brand-title {
            font-size: 1.45rem;
            font-weight: 700;
            letter-spacing: 0.5px;
            color: #ffffff;
        }

        .brand-subtitle {
            font-size: 0.85rem;
            color: var(--accent-gold-light);
            font-weight: 600;
            margin-top: 2px;
        }

        .user-info {
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .user-email {
            font-size: 0.85rem;
            background: rgba(255, 255, 255, 0.15);
            padding: 0.4rem 0.8rem;
            border-radius: 6px;
        }

        .btn {
            padding: 0.6rem 1.25rem;
            border: none;
            border-radius: 6px;
            font-weight: 600;
            font-size: 0.9rem;
            cursor: pointer;
            transition: all 0.2s ease;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 0.5rem;
        }

        .btn-sm {
            padding: 0.4rem 0.85rem;
            font-size: 0.8rem;
            border-radius: 4px;
        }

        .btn-primary { background-color: var(--primary-header); color: white; }
        .btn-primary:hover { background-color: #172554; }
        .btn-gold { background-color: var(--accent-gold); color: white; }
        .btn-gold:hover { background-color: #b45309; }
        .btn-outline { background: transparent; border: 1.5px solid var(--border-color); color: var(--text-dark); }
        .btn-outline:hover { background-color: #f1f5f9; }
        .btn-danger { background-color: var(--incorrect-red); color: white; }
        .btn-danger:hover { background-color: #b91c1c; }
        .btn-success { background-color: var(--correct-green); color: white; }
        .btn-success:hover { background-color: #047857; }

        .screen {
            display: none;
            padding: 2rem;
            max-width: 1400px;
            margin: 0 auto;
            width: 100%;
            flex: 1;
        }

        .screen.active { display: block; }

        #auth-screen {
            max-width: 480px;
            margin: auto;
            padding-top: 4rem;
        }

        .auth-card {
            background: var(--card-bg);
            padding: 2.5rem;
            border-radius: 12px;
            box-shadow: 0 10px 25px -5px rgba(0,0,0,0.05);
            border: 1px solid var(--border-color);
            text-align: center;
        }

        .auth-card h2 { margin-bottom: 0.5rem; color: var(--primary-header); }
        .auth-card p { color: var(--text-muted); font-size: 0.9rem; margin-bottom: 1.5rem; }

        .form-group { margin-bottom: 1.25rem; text-align: left; }
        .form-group label { display: block; margin-bottom: 0.4rem; font-size: 0.85rem; font-weight: 600; }
        .form-group input, .form-group select {
            width: 100%; padding: 0.75rem; border: 1px solid var(--border-color);
            border-radius: 6px; font-size: 1rem; outline: none; background: white;
        }
        .form-group input:focus, .form-group select:focus {
            border-color: var(--primary-header);
            box-shadow: 0 0 0 3px rgba(30, 58, 138, 0.1);
        }

        .quiz-container {
            display: grid;
            grid-template-columns: 1fr 380px;
            gap: 2rem;
            align-items: start;
        }

        .quiz-card {
            background: var(--card-bg);
            border-radius: 12px;
            padding: 2rem;
            border: 1px solid var(--border-color);
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
        }

        .quiz-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 2px solid var(--bg-body);
            padding-bottom: 1rem;
            margin-bottom: 1.25rem;
        }

        .q-badge {
            background: #eff6ff;
            color: var(--primary-header);
            font-weight: 700;
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.85rem;
        }

        .q-title {
            font-size: 1.15rem;
            line-height: 1.5;
            margin-bottom: 0.75rem;
            font-weight: 700;
            color: var(--primary-header);
        }

        .problem-statement {
            background: #f1f5f9;
            border-left: 4px solid var(--primary-header);
            padding: 1.1rem 1.25rem;
            border-radius: 6px;
            font-size: 0.98rem;
            line-height: 1.6;
            margin-bottom: 1.25rem;
            font-weight: 600;
        }

        .scale-graph-container {
            display: flex;
            justify-content: center;
            align-items: center;
            background: #ffffff;
            border: 1px solid var(--border-color);
            border-radius: 8px;
            padding: 1rem;
            margin: 1rem 0 1.5rem 0;
            overflow-x: auto;
        }

        /* Micro Step Blocks */
        .step-block {
            background: #f8fafc;
            border: 1.5px solid var(--border-color);
            border-radius: 10px;
            padding: 1.25rem;
            margin-bottom: 1.25rem;
            transition: all 0.3s ease;
        }

        .step-block.locked {
            opacity: 0.4;
            pointer-events: none;
            filter: grayscale(0.8);
        }

        .step-block.active-step {
            border-color: var(--primary-header);
            box-shadow: 0 0 0 3px rgba(30, 58, 138, 0.1);
        }

        .step-block.completed-step {
            border-color: var(--correct-green);
            background-color: #f0fdf4;
        }

        .step-block.skipped-step {
            border-color: var(--skipped-orange);
            background-color: var(--skipped-bg);
        }

        .step-header {
            display: flex;
            align-items: center;
            justify-content: space-between;
            margin-bottom: 0.75rem;
        }

        .step-tag {
            font-weight: 700;
            font-size: 0.85rem;
            text-transform: uppercase;
            letter-spacing: 0.5px;
            color: var(--accent-gold);
        }

        .completed-step .step-tag { color: var(--correct-green); }
        .skipped-step .step-tag { color: var(--skipped-orange); }

        .step-prompt {
            font-size: 0.95rem;
            font-weight: 600;
            margin-bottom: 1rem;
            line-height: 1.5;
        }

        .step-actions {
            display: flex;
            gap: 0.5rem;
            margin-top: 1rem;
            padding-top: 0.75rem;
            border-top: 1px dashed var(--border-color);
        }

        .step-options-list {
            display: flex;
            flex-direction: column;
            gap: 0.6rem;
            margin-bottom: 0.5rem;
        }

        .step-option-item {
            display: flex;
            align-items: center;
            padding: 0.75rem 1rem;
            border: 1.5px solid var(--border-color);
            border-radius: 6px;
            cursor: pointer;
            transition: all 0.2s ease;
            background: white;
            font-size: 0.92rem;
            font-weight: 600;
            line-height: 1.4;
        }

        .step-option-item:hover:not(.disabled) {
            border-color: var(--primary-header);
            background-color: #eff6ff;
        }

        .step-option-item.selected {
            border-color: var(--primary-header);
            background-color: #eff6ff;
        }

        .step-option-item.correct {
            border-color: var(--correct-green);
            background-color: var(--correct-bg);
            color: #065f46;
        }

        .step-option-item.incorrect {
            border-color: var(--incorrect-red);
            background-color: var(--incorrect-bg);
            color: #991b1b;
        }

        .step-option-item.disabled { cursor: default; }

        .step-opt-prefix {
            width: 24px;
            height: 24px;
            border-radius: 50%;
            background: #e2e8f0;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 700;
            font-size: 0.75rem;
            margin-right: 0.75rem;
            flex-shrink: 0;
        }

        .step-option-item.selected .step-opt-prefix { background: var(--primary-header); color: white; }
        .step-option-item.correct .step-opt-prefix { background: var(--correct-green); color: white; }
        .step-option-item.incorrect .step-opt-prefix { background: var(--incorrect-red); color: white; }

        .action-bar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding-top: 1.5rem;
            border-top: 1px solid var(--border-color);
        }

        .rationale-box {
            margin-top: 1.5rem;
            padding: 1.25rem;
            border-radius: 8px;
            background: #f1f5f9;
            border-left: 4px solid var(--primary-header);
        }

        .rationale-title { font-weight: 700; color: var(--primary-header); margin-bottom: 0.5rem; }

        .quiz-sidebar {
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
            position: sticky;
            top: 2rem;
        }

        .sidebar-card {
            background: var(--card-bg);
            border-radius: 12px;
            padding: 1.5rem;
            border: 1px solid var(--border-color);
        }

        .sidebar-title {
            font-size: 1.05rem;
            font-weight: 700;
            margin-bottom: 1rem;
            color: var(--primary-header);
        }

        .legend-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 0.5rem;
            margin-bottom: 1.25rem;
            font-size: 0.8rem;
        }

        .legend-item { display: flex; align-items: center; gap: 0.4rem; }
        .legend-dot { width: 12px; height: 12px; border-radius: 3px; }
        .dot-active { border: 2px solid var(--primary-header); background: transparent; }
        .dot-attempted { background: var(--correct-green); }
        .dot-skipped { background: var(--skipped-orange); }
        .dot-unvisited { background: #cbd5e1; }

        .question-grid {
            display: grid;
            grid-template-columns: repeat(6, 1fr);
            gap: 0.45rem;
            max-height: 230px;
            overflow-y: auto;
        }

        .grid-btn {
            aspect-ratio: 1; border: 1px solid var(--border-color); background: #f8fafc;
            color: var(--text-dark); border-radius: 6px; font-weight: 600; font-size: 0.85rem;
            cursor: pointer; transition: all 0.15s ease;
        }

        .grid-btn.active { border: 2px solid var(--primary-header); color: var(--primary-header); font-weight: 800; background: #eff6ff; }
        .grid-btn.attempted { background: var(--correct-green); color: white; border-color: var(--correct-green); }
        .grid-btn.skipped { background: var(--skipped-orange); color: white; border-color: var(--skipped-orange); }

        /* Calculator */
        .calc-display {
            width: 100%;
            padding: 0.6rem;
            font-size: 1.2rem;
            text-align: right;
            border: 1px solid var(--border-color);
            border-radius: 6px;
            margin-bottom: 0.75rem;
            background: #f8fafc;
            font-family: monospace;
            font-weight: bold;
        }

        .calc-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 0.35rem;
        }

        .calc-btn {
            padding: 0.55rem 0.2rem;
            font-size: 0.85rem;
            font-weight: 600;
            border: 1px solid var(--border-color);
            border-radius: 4px;
            background: #fff;
            cursor: pointer;
        }

        .calc-btn:hover { background: #e2e8f0; }
        .calc-btn.op { background: #eff6ff; color: var(--primary-header); }
        .calc-btn.special { background: var(--skipped-bg); color: var(--accent-gold); }

        #desmos-calculator {
            width: 100%;
            height: 260px;
            border-radius: 8px;
            border: 1px solid var(--border-color);
        }

        .results-summary {
            background: var(--card-bg); border-radius: 12px; padding: 2rem;
            border: 1px solid var(--border-color); margin-bottom: 2rem; text-align: center;
        }

        .score-circle {
            width: 130px; height: 130px; border-radius: 50%; background: var(--header-gradient);
            color: white; display: flex; flex-direction: column; align-items: center;
            justify-content: center; margin: 1rem auto;
        }

        .score-num { font-size: 2.2rem; font-weight: 800; color: var(--accent-gold-light); }
        .review-list { display: flex; flex-direction: column; gap: 1.5rem; }
        .review-card { background: var(--card-bg); border-radius: 12px; padding: 1.5rem; border: 1px solid var(--border-color); }

        .status-tag {
            padding: 0.25rem 0.6rem; border-radius: 4px; font-size: 0.75rem;
            font-weight: 700; text-transform: uppercase;
        }

        .tag-correct { background: var(--correct-bg); color: #065f46; }
        .tag-incorrect { background: var(--incorrect-bg); color: #991b1b; }
        .tag-skipped { background: var(--skipped-bg); color: #92400e; }

        @media (max-width: 992px) {
            .quiz-container { grid-template-columns: 1fr; }
            .quiz-sidebar { position: static; }
        }
    </style>
</head>
<body>

    <header>
        <div>
            <div class="brand-title">BRAIN AND MIND ACADEMY</div>
            <div class="brand-subtitle">Digital SAT Practice Test #10 • Math Module 1 (Questions 1 to 27)</div>
        </div>
        <div class="user-info" id="user-header-info" style="display: none;">
            <span class="user-email" id="display-user-email"></span>
            <button class="btn btn-outline" style="color:white; border-color:rgba(255,255,255,0.3);" onclick="logout()">Switch User</button>
        </div>
    </header>

    <!-- Auth Screen -->
    <div id="auth-screen" class="screen active">
        <div class="auth-card">
            <h2>SAT Math Module 1 Portal</h2>
            <p>Access all 27 Math questions with interactive step-by-step guidance and Desmos plotting.</p>
            <form onsubmit="handleLogin(event)">
                <div class="form-group">
                    <label for="email-input">Student Email Address</label>
                    <input type="email" id="email-input" required placeholder="student@satprep.edu">
                </div>
                <button type="submit" class="btn btn-primary" style="width: 100%;">Start Math Module 1 (Questions 1–27)</button>
            </form>
        </div>
    </div>

    <!-- Quiz Screen -->
    <div id="quiz-screen" class="screen">
        <div class="quiz-container">
            <div class="quiz-card">
                <div class="quiz-header">
                    <span class="q-badge" id="q-number-badge">Card 1 of 27</span>
                    <span style="font-size: 0.85rem; color: var(--text-muted);">Digital SAT • Section 2: Math Module 1</span>
                </div>

                <div class="q-title" id="q-title-text"></div>
                <div class="problem-statement" id="q-problem-text"></div>
                <div class="scale-graph-container" id="q-graph-container" style="display: none;"></div>

                <!-- STEP 1 BLOCK -->
                <div class="step-block active-step" id="step1-block">
                    <div class="step-header">
                        <span class="step-tag" id="step1-tag">Step 1: Conceptual Identification</span>
                        <span id="step1-status-tag" style="font-weight:700; font-size:0.8rem; color:var(--accent-gold);">In Progress</span>
                    </div>
                    <div class="step-prompt" id="step1-prompt"></div>
                    <div class="step-options-list" id="step1-options-container"></div>
                    <div class="step-actions" id="step1-actions">
                        <button class="btn btn-primary btn-sm" onclick="checkStep(1)">Check Step 1</button>
                        <button class="btn btn-gold btn-sm" onclick="skipStep(1)">Skip Step 1</button>
                    </div>
                </div>

                <!-- STEP 2 BLOCK -->
                <div class="step-block locked" id="step2-block">
                    <div class="step-header">
                        <span class="step-tag" id="step2-tag">Step 2: Algebraic Formulation</span>
                        <span id="step2-status-tag" style="font-weight:700; font-size:0.8rem; color:var(--text-muted);">Locked</span>
                    </div>
                    <div class="step-prompt" id="step2-prompt"></div>
                    <div class="step-options-list" id="step2-options-container"></div>
                    <div class="step-actions" id="step2-actions" style="display:none;">
                        <button class="btn btn-primary btn-sm" onclick="checkStep(2)">Check Step 2</button>
                        <button class="btn btn-gold btn-sm" onclick="skipStep(2)">Skip Step 2</button>
                    </div>
                </div>

                <!-- STEP 3 BLOCK -->
                <div class="step-block locked" id="step3-block">
                    <div class="step-header">
                        <span class="step-tag" id="step3-tag">Step 3: Final Answer & Verification</span>
                        <span id="step3-status-tag" style="font-weight:700; font-size:0.8rem; color:var(--text-muted);">Locked</span>
                    </div>
                    <div class="step-prompt" id="step3-prompt"></div>
                    <div class="step-options-list" id="step3-options-container"></div>
                    <div class="step-actions" id="step3-actions" style="display:none;">
                        <button class="btn btn-primary btn-sm" onclick="checkStep(3)">Check Step 3</button>
                        <button class="btn btn-gold btn-sm" onclick="skipStep(3)">Skip Step 3</button>
                    </div>
                </div>

                <div class="action-bar">
                    <button class="btn btn-danger" id="skip-card-btn" onclick="skipEntireCard()">Skip Entire Card</button>
                    <button class="btn btn-outline" id="next-btn" style="display: none;" onclick="nextQuestion()">Next Card &rarr;</button>
                </div>

                <div class="rationale-box" id="rationale-container" style="display: none;">
                    <div class="rationale-title">College Board Official Rationale</div>
                    <div id="rationale-text" style="font-size: 0.95rem; line-height: 1.6;"></div>
                </div>
            </div>

            <!-- Sidebar -->
            <div class="quiz-sidebar">
                <div class="sidebar-card">
                    <div class="sidebar-title">Question Navigator (1–27)</div>
                    <div class="legend-grid">
                        <div class="legend-item"><div class="legend-dot dot-active"></div> Active</div>
                        <div class="legend-item"><div class="legend-dot dot-attempted"></div> Submitted</div>
                        <div class="legend-item"><div class="legend-dot dot-skipped"></div> Skipped</div>
                        <div class="legend-item"><div class="legend-dot dot-unvisited"></div> Unvisited</div>
                    </div>
                    <div class="question-grid" id="question-grid"></div>
                    <div style="margin-top: 1rem;">
                        <button class="btn btn-danger" style="width: 100%;" onclick="finishTest()">Finish & Review Module 1</button>
                    </div>
                </div>

                <!-- Desmos Graphing Calculator Embed -->
                <div class="sidebar-card">
                    <div class="sidebar-title" style="margin-bottom:0.5rem;">Desmos SAT Graphing Calculator</div>
                    <div id="desmos-calculator"></div>
                </div>

                <!-- Scientific Calculator -->
                <div class="sidebar-card">
                    <div class="sidebar-title" style="margin-bottom:0.5rem;">Scientific Calculator</div>
                    <input type="text" class="calc-display" id="calc-disp" readonly value="0">
                    <div class="calc-grid">
                        <button class="calc-btn special" onclick="calcSqrt()">√x</button>
                        <button class="calc-btn special" onclick="calcInput('**2')">x²</button>
                        <button class="calc-btn special" onclick="calcInput('**3')">x³</button>
                        <button class="calc-btn op" onclick="calcClear()">C</button>

                        <button class="calc-btn" onclick="calcInput('7')">7</button>
                        <button class="calc-btn" onclick="calcInput('8')">8</button>
                        <button class="calc-btn" onclick="calcInput('9')">9</button>
                        <button class="calc-btn op" onclick="calcInput('/')">÷</button>
                        
                        <button class="calc-btn" onclick="calcInput('4')">4</button>
                        <button class="calc-btn" onclick="calcInput('5')">5</button>
                        <button class="calc-btn" onclick="calcInput('6')">6</button>
                        <button class="calc-btn op" onclick="calcInput('*')">×</button>
                        
                        <button class="calc-btn" onclick="calcInput('1')">1</button>
                        <button class="calc-btn" onclick="calcInput('2')">2</button>
                        <button class="calc-btn" onclick="calcInput('3')">3</button>
                        <button class="calc-btn op" onclick="calcInput('-')">-</button>
                        
                        <button class="calc-btn" onclick="calcInput('0')">0</button>
                        <button class="calc-btn" onclick="calcInput('.')">.</button>
                        <button class="calc-btn op" onclick="calcInput('+')">+</button>
                        <button class="calc-btn op" onclick="calcEval()">=</button>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Review Screen -->
    <div id="review-screen" class="screen">
        <div class="results-summary">
            <h2>Digital SAT Practice Test #10 • Math Module 1 Report</h2>
            <div class="score-circle">
                <span class="score-num" id="final-score">0 / 27</span>
                <span style="font-size: 0.8rem; opacity: 0.8;">Raw Score</span>
            </div>
            <button class="btn btn-primary" onclick="restartQuiz()">Retake Math Module 1</button>
        </div>

        <h3 style="margin-bottom: 1rem; color: var(--primary-header);">Student Performance & Solutions Review</h3>
        <div class="review-list" id="review-list"></div>
    </div>

    <script>
        const AudioFX = {
            ctx: null,
            init() {
                if (!this.ctx) {
                    this.ctx = new (window.AudioContext || window.webkitAudioContext)();
                }
                if (this.ctx.state === 'suspended') {
                    this.ctx.resume();
                }
            },
            playCorrectBell() {
                this.init();
                const now = this.ctx.currentTime;
                const playSingleBell = (freq, time, duration) => {
                    const osc = this.ctx.createOscillator();
                    const gain = this.ctx.createGain();
                    osc.type = 'sine';
                    osc.frequency.setValueAtTime(freq, time);
                    gain.gain.setValueAtTime(0, time);
                    gain.gain.linearRampToValueAtTime(0.3, time + 0.01);
                    gain.gain.exponentialRampToValueAtTime(0.001, time + duration);
                    osc.connect(gain);
                    gain.connect(this.ctx.destination);
                    osc.start(time);
                    osc.stop(time + duration);
                };
                playSingleBell(880, now, 0.8);        
                playSingleBell(1318.51, now + 0.12, 1.2); 
            },
            playIncorrectBell() {
                this.init();
                const now = this.ctx.currentTime;
                const osc = this.ctx.createOscillator();
                const gain = this.ctx.createGain();
                osc.type = 'triangle';
                osc.frequency.setValueAtTime(220, now); 
                gain.gain.setValueAtTime(0, now);
                gain.gain.linearRampToValueAtTime(0.35, now + 0.01);
                gain.gain.exponentialRampToValueAtTime(0.001, now + 0.6);
                osc.connect(gain);
                gain.connect(this.ctx.destination);
                osc.start(now);
                osc.stop(now + 0.6);
            },
            playSkipChime() {
                this.init();
                const now = this.ctx.currentTime;
                const osc = this.ctx.createOscillator();
                const gain = this.ctx.createGain();
                osc.type = 'sine';
                osc.frequency.setValueAtTime(523.25, now); 
                osc.frequency.exponentialRampToValueAtTime(392, now + 0.15); 
                gain.gain.setValueAtTime(0.15, now);
                gain.gain.exponentialRampToValueAtTime(0.001, now + 0.15);
                osc.connect(gain);
                gain.connect(this.ctx.destination);
                osc.start(now);
                osc.stop(now + 0.15);
            }
        };

        const CHAPTER_KEY = "SAT_PRACTICE_TEST_10_MATH_MODULE_1_FULL_27";

        // Scale-Accurate Coordinate Grid Generator
        function generateSATGridSVG(elements, xRange = [-6, 6], yRange = [-6, 6], width = 300, height = 280) {
            const pad = 28;
            const plotW = width - 2 * pad;
            const plotH = height - 2 * pad;
            const toX = val => pad + ((val - xRange[0]) / (xRange[1] - xRange[0])) * plotW;
            const toY = val => pad + ((yRange[1] - val) / (yRange[1] - yRange[0])) * plotH;

            let gridLines = '';
            for (let x = Math.ceil(xRange[0]); x <= Math.floor(xRange[1]); x++) {
                gridLines += `<line x1="${toX(x)}" y1="${pad}" x2="${toX(x)}" y2="${height - pad}" stroke="#e2e8f0" stroke-width="1"/>`;
                if (x !== 0 && x % 2 === 0) {
                    gridLines += `<text x="${toX(x)}" y="${toY(0) + 14}" font-size="9" text-anchor="middle" fill="#64748b">${x}</text>`;
                }
            }
            for (let y = Math.ceil(yRange[0]); y <= Math.floor(yRange[1]); y++) {
                gridLines += `<line x1="${pad}" y1="${toY(y)}" x2="${width - pad}" y2="${toY(y)}" stroke="#e2e8f0" stroke-width="1"/>`;
                if (y !== 0 && y % 2 === 0) {
                    gridLines += `<text x="${toX(0) - 6}" y="${toY(y) + 3}" font-size="9" text-anchor="end" fill="#64748b">${y}</text>`;
                }
            }

            const xAxis = `<line x1="${pad - 10}" y1="${toY(0)}" x2="${width - pad + 10}" y2="${toY(0)}" stroke="#334155" stroke-width="2"/>
                           <text x="${width - pad + 14}" y="${toY(0) + 4}" font-size="11" font-weight="bold" fill="#334155">x</text>`;
            const yAxis = `<line x1="${toX(0)}" y1="${height - pad + 10}" x2="${toX(0)}" y2="${pad - 10}" stroke="#334155" stroke-width="2"/>
                           <text x="${toX(0) + 5}" y="${pad - 12}" font-size="11" font-weight="bold" fill="#334155">y</text>`;

            let content = '';
            elements.forEach(el => {
                if (el.type === 'curve') {
                    let d = '';
                    const step = 0.05;
                    let first = true;
                    for (let x = el.min; x <= el.max; x += step) {
                        const y = el.fn(x);
                        if (y >= yRange[0] - 1 && y <= yRange[1] + 1) {
                            d += `${first ? 'M' : 'L'} ${toX(x).toFixed(1)} ${toY(y).toFixed(1)} `;
                            first = false;
                        } else {
                            first = true;
                        }
                    }
                    content += `<path d="${d}" fill="none" stroke="${el.color}" stroke-width="${el.width || 2.5}"/>`;
                } else if (el.type === 'point') {
                    content += `<circle cx="${toX(el.x)}" cy="${toY(el.y)}" r="${el.r || 4}" fill="${el.color}"/>`;
                    if (el.label) {
                        content += `<text x="${toX(el.x) + 7}" y="${toY(el.y) - 6}" font-size="10" font-weight="bold" fill="${el.color}">${el.label}</text>`;
                    }
                } else if (el.type === 'line') {
                    content += `<line x1="${toX(el.x1)}" y1="${toY(el.y1)}" x2="${toX(el.x2)}" y2="${toY(el.y2)}" stroke="${el.color}" stroke-width="${el.width || 2.5}"/>`;
                }
            });

            return `<svg width="${width}" height="${height}" viewBox="0 0 ${width} ${height}">${gridLines}${xAxis}${yAxis}${content}</svg>`;
        }

        // ALL 27 QUESTIONS of Digital SAT Practice Test #10, Math Module 1
        const questionsData = [
            // Q1
            {
                id: 1,
                desmosLatex: 'y=4',
                title: "Card 1 (Question 1): Used Car Lot Model Year Line Graph",
                problem: "The line graph shows the percent of cars for sale at a used car lot on a given day by model year from 2010 to 2019. For what model year is the percent of cars for sale the smallest?",
                graphSVG: `<svg width="290" height="150" viewBox="0 0 290 150">
                    <line x1="35" y1="120" x2="270" y2="120" stroke="#333" stroke-width="2"/>
                    <line x1="35" y1="120" x2="35" y2="20" stroke="#333" stroke-width="2"/>
                    <text x="10" y="125" font-size="8">0%</text>
                    <text x="10" y="75" font-size="8">8%</text>
                    <text x="5" y="25" font-size="8">15%</text>
                    <polyline points="45,40 68,40 91,40 114,75 137,105 160,68 183,58 206,58 229,48 252,48" fill="none" stroke="#1e3a8a" stroke-width="2.5"/>
                    <circle cx="137" cy="105" r="5" fill="#dc2626"/>
                    <text x="137" y="125" font-size="8" font-weight="bold" fill="#dc2626" text-anchor="middle">2014</text>
                </svg>`,
                step1: {
                    tag: "Step 1: Reading the Axes",
                    prompt: "What does the vertical axis measure, and how is the smallest value identified?",
                    options: [
                        "The vertical axis indicates the model year, and the left-most point is the smallest.",
                        "The vertical axis indicates the percent of cars for sale, so the lowest point represents the smallest percentage.",
                        "The vertical axis measures the price in thousands of dollars.",
                        "The vertical axis shows car mileage."
                    ],
                    correct: 1
                },
                step2: {
                    tag: "Step 2: Identifying the Minimum Point",
                    prompt: "Locate the minimum point on the graph and read the horizontal axis value:",
                    options: [
                        "The graph reaches its lowest point at the year 2012.",
                        "The graph reaches its lowest point at the year 2013.",
                        "The graph reaches its lowest point at the year 2014 with a percentage of approximately 4%.",
                        "The graph reaches its lowest point at the year 2015."
                    ],
                    correct: 2
                },
                step3: {
                    tag: "Step 3: Concluding the Model Year",
                    prompt: "State the model year with the smallest percentage:",
                    options: [
                        "A) 2012",
                        "B) 2013",
                        "C) 2014",
                        "D) 2015"
                    ],
                    correct: 2
                },
                rationale: "The vertical axis represents the percent of cars for sale. Looking at the graph, the lowest point occurs at the model year 2014 (approx 4%). Therefore, the answer is 2014 (Choice C)."
            },
            // Q2
            {
                id: 2,
                desmosLatex: 'y=-2x+3',
                title: "Card 2 (Question 2): System of Linear Equations Graph",
                problem: "The graph of a system of linear equations is shown. What is the solution (x, y) to the system?",
                graphSVG: generateSATGridSVG([
                    { type: 'line', x1: -1, y1: 5.5, x2: 5, y2: -6.5, color: '#1e3a8a', width: 2.5 },
                    { type: 'line', x1: -6, y1: 2.5, x2: 6, y2: -6.5, color: '#059669', width: 2.5 },
                    { type: 'point', x: 4, y: -5, color: '#dc2626', r: 5, label: '(4, -5)' }
                ], [-6, 6], [-6, 6]),
                step1: {
                    tag: "Step 1: Graphical Solution Definition",
                    prompt: "What represents the solution to a system of two lines graphed in the coordinate plane?",
                    options: [
                        "The point of intersection (x, y) where the two lines cross.",
                        "The y-intercept of the steeper line.",
                        "The x-intercept of the flatter line.",
                        "The midpoint between the x-intercepts."
                    ],
                    correct: 0
                },
                step2: {
                    tag: "Step 2: Reading the Intersection Coordinates",
                    prompt: "Inspect the coordinate grid where the lines cross in Quadrant IV:",
                    options: [
                        "The lines cross at x = 0, y = 3.",
                        "The lines cross at x = 0, y = -2.",
                        "The lines cross at x = -2, y = 3.",
                        "The lines cross at x = 4, y = -5."
                    ],
                    correct: 3
                },
                step3: {
                    tag: "Step 3: Stating the Solution",
                    prompt: "Select the correct ordered pair (x, y):",
                    options: [
                        "A) (4, -5)",
                        "B) (0, 3)",
                        "C) (0, -2)",
                        "D) (-2, 3)"
                    ],
                    correct: 0
                },
                rationale: "The solution to a system of linear equations on a graph is the coordinate point of intersection. Here, the two lines intersect at (4, -5) (Choice A)."
            },
            // Q3
            {
                id: 3,
                desmosLatex: '25+10t<=75',
                title: "Card 3 (Question 3): Linear Inequality for Surfboard Rental",
                problem: "The total cost, in dollars, to rent a surfboard consists of a $25 service fee and a $10 per hour rental fee. A person rents a surfboard for t hours and intends to spend a maximum of $75 to rent the surfboard. Which inequality represents this situation?",
                graphSVG: null,
                step1: {
                    tag: "Step 1: Identifying Cost Components",
                    prompt: "Identify the fixed cost and the variable cost for renting for t hours:",
                    options: [
                        "Fixed fee is $10 and hourly fee is $25t.",
                        "Fixed service fee is $25, and hourly fee is $10 per hour for t hours, giving $10t.",
                        "Both fees depend on t: 25t + 10t.",
                        "There is no fixed fee."
                    ],
                    correct: 1
                },
                step2: {
                    tag: "Step 2: Budget Constraint Inequality",
                    prompt: "The person intends to spend a 'maximum of $75' (at most $75):",
                    options: [
                        "Total cost must be strictly greater than 75: Total > 75",
                        "Total cost must equal 75: Total = 75",
                        "Total cost must be less than or equal to 75: Total ≤ 75",
                        "Total cost must be strictly less than 75: Total < 75"
                    ],
                    correct: 2
                },
                step3: {
                    tag: "Step 3: Formulating the Complete Inequality",
                    prompt: "Select the correct inequality representing this situation:",
                    options: [
                        "A) 10t ≤ 75",
                        "B) 10 + 25t ≤ 75",
                        "C) 25t ≤ 75",
                        "D) 25 + 10t ≤ 75"
                    ],
                    correct: 3
                },
                rationale: "The total cost is the sum of the $25 one-time fee and $10 for each of the t hours (10t). A maximum of $75 means ≤ 75. Therefore, 25 + 10t ≤ 75 (Choice D)."
            },
            // Q4
            {
                id: 4,
                desmosLatex: 'y=(x-2)^2+2',
                title: "Card 4 (Question 4): Vertical Translation of a Parabola",
                problem: "The graph shown has its vertex at (2, -2). If this graph is translated up 4 units, which of the following will be the resulting graph?",
                graphSVG: generateSATGridSVG([
                    { type: 'curve', fn: x => Math.pow(x - 2, 2) - 2, min: -1, max: 5, color: '#1e3a8a', width: 2.5 },
                    { type: 'point', x: 2, y: -2, color: '#dc2626', r: 5, label: '(2, -2)' }
                ], [-6, 10], [-6, 6]),
                step1: {
                    tag: "Step 1: Vertical Translation Rule",
                    prompt: "What mathematical transformation occurs to the coordinates when a graph is shifted up by 4 units?",
                    options: [
                        "Every x-coordinate increases by 4: (x + 4, y)",
                        "Every y-coordinate increases by 4 while the x-coordinate stays unchanged: (x, y + 4)",
                        "Both x and y coordinates are multiplied by 4",
                        "The parabola flips upside down"
                    ],
                    correct: 1
                },
                step2: {
                    tag: "Step 2: Shifting the Vertex",
                    prompt: "Calculate the coordinates of the new vertex starting from (2, -2):",
                    options: [
                        "New vertex = (2 + 4, -2) = (6, -2)",
                        "New vertex = (2, -2 - 4) = (2, -6)",
                        "New vertex = (2, -2 + 4) = (2, 2)",
                        "New vertex = (-2, 2)"
                    ],
                    correct: 2
                },
                step3: {
                    tag: "Step 3: Selecting the Resulting Graph",
                    prompt: "Which choice depicts an upward-opening parabola with vertex at (2, 2)?",
                    options: [
                        "A) Graph with vertex at (2, 2)",
                        "B) Graph with vertex at (2, -6)",
                        "C) Graph with vertex at (-2, -2)",
                        "D) Graph with vertex at (6, -2)"
                    ],
                    correct: 0
                },
                rationale: "Translating a graph up 4 units adds 4 to the y-coordinate of every point. The original vertex at (2, -2) shifts to (2, -2 + 4) = (2, 2). This matches Choice A."
            },
            // Q5
            {
                id: 5,
                desmosLatex: 's=40+3*5',
                title: "Card 5 (Question 5): Speed Calculation from Linear Acceleration",
                problem: "The equation s = 40 + 3t gives the speed s, in miles per hour, of a certain car t seconds after it began to accelerate. What is the speed, in miles per hour, of the car 5 seconds after it began to accelerate?",
                graphSVG: null,
                step1: {
                    tag: "Step 1: Identifying Given Variables",
                    prompt: "Identify the time value given in the problem to evaluate the speed equation:",
                    options: [
                        "s = 5 mph",
                        "t = 5 seconds",
                        "t = 40 seconds",
                        "s = 40 mph"
                    ],
                    correct: 1
                },
                step2: {
                    tag: "Step 2: Substituting into Equation",
                    prompt: "Substitute t = 5 into s = 40 + 3t:",
                    options: [
                        "s = 40 + 3(5) = 40 + 15",
                        "s = 40 × 3 × 5",
                        "s = (40 + 3) × 5",
                        "s = 40 + 8"
                    ],
                    correct: 0
                },
                step3: {
                    tag: "Step 3: Calculating Speed",
                    prompt: "Calculate s = 40 + 15 = [ _____ ] mph:",
                    options: [
                        "A) 40",
                        "B) 43",
                        "C) 45",
                        "D) 55"
                    ],
                    correct: 3
                },
                rationale: "Substitute t = 5 into s = 40 + 3t: s = 40 + 3(5) = 40 + 15 = 55 miles per hour (Choice D)."
            },
            // Q6
            {
                id: 6,
                desmosLatex: 'f(2)=2^2+2+71',
                title: "Card 6 (Question 6): Evaluating Quadratic Function f(2)",
                problem: "The function f is defined by f(x) = x^2 + x + 71. What is the value of f(2)?",
                graphSVG: null,
                step1: {
                    tag: "Step 1: Function Notation Substitution",
                    prompt: "Substitute x = 2 into every instance of x in the quadratic definition:",
                    options: [
                        "f(2) = 2^2 + 2 + 71",
                        "f(2) = 2(2) + 2 + 71",
                        "f(2) = 2^2 + 71",
                        "f(2) = (2 + 1)^2 + 71"
                    ],
                    correct: 0
                },
                step2: {
                    tag: "Step 2: Arithmetic Evaluation",
                    prompt: "Evaluate the squared term and linear term: 2^2 = 4, then 4 + 2 + 71:",
                    options: [
                        "4 + 2 + 71 = 77",
                        "4 + 71 = 75",
                        "8 + 71 = 79",
                        "6 + 71 = 77"
                    ],
                    correct: 0
                },
                step3: {
                    tag: "Step 3: Stating the Final Value",
                    prompt: "State the calculated value of f(2):",
                    options: [
                        "75",
                        "77",
                        "79",
                        "81"
                    ],
                    correct: 1
                },
                rationale: "f(2) = (2)^2 + (2) + 71 = 4 + 2 + 71 = 77."
            },
            // Q7
            {
                id: 7,
                desmosLatex: '35+10.25*n<=300',
                title: "Card 7 (Question 7): Event Planner Budget Optimization",
                problem: "An event planner is planning a party. It costs a onetime fee of $35 to rent the venue and $10.25 per attendee. The event planner has a budget of $300. What is the greatest number of attendees possible without exceeding the budget?",
                graphSVG: null,
                step1: {
                    tag: "Step 1: Setting up the Inequality",
                    prompt: "Formulate the inequality with n attendees: 35 + 10.25n ≤ 300:",
                    options: [
                        "10.25n ≤ 300 - 35 = 265",
                        "35n + 10.25 ≤ 300",
                        "10.25n ≤ 335",
                        "35 + n ≤ 300"
                    ],
                    correct: 0
                },
                step2: {
                    tag: "Step 2: Solving for n",
                    prompt: "Divide 265 by 10.25: n ≤ 265 / 10.25:",
                    options: [
                        "n ≤ 26.5",
                        "n ≤ 25.8536...",
                        "n ≤ 24.2",
                        "n ≤ 27.0"
                    ],
                    correct: 1
                },
                step3: {
                    tag: "Step 3: Whole Number Attendee Constraint",
                    prompt: "Since attendees must be an integer and the budget cannot be exceeded, round down:",
                    options: [
                        "Maximum attendees = 26",
                        "Maximum attendees = 25",
                        "Maximum attendees = 24",
                        "Maximum attendees = 20"
                    ],
                    correct: 1
                },
                rationale: "35 + 10.25n ≤ 300 ⇒ 10.25n ≤ 265 ⇒ n ≤ 25.85. Since the number of attendees must be a whole number without exceeding $300, the maximum is 25."
            },
            // Q8
            {
                id: 8,
                desmosLatex: 'P=20/80',
                title: "Card 8 (Question 8): Two-Way Table Mascot Probability",
                problem: "The table gives the distribution of votes for a new school mascot among 80 students: Badger (22), Lion (20), Longhorn (14), Tiger (24). Total = 80. If one student is selected at random, what is the probability of selecting a student who voted for a lion?",
                graphSVG: null,
                step1: {
                    tag: "Step 1: Identifying Probability Ratio",
                    prompt: "State the formula: P(Lion) = (Total votes for Lion) / (Total student votes):",
                    options: [
                        "P = 20 / 80",
                        "P = 80 / 20",
                        "P = 20 / 26",
                        "P = 9 / 20"
                    ],
                    correct: 0
                },
                step2: {
                    tag: "Step 2: Simplifying the Ratio",
                    prompt: "Divide numerator and denominator by 20:",
                    options: [
                        "20/80 = 1/4",
                        "20/80 = 1/5",
                        "20/80 = 2/5",
                        "20/80 = 1/2"
                    ],
                    correct: 0
                },
                step3: {
                    tag: "Step 3: Selecting Answer Choice",
                    prompt: "Select the correct probability choice:",
                    options: [
                        "A) 1/9",
                        "B) 1/5",
                        "C) 1/4",
                        "D) 2/3"
                    ],
                    correct: 2
                },
                rationale: "The total number of students voting for a lion is 20 out of 80. Probability = 20/80 = 1/4 (Choice C)."
            },
            // Q9
            {
                id: 9,
                desmosLatex: 'F=90-18',
                title: "Card 9 (Question 9): Congruent Triangles Angle Measure",
                problem: "Triangles ABC and DEF are congruent, where A corresponds to D, and B and E are right angles. The measure of angle A is 18°. What is the measure of angle F?",
                graphSVG: null,
                step1: {
                    tag: "Step 1: Congruence of Corresponding Angles",
                    prompt: "Since △ABC ≅ △DEF and vertex A corresponds to D, what is the measure of angle D?",
                    options: [
                        "Angle D = 90°",
                        "Angle D = Angle A = 18°",
                        "Angle D = 72°",
                        "Angle D = 180°"
                    ],
                    correct: 1
                },
                step2: {
                    tag: "Step 2: Right Triangle Complementary Angles",
                    prompt: "In right triangle DEF, angle E = 90°. The other two acute angles must sum to 90°:",
                    options: [
                        "Angle F = 90° - 18°",
                        "Angle F = 180° - 18°",
                        "Angle F = 18°",
                        "Angle F = 90° + 18°"
                    ],
                    correct: 0
                },
                step3: {
                    tag: "Step 3: Calculating Measure of Angle F",
                    prompt: "Calculate 90° - 18° = [ _____ ]°:",
                    options: [
                        "A) 18°",
                        "B) 72°",
                        "C) 90°",
                        "D) 162°"
                    ],
                    correct: 1
                },
                rationale: "Because △ABC ≅ △DEF, angle D = angle A = 18°. Triangle DEF is a right triangle with right angle at E (90°). Thus, angle F = 90° - 18° = 72° (Choice B)."
            },
            // Q10
            {
                id: 10,
                desmosLatex: '16x+8=4*(4x+2)',
                title: "Card 10 (Question 10): Linear Expression Scaling",
                problem: "If 4x + 2 = 12, what is the value of 16x + 8?",
                graphSVG: null,
                step1: {
                    tag: "Step 1: Observing the Common Factor",
                    prompt: "Factor out 4 from the expression 16x + 8:",
                    options: [
                        "16x + 8 = 4(4x + 2)",
                        "16x + 8 = 2(8x + 4)",
                        "16x + 8 = 8(2x + 1)",
                        "16x + 8 = 4(4x + 4)"
                    ],
                    correct: 0
                },
                step2: {
                    tag: "Step 2: Substituting Known Value",
                    prompt: "Substitute (4x + 2) = 12 into 4(4x + 2):",
                    options: [
                        "4 × 12 = 48",
                        "4 + 12 = 16",
                        "12 / 4 = 3",
                        "16 × 12 = 192"
                    ],
                    correct: 0
                },
                step3: {
                    tag: "Step 3: Selecting the Correct Option",
                    prompt: "What is the value of 16x + 8?",
                    options: [
                        "A) 40",
                        "B) 48",
                        "C) 56",
                        "D) 60"
                    ],
                    correct: 1
                },
                rationale: "Notice that 16x + 8 = 4(4x + 2). Since 4x + 2 = 12, 16x + 8 = 4(12) = 48 (Choice B)."
            },
            // Q11
            {
                id: 11,
                desmosLatex: '(m^4*q^4*z^-1)*(m*q^5*z^3)',
                title: "Card 11 (Question 11): Exponent Rules for Product of Monomials",
                problem: "Which expression is equivalent to (m^4 q^4 z^-1)(m q^5 z^3), where m, q, and z are positive?",
                graphSVG: null,
                step1: {
                    tag: "Step 1: Product of Powers Rule",
                    prompt: "When multiplying like bases, add their exponents (x^a · x^b = x^(a+b)):",
                    options: [
                        "Exponents should be multiplied: 4 × 1, 4 × 5, -1 × 3",
                        "Exponents must be added for each base: m^(4+1), q^(4+5), z^(-1+3)",
                        "Exponents must be subtracted",
                        "Exponents stay the same"
                    ],
                    correct: 1
                },
                step2: {
                    tag: "Step 2: Evaluating the Sum of Exponents",
                    prompt: "Calculate each sum: for m: 4 + 1 = 5; for q: 4 + 5 = 9; for z: -1 + 3 = 2:",
                    options: [
                        "m^5 q^9 z^2",
                        "m^4 q^20 z^-3",
                        "m^6 q^8 z^-1",
                        "m^20 q^12 z^-2"
                    ],
                    correct: 0
                },
                step3: {
                    tag: "Step 3: Selecting Equivalent Expression",
                    prompt: "Select the correct equivalent choice:",
                    options: [
                        "A) m^4 q^20 z^-3",
                        "B) m^5 q^9 z^2",
                        "C) m^6 q^8 z^-1",
                        "D) m^20 q^12 z^-2"
                    ],
                    correct: 1
                },
                rationale: "Add exponents for like variables: for m, 4 + 1 = 5; for q, 4 + 5 = 9; for z, -1 + 3 = 2. The simplified product is m^5 q^9 z^2 (Choice B)."
            },
            // Q12
            {
                id: 12,
                desmosLatex: 'y=9500-400x',
                title: "Card 12 (Question 12): Identifying Linear vs. Exponential Models",
                problem: "An airplane descends from an altitude of 9,500 feet to 5,000 feet at a constant rate of 400 feet per minute. What type of function best models the relationship between the descending airplane's altitude and time?",
                graphSVG: null,
                step1: {
                    tag: "Step 1: Constant Rate Interpretation",
                    prompt: "What type of function is defined by a 'constant rate of change per unit of time'?",
                    options: [
                        "Exponential function",
                        "Linear function",
                        "Quadratic function",
                        "Inverse variation"
                    ],
                    correct: 1
                },
                step2: {
                    tag: "Step 2: Determining Direction of Change",
                    prompt: "The airplane 'descends', meaning its altitude decreases as time advances:",
                    options: [
                        "Increasing relationship",
                        "Periodic relationship",
                        "Decreasing relationship",
                        "Constant relationship"
                    ],
                    correct: 2
                },
                step3: {
                    tag: "Step 3: Selecting Model Type",
                    prompt: "Combining a constant rate of change and decreasing altitude yields:",
                    options: [
                        "A) Decreasing exponential",
                        "B) Decreasing linear",
                        "C) Increasing exponential",
                        "D) Increasing linear"
                    ],
                    correct: 1
                },
                rationale: "A constant rate of change over equal intervals characterizes a linear model. Because the airplane descends (altitude decreases), it is a decreasing linear function (Choice B)."
            },
            // Q13
            {
                id: 13,
                desmosLatex: '3x+6=4y',
                title: "Card 13 (Question 13): System of Linear Equations Elimination",
                problem: "Consider the system of equations: 3x + 6 = 4y and 3x + 4 = 2y. The solution to the given system is (x, y). What is the value of y?",
                graphSVG: null,
                step1: {
                    tag: "Step 1: Elimination Strategy",
                    prompt: "Notice both equations have matching term 3x. Subtract the second equation from the first:",
                    options: [
                        "(3x + 6) - (3x + 4) = 4y - 2y",
                        "(3x + 6) + (3x + 4) = 4y + 2y",
                        "3x = 4y - 6",
                        "Multiply equations together"
                    ],
                    correct: 0
                },
                step2: {
                    tag: "Step 2: Solving for y",
                    prompt: "Simplify the difference: 2 = 2y ⇒ y = 2 / 2:",
                    options: [
                        "y = 2",
                        "y = 1",
                        "y = 0",
                        "y = -1"
                    ],
                    correct: 1
                },
                step3: {
                    tag: "Step 3: Final Value of y",
                    prompt: "State the value of y:",
                    options: [
                        "0",
                        "1",
                        "2",
                        "3"
                    ],
                    correct: 1
                },
                rationale: "Subtracting the second equation from the first cancels 3x: (3x + 6) - (3x + 4) = 4y - 2y ⇒ 2 = 2y ⇒ y = 1."
            },
            // Q14
            {
                id: 14,
                desmosLatex: 'g(0)=((0-6)*(0-2)*(0+6))+4',
                title: "Card 14 (Question 14): Vertical Translation of Polynomial Function",
                problem: "The function f is defined by f(x) = (x - 6)(x - 2)(x + 6). In the xy-plane, the graph of y = g(x) is the result of translating the graph of y = f(x) up 4 units. What is the value of g(0)?",
                graphSVG: null,
                step1: {
                    tag: "Step 1: Evaluate f(0)",
                    prompt: "Substitute x = 0 into f(x) = (0 - 6)(0 - 2)(0 + 6):",
                    options: [
                        "f(0) = (-6)(-2)(6) = 72",
                        "f(0) = -72",
                        "f(0) = 0",
                        "f(0) = 36"
                    ],
                    correct: 0
                },
                step2: {
                    tag: "Step 2: Apply Translation",
                    prompt: "Since g(x) = f(x) + 4, find g(0) = f(0) + 4:",
                    options: [
                        "g(0) = 72 + 4 = 76",
                        "g(0) = 72 - 4 = 68",
                        "g(0) = 72 × 4 = 288",
                        "g(0) = 4"
                    ],
                    correct: 0
                },
                step3: {
                    tag: "Step 3: Final Value",
                    prompt: "State the numerical value of g(0):",
                    options: [
                        "68",
                        "72",
                        "76",
                        "80"
                    ],
                    correct: 2
                },
                rationale: "f(0) = (0 - 6)(0 - 2)(0 + 6) = (-6)(-2)(6) = 72. Since g(x) translates f(x) up 4 units, g(0) = f(0) + 4 = 72 + 4 = 76."
            },
            // Q15
            {
                id: 15,
                desmosLatex: 'f(w)=6w^2',
                title: "Card 15 (Question 15): Interpreting Function Notation in Context",
                problem: "The function f(w) = 6w^2 gives the area of a rectangle, in square feet (ft^2), if its width is w ft and its length is 6 times its width. Which of the following is the best interpretation of f(14) = 1,176?",
                graphSVG: null,
                step1: {
                    tag: "Step 1: Identifying Input and Output Units",
                    prompt: "What does the input w and output f(w) represent in the problem?",
                    options: [
                        "w is length, f(w) is width",
                        "w is the width in feet, and f(w) is the total area in square feet",
                        "w is area, f(w) is perimeter",
                        "w is cost, f(w) is length"
                    ],
                    correct: 1
                },
                step2: {
                    tag: "Step 2: Interpreting Values 14 and 1,176",
                    prompt: "In f(14) = 1,176, w = 14 and f(w) = 1,176:",
                    options: [
                        "Width is 14 ft, area is 1,176 ft^2",
                        "Length is 14 ft, width is 1,176 ft",
                        "Area is 14 ft^2, width is 1,176 ft",
                        "Width is 1,176 ft, length is 14 ft"
                    ],
                    correct: 0
                },
                step3: {
                    tag: "Step 3: Matching Official Option",
                    prompt: "Select the best interpretation statement:",
                    options: [
                        "A) If the width of the rectangle is 14 ft, then the area of the rectangle is 1,176 ft^2.",
                        "B) If the width of the rectangle is 14 ft, then the length of the rectangle is 1,176 ft.",
                        "C) If the width of the rectangle is 1,176 ft, then the length of the rectangle is 14 ft.",
                        "D) If the width of the rectangle is 1,176 ft, then the area of the rectangle is 14 ft^2."
                    ],
                    correct: 0
                },
                rationale: "The input variable w represents the width of the rectangle in feet, and f(w) represents the area in square feet. Thus, f(14) = 1,176 means that if the width is 14 ft, the area is 1,176 ft^2 (Choice A)."
            },
            // Q16
            {
                id: 16,
                desmosLatex: 'y=44000*(2)^t',
                title: "Card 16 (Question 16): Exponential Doubling Growth Model",
                problem: "The number of bacteria in a liquid medium doubles every day. There are 44,000 bacteria in the liquid medium at the start of an observation. Which of the following represents the number of bacteria, y, in the liquid medium t days after the start?",
                graphSVG: null,
                step1: {
                    tag: "Step 1: Exponential Growth Formula",
                    prompt: "Recall the standard exponential growth formula y = a · b^t:",
                    options: [
                        "a is growth rate, b is initial value",
                        "a is initial value (44,000) and b is growth factor per day (doubling means b = 2)",
                        "b must be 1/2",
                        "y is linear"
                    ],
                    correct: 1
                },
                step2: {
                    tag: "Step 2: Assembling Model",
                    prompt: "Substitute a = 44,000 and b = 2 into y = a · b^t:",
                    options: [
                        "y = 44,000(2)^t",
                        "y = 2(44,000)^t",
                        "y = 44,000(1/2)^t",
                        "y = 1/2(44,000)^t"
                    ],
                    correct: 0
                },
                step3: {
                    tag: "Step 3: Selecting Correct Choice",
                    prompt: "Select the equation matching the model:",
                    options: [
                        "A) y = 1/2(44,000)^t",
                        "B) y = 2(44,000)^t",
                        "C) y = 44,000(1/2)^t",
                        "D) y = 44,000(2)^t"
                    ],
                    correct: 3
                },
                rationale: "The initial quantity is 44,000, and it doubles (multiplies by 2) each day t. Therefore, the function is y = 44,000(2)^t (Choice D)."
            },
            // Q17
            {
                id: 17,
                desmosLatex: 'h(x)=1.23*(1.12)^x',
                title: "Card 17 (Question 17): Exponential Model from Data Table",
                problem: "The table shows the exponential relationship between years x and pole vault height h(x): (0, 1.23), (2, 1.54), (4, 1.94). Which function best represents this relationship?",
                graphSVG: null,
                step1: {
                    tag: "Step 1: Determine Initial Value h(0)",
                    prompt: "From the table, at x = 0, h(0) = 1.23. In h(x) = a · b^x, what is a?",
                    options: [
                        "a = 1.12",
                        "a = 1.23",
                        "a = 0.23",
                        "a = 1.54"
                    ],
                    correct: 1
                },
                step2: {
                    tag: "Step 2: Test Growth Factor b",
                    prompt: "Since h(x) increases as x increases (1.23 to 1.54 to 1.94), the base b must be greater than 1:",
                    options: [
                        "b = 0.12 (decreasing)",
                        "b = 0.23 (decreasing)",
                        "b = 1.12 (increasing, 1.23 × 1.12^2 ≈ 1.54)",
                        "b = 1.23"
                    ],
                    correct: 2
                },
                step3: {
                    tag: "Step 3: Concluding Function",
                    prompt: "Select the best model:",
                    options: [
                        "A) h(x) = 1.12(0.23)^x",
                        "B) h(x) = 1.12(1.23)^x",
                        "C) h(x) = 1.23(0.12)^x",
                        "D) h(x) = 1.23(1.12)^x"
                    ],
                    correct: 3
                },
                rationale: "When x = 0, h(0) = a = 1.23. The height increases over time, so the base must be greater than 1. Testing b = 1.12: h(2) = 1.23(1.12)^2 ≈ 1.54, which fits the data. Choice D is correct."
            },
            // Q18
            {
                id: 18,
                desmosLatex: 'h(x)=4x+28',
                title: "Card 18 (Question 18): Sum of Intercepts of a Linear Function",
                problem: "The function h is defined by h(x) = 4x + 28. Its graph has an x-intercept at (a, 0) and a y-intercept at (0, b). What is the value of a + b?",
                graphSVG: null,
                step1: {
                    tag: "Step 1: Finding x-Intercept (a, 0)",
                    prompt: "Set h(x) = 0 and solve for x: 0 = 4x + 28:",
                    options: [
                        "4x = -28 ⇒ a = -7",
                        "4x = 28 ⇒ a = 7",
                        "a = 28",
                        "a = 0"
                    ],
                    correct: 0
                },
                step2: {
                    tag: "Step 2: Finding y-Intercept (0, b)",
                    prompt: "Evaluate h(0): h(0) = 4(0) + 28 = b:",
                    options: [
                        "b = 4",
                        "b = -28",
                        "b = 28",
                        "b = 7"
                    ],
                    correct: 2
                },
                step3: {
                    tag: "Step 3: Calculating a + b",
                    prompt: "Compute a + b = -7 + 28 = [ _____ ]:",
                    options: [
                        "A) 21",
                        "B) 28",
                        "C) 32",
                        "D) 35"
                    ],
                    correct: 0
                },
                rationale: "The x-intercept occurs where y = 0: 4x + 28 = 0 ⇒ x = -7, so a = -7. The y-intercept occurs where x = 0: b = 28. Then a + b = -7 + 28 = 21 (Choice A)."
            },
            // Q19
            {
                id: 19,
                desmosLatex: 'y<5x+6',
                title: "Card 19 (Question 19): Checking Solutions to a Linear Inequality",
                problem: "For which of the following tables are all the values of x and their corresponding values of y solutions to the inequality y < 5x + 6?",
                graphSVG: null,
                step1: {
                    tag: "Step 1: Compute Boundary 5x + 6 for x = 3, 5, 7",
                    prompt: "Evaluate boundary line 5x + 6 at the three given x-values:",
                    options: [
                        "At x=3: 21; At x=5: 31; At x=7: 41",
                        "At x=3: 15; At x=5: 25; At x=7: 35",
                        "At x=3: 20; At x=5: 30; At x=7: 40",
                        "At x=3: 18; At x=5: 28; At x=7: 38"
                    ],
                    correct: 0
                },
                step2: {
                    tag: "Step 2: Test Table A Against the Strict Inequality",
                    prompt: "Check Table A points (3, 17), (5, 27), (7, 37) against y < 5x + 6:",
                    options: [
                        "17 < 21 (True), 27 < 31 (True), 37 < 41 (True)",
                        "17 < 21 (True), but 27 > 31 (False)",
                        "None are less",
                        "Only the first point works"
                    ],
                    correct: 0
                },
                step3: {
                    tag: "Step 3: Concluding Valid Table",
                    prompt: "Select the table where all pairs satisfy y < 5x + 6:",
                    options: [
                        "A) Table with (3, 17), (5, 27), (7, 37)",
                        "B) Table with (3, 17), (5, 35), (7, 37)",
                        "C) Table with (3, 25), (5, 35), (7, 45)",
                        "D) Table with (3, 21), (5, 31), (7, 41)"
                    ],
                    correct: 0
                },
                rationale: "For Table A: at x = 3, y = 17 < 5(3)+6 = 21; at x = 5, y = 27 < 5(5)+6 = 31; at x = 7, y = 37 < 5(7)+6 = 41. All three pairs satisfy the strict inequality. Choice A is correct."
            },
            // Q20
            {
                id: 20,
                desmosLatex: 'y=4x+1',
                title: "Card 20 (Question 20): Linear System Value of x - y",
                problem: "Consider the system of equations y = 4x + 1 and 4y = 15x - 8. The solution is (x, y). What is the value of x - y?",
                graphSVG: null,
                step1: {
                    tag: "Step 1: Substitution Strategy",
                    prompt: "Substitute y = 4x + 1 into the second equation 4y = 15x - 8:",
                    options: [
                        "4(4x + 1) = 15x - 8 ⇒ 16x + 4 = 15x - 8",
                        "4x + 1 = 15x - 8",
                        "4(4x) = 15x - 8",
                        "16x + 1 = 15x - 8"
                    ],
                    correct: 0
                },
                step2: {
                    tag: "Step 2: Solve for x and y",
                    prompt: "16x - 15x = -8 - 4 ⇒ x = -12. Find y = 4(-12) + 1:",
                    options: [
                        "y = -48",
                        "y = -47",
                        "y = 47",
                        "y = -49"
                    ],
                    correct: 1
                },
                step3: {
                    tag: "Step 3: Compute x - y",
                    prompt: "Calculate x - y = -12 - (-47) = -12 + 47 = [ _____ ]:",
                    options: [
                        "-59",
                        "35",
                        "59",
                        "-35"
                    ],
                    correct: 1
                },
                rationale: "Substitute y = 4x + 1 into 4y = 15x - 8: 16x + 4 = 15x - 8 ⇒ x = -12. Then y = 4(-12) + 1 = -47. Finally, x - y = -12 - (-47) = 35."
            },
            // Q21
            {
                id: 21,
                desmosLatex: 'c=\\sqrt{24^2+21^2}',
                title: "Card 21 (Question 21): Pythagorean Theorem & Radical Simplification",
                problem: "A right triangle has legs with lengths of 24 cm and 21 cm. If the length of its hypotenuse can be written in the form 3√d where d is an integer, what is the value of d?",
                graphSVG: null,
                step1: {
                    tag: "Step 1: Compute Hypotenuse via c^2 = a^2 + b^2",
                    prompt: "Square both legs and add: 24^2 + 21^2 = 576 + 441:",
                    options: [
                        "c^2 = 1017",
                        "c^2 = 1000",
                        "c^2 = 945",
                        "c^2 = 45"
                    ],
                    correct: 0
                },
                step2: {
                    tag: "Step 2: Factor Out Square of 3",
                    prompt: "Since the hypotenuse is 3√d, factor 9 (which is 3^2) out of 1017: 1017 / 9:",
                    options: [
                        "1017 / 9 = 113",
                        "1017 / 9 = 117",
                        "1017 / 9 = 103",
                        "1017 / 9 = 123"
                    ],
                    correct: 0
                },
                step3: {
                    tag: "Step 3: Stating d",
                    prompt: "Since c = √(9 × 113) = 3√113, what is the integer d?",
                    options: [
                        "9",
                        "1017",
                        "113",
                        "339"
                    ],
                    correct: 2
                },
                rationale: "Hypotenuse c = √(24^2 + 21^2) = √(576 + 441) = √1017 = √(9 × 113) = 3√113. Thus, d = 113."
            },
            // Q22
            {
                id: 22,
                desmosLatex: 'A=600*(1/10)^2',
                title: "Card 22 (Question 22): Scaling Area of a Ballroom",
                problem: "The floor of a ballroom has an area of 600 square meters. An architect creates a scale model where each side is 1/10 times the actual side length. What is the area, in square meters, of the scale model?",
                graphSVG: null,
                step1: {
                    tag: "Step 1: Area Scale Factor Rule",
                    prompt: "When linear dimensions scale by factor k, area scales by k^2:",
                    options: [
                        "k^2 = (1/10)^2 = 1/100",
                        "k^2 = 1/10",
                        "k^2 = 1/20",
                        "k^2 = 2/10"
                    ],
                    correct: 0
                },
                step2: {
                    tag: "Step 2: Compute Scaled Area",
                    prompt: "Multiply actual area 600 m^2 by 1/100: 600 × 1/100:",
                    options: [
                        "60 m^2",
                        "6 m^2",
                        "10 m^2",
                        "150 m^2"
                    ],
                    correct: 1
                },
                step3: {
                    tag: "Step 3: Select Correct Answer",
                    prompt: "Select the correct area choice:",
                    options: [
                        "A) 6",
                        "B) 10",
                        "C) 60",
                        "D) 150"
                    ],
                    correct: 0
                },
                rationale: "The area scales with the square of the linear scale factor: (1/10)^2 = 1/100. Scaled area = 600 × 1/100 = 6 m^2 (Choice A)."
            },
            // Q23
            {
                id: 23,
                desmosLatex: '(x-4)^2+(y-9)^2=16',
                title: "Card 23 (Question 23): Circle Tangent to the y-Axis",
                problem: "Which of the following equations represents a circle in the xy-plane that intersects the y-axis at exactly one point?",
                graphSVG: null,
                step1: {
                    tag: "Step 1: Tangency Condition to y-Axis",
                    prompt: "A circle (x - h)^2 + (y - k)^2 = r^2 intersects the y-axis at exactly one point if and only if:",
                    options: [
                        "|k| = r",
                        "|h| = r (the horizontal distance from center to y-axis equals radius)",
                        "h = 0 and k = 0",
                        "r = 0"
                    ],
                    correct: 1
                },
                step2: {
                    tag: "Step 2: Analyzing Choice C: (x - 4)^2 + (y - 9)^2 = 16",
                    prompt: "Identify the center (h, k) and radius r of (x - 4)^2 + (y - 9)^2 = 16:",
                    options: [
                        "Center is (4, 9) and radius r = √16 = 4. Since |h| = 4 = r, it is tangent to the y-axis!",
                        "Center is (-4, -9) and radius is 16",
                        "Center is (9, 4) and radius is 4",
                        "Radius is 8"
                    ],
                    correct: 0
                },
                step3: {
                    tag: "Step 3: Select Choice",
                    prompt: "Select the correct circle equation:",
                    options: [
                        "A) (x - 8)^2 + (y - 8)^2 = 16",
                        "B) (x - 8)^2 + (y - 4)^2 = 16",
                        "C) (x - 4)^2 + (y - 9)^2 = 16",
                        "D) x^2 + (y - 9)^2 = 16"
                    ],
                    correct: 2
                },
                rationale: "For a circle to intersect the y-axis at exactly one point, the distance from its center (h, k) to the line x = 0 must equal the radius r (|h| = r). In (x - 4)^2 + (y - 9)^2 = 16, h = 4 and r = 4, so |4| = 4. Choice C is correct."
            },
            // Q24
            {
                id: 24,
                desmosLatex: 'x=27',
                title: "Card 24 (Question 24): Triangle Congruence Criteria",
                problem: "In triangles ABC and DEF, angles B and E each measure 27°, and angles C and F each measure 41°. Which additional piece of information is sufficient to determine whether triangle ABC is congruent to triangle DEF?",
                graphSVG: null,
                step1: {
                    tag: "Step 1: Current State of Similarity",
                    prompt: "Two pairs of equal angles (AA) establishes that triangles are similar, but similarity alone does NOT guarantee congruence:",
                    options: [
                        "We need the measure of the third angle.",
                        "We need at least one pair of corresponding side lengths to establish scale.",
                        "No additional information is ever needed.",
                        "Triangles are automatically congruent."
                    ],
                    correct: 1
                },
                step2: {
                    tag: "Step 2: Checking Options",
                    prompt: "Evaluate Choice C (lengths of sides BC and EF):",
                    options: [
                        "Side BC connects angles B and C; side EF connects corresponding angles E and F. Equal lengths would prove congruence by ASA!",
                        "Angle A only gives AAA which is still only similarity.",
                        "Side AB does not specify side DE.",
                        "Choice C is insufficient."
                    ],
                    correct: 0
                },
                step3: {
                    tag: "Step 3: Selecting Correct Answer",
                    prompt: "Which additional piece of information is sufficient?",
                    options: [
                        "A) The measure of angle A",
                        "B) The length of side AB",
                        "C) The lengths of sides BC and EF",
                        "D) No additional information is necessary."
                    ],
                    correct: 2
                },
                rationale: "Knowing two angles proves similarity. To prove congruence, we need corresponding side lengths. Sides BC and EF are both between the 27° and 41° angles. Knowing both allows us to verify congruence via ASA. Choice C is correct."
            },
            // Q25
            {
                id: 25,
                desmosLatex: '19*x=684',
                title: "Card 25 (Question 25): Solving Percent Increase Backwards",
                problem: "The result of increasing the quantity x by 1,800% is 684. What is the value of x?",
                graphSVG: null,
                step1: {
                    tag: "Step 1: Formulating 1,800% Increase",
                    prompt: "Increasing x by 1,800% means adding (1800/100)x = 18x to original quantity x:",
                    options: [
                        "x + 18x = 19x",
                        "18x = 684",
                        "1.8x = 684",
                        "x + 1.8x = 2.8x"
                    ],
                    correct: 0
                },
                step2: {
                    tag: "Step 2: Solving 19x = 684",
                    prompt: "Divide 684 by 19:",
                    options: [
                        "684 / 19 = 36",
                        "684 / 19 = 38",
                        "684 / 18 = 38",
                        "684 / 19 = 42"
                    ],
                    correct: 0
                },
                step3: {
                    tag: "Step 3: Selecting the Correct Value of x",
                    prompt: "Select the correct value of x:",
                    options: [
                        "A) 12,996",
                        "B) 12,312",
                        "C) 38",
                        "D) 36"
                    ],
                    correct: 3
                },
                rationale: "An increase of 1,800% results in x + 18x = 19x. We are given 19x = 684 ⇒ x = 684 / 19 = 36 (Choice D)."
            },
            // Q26
            {
                id: 26,
                desmosLatex: 'f(x)=60x+100',
                title: "Card 26 (Question 26): Piecewise Linear Repair Cost Function",
                problem: "A window repair specialist charges $220 for the first 2 hours plus an hourly fee for each additional hour. The total cost for 5 hours of repair is $400. Which function f gives the total cost, in dollars, for x hours of repair, where x ≥ 2?",
                graphSVG: null,
                step1: {
                    tag: "Step 1: Calculate Additional Hourly Rate",
                    prompt: "For 5 hours, there are 5 - 2 = 3 additional hours. Additional cost = $400 - $220 = $180. Find hourly rate:",
                    options: [
                        "Hourly rate = $180 / 3 = $60 per hour",
                        "Hourly rate = $400 / 5 = $80 per hour",
                        "Hourly rate = $220 / 2 = $110 per hour",
                        "Hourly rate = $50 per hour"
                    ],
                    correct: 0
                },
                step2: {
                    tag: "Step 2: Model for x ≥ 2",
                    prompt: "Express total cost as base fee $220 plus $60 for each hour beyond 2 (x - 2): f(x) = 220 + 60(x - 2):",
                    options: [
                        "f(x) = 220 + 60x - 120 = 60x + 100",
                        "f(x) = 60x + 220",
                        "f(x) = 80x",
                        "f(x) = 80x + 220"
                    ],
                    correct: 0
                },
                step3: {
                    tag: "Step 3: Selecting Correct Choice",
                    prompt: "Select the matching function choice:",
                    options: [
                        "A) f(x) = 60x + 100",
                        "B) f(x) = 60x + 220",
                        "C) f(x) = 80x",
                        "D) f(x) = 80x + 220"
                    ],
                    correct: 0
                },
                rationale: "The cost for 3 additional hours is 400 - 220 = $180, so the additional rate is 180 / 3 = $60/hr. For x ≥ 2, f(x) = 220 + 60(x - 2) = 60x + 100 (Choice A)."
            },
            // Q27
            {
                id: 27,
                desmosLatex: '3x^2-29x+56=0',
                title: "Card 27 (Question 27): Sum of Solutions to a Quadratic Equation",
                problem: "x(x + 1) - 56 = 4x(x - 7). What is the sum of the solutions to the given equation?",
                graphSVG: null,
                step1: {
                    tag: "Step 1: Expand Both Sides",
                    prompt: "Expand: x^2 + x - 56 = 4x^2 - 28x:",
                    options: [
                        "x^2 + x - 56 = 4x^2 - 28x",
                        "x^2 + 1 - 56 = 4x^2 - 7",
                        "2x - 56 = 4x^2 - 28x",
                        "x^2 - 56 = 4x^2 - 28x"
                    ],
                    correct: 0
                },
                step2: {
                    tag: "Step 2: Collect into Standard Form ax^2 + bx + c = 0",
                    prompt: "Subtract (x^2 + x - 56) from both sides: 3x^2 - 29x + 56 = 0:",
                    options: [
                        "3x^2 - 29x + 56 = 0",
                        "3x^2 - 27x + 56 = 0",
                        "5x^2 - 29x - 56 = 0",
                        "3x^2 - 29x - 56 = 0"
                    ],
                    correct: 0
                },
                step3: {
                    tag: "Step 3: Sum of Roots via Vieta's Formula (-b / a)",
                    prompt: "For ax^2 + bx + c = 0, sum of roots = -b / a = -(-29) / 3 = [ _____ ]:",
                    options: [
                        "29/3 (approx 9.67)",
                        "-29/3",
                        "56/3",
                        "29"
                    ],
                    correct: 0
                },
                rationale: "Expanding gives x^2 + x - 56 = 4x^2 - 28x ⇒ 3x^2 - 29x + 56 = 0. By Vieta's formulas, the sum of the roots is -b/a = -(-29)/3 = 29/3."
            }
        ];

        let currentUser = null;
        let currentPointer = 0;
        let userState = { answers: {}, status: {}, cardSteps: {} };
        let desmosCalc = null;

        function initDesmos() {
            const elt = document.getElementById('desmos-calculator');
            if (elt && !desmosCalc && window.Desmos) {
                desmosCalc = Desmos.GraphingCalculator(elt, {
                    expressions: true,
                    keypad: false,
                    settingsMenu: false
                });
            }
            updateDesmosView();
        }

        function updateDesmosView() {
            if (!desmosCalc) return;
            const q = questionsData[currentPointer];
            if (q && q.desmosLatex) {
                desmosCalc.setBlank();
                desmosCalc.setExpression({ id: 'fn', latex: q.desmosLatex });
            }
        }

        function calcInput(val) {
            const d = document.getElementById('calc-disp');
            if (d.value === '0' || d.value === 'Error') d.value = val;
            else d.value += val;
        }

        function calcClear() {
            document.getElementById('calc-disp').value = '0';
        }

        function calcEval() {
            const d = document.getElementById('calc-disp');
            try {
                d.value = eval(d.value);
            } catch(e) {
                d.value = 'Error';
            }
        }

        function calcSqrt() {
            const d = document.getElementById('calc-disp');
            try {
                const val = parseFloat(d.value) || 0;
                d.value = Number(Math.sqrt(val).toFixed(4));
            } catch(e) {
                d.value = 'Error';
            }
        }

        function handleLogin(e) {
            e.preventDefault();
            const email = document.getElementById('email-input').value.trim();
            if (email) {
                currentUser = email;
                localStorage.setItem('bm_sat10_m1_email', email);
                initSession();
            }
        }

        function initSession() {
            document.getElementById('display-user-email').innerText = currentUser;
            document.getElementById('user-header-info').style.display = 'flex';

            const savedData = localStorage.getItem(`${currentUser}_${CHAPTER_KEY}`);
            if (savedData) {
                userState = JSON.parse(savedData);
            } else {
                userState = { answers: {}, status: {}, cardSteps: {} };
            }

            switchScreen('quiz-screen');
            currentPointer = 0;
            renderGrid();
            loadCardByPointer(currentPointer);
            setTimeout(initDesmos, 300);
        }

        function logout() {
            localStorage.removeItem('bm_sat10_m1_email');
            currentUser = null;
            document.getElementById('user-header-info').style.display = 'none';
            switchScreen('auth-screen');
        }

        function saveState() {
            if (currentUser) {
                localStorage.setItem(`${currentUser}_${CHAPTER_KEY}`, JSON.stringify(userState));
            }
        }

        function switchScreen(id) {
            document.querySelectorAll('.screen').forEach(s => s.classList.remove('active'));
            document.getElementById(id).classList.add('active');
        }

        function renderGrid() {
            const grid = document.getElementById('question-grid');
            grid.innerHTML = '';
            questionsData.forEach((q, idx) => {
                const btn = document.createElement('button');
                btn.className = 'grid-btn';
                btn.innerText = idx + 1;

                if (idx === currentPointer) btn.classList.add('active');
                if (userState.status[idx] === 'submitted') btn.classList.add('attempted');
                if (userState.status[idx] === 'skipped') btn.classList.add('skipped');

                btn.onclick = () => {
                    currentPointer = idx;
                    loadCardByPointer(currentPointer);
                };
                grid.appendChild(btn);
            });
        }

        function loadCardByPointer(ptr) {
            currentPointer = ptr;
            const q = questionsData[currentPointer];

            document.getElementById('q-number-badge').innerText = `Card ${ptr + 1} of ${questionsData.length}`;
            document.getElementById('q-title-text').innerHTML = q.title;
            document.getElementById('q-problem-text').innerHTML = q.problem;

            const graphContainer = document.getElementById('q-graph-container');
            if (q.graphSVG) {
                graphContainer.innerHTML = q.graphSVG;
                graphContainer.style.display = 'flex';
            } else {
                graphContainer.style.display = 'none';
                graphContainer.innerHTML = '';
            }

            if (!userState.cardSteps[ptr]) {
                userState.cardSteps[ptr] = {
                    s1Selection: null, s1Status: 'unattempted',
                    s2Selection: null, s2Status: 'unattempted',
                    s3Selection: null, s3Status: 'unattempted'
                };
            }

            const cState = userState.cardSteps[ptr];

            renderStepUI(1, q.step1, cState.s1Selection, cState.s1Status, true);
            const isStep1Passed = cState.s1Status === 'correct' || cState.s1Status === 'skipped';
            renderStepUI(2, q.step2, cState.s2Selection, cState.s2Status, isStep1Passed);
            const isStep2Passed = cState.s2Status === 'correct' || cState.s2Status === 'skipped';
            renderStepUI(3, q.step3, cState.s3Selection, cState.s3Status, isStep2Passed);

            const isCardFinished = userState.status[ptr] === 'submitted' || userState.status[ptr] === 'skipped';
            const ratBox = document.getElementById('rationale-container');

            if (isCardFinished) {
                ratBox.style.display = 'block';
                document.getElementById('rationale-text').innerHTML = q.rationale;
                document.getElementById('skip-card-btn').style.display = 'none';
                document.getElementById('next-btn').style.display = 'inline-flex';
            } else {
                ratBox.style.display = 'none';
                document.getElementById('skip-card-btn').style.display = 'inline-flex';
                document.getElementById('next-btn').style.display = 'none';
            }

            updateDesmosView();
            renderGrid();
        }

        function renderStepUI(stepNum, stepData, currentSelection, currentStatus, isUnlocked) {
            const block = document.getElementById(`step${stepNum}-block`);
            const container = document.getElementById(`step${stepNum}-options-container`);
            const tag = document.getElementById(`step${stepNum}-status-tag`);
            const prompt = document.getElementById(`step${stepNum}-prompt`);
            const tagLabel = document.getElementById(`step${stepNum}-tag`);
            const actions = document.getElementById(`step${stepNum}-actions`);
            
            container.innerHTML = '';
            tagLabel.innerText = stepData.tag;
            prompt.innerHTML = stepData.prompt;

            if (!isUnlocked) {
                block.className = 'step-block locked';
                tag.innerText = 'Locked';
                tag.style.color = 'var(--text-muted)';
                actions.style.display = 'none';
                return;
            }

            if (currentStatus === 'correct') {
                block.className = 'step-block completed-step';
                tag.innerText = '✓ Correct';
                tag.style.color = 'var(--correct-green)';
                actions.style.display = 'none';
            } else if (currentStatus === 'skipped') {
                block.className = 'step-block skipped-step';
                tag.innerText = 'Skipped';
                tag.style.color = 'var(--skipped-orange)';
                actions.style.display = 'none';
            } else {
                block.className = 'step-block active-step';
                tag.innerText = 'In Progress';
                tag.style.color = 'var(--accent-gold)';
                actions.style.display = 'flex';
            }

            stepData.options.forEach((optText, idx) => {
                const item = document.createElement('div');
                item.className = 'step-option-item';

                if (currentSelection === idx) item.classList.add('selected');

                if (currentStatus === 'correct' || currentStatus === 'skipped') {
                    item.classList.add('disabled');
                    if (idx === stepData.correct) item.classList.add('correct');
                    else if (currentSelection === idx) item.classList.add('incorrect');
                } else if (currentStatus === 'incorrect' && currentSelection === idx) {
                    item.classList.add('incorrect');
                    item.onclick = () => selectStepOption(stepNum, idx);
                } else {
                    item.onclick = () => selectStepOption(stepNum, idx);
                }

                item.innerHTML = `<div class="step-opt-prefix">${String.fromCharCode(65 + idx)}</div><div>${optText}</div>`;
                container.appendChild(item);
            });
        }

        function selectStepOption(stepNum, idx) {
            const cState = userState.cardSteps[currentPointer];
            if (stepNum === 1) {
                if (cState.s1Status === 'correct' || cState.s1Status === 'skipped') return;
                cState.s1Selection = idx;
                cState.s1Status = 'unattempted';
            } else if (stepNum === 2) {
                if (cState.s2Status === 'correct' || cState.s2Status === 'skipped') return;
                cState.s2Selection = idx;
                cState.s2Status = 'unattempted';
            } else if (stepNum === 3) {
                if (cState.s3Status === 'correct' || cState.s3Status === 'skipped') return;
                cState.s3Selection = idx;
                cState.s3Status = 'unattempted';
            }
            saveState();
            loadCardByPointer(currentPointer);
        }

        function checkStep(stepNum) {
            const q = questionsData[currentPointer];
            const cState = userState.cardSteps[currentPointer];

            if (stepNum === 1) {
                if (cState.s1Selection === null) {
                    alert("Please choose an answer for Step 1 first!");
                    return;
                }
                if (cState.s1Selection === q.step1.correct) {
                    cState.s1Status = 'correct';
                    AudioFX.playCorrectBell();
                } else {
                    cState.s1Status = 'incorrect';
                    AudioFX.playIncorrectBell();
                }
            } else if (stepNum === 2) {
                if (cState.s2Selection === null) {
                    alert("Please choose an answer for Step 2 first!");
                    return;
                }
                if (cState.s2Selection === q.step2.correct) {
                    cState.s2Status = 'correct';
                    AudioFX.playCorrectBell();
                } else {
                    cState.s2Status = 'incorrect';
                    AudioFX.playIncorrectBell();
                }
            } else if (stepNum === 3) {
                if (cState.s3Selection === null) {
                    alert("Please choose an answer for Step 3 first!");
                    return;
                }
                if (cState.s3Selection === q.step3.correct) {
                    cState.s3Status = 'correct';
                    userState.status[currentPointer] = 'submitted';
                    userState.answers[currentPointer] = cState.s3Selection;
                    AudioFX.playCorrectBell();
                } else {
                    cState.s3Status = 'incorrect';
                    AudioFX.playIncorrectBell();
                }
            }
            saveState();
            loadCardByPointer(currentPointer);
        }

        function skipStep(stepNum) {
            const cState = userState.cardSteps[currentPointer];
            if (stepNum === 1) {
                cState.s1Status = 'skipped';
                AudioFX.playSkipChime();
            } else if (stepNum === 2) {
                cState.s2Status = 'skipped';
                AudioFX.playSkipChime();
            } else if (stepNum === 3) {
                cState.s3Status = 'skipped';
                userState.status[currentPointer] = 'submitted';
                AudioFX.playSkipChime();
            }
            saveState();
            loadCardByPointer(currentPointer);
        }

        function skipEntireCard() {
            const cState = userState.cardSteps[currentPointer];
            cState.s1Status = 'skipped';
            cState.s2Status = 'skipped';
            cState.s3Status = 'skipped';
            userState.status[currentPointer] = 'skipped';
            saveState();
            AudioFX.playSkipChime();
            nextQuestion();
        }

        function nextQuestion() {
            if (currentPointer < questionsData.length - 1) {
                loadCardByPointer(currentPointer + 1);
            } else {
                finishTest();
            }
        }

        function finishTest() {
            switchScreen('review-screen');
            let score = 0;
            const reviewList = document.getElementById('review-list');
            reviewList.innerHTML = '';

            questionsData.forEach((q, idx) => {
                const status = userState.status[idx];
                const cState = userState.cardSteps[idx] || {};
                const isFullyCorrect = cState.s1Status === 'correct' && cState.s2Status === 'correct' && cState.s3Status === 'correct';

                if (isFullyCorrect) score++;

                const card = document.createElement('div');
                card.className = 'review-card';

                let tagHtml = '<span class="status-tag tag-skipped">Skipped</span>';
                if (status === 'submitted') {
                    tagHtml = isFullyCorrect 
                        ? '<span class="status-tag tag-correct">Fully Correct</span>' 
                        : '<span class="status-tag tag-incorrect">Completed with Help</span>';
                }

                const s3Answer = cState.s3Selection !== null ? q.step3.options[cState.s3Selection] : 'None';
                const s3Correct = q.step3.options[q.step3.correct];

                card.innerHTML = `
                    <div style="display:flex; justify-content:space-between; margin-bottom:0.5rem;">
                        <strong>${q.title}</strong>
                        ${tagHtml}
                    </div>
                    <p style="font-size:0.9rem; margin-bottom:0.5rem;">${q.problem}</p>
                    <p style="font-size:0.9rem; color:var(--text-muted);">
                        <strong>Your Step 3 Answer:</strong> ${s3Answer} | 
                        <strong>Correct Answer:</strong> ${s3Correct}
                    </p>
                    <div style="margin-top:0.5rem; font-size:0.85rem; background:#f8fafc; padding:0.5rem; border-radius:4px;">
                        <strong>Solution:</strong> ${q.rationale}
                    </div>
                `;
                reviewList.appendChild(card);
            });

            document.getElementById('final-score').innerText = `${score} / ${questionsData.length}`;
        }

        function restartQuiz() {
            userState = { answers: {}, status: {}, cardSteps: {} };
            saveState();
            currentPointer = 0;
            switchScreen('quiz-screen');
            loadCardByPointer(0);
        }

        window.onload = function() {
            const savedUser = localStorage.getItem('bm_sat10_m1_email');
            if (savedUser) {
                currentUser = savedUser;
                initSession();
            }
        };
    </script>
</body>
</html>
