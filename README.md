<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Akbar Khan Qalati - Web Developer Portfolio</title>
    
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;700;900&family=Orbitron:wght@400;700&display=swap" rel="stylesheet">
    
    <!-- Custom CSS for advanced effects -->
    <style>
        :root {
            --glow-purple: #ff00cc;
            --glow-teal: #00ff99;
            --dark-bg: #0a0a1a;
        }

        /* Set base font and background */
        body {
            font-family: 'Inter', sans-serif;
            background-color: var(--dark-bg);
            color: #d1d5db; /* Lighter gray for body text */
            overflow-x: hidden;
            scroll-behavior: smooth;
        }

        /* --- Header --- */
        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            z-index: 100;
            background: rgba(10, 10, 20, 0.5);
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }
        .nav-link {
            transition: color 0.3s;
        }
        .nav-link:hover {
            color: var(--glow-teal);
        }

        /* --- Custom Scrollbar --- */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: var(--dark-bg);
        }
        ::-webkit-scrollbar-thumb {
            background: linear-gradient(45deg, var(--glow-purple), var(--glow-teal));
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: linear-gradient(45deg, #ff40e6, #4dffb8);
        }

        /* --- New Liquid Glass Font Effect --- */
        .glass-font {
            font-family: 'Orbitron', sans-serif;
            font-weight: 700;
            color: rgba(255, 255, 255, 0.9);
            text-shadow: 0 0 8px rgba(0, 255, 153, 0.4), 0 0 20px rgba(0, 255, 153, 0.2);
        }


        /* --- Glass Morphism Panel --- */
        .glass-panel {
            background: rgba(20, 20, 40, 0.4);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border: 1.5px solid rgba(255, 255, 255, 0.1);
            border-radius: 16px;
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.2), 
                        inset 0 0 15px rgba(255, 255, 255, 0.05);
            transition: all 0.3s ease;
        }
        
        /* --- Liquid Glass Skill Icon --- */
        .skill-icon-container {
            width: 80px;
            height: 80px;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
            border-radius: 16px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 1rem;
            transition: transform 0.3s, box-shadow 0.3s;
        }
        .skill-card:hover .skill-icon-container {
            transform: scale(1.1);
            box-shadow: 0 0 20px rgba(0, 255, 153, 0.3);
        }
        .skill-icon-container svg {
            width: 40px;
            height: 40px;
            color: white;
            opacity: 0.9;
        }

        /* --- Neo-Brutalism Pulsing Border --- */
        .pulsing-border {
            position: relative;
            overflow: hidden;
        }
        .pulsing-border::before {
            content: '';
            position: absolute;
            top: 0; right: 0; bottom: 0; left: 0;
            z-index: -1;
            margin: -2px;
            border-radius: inherit;
            background: linear-gradient(45deg, var(--glow-purple), var(--glow-teal));
            opacity: 0;
            transition: opacity 0.3s ease-in-out;
        }
        .pulsing-border:hover::before {
            opacity: 1;
            animation: pulse-glow 2s infinite;
        }

        @keyframes pulse-glow {
            0%, 100% { transform: scale(1); filter: brightness(1); }
            50% { transform: scale(1.02); filter: brightness(1.5); }
        }
        
        /* --- Animated Gradient Button --- */
        .gradient-btn {
            background-image: linear-gradient(45deg, var(--glow-purple) 0%, var(--glow-teal) 50%, var(--glow-purple) 100%);
            background-size: 200% auto;
            transition: all 0.4s ease;
        }
        .gradient-btn:hover {
            background-position: right center;
            transform: scale(1.05);
        }

        /* --- Kinetic Typography (Scroll-based) --- */
        .kinetic-scroll {
            transition: transform 0.5s ease-out, opacity 0.5s ease-out;
            transform: scale(0.9);
            opacity: 0;
        }
        .kinetic-scroll.in-view {
            transform: scale(1);
            opacity: 1;
        }
        
        /* --- Floating Input Labels for Contact Form --- */
        .form-group {
            position: relative;
        }
        .form-input {
            background: rgba(0,0,0,0.2);
            border: 1px solid rgba(255, 255, 255, 0.2);
            transition: all 0.3s ease;
        }
        .form-label {
            position: absolute;
            left: 1rem;
            top: 0.85rem;
            pointer-events: none;
            transition: all 0.2s ease-out;
            color: rgba(255,255,255,0.6);
        }
        .form-input:focus + .form-label,
        .form-input:not(:placeholder-shown) + .form-label {
            top: -0.6rem;
            left: 0.75rem;
            font-size: 0.75rem;
            color: var(--glow-teal);
            padding: 0 0.25rem;
            background: var(--dark-bg);
        }
        .form-input:focus {
            border-color: var(--glow-teal);
            box-shadow: 0 0 10px var(--glow-teal);
        }
        
        #hero-canvas, #particle-canvas {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -2;
        }

        #project-details-section {
            display: none;
            transition: opacity 0.5s ease;
        }
        .project-detail-content {
            display: none;
        }
        .project-detail-content.active {
            display: block;
        }
        
        @media (max-width: 768px) {
            #hero-canvas {
                background: linear-gradient(-45deg, #0f0c29, #302b63, #24243e);
	            background-size: 400% 400%;
	            animation: gradient-bg 15s ease infinite;
            }
            .glass-font { font-size: 2.5rem; line-height: 1.2; }
            header .nav-links {
                display: none;
            }
        }
        
        @keyframes gradient-bg {
	        0% { background-position: 0% 50%; }
	        50% { background-position: 100% 50%; }
	        100% { background-position: 0% 50%; }
        }

        @media (prefers-reduced-motion: reduce) {
            *, *::before, *::after {
                animation-duration: 0.01ms !important;
                animation-iteration-count: 1 !important;
                transition-duration: 0.01ms !important;
                scroll-behavior: auto !important;
            }
        }
        
        #voice-indicator {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background-color: rgba(0, 255, 153, 0.8);
            color: #0a0a1a;
            padding: 10px 15px;
            border-radius: 50px;
            font-weight: bold;
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.3s, transform 0.3s;
            z-index: 1000;
        }
        #voice-indicator.active {
            opacity: 1;
            transform: translateY(0);
        }
        
        .footer-icon-container {
            width: 48px;
            height: 48px;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
            border-radius: 16px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            display: flex;
            align-items: center;
            justify-content: center;
            transition: transform 0.3s, background-color 0.3s;
        }
        .footer-icon-container:hover {
            transform: scale(1.1);
            background: rgba(0, 255, 153, 0.2);
        }
        .footer-icon-container svg {
            width: 24px;
            height: 24px;
            color: white;
            transition: color 0.3s;
        }
    </style>
</head>
<body class="bg-dark-bg">

    <header>
        <nav class="container mx-auto px-6 py-4 flex justify-between items-center">
            <a href="#hero" class="text-xl font-bold text-white">Akbar Qalati</a>
            <div class="nav-links space-x-8">
                 <a href="#skills" class="nav-link">Skills</a>
                 <a href="#projects" class="nav-link">Projects</a>
                 <a href="#bio" class="nav-link">About</a>
                 <a href="#contact" class="nav-link">Contact</a>
            </div>
        </nav>
    </header>

    <!-- Background Canvases -->
    <canvas id="hero-canvas"></canvas>
    <canvas id="particle-canvas"></canvas>
    
    <!-- Voice Command UI -->
    <div id="voice-indicator">Listening...</div>
    <button id="voice-btn" class="fixed bottom-5 right-5 z-50 p-3 rounded-full gradient-btn shadow-lg" title="Activate Voice Commands">
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="text-white"><path d="M12 2a3 3 0 0 0-3 3v7a3 3 0 0 0 6 0V5a3 3 0 0 0-3-3Z"/><path d="M19 10v2a7 7 0 0 1-14 0v-2"/><line x1="12" x2="12" y1="19" y2="22"/></svg>
    </button>
    <div id="reduce-motion-toggle" class="fixed bottom-5 left-5 z-50 p-3 rounded-full bg-gray-800 shadow-lg text-white cursor-pointer" title="Toggle Reduced Motion">
        <span>RM</span>
    </div>


    <main class="relative z-10">

        <!-- HERO SECTION -->
        <section id="hero" class="h-screen flex items-center justify-center md:justify-start px-8 md:px-16 lg:px-24">
            <div class="max-w-xl text-center md:text-left">
                <h1 class="text-4xl md:text-6xl lg:text-7xl glass-font leading-tight mb-4 kinetic-scroll">
                    Akbar Khan Qalati
                </h1>
                <p class="text-lg md:text-xl text-gray-300 mb-8 kinetic-scroll" style="transition-delay: 0.2s;">
                    Creative Web Developer specializing in Interactive and 3D Experiences.
                </p>
                <a href="#projects" class="gradient-btn text-white font-bold py-3 px-8 rounded-lg inline-block text-lg kinetic-scroll" style="transition-delay: 0.4s;">
                    View My Work
                </a>
            </div>
        </section>

        <!-- SKILLS MATRIX -->
        <section id="skills" class="py-24 px-4 sm:px-8">
            <div class="container mx-auto">
                <div class="glass-panel p-8 md:p-12">
                    <h2 class="text-4xl md:text-5xl glass-font text-center mb-16 kinetic-scroll">
                        Skills Matrix
                    </h2>
                    <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 lg:grid-cols-5 gap-8">
                        <div class="text-center flex flex-col items-center skill-card kinetic-scroll">
                            <div class="skill-icon-container">
                                 <svg role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>JavaScript</title><path d="M0 0h24v24H0V0zm22.034 18.256h-2.072v-2.008c0-1.524.84-2.28 1.932-2.28.6 0 1.02.24 1.32.72l1.524-.96c-.48-.84-1.38-1.44-2.88-1.44-2.28 0-3.6 1.44-3.6 3.96v2.008h-1.32v-8.04h2.22v1.2c.54-.96 1.5-1.56 2.76-1.56.24 0 .42.06.66.06v2.16c-.24-.06-.48-.06-.78-.06-1.26 0-2.1.78-2.1 2.22v4.02zM8.382 18.256V10.216h-2.1v-.008c0-1.524.84-2.28 1.932-2.28.6 0 1.02.24 1.32.72l1.524-.96c-.48-.84-1.38-1.44-2.88-1.44-2.28 0-3.6 1.44-3.6 3.96v6.96h2.22v1.14h3.6v-1.14H8.382z"/></svg>
                            </div>
                            <h3 class="font-bold text-xl">JavaScript</h3>
                        </div>
                         <div class="text-center flex flex-col items-center skill-card kinetic-scroll" style="transition-delay: 0.1s;">
                            <div class="skill-icon-container">
                                 <svg role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>React</title><path d="M12 2.162c-6.627 0-12 2.53-12 5.625s5.373 5.625 12 5.625 12-2.53 12-5.625S18.627 2.162 12 2.162zm0 9.75c-4.97 0-9-2.01-9-4.5s4.03-4.5 9-4.5 9 2.01 9 4.5-4.03 4.5-9 4.5zm0-2.25a2.25 2.25 0 100-4.5 2.25 2.25 0 000 4.5zM6.16 9.073l-2.05-3.55a9.887 9.887 0 0115.78 0l-2.05 3.55a5.16 5.16 0 00-11.68 0zm11.68 5.854l2.05 3.55a9.887 9.887 0 01-15.78 0l2.05-3.55a5.16 5.16 0 0011.68 0z"/></svg>
                            </div>
                            <h3 class="font-bold text-xl">React</h3>
                        </div>
                         <div class="text-center flex flex-col items-center skill-card kinetic-scroll" style="transition-delay: 0.2s;">
                            <div class="skill-icon-container">
                                 <svg role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>Three.js</title><path d="M.44 18.025L11.53 23.82l12.03-5.912-11.53-5.795L.44 18.025zm23.12-6.14L12.03 6.073.44 11.886l11.56 5.795 11.56-5.796zM11.53.18L.44 5.975l11.56 5.796L23.56 6.07.44.18z"/></svg>
                            </div>
                            <h3 class="font-bold text-xl">Three.js</h3>
                        </div>
                         <div class="text-center flex flex-col items-center skill-card kinetic-scroll" style="transition-delay: 0.3s;">
                            <div class="skill-icon-container">
                                 <svg role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>HTML5</title><path d="M1.5 0h21l-1.91 21.563L11.977 24l-8.565-2.438L1.5 0zm17.09 4.91L5.41 4.91l.213 2.622 10.125.002-.234 2.14-7.313.002.214 2.622 6.64.002-.254 2.453-4.14.002-.275 2.85L12 19.34l3.545-.96.48-5.59h-2.14l-.19 2.103-1.695.46L8.14 15.1l-.19-2.142h8.72l.33-4.195.19-2.14.17-2.622z"/></svg>
                            </div>
                            <h3 class="font-bold text-xl">HTML & CSS</h3>
                        </div>
                         <div class="text-center flex flex-col items-center skill-card kinetic-scroll" style="transition-delay: 0.4s;">
                            <div class="skill-icon-container">
                                <svg role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>WordPress</title><path d="M12 0c-6.627 0-12 5.373-12 12s5.373 12 12 12 12-5.373 12-12S18.627 0 12 0zm7.13 10.384l-3.328 8.825-3.327-8.825-1.974.001 5.3 12.018 5.303-12.018zM6.92 7.74l3.328 8.825 2.175-5.772-3.328-3.053zm3.723-3.054l-1.974 4.542-1.973-4.542h3.947zM4.773 13.926l-1.25-3.054h2.5L4.773 13.926z"/></svg>
                            </div>
                            <h3 class="font-bold text-xl">WordPress</h3>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- PROJECTS GALLERY -->
        <section id="projects" class="py-24 px-4 sm:px-8">
            <div class="container mx-auto">
                <div class="glass-panel p-8 md:p-12">
                    <h2 class="text-4xl md:text-5xl glass-font text-center mb-16 kinetic-scroll">
                        Project Gallery
                    </h2>
                    <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
                        <!-- Project Card -->
                        <div class="glass-panel pulsing-border project-card kinetic-scroll overflow-hidden">
                            <img src="https://placehold.co/600x400/1a1a2e/e0e0e0?text=E-commerce+Platform" alt="E-commerce Platform Project" class="w-full h-48 object-cover opacity-90">
                            <div class="p-6">
                                <h3 class="text-2xl font-bold mb-2 glass-font">Dynamic E-commerce Platform</h3>
                                <p class="text-gray-300 mb-4">A full-featured e-commerce website with a custom theme, product management, and a secure checkout process.</p>
                                <a href="#project-details-section" data-project="ecommerce" class="view-details-btn text-teal-300 hover:text-teal-100 font-semibold">View Details &rarr;</a>
                            </div>
                        </div>
                        <!-- Project Card 2 -->
                        <div class="glass-panel pulsing-border project-card kinetic-scroll overflow-hidden" style="transition-delay: 0.2s;">
                            <img src="https://placehold.co/600x400/1a1a2e/e0e0e0?text=Data+Visualization" alt="Data Visualization Project" class="w-full h-48 object-cover opacity-90">
                             <div class="p-6">
                                <h3 class="text-2xl font-bold mb-2 glass-font">Interactive Data Visualization</h3>
                                <p class="text-gray-300 mb-4">An interactive dashboard for visualizing complex datasets using D3.js and React, with dynamic charts and filters.</p>
                                <a href="#project-details-section" data-project="dataviz" class="view-details-btn text-teal-300 hover:text-teal-100 font-semibold">View Details &rarr;</a>
                            </div>
                        </div>
                        <!-- Project Card 3 -->
                        <div class="glass-panel pulsing-border project-card kinetic-scroll overflow-hidden" style="transition-delay: 0.4s;">
                           <img src="https://placehold.co/600x400/1a1a2e/e0e0e0?text=WebGL+Game+Proto" alt="WebGL Game Prototype" class="w-full h-48 object-cover opacity-90">
                           <div class="p-6">
                                <h3 class="text-2xl font-bold mb-2 glass-font">Interactive WebGL Game Prototype</h3>
                                <p class="text-gray-300 mb-4">An exploration into gaming and animation design, featuring a 3D interactive experience built for the web.</p>
                                <a href="#project-details-section" data-project="game" class="view-details-btn text-teal-300 hover:text-teal-100 font-semibold">View Details &rarr;</a>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- PROJECT DETAILS SECTION (Initially Hidden) -->
        <section id="project-details-section" class="py-24 px-4 sm:px-8">
            <div class="container mx-auto max-w-4xl glass-panel p-8 md:p-12">
                <div class="relative">
                    <button id="close-details-btn" class="absolute -top-4 -right-4 md:-top-8 md:-right-8 text-white bg-red-500 rounded-full w-10 h-10 flex items-center justify-center text-2xl font-bold">&times;</button>
                    <!-- Detail Content for Project 1 -->
                    <div id="details-ecommerce" class="project-detail-content">
                        <h2 class="text-4xl glass-font mb-4">Dynamic E-commerce Platform</h2>
                        <p class="text-gray-300">This project involved building a responsive and performant online store from the ground up. I developed a custom WordPress theme that allows for easy product management and content updates. Key features include a mobile-first design, AJAX-powered cart, integration with popular payment gateways, and optimization for fast load times to ensure a smooth user experience.</p>
                    </div>
                    <!-- Detail Content for Project 2 -->
                    <div id="details-dataviz" class="project-detail-content">
                        <h2 class="text-4xl glass-font mb-4">Interactive Data Visualization</h2>
                        <p class="text-gray-300">I developed a web-based tool for visualizing complex data sets in an intuitive way. Using React for the user interface and D3.js for charting, I created a range of dynamic graphs and maps that allow users to filter, sort, and explore data in real-time. The goal was to transform raw numbers into compelling visual stories that are easy to understand.</p>
                    </div>
                    <!-- Detail Content for Project 3 -->
                    <div id="details-game" class="project-detail-content">
                        <h2 class="text-4xl glass-font mb-4">Interactive WebGL Game Prototype</h2>
                        <p class="text-gray-300">As part of my ongoing studies in animation and gaming, I created this interactive 3D prototype using WebGL and Three.js. It features a simple game mechanic, custom shaders for visual effects, and physics-based interactions. This project demonstrates my ability to blend technical programming skills with creative design principles to build engaging web-based experiences.</p>
                    </div>
                </div>
            </div>
        </section>


        <!-- BIO SECTION -->
        <section id="bio" class="py-24 px-4 sm:px-8">
             <div class="container mx-auto max-w-4xl glass-panel p-8 md:p-12 kinetic-scroll">
                <div class="flex flex-col md:flex-row items-center gap-8">
                    <img src="https://placehold.co/200x200/0a0a1a/ff00cc?text=AKQ" alt="AI-generated portrait of Akbar Khan Qalati" class="w-48 h-48 rounded-full border-2 border-purple-500 shadow-lg">
                    <div class="text-center md:text-left">
                        <h2 class="text-4xl glass-font mb-4">About Me</h2>
                        <p class="text-gray-300">
                           A dynamic and creative web developer with a passion for building beautiful and interactive digital experiences. With a solid foundation in computer science and specialized skills in web technologies, I excel at turning ideas into reality. I am currently enhancing my skills in animation and gaming design to create even more immersive web applications. I am committed to leveraging my technical expertise and creative vision to build the next generation of web software.
                        </p>
                    </div>
                </div>
            </div>
        </section>


        <!-- CONTACT SECTION -->
        <section id="contact" class="py-24 px-4 sm:px-8">
            <div class="container mx-auto max-w-2xl">
                <h2 class="text-4xl md:text-5xl glass-font text-center mb-12 kinetic-scroll">
                    Get In Touch
                </h2>
                <form id="contact-form" class="glass-panel p-8 md:p-12 space-y-8 kinetic-scroll">
                    <div class="form-group">
                        <input type="text" id="name" name="name" class="w-full p-3 rounded-lg form-input" placeholder=" " required>
                        <label for="name" class="form-label">Full Name</label>
                    </div>
                    <div class="form-group">
                        <input type="email" id="email" name="email" class="w-full p-3 rounded-lg form-input" placeholder=" " required>
                        <label for="email" class="form-label">Your Email Address</label>
                    </div>
                    <div class="form-group">
                        <textarea id="message" name="message" rows="5" class="w-full p-3 rounded-lg form-input" placeholder=" " required></textarea>
                        <label for="message" class="form-label">Your Message</label>
                    </div>
                    <div class="text-center">
                        <button type="submit" id="submit-btn" class="gradient-btn text-white font-bold py-3 px-12 rounded-lg text-lg">
                            Send Message
                        </button>
                    </div>
                </form>
            </div>
        </section>

    </main>

    <footer class="text-center py-8 text-gray-400 glass-panel mt-16">
        <div class="flex justify-center space-x-4 mb-6">
            <a href="https://www.linkedin.com/in/imakbarkhanqalati" target="_blank" rel="noopener noreferrer" class="footer-icon-container">
                <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24"><path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/></svg>
            </a>
            <a href="https://github.com/imakbarkhanqalati" target="_blank" rel="noopener noreferrer" class="footer-icon-container">
                <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24"><path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.91 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/></svg>
            </a>
            <a href="https://www.facebook.com/akqqalati/" target="_blank" rel="noopener noreferrer" class="footer-icon-container">
                <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24"><path d="M22.675 0h-21.35c-.732 0-1.325.593-1.325 1.325v21.351c0 .731.593 1.324 1.325 1.324h11.495v-9.294h-3.128v-3.622h3.128v-2.671c0-3.1 1.893-4.788 4.659-4.788 1.325 0 2.463.099 2.795.143v3.24l-1.918.001c-1.504 0-1.795.715-1.795 1.763v2.313h3.587l-.467 3.622h-3.12v9.293h6.116c.73 0 1.323-.593 1.323-1.325v-21.35c0-.732-.593-1.325-1.323-1.325z"/></svg>
            </a>
        </div>
        <p>&copy; 2025 Akbar Khan Qalati. All rights reserved.</p>
    </footer>

    <!-- Three.js Library -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>

    <script>
    document.addEventListener('DOMContentLoaded', () => {

        // --- FEATURE: REDUCE MOTION TOGGLE ---
        const reduceMotionToggle = document.getElementById('reduce-motion-toggle');
        let motionReduced = window.matchMedia('(prefers-reduced-motion: reduce)').matches;

        const updateMotionState = () => {
            document.body.classList.toggle('reduce-motion', motionReduced);
            if (motionReduced) {
                reduceMotionToggle.style.backgroundColor = 'var(--glow-teal)';
                reduceMotionToggle.title = 'Enable Motion';
            } else {
                reduceMotionToggle.style.backgroundColor = '#374151'; // bg-gray-700
                reduceMotionToggle.title = 'Disable Motion (Reduce)';
            }
        };

        reduceMotionToggle.addEventListener('click', () => {
            motionReduced = !motionReduced;
            updateMotionState();
        });

        updateMotionState();


        // --- 3D HERO SCENE (DESKTOP ONLY) ---
        let scene, camera, renderer, shapesGroup;
        const heroCanvas = document.getElementById('hero-canvas');

        function init3D() {
            if (window.innerWidth <= 768 || motionReduced) {
                if(renderer) { // Cleanup if exists
                    renderer.dispose();
                    if(heroCanvas.contains(renderer.domElement)) {
                        heroCanvas.removeChild(renderer.domElement);
                    }
                }
                return;
            };

            scene = new THREE.Scene();
            camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
            renderer = new THREE.WebGLRenderer({ canvas: heroCanvas, alpha: true });
            renderer.setSize(window.innerWidth, window.innerHeight);
            renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));

            // Create a group to hold the shapes
            shapesGroup = new THREE.Group();

            // Material with physical properties for a modern look
            const material = new THREE.MeshPhysicalMaterial({
                color: 0xff00cc,
                metalness: 0.1,
                roughness: 0.2,
                clearcoat: 1.0,
                clearcoatRoughness: 0.1,
                transmission: 0.5, // Simulates glass/plastic
                opacity: 0.8,
                transparent: true
            });
            
            // Floating shapes
            const geometry1 = new THREE.TorusKnotGeometry(1, 0.3, 128, 16);
            const shape1 = new THREE.Mesh(geometry1, material);
            shape1.position.set(-1.5, 0, 0);

            const geometry2 = new THREE.TetrahedronGeometry(1.2, 0);
            const shape2 = new THREE.Mesh(geometry2, material.clone());
            shape2.material.color.set(0x00ff99);
            shape2.position.set(1.5, 0, 0);

            shapesGroup.add(shape1);
            shapesGroup.add(shape2);
            scene.add(shapesGroup);

            // Lighting
            const ambientLight = new THREE.AmbientLight(0xffffff, 0.5);
            scene.add(ambientLight);
            const pointLight = new THREE.PointLight(0xffffff, 1);
            pointLight.position.set(5, 5, 5);
            scene.add(pointLight);

            camera.position.z = 5;

            animate3D();
        }

        const clock = new THREE.Clock();
        const pointer = new THREE.Vector2();

        function animate3D() {
            if (!renderer || motionReduced) return;
            requestAnimationFrame(animate3D);

            const elapsedTime = clock.getElapsedTime();

            // Animate shapes
            shapesGroup.rotation.y = elapsedTime * 0.1;
            shapesGroup.rotation.x = elapsedTime * 0.05;

            // Follow cursor
            shapesGroup.position.x += (pointer.x * 0.5 - shapesGroup.position.x) * 0.05;
            shapesGroup.position.y += (-pointer.y * 0.5 - shapesGroup.position.y) * 0.05;
            
            // Change color on scroll
            const scrollY = window.scrollY;
            const scrollMax = document.body.scrollHeight - window.innerHeight;
            const scrollPercent = Math.min(scrollY / 500, 1); // Only react to first 500px of scroll
            const colorA = new THREE.Color(0xff00cc);
            const colorB = new THREE.Color(0x3333ff);
            shapesGroup.children[0].material.color.lerpColors(colorA, colorB, scrollPercent);

            renderer.render(scene, camera);
        }

        // Handle mouse move for 3D scene
        window.addEventListener('mousemove', (event) => {
            pointer.x = (event.clientX / window.innerWidth) * 2 - 1;
            pointer.y = -(event.clientY / window.innerHeight) * 2 + 1;
        });


        // --- CURSOR PARTICLE TRAIL ---
        const particleCanvas = document.getElementById('particle-canvas');
        const ctx = particleCanvas.getContext('2d');
        particleCanvas.width = window.innerWidth;
        particleCanvas.height = window.innerHeight;
        let particlesArray = [];
        
        const mouse = { x: null, y: null };

        window.addEventListener('mousemove', (event) => {
            mouse.x = event.x;
            mouse.y = event.y;
            for (let i = 0; i < 2; i++) {
                particlesArray.push(new Particle());
            }
        });
        
        class Particle {
            constructor() {
                this.x = mouse.x;
                this.y = mouse.y;
                this.size = Math.random() * 2 + 1;
                this.speedX = Math.random() * 3 - 1.5;
                this.speedY = Math.random() * 3 - 1.5;
                this.color = `hsl(${Math.random() * 360}, 100%, 75%)`;
            }
            update() {
                this.x += this.speedX;
                this.y += this.speedY;
                if (this.size > 0.1) this.size -= 0.03;
            }
            draw() {
                ctx.fillStyle = this.color;
                ctx.beginPath();
                ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
                ctx.fill();
            }
        }

        function handleParticles() {
            if (motionReduced) {
                 ctx.clearRect(0, 0, particleCanvas.width, particleCanvas.height);
                 particlesArray = [];
                 return;
            }
            ctx.clearRect(0, 0, particleCanvas.width, particleCanvas.height);
            for (let i = 0; i < particlesArray.length; i++) {
                particlesArray[i].update();
                particlesArray[i].draw();
                if (particlesArray[i].size <= 0.1) {
                    particlesArray.splice(i, 1);
                    i--;
                }
            }
            requestAnimationFrame(handleParticles);
        }

        // --- KINETIC TYPOGRAPHY ON SCROLL ---
        const scrollElements = document.querySelectorAll('.kinetic-scroll');
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('in-view');
                }
            });
        }, { threshold: 0.1 });

        scrollElements.forEach(el => observer.observe(el));


        // --- PROJECT CARD TILT EFFECT ---
        const projectCards = document.querySelectorAll('.project-card');
        projectCards.forEach(card => {
            card.addEventListener('mousemove', e => {
                if (motionReduced) return;
                const rect = card.getBoundingClientRect();
                const x = e.clientX - rect.left;
                const y = e.clientY - rect.top;
                const { width, height } = rect;
                const rotateX = (y / height - 0.5) * -15; // Max rotation 7.5deg
                const rotateY = (x / width - 0.5) * 15;   // Max rotation 7.5deg
                card.style.transform = `perspective(1000px) rotateX(${rotateX}deg) rotateY(${rotateY}deg) scale3d(1.05, 1.05, 1.05)`;
            });
            card.addEventListener('mouseleave', () => {
                card.style.transform = 'perspective(1000px) rotateX(0) rotateY(0) scale3d(1, 1, 1)';
            });
        });


        // --- VOICE NAVIGATION ---
        const voiceBtn = document.getElementById('voice-btn');
        const voiceIndicator = document.getElementById('voice-indicator');
        const SpeechRecognition = window.SpeechRecognition || window.webkitSpeechRecognition;

        if (SpeechRecognition) {
            const recognition = new SpeechRecognition();
            recognition.continuous = false;
            recognition.lang = 'en-US';
            recognition.interimResults = false;
            recognition.maxAlternatives = 1;

            voiceBtn.addEventListener('click', () => {
                recognition.start();
            });

            recognition.onstart = () => {
                voiceIndicator.classList.add('active');
            };

            recognition.onspeechend = () => {
                recognition.stop();
                voiceIndicator.classList.remove('active');
            };
            
            recognition.onerror = () => {
                 voiceIndicator.classList.remove('active');
            }

            recognition.onresult = (event) => {
                const command = event.results[0][0].transcript.toLowerCase().trim();
                handleVoiceCommand(command);
            };

        } else {
            if (voiceBtn) {
                voiceBtn.style.display = 'none';
            }
        }

        function handleVoiceCommand(command) {
            console.log('Voice command:', command);
            let targetElement;
            if (command.includes('skill') || command.includes('skills')) {
                targetElement = document.getElementById('skills');
            } else if (command.includes('project') || command.includes('work')) {
                targetElement = document.getElementById('projects');
            } else if (command.includes('contact') || command.includes('connect')) {
                targetElement = document.getElementById('contact');
                const submitBtn = document.getElementById('submit-btn');
                submitBtn.style.animation = 'pulse-glow 1.5s 2';
                setTimeout(() => submitBtn.style.animation = '', 3000);
                document.getElementById('name').focus();
            } else if (command.includes('about') || command.includes('bio')) {
                targetElement = document.getElementById('bio');
            }

            if (targetElement) {
                targetElement.scrollIntoView({ behavior: 'smooth' });
            }
        }
        
        // --- WINDOW RESIZE HANDLING ---
        window.addEventListener('resize', () => {
            // Re-initialize canvases and 3D scene on resize
            particleCanvas.width = window.innerWidth;
            particleCanvas.height = window.innerHeight;

            if (renderer) {
                camera.aspect = window.innerWidth / window.innerHeight;
                camera.updateProjectionMatrix();
                renderer.setSize(window.innerWidth, window.innerHeight);
                renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));
            }
            
            // Debounce or throttle this if performance is an issue
            init3D();
        });

        // --- PROJECT DETAILS LOGIC ---
        const detailsSection = document.getElementById('project-details-section');
        const detailContents = document.querySelectorAll('.project-detail-content');
        const viewDetailsBtns = document.querySelectorAll('.view-details-btn');
        const closeDetailsBtn = document.getElementById('close-details-btn');

        viewDetailsBtns.forEach(btn => {
            btn.addEventListener('click', (e) => {
                e.preventDefault();
                const project = btn.getAttribute('data-project');
                
                // Hide all detail contents
                detailContents.forEach(content => content.classList.remove('active'));
                
                // Show the specific one
                const activeContent = document.getElementById(`details-${project}`);
                if (activeContent) {
                    activeContent.classList.add('active');
                }
                
                // Show the details section and scroll to it
                detailsSection.style.display = 'block';
                detailsSection.scrollIntoView({ behavior: 'smooth' });
            });
        });

        closeDetailsBtn.addEventListener('click', () => {
            detailsSection.style.display = 'none';
        });

        // --- CONTACT FORM HANDLING ---
        const contactForm = document.getElementById('contact-form');
        contactForm.addEventListener('submit', function(e) {
            e.preventDefault();
            
            const name = document.getElementById('name').value;
            const email = document.getElementById('email').value;
            const message = document.getElementById('message').value;

            const subject = `Message from ${name} via Portfolio`;
            const body = `Name: ${name}\nEmail: ${email}\n\nMessage:\n${message}`;

            const mailtoLink = `mailto:akq.qalati@gmail.com?subject=${encodeURIComponent(subject)}&body=${encodeURIComponent(body)}`;
            
            window.location.href = mailtoLink;
        });
        
        // --- FOOTER MAIL ICON FIX ---
        const mailIconLink = document.getElementById('mail-icon-link');
        if(mailIconLink) {
            mailIconLink.addEventListener('click', function(e) {
                e.preventDefault();
                window.location.href = 'mailto:akq.qalati@gmail.com';
            });
        }


        // --- INITIALIZE EVERYTHING ---
        init3D();
        handleParticles();
        
        // --- ANCHOR LINK HANDLING (for non-project links) ---
        document.querySelectorAll('a[href^="#"]:not(.view-details-btn)').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                const href = this.getAttribute('href');
                const targetElement = document.querySelector(href);
                if (targetElement) {
                    e.preventDefault();
                    targetElement.scrollIntoView({
                        behavior: 'smooth'
                    });
                }
            });
        });
    
    });
    </script>
</body>
</html>
