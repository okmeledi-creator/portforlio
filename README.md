<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Владислав Козмеску — Видеомонтажёр</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Syne:wght@400;600;800&display=swap');
    </style>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Syne', sans-serif;
            background: linear-gradient(135deg, #e8f0ff 0%, #f3e8ff 100%);
            color: #2d3748;
            overflow-x: hidden;
            min-height: 100vh;
        }

        #particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        .particle {
            position: absolute;
            width: 4px;
            height: 4px;
            background: radial-gradient(circle, rgba(147, 197, 253, 0.8), transparent);
            border-radius: 50%;
            pointer-events: none;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 40px 20px;
            position: relative;
            z-index: 2;
        }

        header {
            text-align: center;
            margin-bottom: 60px;
            animation: fadeInDown 1s ease;
        }

        h1 {
            font-family: 'Syne', sans-serif;
            font-weight: 800;
            font-size: 4.5rem;
            background: linear-gradient(135deg, #667eea 0%, #a78bfa 50%, #667eea 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 10px;
            letter-spacing: -2px;
        }

        .subtitle {
            font-size: 1.3rem;
            color: #6b7280;
            font-weight: 400;
        }

        .glass-card {
            background: rgba(255, 255, 255, 0.25);
            backdrop-filter: blur(20px);
            border: 1px solid rgba(255, 255, 255, 0.4);
            border-radius: 30px;
            padding: 40px;
            margin-bottom: 30px;
            box-shadow: 0 8px 32px rgba(102, 126, 234, 0.15);
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            animation: fadeInUp 0.8s ease both;
        }

        .glass-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 45px rgba(102, 126, 234, 0.25);
            background: rgba(255, 255, 255, 0.35);
        }

        .intro-section {
            display: flex;
            align-items: center;
            gap: 30px;
            flex-wrap: wrap;
        }

        .profile-photo {
            width: 150px;
            height: 150px;
            border-radius: 30px;
            object-fit: cover;
            border: 3px solid rgba(255, 255, 255, 0.5);
            box-shadow: 0 8px 32px rgba(102, 126, 234, 0.2);
        }

        .intro-text {
            flex: 1;
            min-width: 300px;
        }

        h2 {
            font-size: 2.5rem;
            font-weight: 800;
            margin-bottom: 30px;
            background: linear-gradient(135deg, #667eea 0%, #a78bfa 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            text-align: center;
        }

        h3 {
            font-size: 1.5rem;
            font-weight: 600;
            margin-bottom: 15px;
            color: #4b5563;
        }

        p {
            line-height: 1.8;
            color: #6b7280;
            margin-bottom: 20px;
        }

        .video-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 25px;
            margin-top: 30px;
            max-width: 800px;
            margin-left: auto;
            margin-right: auto;
        }

        .video-card {
            background: rgba(255, 255, 255, 0.3);
            backdrop-filter: blur(15px);
            border: 1px solid rgba(255, 255, 255, 0.5);
            border-radius: 25px;
            padding: 0;
            overflow: hidden;
            transition: all 0.3s ease;
            text-decoration: none;
            color: inherit;
            display: block;
            cursor: pointer;
        }

        .video-card:hover {
            transform: scale(1.02);
            background: rgba(255, 255, 255, 0.4);
        }

        .video-card video {
            width: 100%;
            height: 0;
            padding-bottom: 177.78%;
            object-fit: cover;
            border-radius: 25px 25px 0 0;
        }

        .video-card iframe {
            width: 100%;
            height: 0;
            padding-bottom: 177.78%;
            border: none;
            border-radius: 25px 25px 0 0;
            display: block;
        }

        .video-card > div:first-child {
            position: relative;
            width: 100%;
            padding-bottom: 177.78%;
        }

        .video-card > div:first-child > * {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
        }

        .video-info {
            padding: 20px;
        }

        .contact-info {
            display: flex;
            flex-direction: column;
            gap: 20px;
            margin-top: 30px;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 20px;
            padding: 20px;
            background: rgba(255, 255, 255, 0.3);
            backdrop-filter: blur(15px);
            border: 1px solid rgba(255, 255, 255, 0.5);
            border-radius: 20px;
            transition: all 0.3s ease;
            text-decoration: none;
            color: inherit;
        }

        .contact-item:hover {
            background: rgba(255, 255, 255, 0.45);
            transform: translateX(10px);
        }

        .contact-icon {
            width: 40px;
            height: 40px;
            fill: none;
            stroke: url(#gradient);
            stroke-width: 2;
            flex-shrink: 0;
        }

        .telegram-icon {
            width: 40px;
            height: 40px;
            flex-shrink: 0;
        }

        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @media (max-width: 768px) {
            h1 {
                font-size: 3rem;
            }

            .glass-card {
                padding: 25px;
            }

            .intro-section {
                flex-direction: column;
                text-align: center;
            }

            .profile-photo {
                margin: 0 auto;
            }
        }

        svg defs {
            display: none;
        }

        svg defs:first-of-type {
            display: block;
        }
    </style>
</head>
<body>
    <div id="particles"></div>
    
    <svg width="0" height="0">
        <defs>
            <linearGradient id="gradient" x1="0%" y1="0%" x2="100%" y2="100%">
                <stop offset="0%" style="stop-color:#667eea;stop-opacity:1" />
                <stop offset="100%" style="stop-color:#a78bfa;stop-opacity:1" />
            </linearGradient>
        </defs>
    </svg>

    <div class="container">
        <header>
            <h1>Владислав Козмеску</h1>
            <p class="subtitle">Видеомонтажёр вертикального контента</p>
        </header>

        <div class="glass-card">
            <div class="intro-section">
                <img src="https://i.imgur.com/G6RhGim.jpg" alt="Владислав Козмеску" class="profile-photo">
                <div class="intro-text">
                    <p style="font-size: 1.3rem; font-weight: 600; margin-bottom: 10px;">Меня зовут Владислав</p>
                    <p>Я — монтажёр рилс, которые сделают ваши видео вирусными</p>
                </div>
            </div>
        </div>

        <div class="glass-card">
            <h2>Мои работы</h2>

            <div class="video-grid">
                <a href="https://youtube.com/shorts/-CgpIJrZjFk?feature=share" target="_blank" class="video-card">
                    <div style="position: relative; width: 100%; padding-bottom: 177.78%; background: linear-gradient(135deg, #667eea 0%, #a78bfa 100%); border-radius: 25px 25px 0 0;">
                        <div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; display: flex; flex-direction: column; align-items: center; justify-content: center;">
                            <svg width="100" height="100" viewBox="0 0 24 24" fill="white" style="filter: drop-shadow(0 6px 12px rgba(0,0,0,0.4)); margin-bottom: 20px;">
                                <circle cx="12" cy="12" r="10" fill="rgba(255,255,255,0.2)"/>
                                <path d="M10 8l6 4-6 4V8z"/>
                            </svg>
                            <p style="color: white; font-size: 1.1rem; font-weight: 600; text-shadow: 0 2px 8px rgba(0,0,0,0.3);">Смотреть на YouTube</p>
                        </div>
                    </div>
                    <div class="video-info">
                        <h3>Динамичный рилс</h3>
                        <p>Быстрый монтаж с эффектными переходами</p>
                    </div>
                </a>

                <a href="https://youtube.com/shorts/O1Gnw6uEjqQ?feature=share" target="_blank" class="video-card">
                    <div style="position: relative; width: 100%; padding-bottom: 177.78%; background: linear-gradient(135deg, #a78bfa 0%, #667eea 100%); border-radius: 25px 25px 0 0;">
                        <div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; display: flex; flex-direction: column; align-items: center; justify-content: center;">
                            <svg width="100" height="100" viewBox="0 0 24 24" fill="white" style="filter: drop-shadow(0 6px 12px rgba(0,0,0,0.4)); margin-bottom: 20px;">
                                <circle cx="12" cy="12" r="10" fill="rgba(255,255,255,0.2)"/>
                                <path d="M10 8l6 4-6 4V8z"/>
                            </svg>
                            <p style="color: white; font-size: 1.1rem; font-weight: 600; text-shadow: 0 2px 8px rgba(0,0,0,0.3);">Смотреть на YouTube</p>
                        </div>
                    </div>
                    <div class="video-info">
                        <h3>Креативный контент</h3>
                        <p>Стильное оформление и качественный монтаж</p>
                    </div>
                </a>
            </div>
        </div>

        <div class="glass-card">
            <h2>Контакты</h2>

            <div class="contact-info">
                <div class="contact-item">
                    <svg class="contact-icon" viewBox="0 0 24 24">
                        <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/>
                        <polyline points="22,6 12,13 2,6"/>
                    </svg>
                    <div>
                        <h3 style="margin-bottom: 5px;">Email</h3>
                        <p style="margin: 0;">okmeledi@gmail.com</p>
                    </div>
                </div>

                <a href="http://t.me/Dontfall23" target="_blank" class="contact-item">
                    <svg class="telegram-icon" viewBox="0 0 24 24" fill="url(#gradient)">
                        <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm4.64 6.8c-.15 1.58-.8 5.42-1.13 7.19-.14.75-.42 1-.68 1.03-.58.05-1.02-.38-1.58-.75-.88-.58-1.38-.94-2.23-1.5-.99-.65-.35-1.01.22-1.59.15-.15 2.71-2.48 2.76-2.69a.2.2 0 00-.05-.18c-.06-.05-.14-.03-.21-.02-.09.02-1.49.95-4.22 2.79-.4.27-.76.41-1.08.4-.36-.01-1.04-.2-1.55-.37-.63-.2-1.12-.31-1.08-.66.02-.18.27-.36.74-.55 2.92-1.27 4.86-2.11 5.83-2.51 2.78-1.16 3.35-1.36 3.73-1.36.08 0 .27.02.39.12.1.08.13.19.14.27-.01.06.01.24 0 .38z"/>
                    </svg>
                    <div>
                        <h3 style="margin-bottom: 5px;">Telegram</h3>
                        <p style="margin: 0;">@Dontfall23</p>
                    </div>
                </a>
            </div>
        </div>
    </div>

    <script>
        // Летающие частицы
        const particlesContainer = document.getElementById('particles');
        const particleCount = 50;

        function createParticle() {
            const particle = document.createElement('div');
            particle.className = 'particle';
            
            const startX = Math.random() * window.innerWidth;
            const startY = Math.random() * window.innerHeight;
            const endX = startX + (Math.random() - 0.5) * 200;
            const endY = startY - Math.random() * 300;
            const duration = 3 + Math.random() * 4;
            const delay = Math.random() * 2;
            
            particle.style.left = startX + 'px';
            particle.style.top = startY + 'px';
            particle.style.animation = `floatParticle ${duration}s ease-in-out ${delay}s infinite`;
            
            particlesContainer.appendChild(particle);
            
            const style = document.createElement('style');
            const animationName = `floatParticle${Math.random().toString(36).substr(2, 9)}`;
            style.innerHTML = `
                @keyframes ${animationName} {
                    0%, 100% {
                        transform: translate(0, 0);
                        opacity: 0;
                    }
                    10% {
                        opacity: 0.8;
                    }
                    90% {
                        opacity: 0.8;
                    }
                    100% {
                        transform: translate(${endX - startX}px, ${endY - startY}px);
                        opacity: 0;
                    }
                }
            `;
            document.head.appendChild(style);
            particle.style.animation = `${animationName} ${duration}s ease-in-out ${delay}s infinite`;
        }

        for (let i = 0; i < particleCount; i++) {
            createParticle();
        }

        // Обновление частиц при изменении размера окна
        window.addEventListener('resize', () => {
            particlesContainer.innerHTML = '';
            for (let i = 0; i < particleCount; i++) {
                createParticle();
            }
        });
    </script>
</body>
</html>
