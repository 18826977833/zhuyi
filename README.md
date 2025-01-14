<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>划消测验</title>
    <style>
        * {
            box-sizing: border-box;
            -webkit-tap-highlight-color: transparent;
        }

        body {
            margin: 0;
            padding: 15px;
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
            background-color: #f8f8f8;
            touch-action: manipulation;
        }
        
        .container {
            max-width: 100%;
            margin: 0 auto;
            text-align: center;
        }

        h1 {
            font-size: 1.5rem;
            margin: 10px 0;
        }

        .game-grid {
            display: grid;
            grid-template-columns: repeat(10, 1fr);
            gap: 2px;
            margin: 15px auto;
            background-color: #fff;
            padding: 8px;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }

        .cell {
            aspect-ratio: 1;
            border: 1px solid #ddd;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            position: relative;
            font-size: 16px;
            background-color: white;
            user-select: none;
            touch-action: manipulation;
        }

        .cell.crossed {
            color: #ccc;
        }

        .cell.crossed::after {
            content: '';
            position: absolute;
            top: 50%;
            left: 0;
            width: 100%;
            height: 2px;
            background-color: #ff4444;
            transform: rotate(-45deg);
        }

        button {
            padding: 12px 24px;
            font-size: 16px;
            cursor: pointer;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 25px;
            margin: 10px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
        }

        button:active {
            transform: scale(0.98);
        }

        .button-started {
            background-color: #ff4444 !important;
        }

        .results {
            margin-top: 20px;
            padding: 15px;
            background-color: #fff;
            border-radius: 8px;
            display: none;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }

        .timer {
            font-size: 1.2em;
            font-weight: bold;
            margin: 10px 0;
            color: #333;
        }

        .score-item {
            margin: 8px 0;
            padding: 8px;
            background-color: #f8f8f8;
            border-radius: 6px;
            font-size: 14px;
        }

        .status-text {
            color: #ff4444;
            font-weight: bold;
            display: none;
            margin: 10px 0;
            padding: 8px;
            background-color: #fff;
            border-radius: 6px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }

        .rules {
            background-color: #fff;
            padding: 12px;
            border-radius: 8px;
            margin: 10px 0;
            font-size: 14px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>划消测验</h1>
        <div class="rules">
            <p>规则：请找出并点击所有的奇数（1、3、5、7、9）</p>
        </div>
        <p id="statusText" class="status-text">测验已开始，请立即开始划掉奇数！</p>
        <p class="timer">用时：<span id="time">0:00</span></p>
        <button id="startBtn">开始测验</button>
        
        <div class="game-grid" id="gameGrid"></div>
        
        <div class="results" id="results">
            <h2>测验结束！</h2>
            <div id="scoreDetails"></div>
            <button id="restartBtn">重新开始</button>
        </div>
    </div>

    <script>
        // JavaScript 代码保持不变
    </script>
</body>
</html>
