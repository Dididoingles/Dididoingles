<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dididoingles - English Professor & EdTech Developer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Press Start 2P', 'Courier New', monospace;
            background: linear-gradient(135deg, #000000 0%, #1a1a1a 100%);
            color: #fff;
            line-height: 1.6;
            min-height: 100vh;
            position: relative;
            overflow-x: hidden;
        }

        /* Arcade grid background */
        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: 
                linear-gradient(0deg, transparent 24%, rgba(194, 0, 0, 0.05) 25%, rgba(194, 0, 0, 0.05) 26%, transparent 27%, transparent 74%, rgba(194, 0, 0, 0.05) 75%, rgba(194, 0, 0, 0.05) 76%, transparent 77%, transparent),
                linear-gradient(90deg, transparent 24%, rgba(194, 0, 0, 0.05) 25%, rgba(194, 0, 0, 0.05) 26%, transparent 27%, transparent 74%, rgba(194, 0, 0, 0.05) 75%, rgba(194, 0, 0, 0.05) 76%, transparent 77%, transparent);
            background-size: 50px 50px;
            pointer-events: none;
            z-index: 1;
        }

        .container {
            max-width: 900px;
            margin: 0 auto;
            padding: 40px 20px;
            position: relative;
            z-index: 2;
        }

        /* Glitch Header */
        .header {
            text-align: center;
            margin-bottom: 60px;
            position: relative;
        }

        .glitch {
            font-size: 3.5rem;
            font-weight: bold;
            color: #c20000;
            position: relative;
            text-shadow: 2px 2px 0 #000, 4px 4px 0 rgba(194, 0, 0, 0.5);
            animation: glitch-animation 3s infinite;
            letter-spacing: 3px;
        }

        @keyframes glitch-animation {
            0%, 100% {
                text-shadow: 2px 2px 0 #000, 4px 4px 0 rgba(194, 0, 0, 0.5);
                transform: translate(0);
            }
            20% {
                text-shadow: -2px 0 #c20000, 2px 2px 0 #000;
                transform: translate(-2px, 2px);
            }
            40% {
                text-shadow: 2px 0 #c20000, -2px -2px 0 #000;
                transform: translate(2px, -2px);
            }
            60% {
                text-shadow: 0 0 10px rgba(194, 0, 0, 0.8);
                transform: translate(1px, 1px);
            }
            80% {
                text-shadow: -2px 2px 0 rgba(194, 0, 0, 0.6);
                transform: translate(-1px, -1px);
            }
        }

        .subtitle {
            font-size: 1.2rem;
            color: #fff;
            margin-top: 20px;
            letter-spacing: 2px;
            animation: blink 1.5s infinite;
        }

        @keyframes blink {
            0%, 49%, 100% {
                opacity: 1;
            }
            50%, 99% {
                opacity: 0.3;
            }
        }

        .tagline {
            font-size: 0.8rem;
            color: #c20000;
            margin-top: 10px;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0%, 100% {
                opacity: 1;
            }
            50% {
                opacity: 0.7;
            }
        }

        /* Scoreboard */
        .scoreboard {
            background: #c20000;
            color: #000;
            padding: 30px;
            margin-bottom: 40px;
            border: 4px solid #000;
            border-radius: 10px;
            text-align: center;
            box-shadow: 0 10px 30px rgba(194, 0, 0, 0.3);
            animation: slideIn 0.8s ease-out;
        }

        @keyframes slideIn {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .score-item {
            display: inline-block;
            margin: 10px 20px;
            font-size: 1.2rem;
            font-weight: bold;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        /* Section Titles */
        .section-title {
            font-size: 2rem;
            color: #c20000;
            margin: 50px 0 30px 0;
            text-transform: uppercase;
            letter-spacing: 2px;
            padding-bottom: 10px;
            border-bottom: 3px solid #c20000;
            animation: slideInLeft 0.8s ease-out;
            display: flex;
            align-items: center;
        }

        .section-title::before {
            content: '▶ ';
            margin-right: 15px;
            animation: blink 1s infinite;
        }

        @keyframes slideInLeft {
            from {
                opacity: 0;
                transform: translateX(-30px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        /* Content Box */
        .content-box {
            background: rgba(194, 0, 0, 0.1);
            border: 2px solid #c20000;
            padding: 25px;
            margin-bottom: 25px;
            border-radius: 5px;
            animation: fadeIn 1s ease-out;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
            }
            to {
                opacity: 1;
            }
        }

        .content-box h3 {
            color: #c20000;
            font-size: 1.3rem;
            margin-bottom: 15px;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .content-box p {
            font-size: 0.7rem;
            line-height: 1.8;
            color: #fff;
        }

        /* Project Cards */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin-bottom: 40px;
        }

        .project-card {
            background: linear-gradient(135deg, rgba(194, 0, 0, 0.2) 0%, rgba(194, 0, 0, 0.05) 100%);
            border: 3px solid #c20000;
            padding: 25px;
            border-radius: 5px;
            transition: all 0.3s ease;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: rgba(194, 0, 0, 0.2);
            transition: left 0.3s ease;
            z-index: -1;
        }

        .project-card:hover {
            transform: translate(-5px, -5px);
            box-shadow: 5px 5px 0 #c20000;
            border-color: #fff;
        }

        .project-card:hover::before {
            left: 100%;
        }

        .project-card h4 {
            color: #fff;
            font-size: 1.1rem;
            margin-bottom: 10px;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .project-card p {
            font-size: 0.65rem;
            color: #ccc;
            line-height: 1.6;
        }

        /* Button Arcade Style */
        .arcade-button {
            display: inline-block;
            background: #c20000;
            color: #000;
            padding: 15px 30px;
            margin: 10px 10px 10px 0;
            border: 3px solid #000;
            border-radius: 5px;
            font-family: 'Press Start 2P', monospace;
            font-size: 0.7rem;
            font-weight: bold;
            text-transform: uppercase;
            letter-spacing: 1px;
            text-decoration: none;
            cursor: pointer;
            transition: all 0.2s;
            box-shadow: 4px 4px 0 #000;
            text-align: center;
        }

        .arcade-button:hover {
            transform: translate(-2px, -2px);
            box-shadow: 6px 6px 0 #000;
            background: #fff;
            color: #c20000;
        }

        .arcade-button:active {
            transform: translate(0, 0);
            box-shadow: 2px 2px 0 #000;
        }

        /* Social Links */
        .social-links {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            margin-top: 30px;
            justify-content: center;
        }

        .social-link {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 50px;
            height: 50px;
            background: #c20000;
            color: #000;
            border: 2px solid #000;
            border-radius: 5px;
            font-size: 1.5rem;
            text-decoration: none;
            transition: all 0.3s;
            font-weight: bold;
        }

        .social-link:hover {
            transform: scale(1.2) rotate(5deg);
            box-shadow: 0 0 20px rgba(194, 0, 0, 0.6);
        }

        /* Game Stats */
        .game-stats {
            background: #c20000;
            color: #000;
            padding: 25px;
            border: 3px solid #000;
            border-radius: 5px;
            margin-bottom: 30px;
        }

        .stat-row {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin: 15px 0;
            font-size: 0.9rem;
            font-weight: bold;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .stat-label {
            flex: 1;
        }

        .stat-bar {
            flex: 2;
            background: #000;
            height: 20px;
            margin: 0 20px;
            border: 2px solid #000;
            position: relative;
            border-radius: 3px;
            overflow: hidden;
        }

        .stat-fill {
            height: 100%;
            background: #fff;
            animation: fillBar 1.5s ease-out;
        }

        @keyframes fillBar {
            from {
                width: 0;
            }
        }

        .stat-value {
            min-width: 50px;
            text-align: right;
        }

        /* Footer */
        .footer {
            text-align: center;
            margin-top: 60px;
            padding-top: 30px;
            border-top: 3px solid #c20000;
            font-size: 0.8rem;
            color: #999;
        }

        .heart {
            color: #c20000;
            display: inline-block;
            animation: heartbeat 1.2s ease-in-out infinite;
        }

        @keyframes heartbeat {
            0%, 100% {
                transform: scale(1);
            }
            25% {
                transform: scale(1.3);
            }
            50% {
                transform: scale(1);
            }
        }

        /* Responsive */
        @media (max-width: 768px) {
            .glitch {
                font-size: 2.5rem;
            }

            .subtitle {
                font-size: 0.9rem;
            }

            .section-title {
                font-size: 1.5rem;
            }

            .projects-grid {
                grid-template-columns: 1fr;
            }

            .scoreboard {
                padding: 20px;
            }

            .score-item {
                display: block;
                margin: 10px 0;
            }

            .stat-row {
                flex-direction: column;
                align-items: flex-start;
                gap: 10px;
            }

            .stat-bar {
                width: 100%;
                margin: 10px 0;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Header -->
        <div class="header">
            <div class="glitch">DIDIDOINGLES</div>
            <div class="subtitle">▶ ENGLISH PROFESSOR & EDTECH DEVELOPER ◀</div>
            <div class="tagline">🎮 GAME ON FOR EDUCATION 🎮</div>
        </div>

        <!-- Scoreboard -->
        <div class="scoreboard">
            <div class="score-item">🎯 STUDENTS INSPIRED</div>
            <div class="score-item">📚 TOOLS CREATED</div>
            <div class="score-item">🌟 LEVELS UNLOCKED</div>
        </div>

        <!-- About Me Section -->
        <h2 class="section-title">ABOUT ME</h2>
        <div class="content-box">
            <h3>👨‍🏫 Who I Am</h3>
            <p>
                [Edit this section to tell your story! Share your teaching journey, what drives your passion for language education, and why you're dedicated to helping students master English. This is your chance to connect with visitors and showcase your unique teaching philosophy.]
            </p>
        </div>

        <!-- My Projects Section -->
        <h2 class="section-title">MY PROJECTS</h2>
        <div class="projects-grid">
            <div class="project-card">
                <h4>📝 Whiteboard</h4>
                <p>An interactive whiteboard tool designed to enhance classroom engagement and collaborative learning experiences for English students.</p>
            </div>
            <div class="project-card">
                <h4>🎧 English Lab</h4>
                <p>Complete language laboratory practicing all English abilities: Speaking, Listening, Reading, and Writing. Master every skill in one comprehensive platform.</p>
            </div>
            <div class="project-card">
                <h4>📖 Free eBooks</h4>
                <p>"A Mente que Fala Inglês" - Your guide to thinking in English. Free download to help students develop native-like thinking patterns.</p>
            </div>
        </div>

        <!-- Free eBook Section -->
        <h2 class="section-title">FREE RESOURCES</h2>
        <div class="content-box">
            <h3>📚 A Mente que Fala Inglês</h3>
            <p>
                Download our free eBook and discover the secrets to thinking in English like a native speaker. This comprehensive guide includes practical exercises, mental models, and proven strategies to accelerate your English learning journey.
            </p>
            <div style="margin-top: 20px;">
                <a href="[your ebook link here]" class="arcade-button">⬇️ DOWNLOAD EBOOK</a>
            </div>
        </div>

        <!-- Teaching Philosophy -->
        <h2 class="section-title">TEACHING PHILOSOPHY</h2>
        <div class="content-box">
            <h3>🎮 My Approach</h3>
            <p>
                [Edit this section to share your teaching methodology! Explain your educational philosophy, your approach to language learning, and what makes your teaching unique. What core beliefs guide your work? How do you help students achieve their goals?]
            </p>
        </div>

        <!-- Game Stats -->
        <h2 class="section-title">PLAYER STATS</h2>
        <div class="game-stats">
            <div class="stat-row">
                <span class="stat-label">Teaching Experience</span>
                <div class="stat-bar">
                    <div class="stat-fill" style="width: 85%;"></div>
                </div>
                <span class="stat-value">85%</span>
            </div>
            <div class="stat-row">
                <span class="stat-label">Student Satisfaction</span>
                <div class="stat-bar">
                    <div class="stat-fill" style="width: 95%;"></div>
                </div>
                <span class="stat-value">95%</span>
            </div>
            <div class="stat-row">
                <span class="stat-label">EdTech Innovation</span>
                <div class="stat-bar">
                    <div class="stat-fill" style="width: 90%;"></div>
                </div>
                <span class="stat-value">90%</span>
            </div>
            <div class="stat-row">
                <span class="stat-label">Learning Impact</span>
                <div class="stat-bar">
                    <div class="stat-fill" style="width: 92%;"></div>
                </div>
                <span class="stat-value">92%</span>
            </div>
        </div>

        <!-- Connect Section -->
        <h2 class="section-title">CONNECT WITH ME</h2>
        <div class="content-box" style="text-align: center;">
            <h3>LET'S LEVEL UP YOUR ENGLISH!</h3>
            <p style="margin-bottom: 25px;">
                Have questions about my educational tools or want to collaborate? Reach out through any of these channels:
            </p>
            <div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 15px;">
                <a href="[your website link here]" class="arcade-button">🌐 WEBSITE</a>
                <a href="https://instagram.com/[your instagram here]" class="arcade-button">📸 INSTAGRAM</a>
                <a href="https://wa.me/[your whatsapp here]" class="arcade-button">💬 WHATSAPP</a>
                <a href="mailto:your.email@example.com" class="arcade-button">✉️ EMAIL</a>
            </div>
        </div>

        <!-- Social Links -->
        <div class="social-links">
            <a href="[your website link here]" class="social-link" title="Website">🌐</a>
            <a href="https://instagram.com/[your instagram here]" class="social-link" title="Instagram">📸</a>
            <a href="https://wa.me/[your whatsapp here]" class="social-link" title="WhatsApp">💬</a>
            <a href="mailto:your.email@example.com" class="social-link" title="Email">✉️</a>
        </div>

        <!-- Footer -->
        <div class="footer">
            <p>Made with <span class="heart">❤️</span> for English learners worldwide</p>
            <p style="margin-top: 15px; font-size: 0.65rem;">© 2026 Dididoingles | Arcade-Style Education Rocks!</p>
        </div>
    </div>
</body>
</html>
