<!DOCTYPE html>
<html>
<head>
    <title>终极动词抽选器</title>
    <style>
        body {
            margin: 0;
            padding: 20px;
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            font-family: "微软雅黑", sans-serif;
            height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            animation: fadeIn 0.5s ease-out forwards;
        }

        @keyframes fadeIn {
            to { opacity: 1; }
        }

        h1 {
            color: #2c3e50;
            text-align: center;
            margin: 30px 0;
            font-size: 2.8em;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.1);
            position: relative;
        }

        h1::after {
            content: "";
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 3px;
            background: #3498db;
        }

        #wordDisplay {
            flex: 1;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 5.5em;
            color: #34495e;
            transition: all 0.1s;
            max-width: 90%;
            text-align: center;
            min-height: 200px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.1);
        }

        .highlight {
            color: #ff6b6b !important;
            transform: scale(1.15);
            text-shadow: 3px 3px 6px rgba(255,107,107,0.3);
        }

        .controls {
            position: fixed;
            bottom: 8vh;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            gap: 30px;
            align-items: center;
            background: rgba(255,255,255,0.95);
            padding: 20px 50px;
            border-radius: 50px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.15);
            border: 2px solid #3498db;
            backdrop-filter: blur(5px);
        }

        button {
            padding: 20px 50px;
            font-size: 1.6em;
            background: #3498db;
            color: white;
            border: none;
            border-radius: 40px;
            cursor: pointer;
            transition: 0.3s;
            min-width: 180px;
        }

        button:hover {
            background: #2980b9;
            transform: scale(1.08);
            box-shadow: 0 8px 20px rgba(52,152,219,0.4);
        }

        .speed-container {
            display: flex;
            align-items: center;
            gap: 15px;
            font-size: 1.4em;
        }

        input[type="range"] {
            width: 220px;
            height: 15px;
            background: #e0e7ff;
            border-radius: 10px;
            -webkit-appearance: none;
        }

        input[type="range"]::-webkit-slider-thumb {
            -webkit-appearance: none;
            width: 28px;
            height: 28px;
            background: #3498db;
            border-radius: 50%;
            box-shadow: 0 3px 8px rgba(0,0,0,0.2);
            transition: 0.2s;
        }
    </style>
</head>
<body>
    <h1>🚦 完美调速版动词抽选器</h1>
    <div id="wordDisplay">点击开始 →</div>
    
    <div class="controls">
        <div class="speed-container">
            <span>🐢 慢</span>
            <input type="range" id="speedControl" min="100" max="500" value="300">
            <span>快 🐇</span>
        </div>
        <button id="startBtn">▶️ 开始滚动</button>
    </div>

    <script>
        // 去重后的动词列表
        const words = [...new Set([
            'am', 'thank', 'is', 'sit', 'stand', 'open', 'point', 'look',
            'help', 'count', 'say', 'are', 'know', 'touch', 'go', 'see',
            'swim', 'like', 'play', 'guess', 'sing', 'dance', 'have',
            'watch', 'live', 'chug', 'beep', 'walk', 'goes', 'run',
            'love', 'watches', 'read', 'come', 'listen', 'fly', 'wear',
            'eat', 'wish', 'take', 'rain', 'snow', 'ski', 'smile', 'write',
            'draw', 'colour', 'tidy', 'do', 'sleep', 'call', 'drink', 'hide',
            'talk', 'seek', 'skip', 'clap', 'catch', 'ride', 'cook', 'stop',
            'turn', 'jump', 'back', 'want', 'make'
        ])];

        // 核心变量声明
        let intervalId = null;
        const speedControl = document.getElementById('speedControl');
        const startBtn = document.getElementById('startBtn');
        const wordDisplay = document.getElementById('wordDisplay');

        // 修复后的速度控制函数
        function getSpeed() {
            // 滑块向右（值增大）速度变快
            return 300 - ((speedControl.value - 100) * 250 / 400);
        }

        // 启动滚动
        function startRolling() {
            if (!intervalId) {
                intervalId = setInterval(changeWord, getSpeed());
                startBtn.textContent = '⏸️ 暂停滚动';
                startBtn.style.background = '#ff7675';
            }
        }

        // 停止滚动
        function stopRolling() {
            if (intervalId) {
                clearInterval(intervalId);
                intervalId = null;
                startBtn.textContent = '▶️ 继续滚动';
                startBtn.style.background = '#3498db';
            }
        }

        // 单词切换动画
        function changeWord() {
            const randomIndex = Math.floor(Math.random() * words.length);
            wordDisplay.textContent = words[randomIndex];
            wordDisplay.classList.remove('highlight');
            void wordDisplay.offsetWidth; // 触发动画重置
            wordDisplay.classList.add('highlight');
        }

        // 事件监听
        startBtn.addEventListener('click', () => {
            intervalId ? stopRolling() : startRolling();
        });

        speedControl.addEventListener('input', () => {
            if (intervalId) {
                clearInterval(intervalId);
                intervalId = setInterval(changeWord, getSpeed());
            }
        });

        // 初始化淡入效果
        setTimeout(() => {
            document.body.style.opacity = 1;
        }, 100);
    </script>
</body>
</html>
