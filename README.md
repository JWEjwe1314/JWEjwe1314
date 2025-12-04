<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>金万恩</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            background: #f0f4ff;
            font-family: "Microsoft Yahei", sans-serif;
        }
        /* 名字动画容器 */
        .name-container {
            text-align: center;
        }
        /* 金万恩文字样式 */
        .jinwanen {
            font-size: 6vw;
            font-weight: bold;
            color: #165DFF;
            position: relative;
            display: inline-block;
            animation: float 3s ease-in-out infinite;
        }
        /* 悬浮动画 */
        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-15px); }
        }
        /* 文字描边+渐变 */
        .jinwanen::before {
            content: "金万恩";
            position: absolute;
            top: 0;
            left: 0;
            -webkit-text-stroke: 2px #0e4bdb;
            color: transparent;
            z-index: -1;
            animation: scale 3s ease-in-out infinite;
        }
        /* 缩放动画 */
        @keyframes scale {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }
        /* 点击交互效果 */
        .jinwanen:active {
            transform: scale(0.95);
            transition: transform 0.2s;
        }
        /* 副标题呼吸动画 */
        .subtitle {
            margin-top: 20px;
            color: #666;
            font-size: 1.2rem;
            animation: breathe 4s ease-in-out infinite;
        }
        @keyframes breathe {
            0%, 100% { opacity: 0.7; }
            50% { opacity: 1; }
        }
    </style>
</head>
<body>
    <div class="name-container">
        <!-- 核心：金万恩名字动画 -->
        <div class="jinwanen">金万恩</div>
        <p class="subtitle">专业品质 · 值得信赖</p>
    </div>

    <!-- 简单交互脚本 -->
    <script>
        // 点击名字触发颜色切换动画
        const nameElement = document.querySelector('.jinwanen');
        const colors = ['#165DFF', '#FF7D00', '#00C48C', '#9C27B0', '#FF5252'];
        let colorIndex = 0;

        nameElement.addEventListener('click', () => {
            colorIndex = (colorIndex + 1) % colors.length;
            nameElement.style.color = colors[colorIndex];
            // 点击时的震动效果
            nameElement.style.animation = 'none';
            setTimeout(() => {
                nameElement.style.animation = 'float 3s ease-in-out infinite';
            }, 100);
        });

        // 鼠标悬浮提示
        nameElement.addEventListener('mouseover', () => {
            nameElement.style.cursor = 'pointer';
        });
    </script>
</body>
</html>
