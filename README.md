<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mohamed Thabet - Frontend Developer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #667eea;
            --secondary: #764ba2;
            --accent: #f093fb;
            --dark: #1a1a2e;
            --light: #f5f7fa;
            --text-primary: #2c3e50;
            --text-secondary: #7f8c8d;
            --success: #00d4ff;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            color: var(--text-primary);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* ===== ANIMATIONS ===== */
        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
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

        @keyframes slideInLeft {
            from {
                opacity: 0;
                transform: translateX(-60px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        @keyframes slideInRight {
            from {
                opacity: 0;
                transform: translateX(60px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        @keyframes scaleIn {
            from {
                opacity: 0;
                transform: scale(0.9);
            }
            to {
                opacity: 1;
                transform: scale(1);
            }
        }

        @keyframes float {
            0%, 100% {
                transform: translateY(0px);
            }
            50% {
                transform: translateY(-15px);
            }
        }

        @keyframes glow {
            0%, 100% {
                box-shadow: 0 0 20px rgba(102, 126, 234, 0.3);
            }
            50% {
                box-shadow: 0 0 40px rgba(102, 126, 234, 0.6);
            }
        }

        @keyframes gradient {
            0% {
                background-position: 0% 50%;
            }
            50% {
                background-position: 100% 50%;
            }
            100% {
                background-position: 0% 50%;
            }
        }

        @keyframes shimmer {
            0% {
                background-position: -1000px 0;
            }
            100% {
                background-position: 1000px 0;
            }
        }

        @keyframes pulse {
            0%, 100% {
                opacity: 1;
            }
            50% {
                opacity: 0.7;
            }
        }

        /* ===== HEADER ===== */
        header {
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            color: white;
            padding: 100px 20px;
            text-align: center;
            position: relative;
            overflow: hidden;
            animation: fadeInDown 0.8s ease-out;
        }

        header::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 120"><path d="M0,50 Q300,0 600,50 T1200,50 L1200,120 L0,120 Z" fill="rgba(255,255,255,0.1)"></path></svg>');
            background-size: cover;
            animation: slideInLeft 1s ease-out;
        }

        header .content {
            position: relative;
            z-index: 2;
            max-width: 1000px;
            margin: 0 auto;
        }

        header h1 {
            font-size: 4rem;
            font-weight: 900;
            margin-bottom: 10px;
            text-shadow: 2px 2px 8px rgba(0,0,0,0.3);
            letter-spacing: -2px;
            animation: slideInLeft 0.8s ease-out 0.2s backwards;
        }

        header .subtitle {
            font-size: 1.5rem;
            opacity: 0.95;
            margin-bottom: 30px;
            font-weight: 300;
            letter-spacing: 1px;
            animation: slideInRight 0.8s ease-out 0.3s backwards;
        }

        .badges {
            display: flex;
            gap: 15px;
            justify-content: center;
            flex-wrap: wrap;
            margin-bottom: 30px;
            animation: fadeInUp 0.8s ease-out 0.4s backwards;
        }

        .badge {
            display: inline-block;
            padding: 10px 20px;
            background: rgba(255,255,255,0.15);
            border: 2px solid white;
            color: white;
            border-radius: 50px;
            font-size: 0.9rem;
            font-weight: 600;
            backdrop-filter: blur(10px);
            transition: all 0.3s cubic-bezier(0.34, 1.56, 0.64, 1);
            cursor: pointer;
        }

        .badge:hover {
            background: white;
            color: var(--primary);
            transform: translateY(-5px);
            box-shadow: 0 15px 35px rgba(0,0,0,0.2);
        }

        .social-links {
            display: flex;
            gap: 20px;
            justify-content: center;
            flex-wrap: wrap;
            animation: fadeInUp 0.8s ease-out 0.5s backwards;
        }

        .social-links a {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 50px;
            height: 50px;
            background: rgba(255,255,255,0.2);
            color: white;
            border-radius: 50%;
            transition: all 0.3s ease;
            text-decoration: none;
            font-size: 1.3rem;
        }

        .social-links a:hover {
            background: white;
            color: var(--primary);
            transform: translateY(-5px) scale(1.1);
        }

        /* ===== MAIN CONTENT ===== */
        .container {
            max-width: 1100px;
            margin: 0 auto;
            padding: 60px 20px;
        }

        section {
            margin-bottom: 80px;
            animation: fadeInUp 0.8s ease-out backwards;
        }

        section:nth-child(1) { animation-delay: 0.1s; }
        section:nth-child(2) { animation-delay: 0.2s; }
        section:nth-child(3) { animation-delay: 0.3s; }
        section:nth-child(4) { animation-delay: 0.4s; }
        section:nth-child(5) { animation-delay: 0.5s; }

        h2 {
            font-size: 2.5rem;
            margin-bottom: 40px;
            position: relative;
            display: inline-block;
            font-weight: 800;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 80px;
            height: 5px;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            border-radius: 3px;
            animation: slideInLeft 0.6s ease-out 0.3s backwards;
        }

        /* ===== CARDS ===== */
        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-bottom: 40px;
        }

        .card {
            background: white;
            border-radius: 15px;
            padding: 30px;
            box-shadow: 0 5px 20px rgba(0,0,0,0.08);
            transition: all 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
            border: 2px solid transparent;
            position: relative;
            overflow: hidden;
            animation: fadeInUp 0.6s ease-out backwards;
        }

        .card:nth-child(1) { animation-delay: 0.1s; }
        .card:nth-child(2) { animation-delay: 0.2s; }
        .card:nth-child(3) { animation-delay: 0.3s; }

        .card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
            transition: left 0.5s ease;
        }

        .card:hover::before {
            left: 100%;
        }

        .card:hover {
            transform: translateY(-15px);
            border-color: var(--primary);
            box-shadow: 0 20px 50px rgba(102, 126, 234, 0.25);
        }

        .card-icon {
            font-size: 3rem;
            margin-bottom: 15px;
            animation: float 3s ease-in-out infinite;
        }

        .card-title {
            font-size: 1.4rem;
            font-weight: 700;
            color: var(--text-primary);
            margin-bottom: 15px;
        }

        .card-text {
            color: var(--text-secondary);
            line-height: 1.8;
        }

        /* ===== EXPERIENCE SECTION ===== */
        .experience-item {
            background: white;
            border-radius: 15px;
            padding: 30px;
            margin-bottom: 25px;
            border-left: 5px solid var(--primary);
            box-shadow: 0 5px 20px rgba(0,0,0,0.08);
            transition: all 0.3s ease;
            animation: slideInLeft 0.6s ease-out backwards;
        }

        .experience-item:nth-child(1) { animation-delay: 0.1s; }
        .experience-item:nth-child(2) { animation-delay: 0.2s; }
        .experience-item:nth-child(3) { animation-delay: 0.3s; }

        .experience-item:hover {
            transform: translateX(10px);
            box-shadow: 0 15px 40px rgba(102, 126, 234, 0.2);
            border-left-color: var(--secondary);
        }

        .exp-header {
            display: flex;
            justify-content: space-between;
            align-items: start;
            margin-bottom: 15px;
        }

        .exp-title {
            font-size: 1.3rem;
            font-weight: 700;
            color: var(--text-primary);
        }

        .exp-date {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            padding: 5px 15px;
            border-radius: 20px;
            font-size: 0.85rem;
            font-weight: 600;
        }

        .exp-company {
            color: var(--text-secondary);
            margin-bottom: 15px;
            font-weight: 500;
        }

        .exp-points {
            list-style: none;
            margin: 15px 0;
        }

        .exp-points li {
            color: var(--text-secondary);
            padding: 8px 0 8px 25px;
            position: relative;
            line-height: 1.7;
        }

        .exp-points li::before {
            content: '▶';
            position: absolute;
            left: 0;
            color: var(--primary);
            font-size: 0.8rem;
        }

        .exp-tech {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
            margin-top: 15px;
        }

        .tech-tag {
            background: linear-gradient(135deg, rgba(102, 126, 234, 0.1), rgba(118, 75, 162, 0.1));
            color: var(--primary);
            padding: 6px 12px;
            border-radius: 20px;
            font-size: 0.85rem;
            font-weight: 600;
            border: 1px solid var(--primary);
            transition: all 0.3s ease;
        }

        .tech-tag:hover {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            transform: scale(1.05);
        }

        /* ===== SKILLS SECTION ===== */
        .skill-group {
            margin-bottom: 30px;
            animation: fadeInUp 0.6s ease-out backwards;
        }

        .skill-group:nth-child(1) { animation-delay: 0.1s; }
        .skill-group:nth-child(2) { animation-delay: 0.2s; }
        .skill-group:nth-child(3) { animation-delay: 0.3s; }
        .skill-group:nth-child(4) { animation-delay: 0.4s; }

        .skill-name {
            font-weight: 700;
            margin-bottom: 10px;
            color: var(--text-primary);
            font-size: 1.05rem;
            display: flex;
            justify-content: space-between;
        }

        .skill-bar {
            height: 10px;
            background: #e8e8e8;
            border-radius: 5px;
            overflow: hidden;
            position: relative;
        }

        .skill-bar::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            bottom: 0;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            border-radius: 5px;
            animation: slideInRight 1s cubic-bezier(0.34, 1.56, 0.64, 1) forwards;
        }

        .skill-group:nth-child(1) .skill-bar::after { width: 95%; animation-delay: 0.3s; }
        .skill-group:nth-child(2) .skill-bar::after { width: 90%; animation-delay: 0.4s; }
        .skill-group:nth-child(3) .skill-bar::after { width: 85%; animation-delay: 0.5s; }
        .skill-group:nth-child(4) .skill-bar::after { width: 80%; animation-delay: 0.6s; }

        /* ===== PROJECT CARDS ===== */
        .project-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 20px rgba(0,0,0,0.08);
            transition: all 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
            animation: scaleIn 0.6s ease-out backwards;
        }

        .project-card:nth-child(1) { animation-delay: 0.1s; }
        .project-card:nth-child(2) { animation-delay: 0.2s; }
        .project-card:nth-child(3) { animation-delay: 0.3s; }

        .project-card:hover {
            transform: translateY(-15px);
            box-shadow: 0 20px 50px rgba(102, 126, 234, 0.3);
        }

        .project-header {
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            height: 150px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            position: relative;
            overflow: hidden;
        }

        .project-header::after {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: rgba(255,255,255,0.1);
            animation: slideInRight 0.6s ease-out;
        }

        .project-content {
            padding: 25px;
        }

        .project-name {
            font-size: 1.3rem;
            font-weight: 700;
            color: var(--text-primary);
            margin-bottom: 10px;
        }

        .project-desc {
            color: var(--text-secondary);
            line-height: 1.7;
            margin-bottom: 15px;
        }

        /* ===== FOOTER ===== */
        footer {
            background: linear-gradient(135deg, var(--dark) 0%, #2a2a4e 100%);
            color: white;
            text-align: center;
            padding: 50px 20px;
            margin-top: 80px;
            position: relative;
            overflow: hidden;
        }

        footer::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(102, 126, 234, 0.1) 1px, transparent 1px);
            background-size: 40px 40px;
            animation: slideInLeft 20s linear infinite;
        }

        footer .content {
            position: relative;
            z-index: 1;
            max-width: 800px;
            margin: 0 auto;
        }

        .footer-title {
            font-size: 1.8rem;
            font-weight: 800;
            margin-bottom: 20px;
            animation: fadeInDown 0.8s ease-out;
        }

        .footer-text {
            font-size: 1.1rem;
            opacity: 0.9;
            margin-bottom: 30px;
            animation: fadeInUp 0.8s ease-out 0.1s backwards;
        }

        .footer-links {
            display: flex;
            gap: 20px;
            justify-content: center;
            flex-wrap: wrap;
            margin-bottom: 30px;
            animation: fadeInUp 0.8s ease-out 0.2s backwards;
        }

        .footer-links a {
            color: var(--success);
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            position: relative;
        }

        .footer-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--success);
            transition: width 0.3s ease;
        }

        .footer-links a:hover::after {
            width: 100%;
        }

        .divider {
            height: 2px;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
            margin: 30px 0;
            animation: slideInLeft 0.8s ease-out 0.3s backwards;
        }

        .copyright {
            font-size: 0.95rem;
            opacity: 0.7;
            animation: fadeInUp 0.8s ease-out 0.4s backwards;
        }

        /* ===== RESPONSIVE ===== */
        @media (max-width: 768px) {
            header h1 {
                font-size: 2.5rem;
            }

            header .subtitle {
                font-size: 1.1rem;
            }

            h2 {
                font-size: 2rem;
            }

            .grid {
                grid-template-columns: 1fr;
            }

            .exp-header {
                flex-direction: column;
            }

            .exp-date {
                align-self: flex-start;
                margin-top: 10px;
            }

            .badges {
                gap: 10px;
            }

            .badge {
                padding: 8px 16px;
                font-size: 0.85rem;
            }
        }

        /* ===== SCROLL ANIMATION ===== */
        .reveal {
            opacity: 0;
            transform: translateY(30px);
            animation: fadeInUp 0.6s ease-out forwards;
        }
    </style>
</head>
<body>
    <!-- HEADER -->
    <header>
        <div class="content">
            <h1>👋 Mohamed Thabet</h1>
            <p class="subtitle">Frontend Developer | React & Next.js Specialist</p>
            
            <div class="badges">
                <span class="badge">⚛️ React Expert</span>
                <span class="badge">🚀 Next.js Pro</span>
                <span class="badge">🤖 AI Automation</span>
                <span class="badge">🌍 Open Opportunities</span>
            </div>

            <div class="social-links">
                <a href="mailto:mohamedthabet764@gmail.com" title="Email">📧</a>
                <a href="https://linkedin.com/in/mohamed-thabet7" target="_blank" title="LinkedIn">💼</a>
                <a href="https://github.com/Mohamed2Thabet" target="_blank" title="GitHub">💻</a>
                <a href="https://portfolio-ten-mauve-84.vercel.app" target="_blank" title="Portfolio">🔗</a>
            </div>
        </div>
    </header>

    <!-- MAIN CONTENT -->
    <div class="container">
        <!-- ABOUT SECTION -->
        <section>
            <h2>💼 About Me</h2>
            <div class="grid">
                <div class="card">
                    <div class="card-icon">🏗️</div>
                    <div class="card-title">Full-Stack Development</div>
                    <div class="card-text">Building end-to-end web applications from frontend UI to backend APIs with focus on performance and maintainability.</div>
                </div>
                <div class="card">
                    <div class="card-icon">🎨</div>
                    <div class="card-title">UI/UX Design</div>
                    <div class="card-text">Creating responsive, accessible interfaces that work seamlessly across all devices with modern CSS and components.</div>
                </div>
                <div class="card">
                    <div class="card-icon">⚡</div>
                    <div class="card-title">Performance</div>
                    <div class="card-text">Optimizing load times, reducing bundle sizes, and implementing efficient state management patterns.</div>
                </div>
            </div>
        </section>

        <!-- TECH STACK -->
        <section>
            <h2>💻 Tech Stack</h2>
            <div class="grid">
                <div class="card">
                    <div class="card-icon">⚛️</div>
                    <div class="card-title">Frontend</div>
                    <div class="card-text">React.js, Next.js, TypeScript, Tailwind CSS, Redux Toolkit, TanStack Query, Framer Motion</div>
                </div>
                <div class="card">
                    <div class="card-icon">🔧</div>
                    <div class="card-title">Backend</div>
                    <div class="card-text">Node.js, Express.js, PostgreSQL, Prisma ORM, REST APIs, JWT, Microservices</div>
                </div>
                <div class="card">
                    <div class="card-icon">🛠️</div>
                    <div class="card-title">DevOps</div>
                    <div class="card-text">Git, GitHub, Vercel, Docker, CI/CD Pipelines, Linux, VS Code</div>
                </div>
            </div>
        </section>

        <!-- EXPERIENCE -->
        <section>
            <h2>🚀 Experience</h2>
            
            <div class="experience-item">
                <div class="exp-header">
                    <div>
                        <div class="exp-title">Frontend Developer Intern</div>
                        <div class="exp-company">Xavirgin (OPC) Private Limited</div>
                    </div>
                    <div class="exp-date">03/2026 – 07/2026</div>
                </div>
                <ul class="exp-points">
                    <li>Built marketplace with advanced search, filtering, and infinite scroll</li>
                    <li>Optimized client-side state management reducing re-renders</li>
                    <li>Developed Admin Dashboard modules for platform operations</li>
                    <li>Integrated REST APIs with TanStack Query for data synchronization</li>
                </ul>
                <div class="exp-tech">
                    <span class="tech-tag">React.js</span>
                    <span class="tech-tag">TanStack Query</span>
                    <span class="tech-tag">Tailwind CSS</span>
                    <span class="tech-tag">REST APIs</span>
                </div>
            </div>

            <div class="experience-item">
                <div class="exp-header">
                    <div>
                        <div class="exp-title">Freelance Frontend Developer</div>
                        <div class="exp-company">Rich Sea Clean</div>
                    </div>
                    <div class="exp-date">05/2026 – 06/2026</div>
                </div>
                <ul class="exp-points">
                    <li>Built 10+ reusable UI components for scalable architecture</li>
                    <li>Implemented SEO strategy with sitemap and social sharing</li>
                    <li>Integrated Resend API with fully responsive contact system</li>
                    <li>Deployed production build on Vercel with CI configuration</li>
                </ul>
                <div class="exp-tech">
                    <span class="tech-tag">Next.js 14</span>
                    <span class="tech-tag">TypeScript</span>
                    <span class="tech-tag">Framer Motion</span>
                    <span class="tech-tag">Resend API</span>
                </div>
            </div>

            <div class="experience-item">
                <div class="exp-header">
                    <div>
                        <div class="exp-title">Frontend Developer</div>
                        <div class="exp-company">Mahd E-Learning Platform</div>
                    </div>
                    <div class="exp-date">01/2025 – 07/2025</div>
                </div>
                <ul class="exp-points">
                    <li>Built full-stack e-learning platform with 3 user roles and RBAC</li>
                    <li>Implemented authentication and course management workflows</li>
                    <li>Developed responsive UI with Dark/Light/Accessibility modes</li>
                    <li>Deployed in production-like environment with microservices</li>
                </ul>
                <div class="exp-tech">
                    <span class="tech-tag">React.js</span>
                    <span class="tech-tag">Redux Toolkit</span>
                    <span class="tech-tag">Bootstrap</span>
                    <span class="tech-tag">REST APIs</span>
                </div>
            </div>
        </section>

        <!-- SKILLS -->
        <section>
            <h2>📊 Skills</h2>
            
            <div class="skill-group">
                <div class="skill-name">
                    <span>React & Next.js</span>
                    <span>95%</span>
                </div>
                <div class="skill-bar"></div>
            </div>

            <div class="skill-group">
                <div class="skill-name">
                    <span>TypeScript & JavaScript</span>
                    <span>90%</span>
                </div>
                <div class="skill-bar"></div>
            </div>

            <div class="skill-group">
                <div class="skill-name">
                    <span>State Management & APIs</span>
                    <span>85%</span>
                </div>
                <div class="skill-bar"></div>
            </div>

            <div class="skill-group">
                <div class="skill-name">
                    <span>Backend & Database</span>
                    <span>80%</span>
                </div>
                <div class="skill-bar"></div>
            </div>
        </section>

        <!-- PROJECTS -->
        <section>
            <h2>🏆 Projects</h2>
            <div class="grid">
                <div class="project-card">
                    <div class="project-header">🎓</div>
                    <div class="project-content">
                        <div class="project-name">Mahd E-Learning</div>
                        <div class="project-desc">Full-stack learning management system with role-based access control and adaptive themes.</div>
                        <div class="exp-tech">
                            <span class="tech-tag">React</span>
                            <span class="tech-tag">Redux</span>
                            <span class="tech-tag">Bootstrap</span>
                        </div>
                    </div>
                </div>

                <div class="project-card">
                    <div class="project-header">☁️</div>
                    <div class="project-content">
                        <div class="project-name">Lelam Marketplace</div>
                        <div class="project-desc">Advanced auction marketplace with search, filtering, infinite scroll, and optimized state management.</div>
                        <div class="exp-tech">
                            <span class="tech-tag">React</span>
                            <span class="tech-tag">TanStack Query</span>
                            <span class="tech-tag">Tailwind</span>
                        </div>
                    </div>
                </div>

                <div class="project-card">
                    <div class="project-header">🧹</div>
                    <div class="project-content">
                        <div class="project-name">Rich Sea Clean</div>
                        <div class="project-desc">SEO-optimized service platform with email integration and Vercel deployment.</div>
                        <div class="exp-tech">
                            <span class="tech-tag">Next.js</span>
                            <span class="tech-tag">TypeScript</span>
                            <span class="tech-tag">Framer Motion</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <!-- FOOTER -->
    <footer>
        <div class="content">
            <div class="footer-title">Let's Connect! 🚀</div>
            <p class="footer-text">Always excited to discuss new projects, collaborations, and opportunities.</p>
            
            <div class="footer-links">
                <a href="mailto:mohamedthabet764@gmail.com">📧 Email</a>
                <a href="https://linkedin.com/in/mohamed-thabet7" target="_blank">💼 LinkedIn</a>
                <a href="https://github.com/Mohamed2Thabet" target="_blank">💻 GitHub</a>
                <a href="https://portfolio-ten-mauve-84.vercel.app" target="_blank">🔗 Portfolio</a>
            </div>

            <div class="divider"></div>
            <p class="copyright">© 2026 Mohamed Thabet. Building scalable applications today, AI-powered solutions tomorrow. ❤️</p>
        </div>
    </footer>

    <script>
        // Smooth scroll reveal animation
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('reveal');
                    observer.unobserve(entry.target);
                }
            });
        }, observerOptions);

        document.querySelectorAll('section, footer').forEach(el => {
            observer.observe(el);
        });

        // Add hover effect to cards
        document.querySelectorAll('.card, .project-card, .experience-item').forEach(card => {
            card.addEventListener('mouseenter', function() {
                this.style.cursor = 'pointer';
            });
        });
    </script>
</body>
</html>
