<!DOCTYPE html>
<html>
<head>
    <title>终极版动词抽选器</title>
    <style>
        body {
            margin: 0;
            padding: 20px;
            background: #f0f7ff;
            font-family: "微软雅黑", sans-serif;
            height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        h1 {
            color: #2c3e50;
            text-align: center;
            margin: 30px 0;
            font-size: 2.5em;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.1);
        }

        #wordDisplay {
            flex: 1;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 5em;
            color: #34495e;
            transition: all 0.1s;
            max-width: 90%;
            text-align: center;
            min-height: 200px;
        }

        .highlight {
            color: #ff4757 !important;
            font-weight: 900;
            transform: scale(1.1);
            text-shadow: 3px 3px 6px rgba(0,0,0,0.2);
        }

        .controls {
            position: fixed;
            bottom: 10vh;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            gap: 30px;
            align-items: center;
            background: white;
            padding: 20px 40px;
            border-radius: 50px;
            box-shadow: 0 8px 20px rgba(0,0,0,0.15);
            border: 2px solid #3498db;
        }

        button {
            padding: 18px 45px;
            font-size: 1.5em;
            background: #3498db;
            color: white;
            border: none;
            border-radius: 35px;
            cursor: pointer;
            transition: 0.3s;
            min-width: 150px;
            position: relative;
            overflow: hidden;
        }

        button:hover {
            background: #2980b9;
            transform: scale(1.05);
            box-shadow: 0 6px 12px rgba(52,152,219,0.3);
        }

        button::after {
            content: "";
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: rgba(255,255,255,0.1);
            transform: rotate(45deg);
            transition: 0.5s;
        }

        .speed-container {
            display: flex;
            align-items: center;
            gap: 15px;
            font-size: 1.2em;
        }

        input[type="range"] {
            width: 200px;
            height: 12px;
            background: #dfe6e9;
            border-radius: 10px;
            -webkit-appearance: none;
        }

        input[type="range"]::-webkit-slider-thumb {
            -webkit-appearance: none;
            width: 25px;
            height: 25px;
            background: #3498db;
            border-radius: 50%;
            box-shadow: 0 2px 6px rgba(0,0,0,0.2);
            transition: 0.2s;
        }

        input[type="range"]::-webkit-slider-thumb:hover {
            transform: scale(1.1);
            background: #2980b9;
        }
    </style>
</head>
<body>
    <h1>🔠 动词速记抽选器 🔠</h1>
    <div id="wordDisplay">单击开始享受学习 →</div>
    
    <div class="controls">
        <div class="speed-container">
            <span style="font-size:1.4em">🐢</span>
            <input type="range" id="speedControl" min="50" max="200" value="100">
            <span style="font-size:1.4em">🐇</span>
        </div>
        <button id="startBtn">🎮 开始滚动</button>
    </div>

    <script>
        const words = [
            'sit', 'open', 'count', 'know', 'touch', 'guess', 'dance',
            'watch', 'chug', 'beep', 'come', 'eat', 'wish', 'snow',
            'smile', 'write', 'draw', 'colour', 'tidy', 'do', 'call',
            'hide', 'talk', 'seek', 'skip', 'clap', 'catch', 'turn', 
            'back', 'want', 'thank', 'stand', 'watches', 'ride', 
            'ski', 'rain', 'listen'
        ];

        let intervalId = null;
        const speedControl = document.getElementById('speedControl');
        const startBtn = document.getElementById('startBtn');
        const wordDisplay = document.getElementById('wordDisplay');

        // 优化速度计算算法
        const speedMapper = (value) => Math.pow(200 - value, 1.5) + 50;

        function startRolling() {
            if (!intervalId) {
                intervalId = setInterval(changeWord, speedMapper(speedControl.value));
                startBtn.innerHTML = '⏸️ 暂停滚动';
                startBtn.style.background = '#e74c3c';
                wordDisplay.style.color = '#34495e';
            }
        }

        function stopRolling() {
            if (intervalId) {
                clearInterval(intervalId);
                intervalId = null;
                startBtn.innerHTML = '▶️ 继续滚动';
                startBtn.style.background = '#3498db';
                wordDisplay.style.color = '#ff4757';
            }
        }

        function changeWord() {
            const randomIndex = Math.floor(Math.random() * words.length);
            wordDisplay.textContent = words[randomIndex];
            wordDisplay.classList.remove('highlight');
            void wordDisplay.offsetWidth; // 触发重绘
            wordDisplay.classList.add('highlight');
        }

        startBtn.addEventListener('click', () => {
            intervalId ? stopRolling() : startRolling();
        });

        speedControl.addEventListener('input', () => {
            if (intervalId) {
                clearInterval(intervalId);
                intervalId = setInterval(changeWord, speedMapper(speedControl.value));
            }
        });

        // 初始化渐变入场
        setTimeout(() => {
            document.body.style.opacity = 1;
        }, 100);
    </script>
</body>
</html>
