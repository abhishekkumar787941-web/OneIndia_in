<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Max India Multi-Speciality Hospital</title>
    <style>
        /* Base Styling & Theme Colors */
        :root {
            --primary: #0056b3;
            --secondary: #17a2b8; /* Teal medical accent */
            --emergency: #dc3545;
            --dark: #1e293b;
            --light: #f4f7f6;
            --transition: all 0.4s cubic-bezier(0.165, 0.84, 0.44, 1);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: #ffffff;
            color: var(--dark);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Scroll Animation Triggers */
        .reveal {
            opacity: 0;
            transform: translateY(40px);
            transition: var(--transition);
        }

        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* Fixed Navigation */
        header {
            background: #ffffff;
            box-shadow: 0 4px 20px rgba(0,0,0,0.05);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
        }

        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
            padding: 1.2rem 2rem;
        }

        .logo {
            font-size: 1.6rem;
            font-weight: 700;
            color: var(--primary);
            letter-spacing: 0.5px;
        }

        .logo span {
            color: var(--secondary);
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--dark);
            font-weight: 600;
            transition: var(--transition);
        }

        .nav-links a:hover {
            color: var(--primary);
        }

        /* Combined Hospital Building Visual Hero Section */
        .hero {
            margin-top: 75px;
            position: relative;
            background: linear-gradient(135deg, rgba(15, 32, 67, 0.95) 0%, rgba(0, 86, 179, 0.85) 100%), 
                        url('https://images.unsplash.com/photo-1587351021759-3e566b6af7cc?auto=format&fit=crop&w=1600&q=80') no-repeat center center/cover;
            padding: 8rem 2rem;
            color: white;
            text-align: center;
        }

        .hero-content {
            max-width: 850px;
            margin: 0 auto;
            z-index: 2;
            position: relative;
        }

        .hero h1 {
            font-size: 3.5rem;
            font-weight: 800;
            margin-bottom: 1.2rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            animation: fadeInDown 1s ease forwards;
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 2.5rem;
            color: #e2e8f0;
            font-weight: 300;
            animation: fadeInUp 1s ease 0.2s both;
        }

        .btn {
            display: inline-block;
            padding: 1rem 2.5rem;
            background: var(--secondary);
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            transition: var(--transition);
            box-shadow: 0 5px 15px rgba(23, 162, 184, 0.4);
        }

        .btn:hover {
            background: #138496;
            transform: translateY(-3px) scale(1.02);
            box-shadow: 0 8px 25px rgba(23, 162, 184, 0.6);
        }

        /* Bed & Ward Capacity Interactive Section */
        .bed-status-section {
            max-width: 1200px;
            margin: -50px auto 4rem;
            padding: 0 2rem;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            position: relative;
            z-index: 10;
        }

        .status-card {
            background: white;
            padding: 2rem;
            border-radius: 12px;
            box-shadow: 0 15px 35px rgba(0,0,0,0.08);
            display: flex;
            align-items: center;
            gap: 1.5rem;
            border-bottom: 4px solid var(--primary);
            transition: var(--transition);
        }

        .status-card:hover {
            transform: translateY(-5px);
        }

        /* Pulsing Glow Animation for Live Beds */
        .glow-indicator {
            width: 15px;
            height: 15px;
            background-color: #28a745;
            border-radius: 50%;
            display: inline-block;
            box-shadow: 0 0 0 0 rgba(40, 167, 69, 0.7);
            animation: pulseGlow 1.8s infinite;
        }

        .glow-indicator.critical {
            background-color: var(--emergency);
            box-shadow: 0 0 0 0 rgba(220, 53, 69, 0.7);
        }

        .status-info h3 {
            font-size: 2rem;
            color: var(--dark);
            font-weight: 700;
        }

        .status-info p {
            color: #64748b;
            font-size: 0.95rem;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }

        /* Interactive Tabs System */
        .categories-section {
            max-width: 1200px;
            margin: 5rem auto;
            padding: 0 2rem;
        }

        .section-title {
            text-align: center;
            font-size: 2.6rem;
            color: var(--primary);
            margin-bottom: 3rem;
            font-weight: 700;
        }

        .tab-container {
            background: var(--light);
            padding: 3rem;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.03);
        }

        .tab-menu {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin-bottom: 3rem;
            border-bottom: 2px solid #e2e8f0;
            padding-bottom: 1.5rem;
        }

        .tab-btn {
            padding: 0.8rem 2.2rem;
            border: none;
            background: none;
            font-size: 1.1rem;
            font-weight: 600;
            color: #64748b;
            cursor: pointer;
            transition: var(--transition);
            position: relative;
            border-radius: 8px;
        }

        .tab-btn:hover {
            color: var(--primary);
            background: rgba(0, 86, 179, 0.05);
        }

        .tab-btn.active {
            color: var(--primary);
            background: rgba(0, 86, 179, 0.08);
        }

        .tab-btn.active::after {
            content: '';
            position: absolute;
            bottom: -26px;
            left: 0;
            width: 100%;
            height: 4px;
            background: var(--primary);
            border-radius: 4px;
        }

        /* Smooth Tab Reveal Content */
        .tab-content {
            display: none;
        }

        .tab-content.active {
            display: block;
            animation: tabFadeIn 0.5s ease-out forwards;
        }

        /* Grid Categories & Advanced Hover Animations */
        .category-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
            gap: 2rem;
        }

        .grid-item {
            background: white;
            padding: 2rem;
            border-radius: 12px;
            border: 1px solid #e2e8f0;
            transition: var(--transition);
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        /* Dynamic Border Draw effect on hover */
        .grid-item::before {
            content: '';
            position: absolute;
            top: 0; left: 0; width: 0; height: 3px;
            background: var(--secondary);
            transition: var(--transition);
        }

        .grid-item:hover {
            transform: translateY(-8px);
            box-shadow: 0 12px 25px rgba(0,0,0,0.06);
            border-color: transparent;
        }

        .grid-item:hover::before {
            width: 100%;
        }

        .grid-item h4 {
            color: var(--primary);
            font-size: 1.25rem;
            margin-bottom: 0.6rem;
        }

        .grid-item p {
            color: #64748b;
            font-size: 0.95rem;
        }

        /* Critical Emergency Visual Panel */
        .emergency-box {
            background: #fff5f5;
            border-left: 6px solid var(--emergency);
            padding: 3rem;
            border-radius: 12px;
            box-shadow: 0 10px 25px rgba(220, 53, 69, 0.05);
        }
        
        .emergency-box h3 { 
            color: var(--emergency); 
            margin-bottom: 1.2rem; 
            font-size: 1.8rem;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        /* Footer Layout */
        footer {
            background: var(--dark);
            color: white;
            text-align: center;
            padding: 4rem 2rem;
            margin-top: 8rem;
        }

        /* CSS Keyframe Configurations */
        @keyframes fadeInDown {
            from { opacity: 0; transform: translateY(-30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes tabFadeIn {
            from { opacity: 0; transform: scale(0.98) translateY(10px); }
            to { opacity: 1; transform: scale(1) translateY(0); }
        }

        @keyframes pulseGlow {
            0% { transform: scale(0.95); box-shadow: 0 0 0 0 rgba(40, 167, 69, 0.5); }
            70% { transform: scale(1); box-shadow: 0 0 0 12px rgba(40, 167, 69, 0); }
            100% { transform: scale(0.95); box-shadow: 0 0 0 0 rgba(40, 167, 69, 0); }
        }

        /* Screen Size Adaptability fixes */
        @media (max-width: 768px) {
            .nav-links { display: none; }
            .hero h1 { font-size: 2.4rem; }
            .tab-menu { flex-direction: column; width: 100%; }
            .tab-btn.active::after { display: none; }
            .tab-container { padding: 1.5rem; }
        }
    </style>
</head>
<body>

    <!-- Header & Navigation Bar -->
    <header>
        <nav class="navbar">
            <div class="logo">Max <span>India</span></div>
            <ul class="nav-links">
                <li><a href="#">Home</a></li>
                <li><a href="#categories">Our Services</a></li>
                <li><a href="#beds">Live Bed Availability</a></li>
                <li><a href="#">Contact Support</a></li>
            </ul>
        </nav>
    </header>

    <!-- Modern Architecture Building Showcase Banner -->
    <section class="hero">
        <div class="hero-content">
            <h1>Max India Multi-Speciality</h1>
            <p>World-class medical infrastructure combined with elite clinical intelligence to engineer faster recoveries.</p>
            <a href="#categories" class="btn">View All Hospital Departments</a>
        </div>
    </section>

    <!-- Live Bed Monitoring & Capacity Status Widgets -->
    <section class="bed-status-section reveal" id="beds">
        <div class="status-card">
            <span class="glow-indicator"></span>
            <div class="status-info">
                <h3>420+</h3>
                <p>Active General Beds</p>
            </div>
        </div>
        <div class="status-card">
            <span class="glow-indicator"></span>
            <div class="status-info">
                <h3>85</h3>
                <p>Available Semi-Private Wards</p>
            </div>
        </div>
        <div class="status-card">
            <span class="glow-indicator critical" style="animation-name: pulseGlow;"></span>
            <div class="status-info">
                <h3>12</h3>
                <p>ICU / Critical Beds Free</p>
            </div>
        </div>
    </section>

    <!-- Categorization Tabs Setup -->
    <section class="categories-section reveal" id="categories">
        <h2 class="section-title">Hospital Directory</h2>
        
        <div class="tab-container">
            <!-- Tabs Navigation Row -->
            <div class="tab-menu">
                <button class="tab-btn active" onclick="switchTab(event, 'specialities')">Medical Specialities</button>
                <button class="tab-btn" onclick="switchTab(event, 'patient-care')">Diagnostics & Support</button>
                <button class="tab-btn" onclick="switchTab(event, 'emergency-panel')">Emergency & Critical Response</button>
            </div>

            <!-- Tab Content Panel 1 - Specialities -->
            <div id="specialities" class="tab-content active">
                <div class="category-grid">
                    <div class="grid-item">
                        <h4>Cardiology Division</h4>
                        <p>Advanced mapping, robotic angioplasty, and bypass infrastructure.</p>
                    </div>
                    <div class="grid-item">
                        <h4>Neurology Lab</h4>
                        <p>Intricate brain, nerve, and spinal column microsurgeries.</p>
                    </div>
                    <div class="grid-item">
                        <h4>Orthopedics & Joint</h4>
                        <p>Computer-assisted navigation systems for modern knee/hip replacements.</p>
                    </div>
                    <div class="grid-item">
                        <h4>Oncology Unit</h4>
                        <p>Targeted chemotherapy, linear accelerators, and comprehensive cancer care.</p>
                    </div>
                </div>
            </div>

            <!-- Tab Content Panel 2 - Diagnostics -->
            <div id="patient-care" class="tab-content">
                <div class="category-grid">
                    <div class="grid-item">
                        <h4>Advanced Radiology</h4>
                        <p>High-resolution modern MRI, 128-Slice CT scanners, and diagnostics.</p>
                    </div>
                    <div class="grid-item">
                        <h4>Automated Pathology</h4>
                        <p>Accurate, rapid, completely computerized blood panels open 24/7.</p>
                    </div>
                    <div class="grid-item">
                        <h4>Luxury Recovery Suites</h4>
                        <p>In-patient rooms calibrated for premium healing and comfort.</p>
                    </div>
                </div>
            </div>

            <!-- Tab Content Panel 3 - Emergency -->
            <div id="emergency-panel" class="tab-content">
                <div class="emergency-box">
                    <h3>Level-1 Trauma Center Emergency Response</h3>
                    <p style="margin-bottom: 1.2rem; color: #475569;">Max India hosts an aggressive critical response system tailored to prioritize life-threatening incidents immediately.</p>
                    <ul style="margin-left: 1.5rem; margin-bottom: 1.5rem; color: #475569; line-height: 2;">
                        <li>Cardiac ICU & advanced Neonatal intensive care infrastructure</li>
                        <li>GPS-integrated advanced life support tracking ambulances</li>
                        <li>In-house blood bank and surgical theaters on 0-minute standby</li>
                    </ul>
                    <strong style="font-size: 1.2rem; color: var(--emergency);">Emergency Hotline: +91 11-4202-7216</strong>
                </div>
            </div>
        </div>
    </section>

    <!-- Structural Footer -->
    <footer>
        <p>&copy; 2026 Max India Multi-Speciality Hospital Group. Engineered for life preservation.</p>
    </footer>

    <!-- Execution Scripts for Animations and Interactive Panels -->
    <script>
        // Interactive Tab Toggling Logic
        function switchTab(event, tabId) {
            const contents = document.querySelectorAll('.tab-content');
            contents.forEach(content => content.classList.remove('active'));

            const buttons = document.querySelectorAll('.tab-btn');
            buttons.forEach(btn => btn.classList.remove('active'));

            document.getElementById(tabId).classList.add('active');
            event.currentTarget.classList.add('active');
        }

        // Intersection Detector for Intercepting Scroll-Driven Animations
        function revealSections() {
            const reveals = document.querySelectorAll('.reveal');
            
            reveals.forEach(reveal => {
                const windowHeight = window.innerHeight;
                const elementTop = reveal.getBoundingClientRect().top;
                const elementVisible = 80; 

                if (elementTop < windowHeight - elementVisible) {
                    reveal.classList.add('active');
                }
            });
        }

        window.addEventListener('scroll', revealSections);
        window.addEventListener('load', revealSections);
    </script>
</body>
</html>
