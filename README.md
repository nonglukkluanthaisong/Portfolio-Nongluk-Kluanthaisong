<!DOCTYPE html>
<html lang="th" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nongluk Kluanthaisong - Premium Portfolio</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts (Inter & Sarabun) -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&family=Sarabun:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <!-- FontAwesome for Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <!-- Custom Theme Configuration -->
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Inter', 'Sarabun', 'sans-serif'],
                    },
                    colors: {
                        brand: {
                            50: '#f0f7ff',
                            100: '#e0effe',
                            300: '#7dd3fc',
                            500: '#0088ff', // Vibrant Cyan Blue
                            600: '#0066cc', // Premium Royal Blue
                            700: '#004fa3',
                            800: '#0f172a', // Deep Slate
                            900: '#020617',
                        }
                    }
                }
            }
        }
    </script>

    <style>
        /* Modern Glassmorphic Cards for White Theme */
        .glass-card {
            background: rgba(255, 255, 255, 0.75);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border: 1px solid rgba(0, 102, 204, 0.08);
            transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1);
        }
        .glass-card:hover {
            border-color: rgba(0, 102, 204, 0.25);
            box-shadow: 0 20px 40px rgba(0, 102, 204, 0.08);
            transform: translateY(-5px);
        }

        /* Subtle scroll animations */
        .reveal {
            opacity: 0;
            transform: translateY(40px) scale(0.97);
            transition: all 0.8s cubic-bezier(0.16, 1, 0.3, 1);
        }
        .reveal.active {
            opacity: 1;
            transform: translateY(0) scale(1);
        }

        /* Ambient Dynamic Floating Glow Backdrops for Soft Premium Feel */
        @keyframes float-slow {
            0% { transform: translate(0px, 0px) scale(1); }
            33% { transform: translate(40px, -40px) scale(1.1); }
            66% { transform: translate(-30px, 30px) scale(0.9); }
            100% { transform: translate(0px, 0px) scale(1); }
        }
        .glow-orb {
            position: absolute;
            border-radius: 50%;
            filter: blur(100px);
            opacity: 0.12;
            z-index: 0;
            pointer-events: none;
            animation: float-slow 18s infinite ease-in-out;
        }

        /* Horizontal Scrollbars Customization */
        .scrollbar-hide::-webkit-scrollbar {
            display: none;
        }
        .scrollbar-hide {
            -ms-overflow-style: none;  /* IE and Edge */
            scrollbar-width: none;  /* Firefox */
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
            height: 6px;
        }
        ::-webkit-scrollbar-track {
            background: #f1f5f9;
        }
        ::-webkit-scrollbar-thumb {
            background: #cbd5e1;
            border-radius: 9999px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #0066cc;
        }

        /* Running Glow Header Transition */
        header {
            transition: transform 0.4s cubic-bezier(0.16, 1, 0.3, 1), background-color 0.4s ease, border-color 0.4s ease;
        }
    </style>
</head>
<body class="bg-slate-50 text-slate-800 font-sans antialiased selection:bg-brand-500 selection:text-white overflow-x-hidden">

    <!-- Ambient Blur Background Orbs -->
    <div class="fixed inset-0 overflow-hidden pointer-events-none z-0">
        <div class="glow-orb bg-brand-500 w-[600px] h-[600px] top-[-10%] left-[-5%]"></div>
        <div class="glow-orb bg-indigo-400 w-[500px] h-[500px] bottom-[15%] right-[-5%] animate-pulse" style="animation-duration: 12s;"></div>
        <div class="glow-orb bg-cyan-400 w-[450px] h-[450px] top-[35%] left-[25%]"></div>
    </div>

    <!-- Smart Header -->
    <header id="mainHeader" class="fixed top-0 left-0 right-0 z-40 bg-white/80 backdrop-blur-md border-b border-slate-100 shadow-sm translate-y-0">
        <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8 h-20 flex items-center justify-between">
            <a href="#home" class="font-extrabold text-2xl tracking-wider text-slate-900">
                NONGLUK<span class="text-brand-600">.K</span>
            </a>
            
            <nav id="navMenu" class="hidden md:flex space-x-6 lg:space-x-8 text-sm font-semibold relative">
                <a href="#home" class="nav-item py-2 text-brand-600 transition-all duration-300 relative">Home<span class="nav-line absolute bottom-0 left-0 right-0 h-[3px] bg-brand-600 scale-x-100 transition-transform duration-300 origin-left"></span></a>
                <a href="#education" class="nav-item py-2 text-slate-500 hover:text-brand-600 transition-all duration-300 relative">Education<span class="nav-line absolute bottom-0 left-0 right-0 h-[3px] bg-brand-600 scale-x-0 transition-transform duration-300 origin-left"></span></a>
                <a href="#projects" class="nav-item py-2 text-slate-500 hover:text-brand-600 transition-all duration-300 relative">Works & Projects<span class="nav-line absolute bottom-0 left-0 right-0 h-[3px] bg-brand-600 scale-x-0 transition-transform duration-300 origin-left"></span></a>
                <a href="#certifications" class="nav-item py-2 text-slate-500 hover:text-brand-600 transition-all duration-300 relative">Certificates<span class="nav-line absolute bottom-0 left-0 right-0 h-[3px] bg-brand-600 scale-x-0 transition-transform duration-300 origin-left"></span></a>
                <a href="#activities" class="nav-item py-2 text-slate-500 hover:text-brand-600 transition-all duration-300 relative">Activities<span class="nav-line absolute bottom-0 left-0 right-0 h-[3px] bg-brand-600 scale-x-0 transition-transform duration-300 origin-left"></span></a>
            </nav>
            
            <div>
                <a href="#contact" class="inline-flex items-center justify-center px-5 py-2.5 rounded-full bg-brand-600 hover:bg-brand-500 text-white text-sm font-semibold transition-all duration-300 shadow-lg shadow-brand-600/10 hover:shadow-brand-500/35 transform hover:-translate-y-0.5">
                    Contact Me
                </a>
            </div>
        </div>
    </header>

    <!-- Home / Hero Section (Aligned with image_42fa1c_2.jpg design but using white-blue theme) -->
    <section id="home" class="pt-32 pb-20 md:pt-40 md:pb-28 min-h-screen flex items-center relative z-10">
        <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8 w-full">
            <div class="flex flex-col lg:flex-row items-center gap-12 lg:gap-16">
                
                <!-- Left Details Info -->
                <div class="flex-1 text-center lg:text-left space-y-6 md:space-y-8 reveal active">
                    <!-- Status Badge -->
                    <span class="inline-flex items-center gap-2 px-4 py-1.5 rounded-full text-xs font-bold bg-brand-50 border border-brand-100 text-brand-600 uppercase tracking-widest shadow-sm">
                        <span class="w-2.5 h-2.5 rounded-full bg-brand-500 animate-ping"></span>
                        Available for Internship: 1 Dec 2026 – 31 Mar 2027
                    </span>
                    
                    <!-- Main Title Heading -->
                    <div class="space-y-3">
                        <h1 class="text-5xl sm:text-7xl font-black tracking-tight text-slate-900 leading-tight">
                            Hi, I'm <span class="text-transparent bg-clip-text bg-gradient-to-r from-brand-600 via-brand-500 to-cyan-500">Nongluk</span>
                        </h1>
                        <p class="text-xl sm:text-2xl font-bold text-slate-700 tracking-wide font-mono">
                            Digital Business & Info Systems
                        </p>
                    </div>
                    
                    <!-- Description -->
                    <p class="text-base sm:text-lg text-slate-600 max-w-xl mx-auto lg:mx-0 leading-relaxed font-light">
                        A fourth-year Digital Business and Information Systems student. Passionate about data analysis, business process analysis, and leveraging digital workflows to optimize modern systems with analytics intelligence.
                    </p>

                    <!-- CTA Actions (Based on image_42fa1c_2.jpg but in white-blue) -->
                    <div class="flex flex-wrap justify-center lg:justify-start gap-4 pt-2">
                        <a href="#projects" class="px-8 py-4 rounded-xl bg-slate-900 hover:bg-slate-800 text-white font-bold transition-all duration-300 shadow-lg shadow-slate-900/20 flex items-center gap-3 transform hover:-translate-y-1">
                            View My Work
                            <i class="fa-solid fa-chevron-down text-sm"></i>
                        </a>
                        <button onclick="openCVModal()" class="px-8 py-4 rounded-xl bg-white hover:bg-slate-50 text-slate-700 border border-slate-200 hover:border-brand-500 font-bold transition-all duration-300 flex items-center gap-3 transform hover:-translate-y-1 shadow-sm">
                            <i class="fa-solid fa-file-invoice text-brand-600"></i>
                            Refer to Nongluk.cv.jpg
                        </button>
                    </div>

                    <!-- Horizontally Aligned Stats Counters -->
                    <div class="grid grid-cols-3 gap-6 sm:gap-10 pt-8 border-t border-slate-200/80 max-w-md mx-auto lg:mx-0">
                        <div class="space-y-1">
                            <h3 class="text-3xl sm:text-4xl font-black text-slate-900 font-mono tracking-tight flex items-baseline gap-1">
                                3.68<span class="text-xs text-brand-600 font-semibold">/4</span>
                            </h3>
                            <p class="text-xs font-semibold text-slate-400 uppercase tracking-wider">Current GPAX</p>
                        </div>
                        <div class="space-y-1">
                            <h3 class="text-3xl sm:text-4xl font-black text-slate-900 font-mono tracking-tight">
                                5+
                            </h3>
                            <p class="text-xs font-semibold text-slate-400 uppercase tracking-wider">Credentials</p>
                        </div>
                        <div class="space-y-1">
                            <h3 class="text-3xl sm:text-4xl font-black text-slate-900 font-mono tracking-tight">
                                3+
                            </h3>
                            <p class="text-xs font-semibold text-slate-400 uppercase tracking-wider">Main Projects</p>
                        </div>
                    </div>
                </div>

                <!-- Right Cover Image Slot (Clean Image from image_42fa1c_2.jpg - Single layer, elegant border, no multiple glass frames) -->
                <div class="flex-shrink-0 w-full max-w-[340px] sm:max-w-[380px] reveal active">
                    <div class="relative rounded-[2rem] overflow-hidden shadow-2xl shadow-slate-200 border-4 border-white bg-white group">
                        <!-- Main Portrait Image -->
                        <div class="aspect-[3/4] overflow-hidden">
                            <img src="Nongluk.cv.jpg" alt="Nongluk Kluanthaisong Portrait" class="w-full h-full object-cover transition-transform duration-750 group-hover:scale-105" onerror="this.onerror=null; this.src='https://images.unsplash.com/photo-1573496359142-b8d87734a5a2?q=80&w=600&auto=format&fit=crop';">
                        </div>
                        
                        <!-- Open to Internship floating pill (Exactly matching image_42fa1c_2.jpg orange badge style but in Blue) -->
                        <div class="absolute bottom-5 left-5 bg-gradient-to-r from-brand-600 to-cyan-500 text-white text-xs font-bold px-5 py-2.5 rounded-xl shadow-lg shadow-brand-600/30 flex items-center gap-2">
                            <span class="w-1.5 h-1.5 rounded-full bg-white animate-pulse"></span>
                            Open to Internship
                        </div>
                    </div>
                </div>

            </div>
        </div>
    </section>

    <!-- Education Section -->
    <section id="education" class="py-24 relative z-10 border-t border-slate-100 bg-white">
        <div class="max-w-5xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-16 reveal">
                <span class="text-xs font-bold text-brand-600 uppercase tracking-widest font-mono">Academic Timeline</span>
                <h2 class="text-3xl sm:text-4xl font-extrabold text-slate-900 mt-2">Education</h2>
                <div class="h-1 w-12 bg-brand-600 mx-auto mt-4 rounded-full"></div>
            </div>

            <div class="reveal">
                <div class="glass-card p-8 md:p-10 rounded-3xl relative overflow-hidden group shadow-sm">
                    <div class="absolute top-0 right-0 w-64 h-64 bg-brand-100/30 rounded-full blur-3xl pointer-events-none"></div>
                    
                    <div class="flex flex-col md:flex-row items-start md:items-center justify-between gap-6 pb-8 border-b border-slate-100">
                        <div class="flex items-center gap-5">
                            <div class="w-16 h-16 rounded-2xl bg-brand-50 border border-brand-100 flex items-center justify-center text-brand-600 flex-shrink-0 text-3xl shadow-sm">
                                <i class="fa-solid fa-graduation-cap"></i>
                            </div>
                            <div>
                                <h3 class="text-2xl font-extrabold text-slate-900">Mahasarakham University (MSU)</h3>
                                <p class="text-slate-500 font-medium">Mahasarakham Business School (MBS)</p>
                            </div>
                        </div>
                        <div class="bg-brand-50 text-brand-700 px-5 py-2 rounded-full text-xs font-bold border border-brand-100/50 font-mono">
                            June 2023 – Present (Expected: May 2027)
                        </div>
                    </div>

                    <div class="grid grid-cols-1 md:grid-cols-2 gap-8 pt-8">
                        <div>
                            <h4 class="text-xs font-bold uppercase tracking-wider text-slate-400">Degree Focus</h4>
                            <p class="text-lg font-bold text-slate-800 mt-1">B.A. in Digital Business and Information Systems</p>
                        </div>
                        <div class="flex flex-col sm:flex-row items-start sm:items-center gap-8">
                            <div>
                                <h4 class="text-xs font-bold uppercase tracking-wider text-slate-400">Current GPAX</h4>
                                <div class="flex items-baseline gap-1.5 mt-1">
                                    <span class="text-4xl font-black text-brand-600">3.68</span>
                                    <span class="text-slate-400 text-sm">/ 4.00</span>
                                </div>
                            </div>
                            <div class="sm:border-l sm:border-slate-100 sm:pl-8">
                                <h4 class="text-xs font-bold uppercase tracking-wider text-slate-400">Location</h4>
                                <p class="text-base font-semibold text-slate-700 mt-1.5">Mahasarakham, Thailand</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Works & Projects Section -->
    <section id="projects" class="py-24 relative z-10 border-t border-slate-100 bg-slate-50">
        <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-16 reveal">
                <span class="text-xs font-bold text-brand-600 uppercase tracking-widest font-mono">Academic Excellence</span>
                <h2 class="text-3xl sm:text-4xl font-extrabold text-slate-900 mt-2">Works & Projects</h2>
                <p class="text-slate-500 mt-2 text-sm sm:text-base">ผลงานและโครงการพัฒนาเว็บไซต์/โมเดลวิเคราะห์ข้อมูลที่ผ่านมา</p>
                <div class="h-1 w-12 bg-brand-600 mx-auto mt-4 rounded-full"></div>
            </div>

            <!-- Projects Grid -->
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <!-- Project 1 -->
                <div class="reveal glass-card rounded-3xl overflow-hidden flex flex-col group shadow-sm bg-white">
                    <div class="relative h-48 bg-slate-100 overflow-hidden">
                        <img src="https://images.unsplash.com/photo-1551288049-bebda4e38f71?q=80&w=800&auto=format&fit=crop" alt="Electricity Forecasting Work" class="w-full h-full object-cover opacity-90 group-hover:scale-105 transition-transform duration-500">
                        <div class="absolute inset-0 bg-gradient-to-t from-slate-900/60 to-transparent"></div>
                    </div>
                    <div class="p-6 flex-1 flex flex-col justify-between">
                        <div>
                            <div class="flex items-center justify-between mb-3">
                                <span class="bg-brand-50 text-brand-700 text-[10px] font-bold px-3 py-1 rounded-full border border-brand-100">DATA ANALYTICS</span>
                                <span class="text-[10px] text-slate-400 font-mono">Oct 2025</span>
                            </div>
                            <h3 class="text-xl font-bold text-slate-800 mb-2 group-hover:text-brand-600 transition-colors">Electricity Forecasting in Thailand</h3>
                            <p class="text-slate-600 text-xs leading-relaxed mb-4">
                                โครงการสร้างแบบจำลองคาดการณ์ปริมาณการใช้ไฟฟ้า โดยเตรียมข้อมูลดิบ (Data Cleaning) และใช้โมเดลวิเคราะห์แนวโน้มเพื่อจัดทำสถิติพลังงาน
                            </p>
                        </div>
                        <div class="bg-slate-50 border border-slate-100 p-3 rounded-xl flex items-start gap-2.5">
                            <i class="fa-solid fa-circle-check text-brand-600 text-xs mt-0.5"></i>
                            <p class="text-[11px] text-slate-500 font-medium">
                                Cleaned raw datasets, identified energy consumption behaviors & patterns.
                            </p>
                        </div>
                    </div>
                </div>

                <!-- Project 2 -->
                <div class="reveal glass-card rounded-3xl overflow-hidden flex flex-col group shadow-sm bg-white">
                    <div class="relative h-48 bg-slate-100 overflow-hidden">
                        <img src="https://images.unsplash.com/photo-1541462608143-67571c6738dd?q=80&w=800&auto=format&fit=crop" alt="TrueID UI/UX Redesign" class="w-full h-full object-cover opacity-90 group-hover:scale-105 transition-transform duration-500">
                        <div class="absolute inset-0 bg-gradient-to-t from-slate-900/60 to-transparent"></div>
                    </div>
                    <div class="p-6 flex-1 flex flex-col justify-between">
                        <div>
                            <div class="flex items-center justify-between mb-3">
                                <span class="bg-brand-50 text-brand-700 text-[10px] font-bold px-3 py-1 rounded-full border border-brand-100">UI/UX REDESIGN</span>
                                <span class="text-[10px] text-slate-400 font-mono">Nov 2024</span>
                            </div>
                            <h3 class="text-xl font-bold text-slate-800 mb-2 group-hover:text-brand-600 transition-colors">TrueID App Elevated Experience</h3>
                            <p class="text-slate-600 text-xs leading-relaxed mb-4">
                                ปรับปรุง UI/UX บนแอป TrueID ผ่าน User Research และวิเคราะห์ความต้องการเพื่อสร้าง Interactive Prototype ด้วยโปรแกรม Figma ที่ดียิ่งขึ้น
                            </p>
                        </div>
                        <div class="bg-slate-50 border border-slate-100 p-3 rounded-xl flex items-start gap-2.5">
                            <i class="fa-solid fa-circle-check text-brand-600 text-xs mt-0.5"></i>
                            <p class="text-[11px] text-slate-500 font-medium">
                                Designed high-fidelity layouts based on interactive user journeys in Figma.
                            </p>
                        </div>
                    </div>
                </div>

                <!-- Project 3 -->
                <div class="reveal glass-card rounded-3xl overflow-hidden flex flex-col group shadow-sm bg-white">
                    <div class="relative h-48 bg-slate-100 overflow-hidden">
                        <img src="https://images.unsplash.com/photo-1558591710-4b4a1ae0f04d?q=80&w=800&auto=format&fit=crop" alt="AR Interactive Museum" class="w-full h-full object-cover opacity-90 group-hover:scale-105 transition-transform duration-500">
                        <div class="absolute inset-0 bg-gradient-to-t from-slate-900/60 to-transparent"></div>
                    </div>
                    <div class="p-6 flex-1 flex flex-col justify-between">
                        <div>
                            <div class="flex items-center justify-between mb-3">
                                <span class="bg-brand-50 text-brand-700 text-[10px] font-bold px-3 py-1 rounded-full border border-brand-100">AUGMENTED REALITY</span>
                                <span class="text-[10px] text-slate-400 font-mono">Jan 2024</span>
                            </div>
                            <h3 class="text-xl font-bold text-slate-800 mb-2 group-hover:text-brand-600 transition-colors">AR Learning Media for Museum</h3>
                            <p class="text-slate-600 text-xs leading-relaxed mb-4">
                                การจัดทำสื่อการเรียนรู้จำลองจำลองด้วย AR เทคโนโลยี ผสานกราฟิกสามมิติ เพื่อส่งเสริมการเรียนรู้ที่ตื่นตาในยุคดิจิทัล
                            </p>
                        </div>
                        <div class="bg-slate-50 border border-slate-100 p-3 rounded-xl flex items-start gap-2.5">
                            <i class="fa-solid fa-circle-check text-brand-600 text-xs mt-0.5"></i>
                            <p class="text-[11px] text-slate-500 font-medium">
                                Created mockups integration mapping interactives with 3D model visual contents.
                            </p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Certifications Section (Single Horizontal Row) -->
    <section id="certifications" class="py-24 relative z-10 border-t border-slate-100 bg-white">
        <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
            
            <div class="flex flex-col sm:flex-row items-start sm:items-end justify-between mb-12 gap-4">
                <div class="reveal">
                    <span class="text-xs font-bold text-brand-600 uppercase tracking-widest font-mono">Verified Credentials</span>
                    <h2 class="text-3xl sm:text-4xl font-extrabold text-slate-900 mt-1">Certifications & Training</h2>
                    <p class="text-slate-500 mt-2 text-sm">ใบรับรองและประกาศนียบัตรวิชาชีพ (เลื่อนดูด้านข้างได้)</p>
                </div>
                
                <!-- Horizontal Scroll Controls -->
                <div class="flex items-center gap-3 reveal">
                    <button id="slideLeftBtn" class="w-12 h-12 rounded-xl bg-slate-50 hover:bg-brand-50 border border-slate-200 hover:border-brand-500 text-slate-700 hover:text-brand-600 flex items-center justify-center transition-all duration-300 shadow-sm" title="Slide Left">
                        <i class="fa-solid fa-chevron-left"></i>
                    </button>
                    <button id="slideRightBtn" class="w-12 h-12 rounded-xl bg-slate-50 hover:bg-brand-50 border border-slate-200 hover:border-brand-500 text-slate-700 hover:text-brand-600 flex items-center justify-center transition-all duration-300 shadow-sm" title="Slide Right">
                        <i class="fa-solid fa-chevron-right"></i>
                    </button>
                </div>
            </div>

            <!-- Single horizontal scrolling row -->
            <div id="certScrollContainer" class="flex gap-6 overflow-x-auto snap-x snap-mandatory scroll-smooth pb-4 scrollbar-hide">
                
                <!-- Cert 1 -->
                <div class="snap-start shrink-0 w-[300px] sm:w-[350px] glass-card rounded-3xl overflow-hidden flex flex-col group bg-slate-50/50">
                    <div class="relative aspect-[1.414/1] bg-slate-100 overflow-hidden cursor-pointer" onclick="openLightbox('https://images.unsplash.com/photo-1589330694653-ded6df03f754?q=80&w=800&auto=format&fit=crop', 'MSU English Exit Examination (CEFR B1)')">
                        <img src="https://images.unsplash.com/photo-1589330694653-ded6df03f754?q=80&w=800&auto=format&fit=crop" alt="MSU English Exit Exam Certificate" class="w-full h-full object-cover opacity-90 group-hover:scale-102 transition-transform duration-500">
                        <div class="absolute inset-0 bg-slate-900/30 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center">
                            <span class="bg-brand-600 text-white px-4 py-2 rounded-xl text-xs font-bold flex items-center gap-2 shadow-md">
                                <i class="fa-solid fa-expand"></i> View Certificate
                            </span>
                        </div>
                    </div>
                    <div class="p-6 flex-1 flex flex-col justify-between">
                        <div>
                            <div class="text-[10px] font-bold text-brand-600 uppercase tracking-wider mb-1 font-mono">Feb 2026</div>
                            <h4 class="text-base font-bold text-slate-800 group-hover:text-brand-600 transition-colors line-clamp-2">MSU English Exit Examination (CEFR B1)</h4>
                            <p class="text-xs text-slate-500 mt-2">ประเมินผ่านเกณฑ์สมรรถนะภาษาอังกฤษสำหรับนิสิตระดับปริญญาตรี มหาวิทยาลัยมหาสารคาม</p>
                        </div>
                        <div class="pt-4 border-t border-slate-200 mt-4 text-[11px] text-slate-400 flex items-center gap-1.5 font-mono">
                            <i class="fa-solid fa-university text-brand-600"></i> Mahasarakham University
                        </div>
                    </div>
                </div>

                <!-- Cert 2 -->
                <div class="snap-start shrink-0 w-[300px] sm:w-[350px] glass-card rounded-3xl overflow-hidden flex flex-col group bg-slate-50/50">
                    <div class="relative aspect-[1.414/1] bg-slate-100 overflow-hidden cursor-pointer" onclick="openLightbox('https://images.unsplash.com/photo-1620712943543-bcc4688e7485?q=80&w=800&auto=format&fit=crop', 'Generative AI & ChatGPT for Research')">
                        <img src="https://images.unsplash.com/photo-1620712943543-bcc4688e7485?q=80&w=800&auto=format&fit=crop" alt="Generative AI Certificate" class="w-full h-full object-cover opacity-90 group-hover:scale-102 transition-transform duration-500">
                        <div class="absolute inset-0 bg-slate-900/30 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center">
                            <span class="bg-brand-600 text-white px-4 py-2 rounded-xl text-xs font-bold flex items-center gap-2 shadow-md">
                                <i class="fa-solid fa-expand"></i> View Certificate
                            </span>
                        </div>
                    </div>
                    <div class="p-6 flex-1 flex flex-col justify-between">
                        <div>
                            <div class="text-[10px] font-bold text-brand-600 uppercase tracking-wider mb-1 font-mono">Dec 2025</div>
                            <h4 class="text-base font-bold text-slate-800 group-hover:text-brand-600 transition-colors line-clamp-2">Generative AI & ChatGPT for Research</h4>
                            <p class="text-xs text-slate-500 mt-2">ผ่านการศึกษาทักษะการส่งการเอไอสำหรับงานเอกสารและการวิเคราะห์ความรู้ธุรกิจเชิงดิจิทัล</p>
                        </div>
                        <div class="pt-4 border-t border-slate-200 mt-4 text-[11px] text-slate-400 flex items-center gap-1.5 font-mono">
                            <i class="fa-solid fa-graduation-cap text-brand-600"></i> Kasetsart University (KUMOOC)
                        </div>
                    </div>
                </div>

                <!-- Cert 3 -->
                <div class="snap-start shrink-0 w-[300px] sm:w-[350px] glass-card rounded-3xl overflow-hidden flex flex-col group bg-slate-50/50">
                    <div class="relative aspect-[1.414/1] bg-slate-100 overflow-hidden cursor-pointer" onclick="openLightbox('https://images.unsplash.com/photo-1460925895917-afdab827c52f?q=80&w=800&auto=format&fit=crop', 'Microsoft Power BI Certificate')">
                        <img src="https://images.unsplash.com/photo-1460925895917-afdab827c52f?q=80&w=800&auto=format&fit=crop" alt="Microsoft Power BI Certificate" class="w-full h-full object-cover opacity-90 group-hover:scale-102 transition-transform duration-500">
                        <div class="absolute inset-0 bg-slate-900/30 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center">
                            <span class="bg-brand-600 text-white px-4 py-2 rounded-xl text-xs font-bold flex items-center gap-2 shadow-md">
                                <i class="fa-solid fa-expand"></i> View Certificate
                            </span>
                        </div>
                    </div>
                    <div class="p-6 flex-1 flex flex-col justify-between">
                        <div>
                            <div class="text-[10px] font-bold text-brand-600 uppercase tracking-wider mb-1 font-mono">Jul 2025</div>
                            <h4 class="text-base font-bold text-slate-800 group-hover:text-brand-600 transition-colors line-clamp-2">Microsoft Power BI Professional Training</h4>
                            <p class="text-xs text-slate-500 mt-2">การอบรมพัฒนาความสามารถในการจัดทำแดชบอร์ดสรุปผลข้อมูล และจัดหมวดหมู่ฐานข้อมูลธุรกิจ</p>
                        </div>
                        <div class="pt-4 border-t border-slate-200 mt-4 text-[11px] text-slate-400 flex items-center gap-1.5 font-mono">
                            <i class="fa-solid fa-circle-check text-brand-600"></i> Qualification Institute
                        </div>
                    </div>
                </div>

                <!-- Cert 4 -->
                <div class="snap-start shrink-0 w-[300px] sm:w-[350px] glass-card rounded-3xl overflow-hidden flex flex-col group bg-slate-50/50">
                    <div class="relative aspect-[1.414/1] bg-slate-100 overflow-hidden cursor-pointer" onclick="openLightbox('https://images.unsplash.com/photo-1516321318423-f06f85e504b3?q=80&w=800&auto=format&fit=crop', 'IC3 Digital Literacy Certification')">
                        <img src="https://images.unsplash.com/photo-1516321318423-f06f85e504b3?q=80&w=800&auto=format&fit=crop" alt="IC3 Digital Literacy Certificate" class="w-full h-full object-cover opacity-90 group-hover:scale-102 transition-transform duration-500">
                        <div class="absolute inset-0 bg-slate-900/30 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center">
                            <span class="bg-brand-600 text-white px-4 py-2 rounded-xl text-xs font-bold flex items-center gap-2 shadow-md">
                                <i class="fa-solid fa-expand"></i> View Certificate
                            </span>
                        </div>
                    </div>
                    <div class="p-6 flex-1 flex flex-col justify-between">
                        <div>
                            <div class="text-[10px] font-bold text-brand-600 uppercase tracking-wider mb-1 font-mono">Feb 2025</div>
                            <h4 class="text-base font-bold text-slate-800 group-hover:text-brand-600 transition-colors line-clamp-2">IC3 Digital Literacy (GS6 Level 1)</h4>
                            <p class="text-xs text-slate-500 mt-2">ใบอนุญาตมาตรฐานสากลด้านความรู้ความเข้าใจเกี่ยวกับการประยุกต์ใช้เทคโนโลยีดิจิทัล</p>
                        </div>
                        <div class="pt-4 border-t border-slate-200 mt-4 text-[11px] text-slate-400 flex items-center gap-1.5 font-mono">
                            <i class="fa-solid fa-shield-halved text-brand-600"></i> Certiport (Pearson VUE)
                        </div>
                    </div>
                </div>

                <!-- Cert 5 -->
                <div class="snap-start shrink-0 w-[300px] sm:w-[350px] glass-card rounded-3xl overflow-hidden flex flex-col group bg-slate-50/50">
                    <div class="relative aspect-[1.414/1] bg-slate-100 overflow-hidden cursor-pointer" onclick="openLightbox('https://images.unsplash.com/photo-1557200134-90327ee9fafa?q=80&w=800&auto=format&fit=crop', 'LINE OA Business Growth Strategy')">
                        <img src="https://images.unsplash.com/photo-1557200134-90327ee9fafa?q=80&w=800&auto=format&fit=crop" alt="LINE OA Strategy Training" class="w-full h-full object-cover opacity-90 group-hover:scale-102 transition-transform duration-500">
                        <div class="absolute inset-0 bg-slate-900/30 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center">
                            <span class="bg-brand-600 text-white px-4 py-2 rounded-xl text-xs font-bold flex items-center gap-2 shadow-lg">
                                <i class="fa-solid fa-expand"></i> View Certificate
                            </span>
                        </div>
                    </div>
                    <div class="p-6 flex-1 flex flex-col justify-between">
                        <div>
                            <div class="text-[10px] font-bold text-brand-600 uppercase tracking-wider mb-1 font-mono">Dec 2024</div>
                            <h4 class="text-base font-bold text-slate-800 group-hover:text-brand-600 transition-colors line-clamp-2">LINE Official Account (LINE OA) Strategy</h4>
                            <p class="text-xs text-slate-500 mt-2">ทักษะและการวางกลยุทธ์ช่องทางแชทบรอดแคสต์ เพื่อขยายสัดส่วนผู้ติดตามและบริการลูกค้า</p>
                        </div>
                        <div class="pt-4 border-t border-slate-200 mt-4 text-[11px] text-slate-400 flex items-center gap-1.5 font-mono">
                            <i class="fa-solid fa-shop text-brand-600"></i> Issued by MBS, MSU
                        </div>
                    </div>
                </div>

            </div>
        </div>
    </section>

    <!-- Activities Section -->
    <section id="activities" class="py-24 relative z-10 border-t border-slate-100 bg-slate-50">
        <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-16 reveal">
                <span class="text-xs font-bold text-brand-600 uppercase tracking-widest font-mono">Student Leadership</span>
                <h2 class="text-3xl sm:text-4xl font-extrabold text-slate-900 mt-2">Activities</h2>
                <p class="text-slate-500 mt-2 text-sm">กิจกรรมและงานช่วยเหลือคณะเพื่อสาธารณประโยชน์ที่ได้เข้าร่วม</p>
                <div class="h-1 w-12 bg-brand-600 mx-auto mt-4 rounded-full"></div>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 gap-10">
                <!-- Activity 1 -->
                <div class="reveal glass-card rounded-3xl overflow-hidden group bg-white shadow-sm">
                    <div class="relative h-64 overflow-hidden cursor-pointer" onclick="openLightbox('https://images.unsplash.com/photo-1540575467063-178a50c2df87?q=80&w=800&auto=format&fit=crop', 'MSU Open House 2024 Booth Guide')">
                        <img src="https://images.unsplash.com/photo-1540575467063-178a50c2df87?q=80&w=800&auto=format&fit=crop" alt="MSU Open House Activity" class="w-full h-full object-cover opacity-90 group-hover:scale-105 transition-transform duration-700">
                        <div class="absolute inset-0 bg-gradient-to-t from-slate-950/60 via-transparent to-transparent"></div>
                        <div class="absolute bottom-4 left-6">
                            <span class="bg-brand-600 text-white text-[10px] font-bold px-3 py-1.5 rounded-full uppercase tracking-wider font-mono shadow-sm">Booth Staff & Guide</span>
                        </div>
                    </div>
                    <div class="p-8">
                        <div class="flex items-center justify-between text-[11px] font-bold text-slate-400 mb-2 font-mono">
                            <span>MAHASARAKHAM UNIVERSITY</span>
                            <span>DEC 2024</span>
                        </div>
                        <h3 class="text-xl font-bold text-slate-800 mb-3 group-hover:text-brand-600 transition-colors">MSU Open House 2024</h3>
                        <p class="text-slate-500 text-sm leading-relaxed mb-4">
                            ร่วมทำกิจกรรมในบูธนิทรรศการหลักสูตรวิชาดิจิทัลธุรกิจ แนะนำความรู้และแนะแนวการศึกษาต่อให้กับกลุ่มน้องๆ นักเรียนมัธยมปลาย
                        </p>
                        <div class="pt-4 border-t border-slate-100 text-[11px] text-slate-400 flex items-center gap-2 font-mono">
                            <i class="fa-solid fa-users text-brand-600"></i> Supported Open House activities & guidance.
                        </div>
                    </div>
                </div>

                <!-- Activity 2 -->
                <div class="reveal glass-card rounded-3xl overflow-hidden group bg-white shadow-sm">
                    <div class="relative h-64 overflow-hidden cursor-pointer" onclick="openLightbox('https://images.unsplash.com/photo-1511578314322-379afb476865?q=80&w=800&auto=format&fit=crop', 'MBS Freshy Day Staff')">
                        <img src="https://images.unsplash.com/photo-1511578314322-379afb476865?q=80&w=800&auto=format&fit=crop" alt="MBS Freshy Day Staff" class="w-full h-full object-cover opacity-90 group-hover:scale-105 transition-transform duration-700">
                        <div class="absolute inset-0 bg-gradient-to-t from-slate-950/60 via-transparent to-transparent"></div>
                        <div class="absolute bottom-4 left-6">
                            <span class="bg-indigo-600 text-white text-[10px] font-bold px-3 py-1.5 rounded-full uppercase tracking-wider font-mono shadow-sm">Event Organizer Staff</span>
                        </div>
                    </div>
                    <div class="p-8">
                        <div class="flex items-center justify-between text-[11px] font-bold text-slate-400 mb-2 font-mono">
                            <span>MBS FACULTY EVENTS</span>
                            <span>JUL 2025</span>
                        </div>
                        <h3 class="text-xl font-bold text-slate-800 mb-3 group-hover:text-brand-600 transition-colors">MBS Fresh Day & Fresh Night</h3>
                        <p class="text-slate-500 text-sm leading-relaxed mb-4">
                            ปฏิบัติงานต้อนรับและอำนวยความสะดวก ประสานงานดูแลจุดลงทะเบียนอำนวยความสะดวกให้กับนักศึกษาใหม่ในกิจกรรมสันทนาการคณะ
                        </p>
                        <div class="pt-4 border-t border-slate-100 text-[11px] text-slate-400 flex items-center gap-2 font-mono">
                            <i class="fa-solid fa-handshake text-indigo-500"></i> Assisted with registration & venue flow.
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact & Footer Section -->
    <footer id="contact" class="bg-white text-slate-700 py-20 border-t border-slate-200/80 relative z-10">
        <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 md:grid-cols-2 gap-16 pb-16 border-b border-slate-100 reveal">
                <div class="space-y-6">
                    <h2 class="text-3xl font-extrabold text-slate-900 tracking-tight">Contact Information</h2>
                    <p class="text-slate-500 leading-relaxed max-w-sm">
                        หากคุณต้องการข้อมูลเพิ่มเติมเพื่อพิจารณาเข้าฝึกงาน หรือต้องการพูดคุยเพิ่มเติม สามารถคัดลอกข้อมูลติดต่อหรือส่งข้อความหาฉันได้ทันทีค่ะ
                    </p>
                    <div class="space-y-4">
                        <div class="flex items-center gap-4">
                            <div class="w-12 h-12 rounded-xl bg-slate-50 flex items-center justify-center text-brand-600 border border-slate-200 shadow-sm">
                                <i class="fa-solid fa-map-location-dot"></i>
                            </div>
                            <div>
                                <div class="text-[10px] text-slate-400 font-bold uppercase font-mono">Location</div>
                                <div class="text-sm text-slate-600 font-medium">Mahasarakham University, Thailand</div>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="glass-card p-8 rounded-3xl space-y-6 bg-slate-50/50 shadow-sm">
                    <h3 class="text-lg font-bold text-slate-800 flex items-center gap-2">
                        <i class="fa-solid fa-bolt text-brand-600 animate-pulse"></i> Direct Connection
                    </h3>
                    
                    <!-- Copy Email -->
                    <div class="bg-white p-4 rounded-2xl flex items-center justify-between border border-slate-200/80 group hover:border-brand-500 transition-colors shadow-sm">
                        <div class="flex items-center gap-3 overflow-hidden">
                            <i class="fa-regular fa-envelope text-brand-600 text-xl"></i>
                            <span class="text-xs sm:text-sm font-semibold truncate text-slate-700" id="emailVal">nonglukkluanthaisong@gmail.com</span>
                        </div>
                        <button onclick="copyToClipboard('emailVal')" class="text-brand-600 hover:text-white p-2.5 bg-brand-50 hover:bg-brand-600 rounded-xl transition-all shadow-sm" title="Copy Email">
                            <i class="fa-regular fa-copy"></i>
                        </button>
                    </div>

                    <!-- Copy Phone -->
                    <div class="bg-white p-4 rounded-2xl flex items-center justify-between border border-slate-200/80 group hover:border-brand-500 transition-colors shadow-sm">
                        <div class="flex items-center gap-3">
                            <i class="fa-solid fa-phone text-brand-600 text-xl"></i>
                            <span class="text-xs sm:text-sm font-semibold text-slate-700" id="phoneVal">(+66)94-570-5055</span>
                        </div>
                        <button onclick="copyToClipboard('phoneVal')" class="text-brand-600 hover:text-white p-2.5 bg-brand-50 hover:bg-brand-600 rounded-xl transition-all shadow-sm" title="Copy Phone Number">
                            <i class="fa-regular fa-copy"></i>
                        </button>
                    </div>
                </div>
            </div>

            <!-- Credits -->
            <div class="pt-8 flex flex-col sm:flex-row items-center justify-between text-xs text-slate-400 gap-4 reveal">
                <p>&copy; 2026 Nongluk Kluanthaisong. All Rights Reserved.</p>
                <div class="flex gap-4">
                    <span class="hover:underline cursor-pointer text-brand-600 font-mono font-medium" onclick="openCVModal()">Source: Nongluk.cv.jpg</span>
                    <span>•</span>
                    <span class="font-mono">Digital Business and Information Systems</span>
                </div>
            </div>
        </div>
    </footer>

    <!-- Premium Image Lightbox Viewer -->
    <div id="lightboxModal" class="fixed inset-0 z-50 hidden bg-slate-950/95 backdrop-blur-md flex items-center justify-center p-4">
        <div class="relative max-w-4xl w-full flex flex-col max-h-[90vh]">
            <!-- Close Button -->
            <button onclick="closeLightbox()" class="absolute -top-14 right-0 text-white/80 hover:text-white text-3xl w-10 h-10 flex items-center justify-center bg-white/10 hover:bg-white/20 rounded-full transition-all">
                &times;
            </button>
            <div class="bg-white rounded-3xl p-4 border border-slate-100 overflow-hidden flex flex-col justify-center items-center shadow-2xl">
                <img id="lightboxImage" src="" alt="Certificate View" class="max-w-full max-h-[70vh] rounded-2xl object-contain shadow-lg">
                <p id="lightboxCaption" class="text-sm text-slate-700 mt-4 font-bold text-center"></p>
            </div>
        </div>
    </div>

    <!-- Original CV Resume Modal -->
    <div id="cvModal" class="fixed inset-0 z-50 hidden bg-slate-950/95 backdrop-blur-md flex items-center justify-center p-4">
        <div class="bg-white rounded-3xl max-w-2xl w-full p-6 relative flex flex-col max-h-[90vh] border border-slate-100 shadow-2xl">
            <button onclick="closeCVModal()" class="absolute top-4 right-4 text-slate-400 hover:text-slate-600 text-2xl w-10 h-10 flex items-center justify-center bg-slate-50 hover:bg-slate-100 rounded-full transition-all">
                &times;
            </button>
            <h3 class="text-xl font-bold text-slate-800 mb-4 flex items-center gap-2">
                <i class="fa-solid fa-file-contract text-brand-600"></i> Original CV Document
            </h3>
            <div class="flex-1 overflow-y-auto rounded-2xl border border-slate-100 bg-slate-50">
                <img src="Nongluk.cv.jpg" alt="Nongluk Kluanthaisong Original CV File" class="w-full h-auto" onerror="this.onerror=null; this.src='https://images.unsplash.com/photo-1586281380349-632531db7ed4?q=80&w=800&auto=format&fit=crop';">
            </div>
            <div class="mt-5 pt-4 border-t border-slate-100 flex justify-between items-center text-xs text-slate-400 font-mono">
                <span>Ref: Nongluk.cv.jpg</span>
                <button onclick="closeCVModal()" class="bg-brand-600 hover:bg-brand-500 text-white px-5 py-2.5 rounded-xl font-bold transition-all shadow-md shadow-brand-600/10">Close Viewer</button>
            </div>
        </div>
    </div>

    <!-- Alert Toast Notification for Actions -->
    <div id="toast" class="fixed bottom-6 right-6 bg-slate-900 text-white px-6 py-4 rounded-2xl shadow-2xl transition-all duration-300 transform translate-y-20 opacity-0 z-50 flex items-center gap-3 font-semibold text-sm">
        <i class="fa-solid fa-circle-check text-lg text-brand-500"></i>
        <span id="toastMessage">Copied successfully!</span>
    </div>

    <script>
        // Intersection Observer Scroll Animations Engine (With refined delays)
        document.addEventListener("DOMContentLoaded", function() {
            const reveals = document.querySelectorAll(".reveal");

            const observerOptions = {
                root: null,
                rootMargin: "0px",
                threshold: 0.08 // Trigger reveal naturally
            };

            const revealObserver = new IntersectionObserver(function(entries, observer) {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add("active");
                    }
                });
            }, observerOptions);

            reveals.forEach(el => {
                revealObserver.observe(el);
            });
        });

        // Horizontal Slide Controls for Certifications Row
        const certScroll = document.getElementById('certScrollContainer');
        const slideLeftBtn = document.getElementById('slideLeftBtn');
        const slideRightBtn = document.getElementById('slideRightBtn');

        slideLeftBtn.addEventListener('click', () => {
            certScroll.scrollBy({
                left: -320,
                behavior: 'smooth'
            });
        });

        slideRightBtn.addEventListener('click', () => {
            certScroll.scrollBy({
                left: 320,
                behavior: 'smooth'
            });
        });

        // Smart Header Navigation: Hide on Scroll Down, Show on Scroll Up
        let lastScrollTop = 0;
        const mainHeader = document.getElementById('mainHeader');
        
        window.addEventListener('scroll', function() {
            let scrollTop = window.pageYOffset || document.documentElement.scrollTop;
            
            if (scrollTop > lastScrollTop) {
                // Scroll DOWN -> SHOW the header
                mainHeader.classList.remove('-translate-y-full');
                mainHeader.classList.add('bg-white/90', 'shadow-md');
            } else {
                // Scroll UP -> HIDE the header
                mainHeader.classList.add('-translate-y-full');
            }
            
            // Keep header visible at the absolute top of the page
            if (scrollTop <= 20) {
                mainHeader.classList.remove('-translate-y-full', 'shadow-md');
                mainHeader.classList.add('bg-white/80');
            }
            
            lastScrollTop = scrollTop <= 0 ? 0 : scrollTop; 
        });

        // Scrollspy Active Navigation Indicator (Highlighting matching section)
        const sections = document.querySelectorAll('section[id]');
        const navItems = document.querySelectorAll('.nav-item');

        window.addEventListener('scroll', function() {
            let scrollPosition = document.documentElement.scrollTop || document.body.scrollTop;
            let currentSectionId = 'home';

            sections.forEach(section => {
                const sectionTop = section.offsetTop - 150; // offset for nav bar
                const sectionHeight = section.offsetHeight;

                if (scrollPosition >= sectionTop && scrollPosition < (sectionTop + sectionHeight)) {
                    currentSectionId = section.getAttribute('id');
                }
            });

            navItems.forEach(item => {
                const targetId = item.getAttribute('href').substring(1);
                const line = item.querySelector('.nav-line');
                
                if (targetId === currentSectionId) {
                    item.classList.remove('text-slate-500');
                    item.classList.add('text-brand-600');
                    if (line) line.classList.replace('scale-x-0', 'scale-x-100');
                } else {
                    item.classList.remove('text-brand-600');
                    item.classList.add('text-slate-500');
                    if (line) line.classList.replace('scale-x-100', 'scale-x-0');
                }
            });
        });

        // CV Modal Open/Close handlers
        function openCVModal() {
            document.getElementById('cvModal').classList.remove('hidden');
            document.body.classList.add('overflow-hidden');
        }

        function closeCVModal() {
            document.getElementById('cvModal').classList.add('hidden');
            document.body.classList.remove('overflow-hidden');
        }

        // Lightbox Gallery Viewer handlers
        function openLightbox(imgSrc, caption) {
            document.getElementById('lightboxImage').src = imgSrc;
            document.getElementById('lightboxCaption').innerText = caption;
            document.getElementById('lightboxModal').classList.remove('hidden');
            document.body.classList.add('overflow-hidden');
        }

        function closeLightbox() {
            document.getElementById('lightboxModal').classList.add('hidden');
            document.body.classList.remove('overflow-hidden');
        }

        // Direct Connect Text Copy Helper
        function copyToClipboard(elementId) {
            const textToCopy = document.getElementById(elementId).innerText;
            
            if (navigator.clipboard && window.isSecureContext) {
                navigator.clipboard.writeText(textToCopy).then(() => {
                    showToast("คัดลอกข้อมูลเรียบร้อยแล้ว!");
                }).catch(err => {
                    fallbackCopyToClipboard(textToCopy);
                });
            } else {
                fallbackCopyToClipboard(textToCopy);
            }
        }

        // Fallback Copy to Clipboard
        function fallbackCopyToClipboard(text) {
            const textArea = document.createElement("textarea");
            textArea.value = text;
            textArea.style.position = "fixed";  
            document.body.appendChild(textArea);
            textArea.focus();
            textArea.select();
            try {
                document.execCommand('copy');
                showToast("คัดลอกข้อมูลเรียบร้อยแล้ว!");
            } catch (err) {
                console.error('Copy fallback failed', err);
            }
            document.body.removeChild(textArea);
        }

        // Custom Toast Notification Trigger
        function showToast(message) {
            const toast = document.getElementById('toast');
            document.getElementById('toastMessage').innerText = message;
            
            toast.classList.remove('translate-y-20', 'opacity-0');
            toast.classList.add('translate-y-0', 'opacity-100');
            
            setTimeout(() => {
                toast.classList.add('translate-y-20', 'opacity-0');
                toast.classList.remove('translate-y-0', 'opacity-100');
            }, 3000);
        }
    </script>
</body>
</html>
