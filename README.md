<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Thembelihle Queeneth Maluka | Full Stack Developer</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Playfair+Display:wght@700;900&family=JetBrains+Mono:wght@400;600&display=swap');
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        :root {
            --primary: #F75C7E;
            --secondary: #7B68EE;
            --accent: #FFD700;
            --dark: #0D1117;
            --darker: #010409;
            --light: #FFFFFF;
            --gray: #8B949E;
        }
        
        body {
            font-family: 'Space Mono', monospace;
            background: var(--dark);
            color: var(--light);
            overflow-x: hidden;
            position: relative;
        }
        
        /* Animated background */
        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                radial-gradient(circle at 20% 50%, rgba(247, 92, 126, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 80% 80%, rgba(123, 104, 238, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 40% 20%, rgba(255, 215, 0, 0.05) 0%, transparent 50%);
            animation: backgroundPulse 15s ease-in-out infinite;
            z-index: -1;
        }
        
        @keyframes backgroundPulse {
            0%, 100% { opacity: 0.3; }
            50% { opacity: 0.6; }
        }
        
        /* Floating particles */
        .particle {
            position: fixed;
            width: 4px;
            height: 4px;
            background: var(--primary);
            border-radius: 50%;
            opacity: 0.3;
            animation: float 20s infinite;
            z-index: -1;
        }
        
        @keyframes float {
            0% {
                transform: translateY(100vh) translateX(0) rotate(0deg);
                opacity: 0;
            }
            10% {
                opacity: 0.3;
            }
            90% {
                opacity: 0.3;
            }
            100% {
                transform: translateY(-100px) translateX(100px) rotate(360deg);
                opacity: 0;
            }
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            position: relative;
        }
        
        .hero h1 {
            font-family: 'Playfair Display', serif;
            font-size: 5rem;
            font-weight: 900;
            background: linear-gradient(135deg, var(--primary), var(--secondary), var(--accent));
            background-size: 200% 200%;
            -webkit-background-clip: text;
            background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: gradientShift 5s ease infinite, slideDown 1s ease-out;
            margin-bottom: 20px;
            text-shadow: 0 0 40px rgba(247, 92, 126, 0.3);
        }
        
        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }
        
        @keyframes slideDown {
            from {
                opacity: 0;
                transform: translateY(-50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        .hero .tagline {
            font-size: 1.5rem;
            color: var(--gray);
            animation: fadeIn 1.5s ease-out 0.5s both;
            margin-bottom: 30px;
        }
        
        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        .typing-text {
            font-family: 'JetBrains Mono', monospace;
            font-size: 1.2rem;
            color: var(--primary);
            border-right: 3px solid var(--primary);
            white-space: nowrap;
            overflow: hidden;
            animation: typing 4s steps(50) 1s both, blink 0.75s step-end infinite;
        }
        
        @keyframes typing {
            from { width: 0; }
            to { width: 100%; }
        }
        
        @keyframes blink {
            50% { border-color: transparent; }
        }
        
        /* Code Block Section */
        .code-section {
            background: var(--darker);
            border: 2px solid var(--primary);
            border-radius: 15px;
            padding: 40px;
            margin: 60px 0;
            position: relative;
            overflow: hidden;
            animation: slideIn 1s ease-out;
            box-shadow: 0 0 50px rgba(247, 92, 126, 0.2);
        }
        
        @keyframes slideIn {
            from {
                opacity: 0;
                transform: translateX(-100px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }
        
        .code-section::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(247, 92, 126, 0.1), transparent);
            animation: scan 3s linear infinite;
        }
        
        @keyframes scan {
            0% { transform: translateX(-100%) translateY(-100%) rotate(45deg); }
            100% { transform: translateX(100%) translateY(100%) rotate(45deg); }
        }
        
        .code-section pre {
            position: relative;
            z-index: 1;
            font-family: 'JetBrains Mono', monospace;
            font-size: 0.95rem;
            line-height: 1.8;
            color: var(--light);
        }
        
        .code-keyword { color: #FF79C6; }
        .code-string { color: #50FA7B; }
        .code-number { color: #BD93F9; }
        .code-comment { color: var(--gray); font-style: italic; }
        
        /* Tech Stack */
        .tech-stack {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 20px;
            margin: 60px 0;
        }
        
        .tech-item {
            background: linear-gradient(135deg, var(--darker) 0%, rgba(247, 92, 126, 0.1) 100%);
            border: 2px solid transparent;
            border-radius: 12px;
            padding: 25px;
            text-align: center;
            transition: all 0.3s ease;
            animation: popIn 0.5s ease-out backwards;
            position: relative;
            overflow: hidden;
        }
        
        .tech-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(247, 92, 126, 0.3), transparent);
            transition: left 0.5s ease;
        }
        
        .tech-item:hover::before {
            left: 100%;
        }
        
        .tech-item:nth-child(1) { animation-delay: 0.1s; }
        .tech-item:nth-child(2) { animation-delay: 0.2s; }
        .tech-item:nth-child(3) { animation-delay: 0.3s; }
        .tech-item:nth-child(4) { animation-delay: 0.4s; }
        .tech-item:nth-child(5) { animation-delay: 0.5s; }
        .tech-item:nth-child(6) { animation-delay: 0.6s; }
        
        @keyframes popIn {
            from {
                opacity: 0;
                transform: scale(0.5) rotate(-10deg);
            }
            to {
                opacity: 1;
                transform: scale(1) rotate(0deg);
            }
        }
        
        .tech-item:hover {
            transform: translateY(-10px) scale(1.05);
            border-color: var(--primary);
            box-shadow: 0 10px 40px rgba(247, 92, 126, 0.4);
        }
        
        .tech-item h3 {
            font-size: 1.1rem;
            margin-bottom: 10px;
            color: var(--primary);
        }
        
        .tech-item p {
            font-size: 0.85rem;
            color: var(--gray);
        }
        
        /* Timeline */
        .timeline {
            position: relative;
            padding: 40px 0;
            margin: 60px 0;
        }
        
        .timeline::before {
            content: '';
            position: absolute;
            left: 50%;
            top: 0;
            bottom: 0;
            width: 3px;
            background: linear-gradient(180deg, var(--primary), var(--secondary), var(--accent));
            animation: growLine 2s ease-out;
        }
        
        @keyframes growLine {
            from { height: 0; }
            to { height: 100%; }
        }
        
        .timeline-item {
            position: relative;
            margin: 40px 0;
            animation: fadeInUp 0.8s ease-out backwards;
        }
        
        .timeline-item:nth-child(odd) {
            text-align: right;
            padding-right: calc(50% + 40px);
        }
        
        .timeline-item:nth-child(even) {
            text-align: left;
            padding-left: calc(50% + 40px);
        }
        
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        .timeline-dot {
            position: absolute;
            top: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 20px;
            height: 20px;
            background: var(--primary);
            border: 4px solid var(--dark);
            border-radius: 50%;
            animation: pulse 2s ease-in-out infinite;
        }
        
        @keyframes pulse {
            0%, 100% {
                box-shadow: 0 0 0 0 rgba(247, 92, 126, 0.7);
            }
            50% {
                box-shadow: 0 0 0 20px rgba(247, 92, 126, 0);
            }
        }
        
        /* Contact Section */
        .contact-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
            margin: 60px 0;
        }
        
        .contact-card {
            background: linear-gradient(135deg, var(--darker) 0%, rgba(123, 104, 238, 0.1) 100%);
            border: 2px solid var(--secondary);
            border-radius: 15px;
            padding: 30px;
            text-align: center;
            transition: all 0.4s ease;
            animation: bounceIn 0.8s ease-out backwards;
        }
        
        @keyframes bounceIn {
            0% {
                opacity: 0;
                transform: scale(0.3);
            }
            50% {
                transform: scale(1.05);
            }
            100% {
                opacity: 1;
                transform: scale(1);
            }
        }
        
        .contact-card:hover {
            transform: translateY(-15px) rotate(2deg);
            box-shadow: 0 15px 50px rgba(123, 104, 238, 0.5);
            border-color: var(--accent);
        }
        
        .contact-icon {
            font-size: 3rem;
            margin-bottom: 15px;
            display: inline-block;
            animation: spin 10s linear infinite;
        }
        
        @keyframes spin {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }
        
        .contact-card:hover .contact-icon {
            animation: wobble 0.5s ease;
        }
        
        @keyframes wobble {
            0%, 100% { transform: rotate(0deg); }
            25% { transform: rotate(-10deg); }
            75% { transform: rotate(10deg); }
        }
        
        /* Footer */
        footer {
            text-align: center;
            padding: 60px 20px;
            background: var(--darker);
            border-top: 2px solid var(--primary);
            margin-top: 100px;
        }
        
        .footer-quote {
            font-family: 'Playfair Display', serif;
            font-size: 1.8rem;
            font-style: italic;
            color: var(--accent);
            margin-bottom: 20px;
            animation: glow 3s ease-in-out infinite;
        }
        
        @keyframes glow {
            0%, 100% {
                text-shadow: 0 0 10px rgba(255, 215, 0, 0.5);
            }
            50% {
                text-shadow: 0 0 30px rgba(255, 215, 0, 0.8);
            }
        }
        
        /* Section Headers */
        .section-header {
            font-family: 'Playfair Display', serif;
            font-size: 3rem;
            text-align: center;
            margin: 80px 0 40px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: slideIn 1s ease-out;
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 3rem;
            }
            
            .timeline-item:nth-child(odd),
            .timeline-item:nth-child(even) {
                text-align: left;
                padding-left: 40px;
                padding-right: 0;
            }
            
            .timeline::before {
                left: 10px;
            }
            
            .timeline-dot {
                left: 10px;
            }
        }
    </style>
</head>
<body>
    <!-- Floating particles -->
    <div class="particle" style="left: 10%; animation-delay: 0s;"></div>
    <div class="particle" style="left: 20%; animation-delay: 2s;"></div>
    <div class="particle" style="left: 30%; animation-delay: 4s;"></div>
    <div class="particle" style="left: 40%; animation-delay: 1s;"></div>
    <div class="particle" style="left: 50%; animation-delay: 3s;"></div>
    <div class="particle" style="left: 60%; animation-delay: 5s;"></div>
    <div class="particle" style="left: 70%; animation-delay: 2.5s;"></div>
    <div class="particle" style="left: 80%; animation-delay: 4.5s;"></div>
    <div class="particle" style="left: 90%; animation-delay: 1.5s;"></div>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <h1>Thembelihle Queeneth Maluka</h1>
            <p class="tagline">Full Stack Developer | Tech Enthusiast | Digital Dreamer</p>
            <div class="typing-text">Building Digital Dreams, One Line at a Time ✨</div>
        </div>
    </section>

    <!-- About Me Code Block -->
    <div class="container">
        <h2 class="section-header">👋 About Me</h2>
        <div class="code-section">
            <pre>
<span class="code-keyword">const</span> thembelihle = {
  <span class="code-string">pronouns</span>: <span class="code-string">"She/Her/Miss"</span>,
  <span class="code-string">location</span>: <span class="code-string">"South Africa 🇿🇦"</span>,
  <span class="code-string">education</span>: <span class="code-string">"Diploma in Computer Science @ TUT"</span>,
  <span class="code-string">experience</span>: <span class="code-number">16</span> <span class="code-comment">// months of excellence</span>,
  
  <span class="code-string">inspiration</span>: {
    <span class="code-string">movie</span>: <span class="code-string">"The Social Network"</span>,
    <span class="code-string">moment</span>: <span class="code-string">"Watching Zuckerberg code Facebook"</span>,
    <span class="code-string">result</span>: <span class="code-string">"Fell in love with tech 💙"</span>
  },
  
  <span class="code-string">passion</span>: [<span class="code-string">"Web Development"</span>, <span class="code-string">"Full Stack"</span>, <span class="code-string">"Innovation"</span>],
  <span class="code-string">hobbies</span>: [<span class="code-string">"📚 Reading"</span>, <span class="code-string">"🎬 Movies"</span>, <span class="code-string">"📺 Series"</span>],
  
  <span class="code-string">currentGoal</span>: <span class="code-string">"Join an innovative tech company"</span>,
  <span class="code-string">philosophy</span>: <span class="code-string">"Dream big. Code bigger. 🚀"</span>
};
            </pre>
        </div>

        <!-- Tech Stack -->
        <h2 class="section-header">💻 Tech Arsenal</h2>
        <div class="tech-stack">
            <div class="tech-item">
                <h3>Frontend</h3>
                <p>HTML • CSS • JavaScript • TypeScript • React • React Native</p>
            </div>
            <div class="tech-item">
                <h3>Styling</h3>
                <p>TailwindCSS • Bootstrap • Figma</p>
            </div>
            <div class="tech-item">
                <h3>Backend</h3>
                <p>Node.js • Express • RESTful APIs</p>
            </div>
            <div class="tech-item">
                <h3>Databases</h3>
                <p>PostgreSQL • MySQL</p>
            </div>
            <div class="tech-item">
                <h3>Languages</h3>
                <p>Java • C#</p>
            </div>
            <div class="tech-item">
                <h3>Tools</h3>
                <p>Vercel • Swagger • Postman • Thunder</p>
            </div>
        </div>

        <!-- Journey Timeline -->
        <h2 class="section-header">🌈 My Journey</h2>
        <div class="timeline">
            <div class="timeline-item" style="animation-delay: 0.2s;">
                <div class="timeline-dot"></div>
                <h3>2020 🎬</h3>
                <p>Watched The Social Network - The spark that started it all</p>
            </div>
            <div class="timeline-item" style="animation-delay: 0.4s;">
                <div class="timeline-dot"></div>
                <h3>2021 💻</h3>
                <p>Started my coding journey - First line of code</p>
            </div>
            <div class="timeline-item" style="animation-delay: 0.6s;">
                <div class="timeline-dot"></div>
                <h3>2022 🎓</h3>
                <p>Enrolled at Tshwane University of Technology</p>
            </div>
            <div class="timeline-item" style="animation-delay: 0.8s;">
                <div class="timeline-dot"></div>
                <h3>2023 ✨</h3>
                <p>Graduated with Diploma in Computer Science</p>
            </div>
            <div class="timeline-item" style="animation-delay: 1s;">
                <div class="timeline-dot"></div>
                <h3>2024 🚀</h3>
                <p>16 months of professional experience crafting digital solutions</p>
            </div>
            <div class="timeline-item" style="animation-delay: 1.2s;">
                <div class="timeline-dot"></div>
                <h3>2025 🌟</h3>
                <p>Ready to build the future with innovation & passion</p>
            </div>
        </div>

        <!-- Contact -->
        <h2 class="section-header">📬 Let's Connect!</h2>
        <div class="contact-grid">
            <div class="contact-card" style="animation-delay: 0.2s;">
                <div class="contact-icon">📧</div>
                <h3>Email</h3>
                <p>malukathembelihle95@gmail.com</p>
            </div>
            <div class="contact-card" style="animation-delay: 0.4s;">
                <div class="contact-icon">📱</div>
                <h3>Phone</h3>
                <p>079 331 6193</p>
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer>
        <p class="footer-quote">"The best way to predict the future is to create it."</p>
        <p style="color: var(--gray); margin-top: 20px;">Made with 💙 by Thembelihle Queeneth Maluka</p>
    </footer>
</body>
</html>
