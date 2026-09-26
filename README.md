<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sourov Kumar Nandi | 3D Interactive CSE Portfolio & AI Research Profile (4K Ultra Edition)</title>
    
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;500;600;700&family=Inter:wght@300;400;500;600;700;800;900&family=Outfit:wght@400;600;700;800;900&display=swap" rel="stylesheet">
    
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        :root {
            --bg-primary: #05070c;
            --bg-secondary: #0b0f19;
            --bg-card: rgba(13, 19, 32, 0.7);
            --bg-card-hover: rgba(23, 32, 54, 0.85);
            --border-glow: rgba(0, 242, 254, 0.35);
            --border-light: rgba(255, 255, 255, 0.08);
            
            --accent-cyan: #00f2fe;
            --accent-blue: #38bdf8;
            --accent-teal: #00c7b7;
            --accent-emerald: #10b981;
            --accent-purple: #a855f7;
            --accent-pink: #ec4899;
            --orcid-green: #a6ce39;
            --linkedin-blue: #0a66c2;

            --text-primary: #f8fafc;
            --text-secondary: #94a3b8;
            --text-muted: #64748b;
            
            --radius-xl: 24px;
            --radius-lg: 16px;
            --radius-md: 12px;
            --radius-sm: 8px;

            --shadow-3d: 0 25px 50px -12px rgba(0, 0, 0, 0.7), 0 0 30px rgba(0, 242, 254, 0.15);
            --transition-smooth: all 0.35s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            -webkit-font-smoothing: antialiased;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Inter', sans-serif;
            background-color: var(--bg-primary);
            color: var(--text-primary);
            line-height: 1.6;
            overflow-x: hidden;
            position: relative;
        }

        /* 4K Canvas Background Particles */
        #bgCanvas {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            z-index: -1;
            pointer-events: none;
        }

        /* Container */
        .container {
            max-width: 1320px;
            margin: 0 auto;
            padding: 0 24px;
        }

        /* Click Shockwave Effect */
        .click-shockwave {
            position: fixed;
            border-radius: 50%;
            border: 2px solid var(--accent-cyan);
            pointer-events: none;
            z-index: 9999;
            animation: shockwaveExpand 0.6s ease-out forwards;
            box-shadow: 0 0 20px var(--accent-cyan), inset 0 0 15px var(--accent-cyan);
        }

        @keyframes shockwaveExpand {
            0% {
                width: 0px;
                height: 0px;
                opacity: 1;
                transform: translate(-50%, -50%) scale(0.2);
            }
            100% {
                width: 120px;
                height: 120px;
                opacity: 0;
                transform: translate(-50%, -50%) scale(1);
            }
        }

        /* Navbar */
        header {
            position: sticky;
            top: 0;
            z-index: 100;
            backdrop-filter: blur(25px);
            background: rgba(5, 7, 12, 0.8);
            border-bottom: 1px solid var(--border-light);
        }

        .nav-inner {
            display: flex;
            justify-content: space-between;
            align-items: center;
            height: 80px;
        }

        .logo {
            font-family: 'Outfit', sans-serif;
            font-size: 1.5rem;
            font-weight: 800;
            color: #fff;
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 12px;
            letter-spacing: -0.5px;
        }

        .logo-icon {
            width: 42px;
            height: 42px;
            background: linear-gradient(135deg, var(--accent-cyan), var(--accent-purple));
            border-radius: var(--radius-md);
            display: flex;
            align-items: center;
            justify-content: center;
            color: #000;
            font-size: 1.2rem;
            box-shadow: 0 0 20px rgba(0, 242, 254, 0.4);
            transition: var(--transition-smooth);
        }

        .logo:hover .logo-icon {
            transform: rotate(15deg) scale(1.1);
        }

        .nav-links {
            display: flex;
            gap: 32px;
            list-style: none;
        }

        .nav-links a {
            color: var(--text-secondary);
            text-decoration: none;
            font-size: 0.95rem;
            font-weight: 600;
            transition: var(--transition-smooth);
            position: relative;
            padding: 6px 0;
        }

        .nav-links a:hover {
            color: var(--accent-cyan);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: linear-gradient(90deg, var(--accent-cyan), var(--accent-purple));
            transition: var(--transition-smooth);
            border-radius: 2px;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        /* Interactive Clickable Elements */
        .click-active {
            transition: transform 0.15s cubic-bezier(0.4, 0, 0.2, 1), box-shadow 0.25s ease;
            cursor: pointer;
            user-select: none;
        }

        .click-active:active {
            transform: scale(0.95) rotate(-0.5deg) !important;
        }

        /* 3D Tilt Card Base */
        .tilt-3d {
            perspective: 1000px;
            transform-style: preserve-3d;
            transition: transform 0.1s ease, box-shadow 0.3s ease, border-color 0.3s ease;
            position: relative;
        }

        .tilt-3d-inner {
            transform-style: preserve-3d;
            transition: transform 0.3s ease;
        }

        .tilt-3d:hover .parallax-layer {
            transform: translateZ(35px);
        }

        /* Action Buttons */
        .btn-glow {
            background: linear-gradient(135deg, var(--accent-cyan), var(--accent-blue));
            color: #05070c;
            font-weight: 800;
            padding: 12px 26px;
            border-radius: var(--radius-md);
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 10px;
            font-size: 0.95rem;
            border: none;
            box-shadow: 0 4px 25px rgba(0, 242, 254, 0.35);
        }

        .btn-glow:hover {
            transform: translateY(-3px) scale(1.02);
            box-shadow: 0 8px 30px rgba(0, 242, 254, 0.55);
        }

        /* Hero Section */
        .hero {
            padding: 110px 0 80px;
            text-align: center;
            position: relative;
        }

        .badge-pill {
            display: inline-flex;
            align-items: center;
            gap: 10px;
            background: rgba(0, 242, 254, 0.08);
            border: 1px solid rgba(0, 242, 254, 0.3);
            color: var(--accent-cyan);
            padding: 8px 24px;
            border-radius: 40px;
            font-size: 0.95rem;
            font-weight: 700;
            margin-bottom: 30px;
            backdrop-filter: blur(12px);
            box-shadow: 0 0 25px rgba(0, 242, 254, 0.15);
            letter-spacing: 0.5px;
        }

        .hero h1 {
            font-family: 'Outfit', sans-serif;
            font-size: 4.5rem;
            font-weight: 900;
            letter-spacing: -1.8px;
            line-height: 1.1;
            margin-bottom: 22px;
            background: linear-gradient(180deg, #ffffff 0%, #cbd5e1 60%, #94a3b8 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .hero p.tagline {
            font-size: 1.35rem;
            color: var(--text-secondary);
            max-width: 860px;
            margin: 0 auto 44px;
            font-weight: 400;
            line-height: 1.7;
        }

        /* Keyword Links (NO direct raw URL display!) */
        .keyword-links-grid {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 18px;
            margin-bottom: 64px;
        }

        .kw-card {
            display: flex;
            align-items: center;
            gap: 12px;
            padding: 16px 32px;
            border-radius: var(--radius-lg);
            text-decoration: none;
            font-weight: 800;
            font-size: 1.1rem;
            transition: var(--transition-smooth);
            border: 1px solid var(--border-light);
            background: var(--bg-card);
            backdrop-filter: blur(20px);
            box-shadow: 0 15px 35px rgba(0,0,0,0.4);
            transform-style: preserve-3d;
        }

        .kw-card i {
            font-size: 1.3rem;
            transition: transform 0.3s ease;
        }

        .kw-card:hover i {
            transform: scale(1.2) rotate(8deg);
        }

        /* Keyword link styles */
        .kw-card.kw-portfolio {
            border-color: rgba(0, 199, 183, 0.4);
            color: var(--accent-teal);
            background: linear-gradient(135deg, rgba(0, 199, 183, 0.12), rgba(13, 19, 32, 0.85));
        }
        .kw-card.kw-portfolio:hover {
            border-color: var(--accent-teal);
            box-shadow: 0 15px 40px rgba(0, 199, 183, 0.35);
            transform: translateY(-6px) scale(1.04);
        }

        .kw-card.kw-linkedin {
            border-color: rgba(10, 102, 194, 0.4);
            color: #38bdf8;
            background: linear-gradient(135deg, rgba(10, 102, 194, 0.12), rgba(13, 19, 32, 0.85));
        }
        .kw-card.kw-linkedin:hover {
            border-color: #38bdf8;
            box-shadow: 0 15px 40px rgba(10, 102, 194, 0.35);
            transform: translateY(-6px) scale(1.04);
        }

        .kw-card.kw-orcid {
            border-color: rgba(166, 206, 57, 0.4);
            color: var(--orcid-green);
            background: linear-gradient(135deg, rgba(166, 206, 57, 0.12), rgba(13, 19, 32, 0.85));
        }
        .kw-card.kw-orcid:hover {
            border-color: var(--orcid-green);
            box-shadow: 0 15px 40px rgba(166, 206, 57, 0.35);
            transform: translateY(-6px) scale(1.04);
        }

        .kw-card.kw-github {
            border-color: rgba(255, 255, 255, 0.25);
            color: #ffffff;
            background: linear-gradient(135deg, rgba(255, 255, 255, 0.1), rgba(13, 19, 32, 0.85));
        }
        .kw-card.kw-github:hover {
            border-color: #ffffff;
            box-shadow: 0 15px 40px rgba(255, 255, 255, 0.25);
            transform: translateY(-6px) scale(1.04);
        }

        /* 3D Parallax Metric Cards Grid */
        .metrics-3d-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 28px;
            margin: 0 auto;
        }

        .metric-card-3d {
            background: var(--bg-card);
            border: 1px solid var(--border-light);
            border-radius: var(--radius-xl);
            padding: 36px 28px;
            text-align: center;
            backdrop-filter: blur(20px);
            box-shadow: var(--shadow-3d);
            position: relative;
            overflow: hidden;
        }

        .metric-card-3d::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at var(--mx, 50%) var(--my, 50%), rgba(0, 242, 254, 0.15) 0%, transparent 60%);
            opacity: 0;
            transition: opacity 0.3s ease;
            pointer-events: none;
        }

        .metric-card-3d:hover::after {
            opacity: 1;
        }

        .metric-card-3d:hover {
            border-color: var(--border-glow);
            box-shadow: 0 30px 60px -15px rgba(0, 242, 254, 0.3);
        }

        .metric-icon {
            font-size: 2.4rem;
            margin-bottom: 14px;
            background: linear-gradient(135deg, var(--accent-cyan), var(--accent-purple));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .metric-num {
            font-family: 'Outfit', sans-serif;
            font-size: 3.4rem;
            font-weight: 900;
            color: #fff;
            line-height: 1;
        }

        .metric-txt {
            font-size: 1rem;
            color: var(--text-secondary);
            margin-top: 10px;
            font-weight: 500;
        }

        /* Section Layouts */
        section {
            padding: 90px 0;
            border-top: 1px solid var(--border-light);
        }

        .sec-header {
            margin-bottom: 56px;
        }

        .sec-title {
            font-family: 'Outfit', sans-serif;
            font-size: 2.4rem;
            font-weight: 800;
            display: flex;
            align-items: center;
            gap: 18px;
        }

        .sec-title i {
            color: var(--accent-cyan);
            background: rgba(0, 242, 254, 0.1);
            padding: 12px;
            border-radius: var(--radius-md);
            font-size: 1.6rem;
            box-shadow: 0 0 20px rgba(0, 242, 254, 0.2);
        }

        .sec-desc {
            color: var(--text-secondary);
            font-size: 1.1rem;
            margin-top: 10px;
        }

        /* Publications Cards (3D depth effect) */
        .pub-grid {
            display: flex;
            flex-direction: column;
            gap: 28px;
        }

        .pub-item {
            background: var(--bg-card);
            border: 1px solid var(--border-light);
            border-radius: var(--radius-xl);
            padding: 36px;
            display: grid;
            grid-template-columns: 100px 1fr auto;
            gap: 32px;
            align-items: center;
            backdrop-filter: blur(20px);
            position: relative;
        }

        .pub-item:hover {
            border-color: rgba(0, 242, 254, 0.45);
            transform: translateY(-5px) scale(1.01);
            box-shadow: 0 25px 50px rgba(0, 242, 254, 0.15);
        }

        .pub-badge-year {
            font-family: 'Outfit', sans-serif;
            font-size: 1.7rem;
            font-weight: 900;
            color: var(--accent-cyan);
            background: rgba(0, 242, 254, 0.1);
            border: 1px solid rgba(0, 242, 254, 0.25);
            padding: 18px;
            border-radius: var(--radius-lg);
            text-align: center;
            box-shadow: inset 0 0 15px rgba(0, 242, 254, 0.1);
        }

        .pub-info h3 {
            font-size: 1.3rem;
            font-weight: 700;
            margin-bottom: 12px;
            color: #fff;
            line-height: 1.45;
        }

        .pub-authors-venue {
            font-size: 0.98rem;
            color: var(--text-secondary);
            display: flex;
            flex-wrap: wrap;
            gap: 24px;
        }

        .pub-authors-venue span {
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .btn-kw-action {
            background: linear-gradient(135deg, rgba(56, 189, 248, 0.15), rgba(0, 242, 254, 0.12));
            color: var(--accent-blue);
            border: 1px solid rgba(56, 189, 248, 0.4);
            padding: 14px 24px;
            border-radius: var(--radius-md);
            text-decoration: none;
            font-weight: 800;
            font-size: 0.98rem;
            display: inline-flex;
            align-items: center;
            gap: 10px;
            transition: var(--transition-smooth);
            cursor: pointer;
        }

        .btn-kw-action:hover {
            background: var(--accent-blue);
            color: #05070c;
            box-shadow: 0 10px 30px rgba(56, 189, 248, 0.5);
            transform: translateY(-2px);
        }

        /* 3D Projects Cards Grid */
        .proj-3d-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(380px, 1fr));
            gap: 32px;
        }

        .proj-card {
            background: var(--bg-card);
            border: 1px solid var(--border-light);
            border-radius: var(--radius-xl);
            padding: 36px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            backdrop-filter: blur(20px);
            position: relative;
            overflow: hidden;
            box-shadow: var(--shadow-3d);
        }

        .proj-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 4px;
            background: linear-gradient(90deg, var(--accent-cyan), var(--accent-purple));
            opacity: 0;
            transition: var(--transition-smooth);
        }

        .proj-card:hover {
            border-color: rgba(168, 85, 247, 0.45);
            box-shadow: 0 30px 60px rgba(168, 85, 247, 0.2);
        }

        .proj-card:hover::before {
            opacity: 1;
        }

        .proj-head {
            font-family: 'Outfit', sans-serif;
            font-size: 1.45rem;
            font-weight: 800;
            color: #fff;
            margin-bottom: 16px;
            display: flex;
            align-items: center;
            gap: 14px;
        }

        .proj-desc {
            font-size: 1rem;
            color: var(--text-secondary);
            margin-bottom: 28px;
            line-height: 1.65;
        }

        .proj-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }

        .tag-pill {
            background: rgba(255, 255, 255, 0.06);
            border: 1px solid rgba(255, 255, 255, 0.12);
            color: var(--accent-cyan);
            font-family: 'Fira Code', monospace;
            font-size: 0.82rem;
            padding: 6px 14px;
            border-radius: var(--radius-sm);
        }

        /* Technical Arsenal Grid */
        .arsenal-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(290px, 1fr));
            gap: 28px;
        }

        .arsenal-box {
            background: var(--bg-card);
            border: 1px solid var(--border-light);
            border-radius: var(--radius-xl);
            padding: 32px;
            backdrop-filter: blur(20px);
        }

        .arsenal-title {
            font-size: 1.15rem;
            font-weight: 800;
            color: var(--accent-cyan);
            margin-bottom: 22px;
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .skills-wrap {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
        }

        .skill-item {
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(255, 255, 255, 0.12);
            color: #e2e8f0;
            padding: 10px 18px;
            border-radius: 30px;
            font-size: 0.92rem;
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 10px;
            transition: var(--transition-smooth);
        }

        .skill-item:hover {
            background: rgba(0, 242, 254, 0.15);
            border-color: var(--accent-cyan);
            transform: scale(1.06);
            color: #fff;
            box-shadow: 0 0 15px rgba(0, 242, 254, 0.2);
        }

        /* GitHub Profile Markdown Box */
        .md-box {
            background: var(--bg-secondary);
            border: 1px solid var(--border-light);
            border-radius: var(--radius-xl);
            padding: 36px;
            position: relative;
            backdrop-filter: blur(20px);
        }

        .md-box pre {
            font-family: 'Fira Code', monospace;
            font-size: 0.92rem;
            color: #6ee7b7;
            white-space: pre-wrap;
            word-break: break-word;
            max-height: 440px;
            overflow-y: auto;
            background: #030509;
            padding: 28px;
            border-radius: var(--radius-lg);
            border: 1px solid rgba(255, 255, 255, 0.05);
        }

        /* Interactive Publication Detail Modal */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            background: rgba(5, 7, 12, 0.88);
            backdrop-filter: blur(25px);
            z-index: 1000;
            display: flex;
            align-items: center;
            justify-content: center;
            opacity: 0;
            pointer-events: none;
            transition: var(--transition-smooth);
        }

        .modal-overlay.active {
            opacity: 1;
            pointer-events: auto;
        }

        .modal-card {
            background: var(--bg-secondary);
            border: 1px solid var(--border-glow);
            border-radius: var(--radius-xl);
            padding: 44px;
            max-width: 680px;
            width: 90%;
            box-shadow: 0 35px 70px rgba(0, 242, 254, 0.25);
            position: relative;
            transform: scale(0.88) translateY(30px);
            transition: var(--transition-smooth);
        }

        .modal-overlay.active .modal-card {
            transform: scale(1) translateY(0);
        }

        .modal-close {
            position: absolute;
            top: 24px;
            right: 24px;
            background: rgba(255, 255, 255, 0.1);
            color: #fff;
            border: none;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            cursor: pointer;
            font-size: 1.2rem;
            transition: var(--transition-smooth);
        }

        .modal-close:hover {
            background: var(--accent-pink);
            transform: rotate(90deg);
        }

        /* Toast Notification */
        .toast-msg {
            position: fixed;
            bottom: 40px;
            right: 40px;
            background: linear-gradient(135deg, var(--accent-emerald), #059669);
            color: #fff;
            font-weight: 800;
            padding: 18px 32px;
            border-radius: var(--radius-lg);
            box-shadow: 0 20px 40px rgba(16, 185, 129, 0.45);
            opacity: 0;
            transform: translateY(40px);
            transition: var(--transition-smooth);
            pointer-events: none;
            z-index: 2000;
            display: flex;
            align-items: center;
            gap: 14px;
            font-size: 1.05rem;
        }

        .toast-msg.show {
            opacity: 1;
            transform: translateY(0);
        }

        /* Footer */
        footer {
            padding: 60px 0;
            text-align: center;
            border-top: 1px solid var(--border-light);
            color: var(--text-muted);
            font-size: 0.98rem;
        }

        footer a {
            color: var(--text-secondary);
            text-decoration: none;
            font-weight: 700;
            margin: 0 10px;
            transition: var(--transition-smooth);
        }

        footer a:hover {
            color: var(--accent-cyan);
        }

        @media (max-width: 768px) {
            .hero h1 { font-size: 3rem; }
            .pub-item { grid-template-columns: 1fr; }
            .nav-links { display: none; }
        }
    </style>
</head>
<body>

    <!-- 4K Constellation Canvas -->
    <canvas id="bgCanvas"></canvas>

    <!-- Header / Navbar -->
    <header>
        <div class="container nav-inner">
            <a href="#" class="logo click-active">
                <div class="logo-icon"><i class="fa-solid fa-cube"></i></div>
                Sourov <span>Nandi</span>
            </a>
            <ul class="nav-links">
                <li><a href="#about" class="click-active">About</a></li>
                <li><a href="#publications" class="click-active">Publications</a></li>
                <li><a href="#projects" class="click-active">Projects</a></li>
                <li><a href="#skills" class="click-active">Skills</a></li>
                <li><a href="#markdown" class="click-active">GitHub Profile README</a></li>
            </ul>
            <button class="btn-glow click-active" onclick="copyMarkdown()">
                <i class="fa-solid fa-copy"></i> Copy README Markdown
            </button>
        </div>
    </header>

    <!-- Main Content Container -->
    <main class="container">

        <!-- Hero Section -->
        <section class="hero" id="about">
            <div class="badge-pill click-active">
                <i class="fa-solid fa-atom"></i> CSE Student & AI Researcher
            </div>
            <h1>Sourov Kumar Nandi</h1>
            <p class="tagline">
                Computer Science & Engineering undergraduate conducting research in <strong>Explainable AI (XAI)</strong>, 
                <strong>Graph Neural Networks</strong>, <strong>Time-Series Forecasting</strong>, and <strong>Data Engineering</strong>.
            </p>

            <!-- Keyword Links Grid (NO direct raw URLs displayed on screen!) -->
            <div class="keyword-links-grid">
                <a href="https://sourov-nandi.netlify.app/" target="_blank" class="kw-card kw-portfolio click-active tilt-3d">
                    <i class="fa-solid fa-globe"></i> Portfolio
                </a>
                <a href="https://www.linkedin.com/in/sourov-kumar-nandi/" target="_blank" class="kw-card kw-linkedin click-active tilt-3d">
                    <i class="fa-brands fa-linkedin"></i> LinkedIn
                </a>
                <a href="https://orcid.org/0009-0007-7266-6273" target="_blank" class="kw-card kw-orcid click-active tilt-3d">
                    <i class="fa-brands fa-orcid"></i> ORCID Profile
                </a>
                <a href="https://github.com/sourov-nandi" target="_blank" class="kw-card kw-github click-active tilt-3d">
                    <i class="fa-brands fa-github"></i> GitHub
                </a>
            </div>

            <!-- 3D Parallax Metric Cards -->
            <div class="metrics-3d-grid">
                <div class="metric-card-3d tilt-3d click-active">
                    <div class="metric-icon parallax-layer"><i class="fa-solid fa-book-open"></i></div>
                    <div class="metric-num parallax-layer">3</div>
                    <div class="metric-txt parallax-layer">Peer-Reviewed Papers (IEEE / Taylor & Francis)</div>
                </div>
                <div class="metric-card-3d tilt-3d click-active">
                    <div class="metric-icon parallax-layer"><i class="fa-solid fa-microchip"></i></div>
                    <div class="metric-num parallax-layer">3+</div>
                    <div class="metric-txt parallax-layer">Advanced Machine Learning & AI Projects</div>
                </div>
                <div class="metric-card-3d tilt-3d click-active">
                    <div class="metric-icon parallax-layer"><i class="fa-solid fa-award"></i></div>
                    <div class="metric-num parallax-layer">4</div>
                    <div class="metric-txt">Industry Simulations & Certifications</div>
                </div>
            </div>
        </section>

        <!-- Peer-Reviewed Research Publications Section -->
        <section id="publications">
            <div class="sec-header">
                <h2 class="sec-title">
                    <i class="fa-solid fa-feather-pointed"></i> Peer-Reviewed Research Publications
                </h2>
                <p class="sec-desc">Published research in machine learning, encrypted communication, and computer vision.</p>
            </div>

            <div class="pub-grid">
                <!-- Paper 1 -->
                <div class="pub-item tilt-3d click-active" onclick="openPaperModal(1)">
                    <div class="pub-badge-year parallax-layer">2025</div>
                    <div class="pub-info parallax-layer">
                        <h3>Human Activity Recognition in Real-Time: An Accessible Framework for Learning and Application</h3>
                        <div class="pub-authors-venue">
                            <span><i class="fa-solid fa-user-graduate"></i> Nandi, S. K. et al.</span>
                            <span><i class="fa-solid fa-building-columns"></i> Innovations in Computing, Taylor & Francis</span>
                        </div>
                    </div>
                    <a href="https://doi.org/10.1201/9781003652755-48" target="_blank" onclick="event.stopPropagation();" class="btn-kw-action click-active">
                        <i class="fa-solid fa-arrow-up-right-from-square"></i> DOI
                    </a>
                </div>

                <!-- Paper 2 -->
                <div class="pub-item tilt-3d click-active" onclick="openPaperModal(2)">
                    <div class="pub-badge-year parallax-layer">2025</div>
                    <div class="pub-info parallax-layer">
                        <h3>A Novel Framework for End-to-End Encrypted Peer-to-Peer Communication</h3>
                        <div class="pub-authors-venue">
                            <span><i class="fa-solid fa-user-graduate"></i> Nandi, S. K. et al.</span>
                            <span><i class="fa-solid fa-building-columns"></i> IEEE QPAIN 2025 Conference</span>
                        </div>
                    </div>
                    <a href="https://doi.org/10.1109/qpain66474.2025.11171978" target="_blank" onclick="event.stopPropagation();" class="btn-kw-action click-active">
                        <i class="fa-solid fa-arrow-up-right-from-square"></i> DOI
                    </a>
                </div>

                <!-- Paper 3 -->
                <div class="pub-item tilt-3d click-active" onclick="openPaperModal(3)">
                    <div class="pub-badge-year parallax-layer">2024</div>
                    <div class="pub-info parallax-layer">
                        <h3>Heart Health Forecasting with Machine Learning Techniques</h3>
                        <div class="pub-authors-venue">
                            <span><i class="fa-solid fa-user-graduate"></i> Nandi, S. K. et al.</span>
                            <span><i class="fa-solid fa-building-columns"></i> IEEE ISCS 2024 Conference</span>
                        </div>
                    </div>
                    <a href="https://doi.org/10.1109/iscs61804.2024.10581160" target="_blank" onclick="event.stopPropagation();" class="btn-kw-action click-active">
                        <i class="fa-solid fa-arrow-up-right-from-square"></i> DOI
                    </a>
                </div>
            </div>
        </section>

        <!-- 3D Projects Grid Section -->
        <section id="projects">
            <div class="sec-header">
                <h2 class="sec-title">
                    <i class="fa-solid fa-cube"></i> Featured Engineering & AI Projects
                </h2>
                <p class="sec-desc">Practically engineered architectures across Deep Learning, Financial Forecasting, and Medical Predictive Analytics.</p>
            </div>

            <div class="proj-3d-grid">
                <!-- Project 1 -->
                <div class="proj-card tilt-3d click-active">
                    <div class="parallax-layer">
                        <div class="proj-head">
                            <i class="fa-solid fa-brain" style="color: var(--accent-cyan);"></i> Climate-Financial Risk Intelligence
                        </div>
                        <p class="proj-desc">
                            Integrated multi-level Explainable AI (Grad-SHAP, Causal Pathways) with NGFS stress-testing to dynamically map physical climate anomalies to financial drawdowns.
                        </p>
                    </div>
                    <div class="proj-tags parallax-layer">
                        <span class="tag-pill">PyTorch</span>
                        <span class="tag-pill">GNNs</span>
                        <span class="tag-pill">Grad-SHAP</span>
                        <span class="tag-pill">Time-Series</span>
                    </div>
                </div>

                <!-- Project 2 -->
                <div class="proj-card tilt-3d click-active">
                    <div class="parallax-layer">
                        <div class="proj-head">
                            <i class="fa-solid fa-chart-line" style="color: var(--accent-blue);"></i> Google Stock Time-Series Forecasting
                        </div>
                        <p class="proj-desc">
                            Constructed SQL & Python data pipelines processing 13+ years of stock data using window functions and CTEs; deployed recurrent neural ensemble (RNN/LSTM/GRU) predictions.
                        </p>
                    </div>
                    <div class="proj-tags parallax-layer">
                        <span class="tag-pill">SQL</span>
                        <span class="tag-pill">Python</span>
                        <span class="tag-pill">LSTM / GRU</span>
                        <span class="tag-pill">Power BI</span>
                    </div>
                </div>

                <!-- Project 3 -->
                <div class="proj-card tilt-3d click-active">
                    <div class="parallax-layer">
                        <div class="proj-head">
                            <i class="fa-solid fa-heart-pulse" style="color: var(--accent-purple);"></i> Heart Disease Prediction System
                        </div>
                        <p class="proj-desc">
                            Exploratory data analysis and feature engineering on patient records, extracting key medical risk metrics for clinical decision support.
                        </p>
                    </div>
                    <div class="proj-tags parallax-layer">
                        <span class="tag-pill">Scikit-Learn</span>
                        <span class="tag-pill">Python</span>
                        <span class="tag-pill">EDA</span>
                        <span class="tag-pill">Healthcare ML</span>
                    </div>
                </div>
            </div>
        </section>

        <!-- Technical Arsenal Section -->
        <section id="skills">
            <div class="sec-header">
                <h2 class="sec-title">
                    <i class="fa-solid fa-wand-magic-sparkles"></i> Technical Arsenal
                </h2>
                <p class="sec-desc">Core languages, machine learning frameworks, data tools, and cloud infrastructure.</p>
            </div>

            <div class="arsenal-grid">
                <div class="arsenal-box tilt-3d">
                    <div class="arsenal-title"><i class="fa-solid fa-terminal"></i> Languages</div>
                    <div class="skills-wrap">
                        <div class="skill-item click-active"><i class="fa-brands fa-python" style="color:#38bdf8;"></i> Python</div>
                        <div class="skill-item click-active"><i class="fa-solid fa-database" style="color:#00c7b7;"></i> SQL</div>
                        <div class="skill-item click-active">C / C++</div>
                        <div class="skill-item click-active"><i class="fa-brands fa-java" style="color:#f97316;"></i> Java</div>
                        <div class="skill-item click-active"><i class="fa-brands fa-js" style="color:#eab308;"></i> JavaScript</div>
                    </div>
                </div>

                <div class="arsenal-box tilt-3d">
                    <div class="arsenal-title"><i class="fa-solid fa-robot"></i> AI & Machine Learning</div>
                    <div class="skills-wrap">
                        <div class="skill-item click-active">PyTorch</div>
                        <div class="skill-item click-active">TensorFlow</div>
                        <div class="skill-item click-active">Scikit-Learn</div>
                        <div class="skill-item click-active">OpenCV</div>
                        <div class="skill-item click-active">Pandas & NumPy</div>
                        <div class="skill-item click-active">Grad-SHAP (XAI)</div>
                    </div>
                </div>

                <div class="arsenal-box tilt-3d">
                    <div class="arsenal-title"><i class="fa-solid fa-cloud-bolt"></i> Cloud & Data Engineering</div>
                    <div class="skills-wrap">
                        <div class="skill-item click-active"><i class="fa-brands fa-aws" style="color:#ff9900;"></i> AWS (S3, Athena, Glue)</div>
                        <div class="skill-item click-active">MySQL</div>
                        <div class="skill-item click-active">ETL Pipelines</div>
                        <div class="skill-item click-active">Flask REST APIs</div>
                        <div class="skill-item click-active">Git / GitHub</div>
                    </div>
                </div>

                <div class="arsenal-box tilt-3d">
                    <div class="arsenal-title"><i class="fa-solid fa-chart-pie"></i> Analytics & Business BI</div>
                    <div class="skills-wrap">
                        <div class="skill-item click-active">Power BI</div>
                        <div class="skill-item click-active">Tableau</div>
                        <div class="skill-item click-active">DAX Modeling</div>
                        <div class="skill-item click-active">Matplotlib & Seaborn</div>
                    </div>
                </div>
            </div>
        </section>

        <!-- GitHub Profile Markdown Viewer Section -->
        <section id="markdown">
            <div class="sec-header">
                <h2 class="sec-title">
                    <i class="fa-brands fa-github"></i> GitHub Profile README.md Code
                </h2>
                <p class="sec-desc">Optimized markdown ready to paste directly into your GitHub profile repository (e.g. <code>sourov-nandi/README.md</code>).</p>
            </div>

            <div class="md-box tilt-3d">
                <button class="btn-glow click-active" style="position: absolute; top: 40px; right: 40px;" onclick="copyMarkdown()">
                    <i class="fa-solid fa-copy"></i> Copy README Markdown
                </button>
                <pre id="mdCode"># Hi there, I'm Sourov Kumar Nandi 👋

🎓 **Computer Science & Engineering Student | AI & Data Science Researcher**  
🔬 Specializing in **Machine Learning**, **Explainable AI (XAI)**, **Deep Learning**, and **Data Engineering**.

<p align="left">
  <a href="https://sourov-nandi.netlify.app/" target="_blank">
    <img src="https://img.shields.io/badge/Portfolio-Live_Website-00C7B7?style=for-the-badge&logo=netlify&logoColor=white" alt="Portfolio" />
  </a>
  <a href="https://www.linkedin.com/in/sourov-kumar-nandi/" target="_blank">
    <img src="https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" />
  </a>
  <a href="https://orcid.org/0009-0007-7266-6273" target="_blank">
    <img src="https://img.shields.io/badge/ORCID-Research_Profile-A6CE39?style=for-the-badge&logo=orcid&logoColor=white" alt="ORCID Profile" />
  </a>
  <a href="https://github.com/sourov-nandi" target="_blank">
    <img src="https://img.shields.io/badge/GitHub-Profile-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub Profile" />
  </a>
</p>

---

## ⚡ Executive Summary
- 🎓 **Academic Status**: Computer Science & Engineering (CSE) Student focused on cutting-edge AI and Data Systems.
- 📚 **Research Publications**: 3 Peer-Reviewed Papers in **IEEE** conferences and **Taylor & Francis** publications.
- 🎯 **Core Expertise**: Explainable AI (Grad-SHAP), Graph Neural Networks (GNNs), Time-Series Forecasting, PyTorch, SQL Data Engineering, and AWS Cloud Solutions.
- 🌐 **Quick Links**: [Portfolio](https://sourov-nandi.netlify.app/) | [LinkedIn](https://www.linkedin.com/in/sourov-kumar-nandi/) | [ORCID Profile](https://orcid.org/0009-0007-7266-6273) | [GitHub Profile](https://github.com/sourov-nandi)

---

## 🔬 Peer-Reviewed Research Publications

| Year | Paper Title & Authors | Venue / Publisher | Action / DOI |
| :---: | :--- | :---: | :---: |
| **2025** | **Human Activity Recognition in Real-Time: An Accessible Framework for Learning and Application**<br><sub>Nandi, S. K. et al.</sub> | *Innovations in Computing*, Taylor & Francis | [![View Paper](https://img.shields.io/badge/Paper-View_DOI-blue?style=flat-square&logo=doi)](https://doi.org/10.1201/9781003652755-48) |
| **2025** | **A Novel Framework for End-to-End Encrypted Peer-to-Peer Communication**<br><sub>Nandi, S. K. et al.</sub> | *IEEE QPAIN 2025* | [![View Paper](https://img.shields.io/badge/Paper-View_DOI-blue?style=flat-square&logo=doi)](https://doi.org/10.1109/qpain66474.2025.11171978) |
| **2024** | **Heart Health Forecasting with Machine Learning Techniques**<br><sub>Nandi, S. K. et al.</sub> | *IEEE ISCS 2024* | [![View Paper](https://img.shields.io/badge/Paper-View_DOI-blue?style=flat-square&logo=doi)](https://doi.org/10.1109/iscs61804.2024.10581160) |

---

## 📊 GitHub Analytics

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=sourov-nandi&show_icons=true&theme=dark&count_private=true" alt="Sourov Nandi Stats" width="48%" />
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=sourov-nandi&layout=compact&theme=dark" alt="Top Languages" width="48%" />
</p></pre>
            </div>
        </section>

    </main>

    <!-- Publication Detail Modal -->
    <div class="modal-overlay" id="paperModal">
        <div class="modal-card">
            <button class="modal-close" onclick="closePaperModal()"><i class="fa-solid fa-xmark"></i></button>
            <h2 id="modalPaperTitle" style="font-family: 'Outfit', sans-serif; font-size: 1.6rem; color: #fff; margin-bottom: 12px;">Paper Details</h2>
            <p id="modalPaperAuthors" style="color: var(--accent-cyan); font-weight: 600; margin-bottom: 16px;">Nandi, S. K. et al.</p>
            <p id="modalPaperVenue" style="color: var(--text-secondary); margin-bottom: 24px; font-size: 0.98rem;"></p>
            
            <div style="display: flex; gap: 16px;">
                <a id="modalDoiBtn" href="#" target="_blank" class="btn-glow click-active">
                    <i class="fa-solid fa-external-link"></i> View Full Paper DOI
                </a>
                <button class="btn-kw-action click-active" onclick="copyBibtex()">
                    <i class="fa-solid fa-quote-right"></i> Copy Citation
                </button>
            </div>
        </div>
    </div>

    <!-- Toast Notification -->
    <div class="toast-msg" id="toast">
        <i class="fa-solid fa-circle-check"></i> <span id="toastText">README Markdown Copied!</span>
    </div>

    <!-- Footer -->
    <footer>
        <div class="container">
            <p>© 2026 Sourov Kumar Nandi • Computer Science & Engineering Portfolio</p>
            <p style="margin-top: 12px;">
                <a href="https://sourov-nandi.netlify.app/" target="_blank" class="click-active">Portfolio</a> | 
                <a href="https://www.linkedin.com/in/sourov-kumar-nandi/" target="_blank" class="click-active">LinkedIn</a> | 
                <a href="https://orcid.org/0009-0007-7266-6273" target="_blank" class="click-active">ORCID Profile</a> | 
                <a href="https://github.com/sourov-nandi" target="_blank" class="click-active">GitHub Profile</a>
            </p>
        </div>
    </footer>

    <!-- 4K Interactive Engine Scripts -->
    <script>
        // 1. 4K Constellation Particle Network
        const canvas = document.getElementById('bgCanvas');
        const ctx = canvas.getContext('2d');
        let mouseX = 0, mouseY = 0;

        function resizeCanvas() {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        }
        resizeCanvas();
        window.addEventListener('resize', resizeCanvas);

        window.addEventListener('mousemove', (e) => {
            mouseX = e.clientX;
            mouseY = e.clientY;
        });

        const particles = Array.from({ length: 65 }, () => ({
            x: Math.random() * canvas.width,
            y: Math.random() * canvas.height,
            size: Math.random() * 2 + 1,
            vx: (Math.random() - 0.5) * 0.5,
            vy: (Math.random() - 0.5) * 0.5,
            alpha: Math.random() * 0.6 + 0.2
        }));

        function drawConstellation() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            
            for (let i = 0; i < particles.length; i++) {
                let p = particles[i];
                p.x += p.vx;
                p.y += p.vy;

                if (p.x < 0 || p.x > canvas.width) p.vx *= -1;
                if (p.y < 0 || p.y > canvas.height) p.vy *= -1;

                ctx.beginPath();
                ctx.arc(p.x, p.y, p.size, 0, Math.PI * 2);
                ctx.fillStyle = `rgba(0, 242, 254, ${p.alpha})`;
                ctx.fill();

                // Connect nearby particles
                for (let j = i + 1; j < particles.length; j++) {
                    let p2 = particles[j];
                    let dist = Math.hypot(p.x - p2.x, p.y - p2.y);
                    if (dist < 130) {
                        ctx.beginPath();
                        ctx.moveTo(p.x, p.y);
                        ctx.lineTo(p2.x, p2.y);
                        ctx.strokeStyle = `rgba(0, 242, 254, ${0.15 * (1 - dist / 130)})`;
                        ctx.lineWidth = 0.8;
                        ctx.stroke();
                    }
                }
            }
            requestAnimationFrame(drawConstellation);
        }
        drawConstellation();

        // 2. 3D Tilt Cursor Tracking Engine
        document.querySelectorAll('.tilt-3d').forEach(card => {
            card.addEventListener('mousemove', (e) => {
                const rect = card.getBoundingClientRect();
                const x = e.clientX - rect.left;
                const y = e.clientY - rect.top;
                const centerX = rect.width / 2;
                const centerY = rect.height / 2;

                const rotateX = ((y - centerY) / centerY) * -12;
                const rotateY = ((x - centerX) / centerX) * 12;

                card.style.transform = `perspective(1000px) rotateX(${rotateX}deg) rotateY(${rotateY}deg) translateZ(10px)`;
                card.style.setProperty('--mx', `${(x / rect.width) * 100}%`);
                card.style.setProperty('--my', `${(y / rect.height) * 100}%`);
            });

            card.addEventListener('mouseleave', () => {
                card.style.transform = 'perspective(1000px) rotateX(0deg) rotateY(0deg) translateZ(0px)';
            });
        });

        // 3. Shockwave Click Animation
        document.addEventListener('click', (e) => {
            const wave = document.createElement('div');
            wave.className = 'click-shockwave';
            wave.style.left = `${e.clientX}px`;
            wave.style.top = `${e.clientY}px`;
            document.body.appendChild(wave);
            setTimeout(() => wave.remove(), 600);
        });

        // 4. Modal Handler
        const papersData = {
            1: {
                title: "Human Activity Recognition in Real-Time: An Accessible Framework for Learning and Application",
                authors: "Sourov Kumar Nandi et al.",
                venue: "Innovations in Computing, Taylor & Francis (2025)",
                doi: "https://doi.org/10.1201/9781003652755-48"
            },
            2: {
                title: "A Novel Framework for End-to-End Encrypted Peer-to-Peer Communication",
                authors: "Sourov Kumar Nandi et al.",
                venue: "Proceedings of the 2025 IEEE International Conference on Quantum Photonics, AI, and Networking (QPAIN)",
                doi: "https://doi.org/10.1109/qpain66474.2025.11171978"
            },
            3: {
                title: "Heart Health Forecasting with Machine Learning Techniques",
                authors: "Sourov Kumar Nandi et al.",
                venue: "Proceedings of the 2024 IEEE International Conference on Intelligent Systems for Cybersecurity (ISCS)",
                doi: "https://doi.org/10.1109/iscs61804.2024.10581160"
            }
        };

        function openPaperModal(id) {
            const paper = papersData[id];
            if (!paper) return;
            document.getElementById('modalPaperTitle').innerText = paper.title;
            document.getElementById('modalPaperAuthors').innerText = paper.authors;
            document.getElementById('modalPaperVenue').innerText = paper.venue;
            document.getElementById('modalDoiBtn').href = paper.doi;
            document.getElementById('paperModal').classList.add('active');
        }

        function closePaperModal() {
            document.getElementById('paperModal').classList.remove('active');
        }

        function copyBibtex() {
            const text = `@article{nandi2025research,\n  author = {Nandi, Sourov Kumar et al.},\n  title = {${document.getElementById('modalPaperTitle').innerText}},\n  year = {2025}\n}`;
            navigator.clipboard.writeText(text).then(() => {
                showToast("Citation BibTeX Copied!");
            });
        }

        // 5. Toast Notification
        function showToast(msg) {
            const toast = document.getElementById('toast');
            document.getElementById('toastText').innerText = msg;
            toast.classList.add('show');
            setTimeout(() => toast.classList.remove('show'), 3000);
        }

        function copyMarkdown() {
            const code = document.getElementById('mdCode').innerText;
            navigator.clipboard.writeText(code).then(() => {
                showToast("GitHub README Markdown Copied!");
            });
        }
    </script>
</body>
</html>
