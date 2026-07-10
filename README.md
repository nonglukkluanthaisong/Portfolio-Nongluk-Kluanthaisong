<!DOCTYPE html>
<html lang="th" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
    <title>Nongluk Kluanthaisong - Portfolio</title>
    
    <!-- Google Fonts: Playfair Display, Montserrat, Noto Sans Thai -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,300;0,400;0,600;0,700;1,400&family=Noto+Sans+Thai:wght@300;400;500;600;700&family=Playfair+Display:ital,wght@0,600;0,700;1,400&display=swap" rel="stylesheet">
    
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        brandBlue: {
                            50: '#f0f9ff',
                            100: '#e0f2fe',
                            200: '#bae6fd',
                            300: '#7dd3fc',
                            400: '#38bdf8',
                            500: '#0ea5e9',
                            600: '#0284c7',
                            700: '#0369a1',
                            800: '#075985',
                            900: '#0c4a6e',
                            950: '#082f49',
                        }
                    },
                    fontFamily: {
                        sans: ['"Noto Sans Thai"', '"Inter"', 'sans-serif'],
                        tech: ['"Montserrat"', 'sans-serif'],
                        serif: ['"Playfair Display"', 'serif'],
                    }
                }
            }
        }
    </script>
    
    <style>
        html, body {
            width: 100%;
            max-width: 100%;
            overflow-x: hidden;
            -webkit-overflow-scrolling: touch;
            background-color: #f8fafc;
            color: #1e293b;
        }

        /* Ambient light tech grid backdrop */
        .tech-grid {
            background-image: 
                linear-gradient(to right, rgba(14, 160, 234, 0.05) 1px, transparent 1px),
                linear-gradient(to bottom, rgba(14, 160, 234, 0.05) 1px, transparent 1px);
            background-size: 35px 35px;
        }

        /* Glassmorphism Navigation & Cards for Light Theme */
        .glass-nav {
            background: rgba(255, 255, 255, 0.85);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border-bottom: 1px solid rgba(14, 160, 234, 0.08);
        }

        .glass-card {
            background: rgba(255, 255, 255, 0.75);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border: 1px solid rgba(14, 160, 234, 0.08);
            box-shadow: 0 4px 20px -2px rgba(14, 160, 234, 0.03);
            transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1);
        }

        .glass-card:hover {
            border-color: rgba(14, 160, 234, 0.3);
            box-shadow: 0 12px 30px -8px rgba(14, 160, 234, 0.12);
            transform: translateY(-3px);
        }

        /* Reveal Animation on Scroll with Ease-Out-Cubic curves */
        .reveal-element {
            opacity: 0;
            transform: translateY(15px);
            transition: opacity 1.2s cubic-bezier(0.215, 0.61, 0.355, 1), 
                        transform 1.2s cubic-bezier(0.215, 0.61, 0.355, 1);
            will-change: transform, opacity;
        }

        .reveal-element.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* Header show/hide transitions */
        header {
            transition: transform 0.4s cubic-bezier(0.16, 1, 0.3, 1);
        }
        
        .header-hidden {
            transform: translateY(-100%);
        }

        /* Custom Scroll progress bar */
        #scroll-progress {
            position: fixed;
            top: 0;
            left: 0;
            height: 3px;
            background: linear-gradient(to right, #0ea5e9, #0369a1);
            width: 0%;
            z-index: 100;
            transition: width 0.1s ease-out;
        }

        /* Premium sliding Underline Tracker */
        #underline-indicator {
            position: absolute;
            bottom: 0;
            height: 3px;
            background: linear-gradient(90deg, #38bdf8, #0284c7);
            transition: all 0.38s cubic-bezier(0.25, 1, 0.5, 1);
            border-radius: 9999px;
        }

        /* Custom scrollbar for clean premium desktop view */
        ::-webkit-scrollbar {
            width: 6px;
        }
        ::-webkit-scrollbar-track {
            background: #f1f5f9;
        }
        ::-webkit-scrollbar-thumb {
            background: #cbd5e1;
            border-radius: 9999px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #0284c7;
        }
    </style>
</head>
<body class="bg-[#f8fafc] text-slate-800 min-h-screen relative overflow-x-hidden selection:bg-brandBlue-100 selection:text-brandBlue-900">

    <!-- Integrated Tech Backdrops (Pointer-events guarded to prevent iPad shifting or horizontal drift) -->
    <div class="fixed inset-0 w-full h-full overflow-hidden pointer-events-none z-0">
        <!-- Unified Grid Overlay -->
        <div class="absolute inset-0 tech-grid opacity-80"></div>
        
        <!-- Interactive Mathematics Constellation Canvas -->
        <canvas id="neural-canvas" class="absolute inset-0 w-full h-full opacity-40"></canvas>
        
        <!-- Ambient subtle glow to blend sections natively -->
        <div class="absolute top-[20%] left-[-10%] w-[350px] h-[350px] md:w-[600px] md:h-[600px] rounded-full bg-brandBlue-100/30 blur-[130px]"></div>
        <div class="absolute top-[60%] right-[-10%] w-[350px] h-[350px] md:w-[600px] md:h-[600px] rounded-full bg-blue-100/25 blur-[140px]"></div>
        <div class="absolute bottom-[5%] left-[10%] w-[400px] h-[400px] rounded-full bg-brandBlue-50/40 blur-[120px]"></div>
    </div>

    <!-- Scroll Progress -->
    <div id="scroll-progress"></div>

    <!-- Main Content Wrapper (With iOS Safe Areas and locked X width) -->
    <div class="w-full min-h-screen flex flex-col relative z-10 overflow-x-hidden">

        <!-- Global Header Navigation -->
        <header id="main-header" class="fixed top-0 left-0 w-full z-50 glass-nav">
            <div class="max-w-[1440px] mx-auto px-6 md:px-12 h-16 sm:h-20 flex items-center justify-between">
                <!-- Branding -->
                <a href="#home" class="flex flex-col text-left group">
                    <span class="font-tech font-bold text-base sm:text-xl tracking-[0.15em] text-slate-900 group-hover:text-brandBlue-600 transition-colors">
                        NL.KLUANTHAI
                    </span>
                    <span class="text-[9px] sm:text-[10px] tracking-widest text-slate-500 font-tech font-semibold">
                        DIGITAL INFORMATION SYSTEMS
                    </span>
                </a>
                
                <!-- Navigation Items -->
                <nav class="relative hidden md:flex items-center space-x-6 lg:space-x-10 h-full py-2">
                    <a href="#home" class="nav-link font-tech text-xs tracking-widest text-slate-600 hover:text-slate-900 transition-colors duration-300 py-2 h-full flex items-center font-bold" data-sec="home">HOME</a>
                    <a href="#about" class="nav-link font-tech text-xs tracking-widest text-slate-600 hover:text-slate-900 transition-colors duration-300 py-2 h-full flex items-center font-bold" data-sec="about">ABOUT ME</a>
                    <a href="#education" class="nav-link font-tech text-xs tracking-widest text-slate-600 hover:text-slate-900 transition-colors duration-300 py-2 h-full flex items-center font-bold" data-sec="education">EDUCATION</a>
                    <a href="#projects" class="nav-link font-tech text-xs tracking-widest text-slate-600 hover:text-slate-900 transition-colors duration-300 py-2 h-full flex items-center font-bold" data-sec="projects">PROJECTS</a>
                    <a href="#certificates" class="nav-link font-tech text-xs tracking-widest text-slate-600 hover:text-slate-900 transition-colors duration-300 py-2 h-full flex items-center font-bold" data-sec="certificates">CERTIFICATES</a>
                    <a href="#activities" class="nav-link font-tech text-xs tracking-widest text-slate-600 hover:text-slate-900 transition-colors duration-300 py-2 h-full flex items-center font-bold" data-sec="activities">ACTIVITIES</a>
                    <a href="#contact" class="nav-link font-tech text-xs tracking-widest text-slate-600 hover:text-slate-900 transition-colors duration-300 py-2 h-full flex items-center font-bold" data-sec="contact">CONTACT</a>
                    
                    <!-- Sliding Underline Tracker -->
                    <div id="underline-indicator"></div>
                </nav>

                <!-- Action Button -->
                <div class="hidden md:block">
                    <a href="#contact" class="px-5 py-2.5 rounded-lg bg-brandBlue-600 text-white font-tech font-bold text-xs tracking-widest hover:bg-brandBlue-700 hover:-translate-y-0.5 transition-all duration-300 shadow-md shadow-brandBlue-100">
                        GET IN TOUCH
                    </a>
                </div>

                <!-- Mobile Menu Toggle Button -->
                <button id="mobile-toggle" class="md:hidden text-slate-800 hover:text-brandBlue-600 transition-colors p-2" aria-label="Toggle Menu">
                    <i class="fa-solid fa-bars text-xl"></i>
                </button>
            </div>

            <!-- Mobile Dropdown Panel -->
            <div id="mobile-dropdown" class="hidden md:hidden absolute top-full left-0 w-full bg-white/95 border-b border-slate-100 px-6 py-6 space-y-4 flex flex-col backdrop-blur-lg shadow-lg">
                <a href="#home" class="mobile-link font-tech text-xs tracking-widest text-slate-700 hover:text-brandBlue-600 py-2 border-b border-slate-100 font-bold" data-sec="home">HOME</a>
                <a href="#about" class="mobile-link font-tech text-xs tracking-widest text-slate-700 hover:text-brandBlue-600 py-2 border-b border-slate-100 font-bold" data-sec="about">ABOUT ME</a>
                <a href="#education" class="mobile-link font-tech text-xs tracking-widest text-slate-700 hover:text-brandBlue-600 py-2 border-b border-slate-100 font-bold" data-sec="education">EDUCATION</a>
                <a href="#projects" class="mobile-link font-tech text-xs tracking-widest text-slate-700 hover:text-brandBlue-600 py-2 border-b border-slate-100 font-bold" data-sec="projects">PROJECTS</a>
                <a href="#certificates" class="mobile-link font-tech text-xs tracking-widest text-slate-700 hover:text-brandBlue-600 py-2 border-b border-slate-100 font-bold" data-sec="certificates">CERTIFICATES</a>
                <a href="#activities" class="mobile-link font-tech text-xs tracking-widest text-slate-700 hover:text-brandBlue-600 py-2 border-b border-slate-100 font-bold" data-sec="activities">ACTIVITIES</a>
                <a href="#contact" class="mobile-link font-tech text-xs tracking-widest text-slate-700 hover:text-brandBlue-600 py-2 font-bold" data-sec="contact">CONTACT</a>
            </div>
        </header>

        <!-- Main Core Sections Container (Gaps compressed for maximum coherence and beautiful editorial flows) -->
        <main class="relative z-10 w-full max-w-[1440px] mx-auto px-6 sm:px-12 pt-24 sm:pt-28 pb-16 space-y-12 md:space-y-16 overflow-hidden">

            <!-- SECTION 1: HERO HOME (Compact yet Massive High-Impact typography) -->
            <section id="home" class="min-h-[80vh] sm:min-h-[85vh] flex flex-col justify-center items-center text-center py-6 relative overflow-hidden reveal-element active">
                <!-- Metadata watermark -->
                <div class="font-tech text-xs tracking-[0.3em] text-brandBlue-700 font-bold mb-4 bg-brandBlue-100/40 px-4 py-2 rounded-lg border border-brandBlue-200/30">
                    [ SYSTEM_ONLINE // METRICS_OK ]
                </div>
                
                <!-- Main Bold Title -->
                <h1 class="font-serif italic font-bold text-slate-900 leading-[1.05] mb-6 tracking-tight max-w-5xl">
                    <span class="block text-5xl sm:text-7xl md:text-8xl lg:text-9xl opacity-90">Nongluk</span>
                    <span class="block text-6xl sm:text-8xl md:text-9xl lg:text-[10.5rem] bg-clip-text text-transparent bg-gradient-to-r from-brandBlue-700 via-brandBlue-500 to-slate-900">Kluanthaisong</span>
                </h1>
                
                <!-- Professional Bio Snippet -->
                <p class="text-slate-600 text-sm sm:text-base md:text-lg max-w-2xl font-sans leading-relaxed mb-8">
                    นิสิตสาขาธุรกิจดิจิทัลและระบบสารสนเทศชั้นปีที่ 4 ผู้มีความเชี่ยวชาญการจัดการข้อมูล การออกแบบระบบ และการนำเทคโนโลยีดิจิทัลมาเพิ่มประสิทธิภาพกระบวนการทำงานให้เป็นระบบและทันสมัย
                </p>
                
                <!-- Interactive Actions -->
                <div class="flex flex-col sm:flex-row items-center gap-4 w-full sm:w-auto">
                    <a href="#about" class="w-full sm:w-auto px-8 py-3.5 rounded-lg bg-gradient-to-r from-brandBlue-600 to-brandBlue-500 text-white font-tech font-bold text-xs tracking-widest hover:brightness-110 hover:-translate-y-0.5 transition-all shadow-md shadow-brandBlue-200">
                        ABOUT ME <i class="fa-solid fa-arrow-down ml-2 text-[10px]"></i>
                    </a>
                    <a href="#projects" class="w-full sm:w-auto px-8 py-3.5 rounded-lg border border-slate-200 bg-white/70 text-slate-700 font-tech font-bold text-xs tracking-widest hover:border-brandBlue-500 hover:text-brandBlue-600 hover:-translate-y-0.5 transition-all">
                        EXPLORE WORK
                    </a>
                </div>
            </section>

            <!-- COHESIVE DIVIDER: Technical interface indicator -->
            <div class="flex items-center justify-between py-2 border-t border-dashed border-slate-200 text-[10px] tracking-widest text-slate-400 font-tech px-2">
                <span>[ INDEX: 01 // OVERVIEW ]</span>
                <span class="w-24 border-t border-slate-200"></span>
                <span>[ PROFESSIONAL_BIOGRAPHY ]</span>
            </div>

            <!-- SECTION 2: ABOUT ME (Spacious, Elegant, Editorial Design) -->
            <section id="about" class="scroll-mt-24 reveal-element">
                <!-- Section Header -->
                <div class="mb-10 text-center md:text-left">
                    <div class="inline-flex items-center gap-2 mb-2">
                        <span class="w-8 h-[2px] bg-brandBlue-500"></span>
                        <span class="font-tech text-xs tracking-[0.3em] text-brandBlue-600 uppercase font-bold">Biography</span>
                    </div>
                    <h2 class="font-serif italic text-4xl sm:text-5xl md:text-6xl font-bold text-slate-900">About Me</h2>
                </div>

                <!-- Structured Layout Grid -->
                <div class="grid grid-cols-1 lg:grid-cols-12 gap-10 md:gap-14 items-center">
                    
                    <!-- Left: Large Portrait Frame -->
                    <div class="lg:col-span-5 flex flex-col items-center">
                        <div class="relative w-72 h-72 sm:w-96 sm:h-96 rounded-2xl overflow-hidden glass-card group shadow-2xl shadow-slate-200">
                            <!-- Image path is Nongluk.cv_2.jpg, placeholders loaded via onerror -->
                            <img src="Nongluk.cv_2.jpg" alt="นงลักษณ์ เกลื่อนไทสง" class="w-full h-full object-cover group-hover:scale-105 transition-all duration-700" onerror="this.src='https://placehold.co/600x600/e2e8f0/0f172a?text=Nongluk+K.'">
                            <div class="absolute inset-0 bg-gradient-to-t from-slate-950/40 via-transparent to-transparent"></div>
                            
                            <!-- Small floating identity tag -->
                            <div class="absolute bottom-4 left-4 right-4 bg-white/90 backdrop-blur px-4 py-2.5 rounded-xl border border-white/20">
                                <p class="text-slate-900 font-tech font-bold text-sm tracking-wider">Nongluk Kluanthaisong</p>
                                <p class="text-brandBlue-600 text-xs font-sans mt-0.5">ธุรกิจดิจิทัลและระบบสารสนเทศ (Digital Business)</p>
                            </div>
                        </div>
                    </div>

                    <!-- Right: Structured Bio, Core Skillsets, and Tools directory -->
                    <div class="lg:col-span-7 space-y-6">
                        <div class="space-y-4">
                            <h3 class="font-serif italic text-2xl sm:text-3xl font-bold text-slate-900">
                                มุ่งมั่นสร้างสรรค์นวัตกรรมดิจิทัลเพื่อพัฒนาโครงสร้างระบบข้อมูลให้มีประสิทธิภาพสูง
                            </h3>
                            <p class="text-slate-600 text-sm sm:text-base font-sans leading-relaxed">
                                สวัสดีค่ะ ดิฉัน <strong>นงลักษณ์ เกลื่อนไทสง (อิง)</strong> นิสิตสาขาวิชาธุรกิจดิจิทัลและระบบสารสนเทศ ชั้นปีที่ 4 มหาวิทยาลัยมหาสารคาม มีความหลงใหลอย่างลึกซึ้งในการออกแบบระบบฐานข้อมูล วิเคราะห์วิจัยข้อมูลขนาดใหญ่เพื่อส่งเสริมธุรกิจ ตลอดจนสร้างสรรค์แผนการตลาดดิจิทัลและระบบอัตโนมัติ (RPA / Automation Workflows) เพื่อยกระดับและเพิ่มเสถียรภาพให้กับกระบวนการจัดการข้อมูลในระดับองค์กร
                            </p>
                            <p class="text-slate-600 text-sm sm:text-base font-sans leading-relaxed">
                                ดิฉันเป็นคนที่มีความรับผิดชอบต่องานสูง สามารถปรับตัวเข้ากับการทำงานร่วมกับทีมที่หลากหลายรูปแบบ และพร้อมเรียนรู้ระบบวิทยาการเทคโนโลยีและเครื่องมือซอฟต์แวร์ใหม่ๆ ตลอดเวลา เพื่อขับเคลื่อนการปฏิบัติงานสู่มาตรฐานความสำเร็จระดับมืออาชีพ
                            </p>
                        </div>

                        <!-- Core Strengths Sub-Grid -->
                        <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 pt-4 border-t border-slate-100">
                            <div>
                                <span class="text-xs font-tech tracking-wider text-slate-400 font-bold block mb-2">[ CORE SKILLS ]</span>
                                <ul class="space-y-1.5 text-sm text-slate-600">
                                    <li><i class="fa-solid fa-check text-brandBlue-500 mr-2 text-xs"></i>การจัดการและออกแบบระบบฐานข้อมูล</li>
                                    <li><i class="fa-solid fa-check text-brandBlue-500 mr-2 text-xs"></i>การออกแบบ Web & App UX/UI</li>
                                    <li><i class="fa-solid fa-check text-brandBlue-500 mr-2 text-xs"></i>การจัดการข้อมูลและวิเคราะห์ทางธุรกิจ</li>
                                    <li><i class="fa-solid fa-check text-brandBlue-500 mr-2 text-xs"></i>การตลาดดิจิทัลและวิเคราะห์กลุ่มเป้าหมาย</li>
                                </ul>
                            </div>
                            <div>
                                <span class="text-xs font-tech tracking-wider text-slate-400 font-bold block mb-2">[ SOFT SKILLS ]</span>
                                <ul class="space-y-1.5 text-sm text-slate-600">
                                    <li><i class="fa-solid fa-check text-brandBlue-500 mr-2 text-xs"></i>การสื่อสารและทำงานร่วมกับทีม</li>
                                    <li><i class="fa-solid fa-check text-brandBlue-500 mr-2 text-xs"></i>การแก้ปัญหาและคิดวิเคราะห์อย่างเป็นระบบ</li>
                                    <li><i class="fa-solid fa-check text-brandBlue-500 mr-2 text-xs"></i>ความยืดหยุ่นและการเรียนรู้สิ่งใหม่</li>
                                    <li><i class="fa-solid fa-check text-brandBlue-500 mr-2 text-xs"></i>ความรอบคอบและความรับผิดชอบเป็นเลิศ</li>
                                </ul>
                            </div>
                        </div>
                    </div>
                </div>
            </section>

            <!-- COHESIVE DIVIDER -->
            <div class="flex items-center justify-between py-2 border-t border-dashed border-slate-200 text-[10px] tracking-widest text-slate-400 font-tech px-2">
                <span>[ INDEX: 02 // ACADEMIC ]</span>
                <span class="w-24 border-t border-slate-200"></span>
                <span>[ EDUCATION_RECORD ]</span>
            </div>

            <!-- SECTION 3: EDUCATION (Clean layout with GPA Metrics) -->
            <section id="education" class="scroll-mt-24 reveal-element">
                <!-- Section Header -->
                <div class="mb-10 text-center md:text-left">
                    <div class="inline-flex items-center gap-2 mb-2">
                        <span class="w-8 h-[2px] bg-brandBlue-500"></span>
                        <span class="font-tech text-xs tracking-[0.3em] text-brandBlue-600 uppercase font-bold">Background</span>
                    </div>
                    <h2 class="font-serif italic text-4xl sm:text-5xl md:text-6xl font-bold text-slate-900">Education</h2>
                </div>

                <div class="grid grid-cols-1 lg:grid-cols-12 gap-10 items-stretch">
                    <!-- Left: GPA High-end display -->
                    <div class="lg:col-span-4 flex">
                        <div class="w-full glass-card p-8 rounded-2xl flex flex-col justify-between items-center text-center relative overflow-hidden bg-gradient-to-br from-white to-brandBlue-50/20">
                            <div class="absolute top-0 right-0 w-32 h-32 bg-brandBlue-100/30 rounded-full blur-2xl pointer-events-none"></div>
                            <div class="w-full">
                                <span class="font-tech text-xs tracking-widest text-slate-400 font-bold block mb-2 uppercase">[ EXCELLENT ACADEMIC STANDING ]</span>
                                <h4 class="font-serif italic text-xl sm:text-2xl font-bold text-slate-900 mt-1">GPAX สะสมปัจจุบัน</h4>
                            </div>
                            <div class="my-6">
                                <span class="font-tech text-6xl sm:text-7xl lg:text-8xl font-bold bg-clip-text text-transparent bg-gradient-to-r from-brandBlue-600 to-brandBlue-400">3.68</span>
                                <span class="text-slate-400 text-lg sm:text-xl font-bold block mt-1">/ 4.00</span>
                            </div>
                            <div class="w-full pt-4 border-t border-slate-100">
                                <span class="text-xs text-slate-500 font-sans block">หลักสูตรบริหารธุรกิจบัณฑิต (บธ.บ.)</span>
                            </div>
                        </div>
                    </div>

                    <!-- Right: Detailed Education Directory & Software Skill Badges -->
                    <div class="lg:col-span-8 flex flex-col justify-between space-y-6">
                        <!-- Education Card -->
                        <div class="glass-card p-6 sm:p-8 rounded-2xl relative overflow-hidden flex-grow">
                            <div class="flex items-start gap-4">
                                <div class="w-12 h-12 rounded-xl bg-brandBlue-50 border border-brandBlue-200 flex items-center justify-center text-brandBlue-600 shrink-0 shadow-sm">
                                    <i class="fa-solid fa-graduation-cap text-lg"></i>
                                </div>
                                <div class="space-y-2">
                                    <span class="text-xs font-tech font-bold tracking-widest text-brandBlue-600">[ 2022 - PRESENT ]</span>
                                    <h3 class="font-sans text-xl sm:text-2xl font-bold text-slate-900 leading-snug">
                                        คณะการบัญชีและการจัดการ มหาวิทยาลัยมหาสารคาม
                                    </h3>
                                    <p class="text-slate-600 text-base">
                                        หลักสูตรบริหารธุรกิจบัณฑิต (บธ.บ.) สาขาวิชาธุรกิจดิจิทัลและระบบสารสนเทศ
                                    </p>
                                    <p class="text-slate-500 text-sm pt-1 leading-relaxed">
                                        เน้นการวางโครงสร้างฐานข้อมูลสารสนเทศ, พัฒนาเว็บสารสนเทศและแอปพลิเคชันธุรกิจ (Web & App Development), วิเคราะห์ประมวลผลข้อมูล (Data Visualization), การสร้างระบบงานอัตโนมัติ (n8n/RPA) รวมถึงการวางระบบสารสนเทศเพื่อการจัดการสำหรับองค์กรสมัยใหม่ (Management Information System)
                                    </p>
                                </div>
                            </div>
                        </div>

                        <!-- Software platform badges grid -->
                        <div class="glass-card p-6 rounded-2xl">
                            <span class="text-xs font-tech tracking-[0.2em] text-slate-400 font-bold block mb-4 uppercase">
                                [ SOFTWARE & TECHNICAL PLATFORMS ]
                            </span>
                            <div class="grid grid-cols-2 sm:grid-cols-4 gap-2.5 text-center">
                                <div class="px-3 py-2.5 rounded-lg bg-slate-50 border border-slate-100 flex items-center justify-center gap-2 text-slate-700 hover:border-brandBlue-400 hover:bg-white hover:-translate-y-0.5 transition-all duration-300 shadow-sm cursor-default">
                                    <i class="fa-brands fa-figma text-red-500 text-sm"></i>
                                    <span class="font-tech text-xs font-bold">Figma</span>
                                </div>
                                <div class="px-3 py-2.5 rounded-lg bg-slate-50 border border-slate-100 flex items-center justify-center gap-2 text-slate-700 hover:border-brandBlue-400 hover:bg-white hover:-translate-y-0.5 transition-all duration-300 shadow-sm cursor-default">
                                    <i class="fa-solid fa-chart-simple text-amber-500 text-sm"></i>
                                    <span class="font-tech text-xs font-bold">Power BI</span>
                                </div>
                                <div class="px-3 py-2.5 rounded-lg bg-slate-50 border border-slate-100 flex items-center justify-center gap-2 text-slate-700 hover:border-brandBlue-400 hover:bg-white hover:-translate-y-0.5 transition-all duration-300 shadow-sm cursor-default">
                                    <i class="fa-solid fa-file-excel text-emerald-600 text-sm"></i>
                                    <span class="font-tech text-xs font-bold">Excel</span>
                                </div>
                                <div class="px-3 py-2.5 rounded-lg bg-slate-50 border border-slate-100 flex items-center justify-center gap-2 text-slate-700 hover:border-brandBlue-400 hover:bg-white hover:-translate-y-0.5 transition-all duration-300 shadow-sm cursor-default">
                                    <i class="fa-solid fa-wand-magic-sparkles text-sky-500 text-sm"></i>
                                    <span class="font-tech text-xs font-bold">Canva</span>
                                </div>
                                <div class="px-3 py-2.5 rounded-lg bg-slate-50 border border-slate-100 flex items-center justify-center gap-2 text-slate-700 hover:border-brandBlue-400 hover:bg-white hover:-translate-y-0.5 transition-all duration-300 shadow-sm cursor-default">
                                    <i class="fa-solid fa-scissors text-purple-500 text-sm"></i>
                                    <span class="font-tech text-xs font-bold">CapCut</span>
                                </div>
                                <div class="px-3 py-2.5 rounded-lg bg-slate-50 border border-slate-100 flex items-center justify-center gap-2 text-slate-700 hover:border-brandBlue-400 hover:bg-white hover:-translate-y-0.5 transition-all duration-300 shadow-sm cursor-default">
                                    <i class="fa-solid fa-file-word text-blue-600 text-sm"></i>
                                    <span class="font-tech text-xs font-bold">MS Word</span>
                                </div>
                                <div class="px-3 py-2.5 rounded-lg bg-slate-50 border border-slate-100 flex items-center justify-center gap-2 text-slate-700 hover:border-brandBlue-400 hover:bg-white hover:-translate-y-0.5 transition-all duration-300 shadow-sm cursor-default">
                                    <i class="fa-solid fa-file-powerpoint text-orange-600 text-sm"></i>
                                    <span class="font-tech text-xs font-bold">MS PPT</span>
                                </div>
                                <div class="px-3 py-2.5 rounded-lg bg-slate-50 border border-slate-100 flex items-center justify-center gap-2 text-slate-700 hover:border-brandBlue-400 hover:bg-white hover:-translate-y-0.5 transition-all duration-300 shadow-sm cursor-default">
                                    <i class="fa-solid fa-diagram-project text-teal-500 text-sm"></i>
                                    <span class="font-tech text-xs font-bold">n8n</span>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </section>

            <!-- COHESIVE DIVIDER -->
            <div class="flex items-center justify-between py-2 border-t border-dashed border-slate-200 text-[10px] tracking-widest text-slate-400 font-tech px-2">
                <span>[ INDEX: 03 // OUTCOMES ]</span>
                <span class="w-24 border-t border-slate-200"></span>
                <span>[ SYS_DEVELOPMENT_COMPILER ]</span>
            </div>

            <!-- SECTION 4: PROJECTS (Symmetrical, Elegant Grid) -->
            <section id="projects" class="scroll-mt-24 reveal-element">
                <!-- Section Header -->
                <div class="mb-10 text-center md:text-left">
                    <div class="inline-flex items-center gap-2 mb-2">
                        <span class="w-8 h-[2px] bg-brandBlue-500"></span>
                        <span class="font-tech text-xs tracking-[0.3em] text-brandBlue-600 uppercase font-bold">Showcase</span>
                    </div>
                    <h2 class="font-serif italic text-4xl sm:text-5xl md:text-6xl font-bold text-slate-900">Featured Projects</h2>
                </div>

                <!-- Symmetric Grid Display (Unified Card heights) -->
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                    
                    <!-- Project 1 -->
                    <div class="glass-card rounded-2xl overflow-hidden flex flex-col h-full group">
                        <div class="h-44 sm:h-48 overflow-hidden bg-slate-100 relative border-b border-slate-100">
                            <!-- Visual Placeholder/Asset -->
                            <div class="absolute inset-0 bg-gradient-to-tr from-brandBlue-100/30 to-transparent z-10"></div>
                            <div class="absolute inset-0 flex items-center justify-center text-slate-300 font-tech font-bold text-4xl select-none group-hover:scale-105 transition-transform duration-500">
                                <i class="fa-solid fa-laptop-medical text-brandBlue-600/15 text-6xl animate-pulse"></i>
                            </div>
                            <span class="absolute top-4 left-4 z-20 px-3 py-1 rounded-lg bg-white/90 text-brandBlue-700 border border-brandBlue-200 text-[10px] tracking-wider font-tech font-bold shadow-sm">
                                UX/UI CASE STUDY
                            </span>
                        </div>
                        <div class="p-6 flex flex-col justify-between flex-grow space-y-4">
                            <div class="space-y-2">
                                <h3 class="font-sans text-lg font-bold text-slate-900 group-hover:text-brandBlue-600 transition-colors">
                                    PIC2PACS: เว็บแอปพลิเคชันอัปโหลดภาพทางแพทย์
                                </h3>
                                <p class="text-slate-600 text-sm font-sans leading-relaxed">
                                    ร่วมออกแบบขั้นตอนการเดินทางของผู้ใช้งาน (UX Flow) และการวางโครงหน้าจอส่วนติดต่อผู้ใช้งาน (UI Design) ของหน้าเว็บแอปพลิเคชันสำหรับนำเข้าข้อมูลและรูปภาพผลตรวจสุขภาพทางการแพทย์เข้าสู่ระบบ PACS อย่างมีประสิทธิภาพสูงสุด
                                </p>
                            </div>
                            <div class="flex flex-wrap gap-1.5 pt-3 border-t border-slate-100">
                                <span class="px-2.5 py-1 rounded bg-slate-100 text-slate-500 font-tech text-[10px] font-semibold">Figma</span>
                                <span class="px-2.5 py-1 rounded bg-slate-100 text-slate-500 font-tech text-[10px] font-semibold">Healthcare UX</span>
                                <span class="px-2.5 py-1 rounded bg-slate-100 text-slate-500 font-tech text-[10px] font-semibold">Responsive</span>
                            </div>
                        </div>
                    </div>

                    <!-- Project 2 -->
                    <div class="glass-card rounded-2xl overflow-hidden flex flex-col h-full group">
                        <div class="h-44 sm:h-48 overflow-hidden bg-slate-100 relative border-b border-slate-100">
                            <div class="absolute inset-0 bg-gradient-to-tr from-brandBlue-100/30 to-transparent z-10"></div>
                            <div class="absolute inset-0 flex items-center justify-center text-slate-300 font-tech font-bold text-4xl select-none group-hover:scale-105 transition-transform duration-500">
                                <i class="fa-solid fa-box-archive text-brandBlue-600/15 text-6xl"></i>
                            </div>
                            <span class="absolute top-4 left-4 z-20 px-3 py-1 rounded-lg bg-white/90 text-brandBlue-700 border border-brandBlue-200 text-[10px] tracking-wider font-tech font-bold shadow-sm">
                                COOPERATIVE WORK
                            </span>
                        </div>
                        <div class="p-6 flex flex-col justify-between flex-grow space-y-4">
                            <div class="space-y-2">
                                <h3 class="font-sans text-lg font-bold text-slate-900 group-hover:text-brandBlue-600 transition-colors">
                                    OonJai Box: ตู้ตรวจรับพัสดุอัจฉริยะสำหรับหอพัก
                                </h3>
                                <p class="text-slate-600 text-sm font-sans leading-relaxed">
                                    การวางแผนโครงสร้างข้อมูลระดับแนวหน้าและการจำลองระบบสารสนเทศเพื่อรองรับกลไกแจ้งเตือนการฝากรับพัสดุแบบเรียลไทม์ ยกระดับเสถียรภาพความปลอดภัยและการจัดการพัสดุในหอพักนิสิต
                                </p>
                            </div>
                            <div class="flex flex-wrap gap-1.5 pt-3 border-t border-slate-100">
                                <span class="px-2.5 py-1 rounded bg-slate-100 text-slate-500 font-tech text-[10px] font-semibold">Database Design</span>
                                <span class="px-2.5 py-1 rounded bg-slate-100 text-slate-500 font-tech text-[10px] font-semibold">Information Flow</span>
                                <span class="px-2.5 py-1 rounded bg-slate-100 text-slate-500 font-tech text-[10px] font-semibold">IoT Logic</span>
                            </div>
                        </div>
                    </div>

                    <!-- Project 3 -->
                    <div class="glass-card rounded-2xl overflow-hidden flex flex-col h-full group">
                        <div class="h-44 sm:h-48 overflow-hidden bg-slate-100 relative border-b border-slate-100">
                            <div class="absolute inset-0 bg-gradient-to-tr from-brandBlue-100/30 to-transparent z-10"></div>
                            <div class="absolute inset-0 flex items-center justify-center text-slate-300 font-tech font-bold text-4xl select-none group-hover:scale-105 transition-transform duration-500">
                                <i class="fa-solid fa-chart-line text-brandBlue-600/15 text-6xl"></i>
                            </div>
                            <span class="absolute top-4 left-4 z-20 px-3 py-1 rounded-lg bg-white/90 text-brandBlue-700 border border-brandBlue-200 text-[10px] tracking-wider font-tech font-bold shadow-sm">
                                DATA ANALYTICS
                            </span>
                        </div>
                        <div class="p-6 flex flex-col justify-between flex-grow space-y-4">
                            <div class="space-y-2">
                                <h3 class="font-sans text-lg font-bold text-slate-900 group-hover:text-brandBlue-600 transition-colors">
                                    ระบบพยากรณ์ปริมาณการใช้ไฟฟ้าอุตสาหกรรม
                                </h3>
                                <p class="text-slate-600 text-sm font-sans leading-relaxed">
                                    โครงการวิเคราะห์ข้อมูลพลังงานไฟฟ้าเชิงประยุกต์ โดยการดึงเข้าชุดข้อมูลและแปลงค่าประมวลผลเชิงลึกทางสถิติเพื่อคำนวณอัตราความเสี่ยงและการคาดการณ์ทิศทางการเติบโตของไฟฟ้าในภาคอุตสาหกรรมด้วยเครื่องมือทันสมัย
                                </p>
                            </div>
                            <div class="flex flex-wrap gap-1.5 pt-3 border-t border-slate-100">
                                <span class="px-2.5 py-1 rounded bg-slate-100 text-slate-500 font-tech text-[10px] font-semibold">Data Forecasting</span>
                                <span class="px-2.5 py-1 rounded bg-slate-100 text-slate-500 font-tech text-[10px] font-semibold">Power BI</span>
                                <span class="px-2.5 py-1 rounded bg-slate-100 text-slate-500 font-tech text-[10px] font-semibold">Regression</span>
                            </div>
                        </div>
                    </div>

                </div>
            </section>

            <!-- COHESIVE DIVIDER -->
            <div class="flex items-center justify-between py-2 border-t border-dashed border-slate-200 text-[10px] tracking-widest text-slate-400 font-tech px-2">
                <span>[ INDEX: 04 // VERIFICATION ]</span>
                <span class="w-24 border-t border-slate-200"></span>
                <span>[ CERTIFICATE_METADATA_VERIFIED ]</span>
            </div>

            <!-- SECTION 5: CERTIFICATES (Large & Highly Legible Display Grid) -->
            <section id="certificates" class="scroll-mt-24 reveal-element">
                <!-- Section Header -->
                <div class="mb-10 text-center md:text-left">
                    <div class="inline-flex items-center gap-2 mb-2">
                        <span class="w-8 h-[2px] bg-brandBlue-500"></span>
                        <span class="font-tech text-xs tracking-[0.3em] text-brandBlue-600 uppercase font-bold">Credentials</span>
                    </div>
                    <h2 class="font-serif italic text-4xl sm:text-5xl md:text-6xl font-bold text-slate-900">Certificates & Training</h2>
                </div>

                <!-- 2-Column Responsive High-Resolution Display Grid -->
                <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                    
                    <!-- Certificate 1 -->
                    <div class="glass-card rounded-2xl overflow-hidden flex flex-col group h-full">
                        <!-- High Resolution Scaled Frame -->
                        <div class="h-56 sm:h-64 bg-slate-100 relative overflow-hidden flex items-center justify-center border-b border-slate-100">
                            <div class="absolute inset-0 bg-gradient-to-b from-brandBlue-50/25 to-transparent z-10"></div>
                            <div class="absolute inset-0 flex flex-col items-center justify-center p-6 text-center text-slate-400 font-tech font-bold select-none group-hover:scale-105 transition-transform duration-500">
                                <i class="fa-solid fa-certificate text-brandBlue-600/15 text-7xl mb-2 animate-pulse"></i>
                                <span class="text-xs text-slate-400 max-w-xs font-sans">หลักสูตรผ่านการรับรองจากหน่วยงานเทคโนโลยีระดับสูง</span>
                            </div>
                        </div>
                        <div class="p-6 flex-grow flex flex-col justify-between space-y-3">
                            <div class="space-y-1.5">
                                <span class="font-tech text-xs tracking-widest text-brandBlue-600 font-bold">[ VERIFIED CREDENTIAL ]</span>
                                <h3 class="font-sans text-xl font-bold text-slate-900 leading-snug group-hover:text-brandBlue-600 transition-colors">
                                    ใบประกาศนียบัตรการจัดเก็บและประมวลผลข้อมูลสารสนเทศระดับสูง
                                </h3>
                                <p class="text-slate-600 text-sm font-sans leading-relaxed">
                                    ได้รับการประเมินผลทักษะวิชาชีพและการฝึกปฏิบัติเข้มข้นในระบบโครงสร้างฐานข้อมูลองค์กร รวมถึงกลวิธีการบริหารกระบวนการแปลงข้อมูลและการเข้าถึงข้อมูลสารสนเทศอย่างเป็นเอกภาพและปลอดภัยสูงสุด
                                </p>
                            </div>
                        </div>
                    </div>

                    <!-- Certificate 2 -->
                    <div class="glass-card rounded-2xl overflow-hidden flex flex-col group h-full">
                        <!-- High Resolution Scaled Frame -->
                        <div class="h-56 sm:h-64 bg-slate-100 relative overflow-hidden flex items-center justify-center border-b border-slate-100">
                            <div class="absolute inset-0 bg-gradient-to-b from-brandBlue-50/25 to-transparent z-10"></div>
                            <div class="absolute inset-0 flex flex-col items-center justify-center p-6 text-center text-slate-400 font-tech font-bold select-none group-hover:scale-105 transition-transform duration-500">
                                <i class="fa-solid fa-shield-halved text-brandBlue-600/15 text-7xl mb-2"></i>
                                <span class="text-xs text-slate-400 max-w-xs font-sans">ทักษะการเพิ่มประสิทธิภาพการทำงานด้วยหุ่นยนต์ซอฟต์แวร์ RPA</span>
                            </div>
                        </div>
                        <div class="p-6 flex-grow flex flex-col justify-between space-y-3">
                            <div class="space-y-1.5">
                                <span class="font-tech text-xs tracking-widest text-brandBlue-600 font-bold">[ PRO_SKILLS_TRAINING ]</span>
                                <h3 class="font-sans text-xl font-bold text-slate-900 leading-snug group-hover:text-brandBlue-600 transition-colors">
                                    ใบรับรองทักษะวิชาชีพการใช้โปรแกรมวิเคราะห์ข้อมูลสำหรับองค์กรสมัยใหม่
                                </h3>
                                <p class="text-slate-600 text-sm font-sans leading-relaxed">
                                    สมาคมไอทีและผู้ประกอบการธุรกิจดิจิทัลมอบสิทธิรับรองผลทักษะการใช้งานโปรแกรม Power BI, Figma และแพลตฟอร์มวิเคราะห์เชิงสถิติชั้นนำ ตลอดจนการสร้างเวิร์กโฟลว์ข้อมูลแบบไร้รอยต่อ
                                </p>
                            </div>
                        </div>
                    </div>

                </div>
            </section>

            <!-- COHESIVE DIVIDER -->
            <div class="flex items-center justify-between py-2 border-t border-dashed border-slate-200 text-[10px] tracking-widest text-slate-400 font-tech px-2">
                <span>[ INDEX: 05 // ENGAGEMENTS ]</span>
                <span class="w-24 border-t border-slate-200"></span>
                <span>[ ENGAGEMENT_HISTOGRAM ]</span>
            </div>

            <!-- SECTION 6: ACTIVITIES (Clear, Interactive Timelines) -->
            <section id="activities" class="scroll-mt-24 reveal-element">
                <!-- Section Header -->
                <div class="mb-10 text-center md:text-left">
                    <div class="inline-flex items-center gap-2 mb-2">
                        <span class="w-8 h-[2px] bg-brandBlue-500"></span>
                        <span class="font-tech text-xs tracking-[0.3em] text-brandBlue-600 uppercase font-bold">Leadership</span>
                    </div>
                    <h2 class="font-serif italic text-4xl sm:text-5xl md:text-6xl font-bold text-slate-900">Extracurricular Activities</h2>
                </div>

                <!-- Structured Timed Stream Layout -->
                <div class="space-y-4">
                    
                    <!-- Activity 1 -->
                    <div class="glass-card p-6 sm:p-8 rounded-2xl relative overflow-hidden group">
                        <div class="flex flex-col md:flex-row items-start md:items-center justify-between gap-4">
                            <div class="flex items-start gap-4">
                                <div class="w-12 h-12 rounded-xl bg-brandBlue-50 border border-brandBlue-200 flex items-center justify-center text-brandBlue-600 shrink-0 shadow-sm">
                                    <i class="fa-solid fa-users-viewfinder text-lg"></i>
                                </div>
                                <div>
                                    <h3 class="font-sans text-lg font-bold text-slate-900 group-hover:text-brandBlue-600 transition-colors">
                                        ผู้นำกิจกรรมและจัดสัมมนาวิชาการสาขาธุรกิจดิจิทัล
                                    </h3>
                                    <p class="text-slate-600 text-sm font-sans mt-1">
                                        ร่วมประสานงานกับคณาจารย์ประจำคณะการบัญชีและการจัดการ มหาวิทยาลัยมหาสารคาม ในการจัดกิจกรรมพัฒนาทักษะวิชาชีพ แนะนำการใช้แพลตฟอร์มประมวลผลข้อมูล และสนับสนุนการปรับความรู้เทคโนโลยีสารสนเทศให้กับกลุ่มนิสิต
                                    </p>
                                </div>
                            </div>
                            <div class="md:text-right shrink-0">
                                <span class="px-3 py-1.5 rounded-lg bg-brandBlue-50 text-brandBlue-700 border border-brandBlue-200 font-tech text-xs font-bold shadow-sm">
                                    MSU CAMPUS ACTS
                                </span>
                            </div>
                        </div>
                    </div>

                    <!-- Activity 2 -->
                    <div class="glass-card p-6 sm:p-8 rounded-2xl relative overflow-hidden group">
                        <div class="flex flex-col md:flex-row items-start md:items-center justify-between gap-4">
                            <div class="flex items-start gap-4">
                                <div class="w-12 h-12 rounded-xl bg-brandBlue-50 border border-brandBlue-200 flex items-center justify-center text-brandBlue-600 shrink-0 shadow-sm">
                                    <i class="fa-solid fa-code-branch text-lg"></i>
                                </div>
                                <div>
                                    <h3 class="font-sans text-lg font-bold text-slate-900 group-hover:text-brandBlue-600 transition-colors">
                                        ตัวแทนนำเสนอบทความและผลงานนวัตกรรมดิจิทัลระดับสถาบัน
                                    </h3>
                                    <p class="text-slate-600 text-sm font-sans mt-1">
                                        ร่วมกับทีมพัฒนานวัตกรรมนำเสนอโครงงานวิจัยการเพิ่มประสิทธิภาพฐานข้อมูลโรงเรียนและต้นแบบระบบอัตโนมัติแจ้งพัสดุหอพัก ตกแต่งสไลด์การอธิบาย และบรรยายข้อมูลทางวิชาการให้ผู้ประเมินได้อย่างลื่นไหลและเข้าใจง่าย
                                    </p>
                                </div>
                            </div>
                            <div class="md:text-right shrink-0">
                                <span class="px-3 py-1.5 rounded-lg bg-brandBlue-50 text-brandBlue-700 border border-brandBlue-200 font-tech text-xs font-bold shadow-sm">
                                    EXHIBITION LEAD
                                </span>
                            </div>
                        </div>
                    </div>

                </div>
            </section>

            <!-- COHESIVE DIVIDER -->
            <div class="flex items-center justify-between py-2 border-t border-dashed border-slate-200 text-[10px] tracking-widest text-slate-400 font-tech px-2">
                <span>[ INDEX: 06 // GATEWAY ]</span>
                <span class="w-24 border-t border-slate-200"></span>
                <span>[ SMTP_CONNECTIVITY_ESTABLISHED ]</span>
            </div>

            <!-- SECTION 7: CONTACT (Sleek Data Center Aesthetic) -->
            <section id="contact" class="scroll-mt-24 reveal-element">
                <!-- Section Header -->
                <div class="mb-10 text-center md:text-left">
                    <div class="inline-flex items-center gap-2 mb-2">
                        <span class="w-8 h-[2px] bg-brandBlue-500"></span>
                        <span class="font-tech text-xs tracking-[0.3em] text-brandBlue-600 uppercase font-bold">Connect</span>
                    </div>
                    <h2 class="font-serif italic text-4xl sm:text-5xl md:text-6xl font-bold text-slate-900">Get In Touch</h2>
                </div>

                <!-- Structured Layout -->
                <div class="glass-card rounded-2xl p-6 sm:p-8 md:p-10 grid grid-cols-1 lg:grid-cols-12 gap-10 items-start relative overflow-hidden bg-gradient-to-br from-white to-slate-50/50">
                    <div class="absolute top-0 right-0 w-64 h-64 bg-brandBlue-100/10 rounded-full blur-3xl pointer-events-none"></div>

                    <!-- Left: Technical Contact Badges -->
                    <div class="lg:col-span-5 space-y-6">
                        <div class="space-y-3">
                            <h3 class="font-serif italic text-3xl font-bold text-slate-900">Let's build a smarter system together.</h3>
                            <p class="text-slate-600 text-base font-sans leading-relaxed">
                                ยินดีต้อนรับร่วมงาน สหกิจศึกษา สัมภาษณ์งาน ตลอดจนแลกเปลี่ยนความเข้าใจเพื่อประยุกต์ใช้งานระบบฐานข้อมูล การวิเคราะห์ข้อมูลเชิงธุรกิจ และพัฒนาระบบธุรกิจดิจิทัลให้มีประสิทธิภาพสูงสุด
                            </p>
                        </div>

                        <!-- Info details row -->
                        <div class="space-y-4 pt-6 border-t border-slate-100">
                            <!-- Detail 1 -->
                            <div class="flex items-center gap-3">
                                <div class="w-11 h-11 rounded-lg bg-white flex items-center justify-center text-brandBlue-600 border border-slate-100 shadow-sm">
                                    <i class="fa-solid fa-envelope text-sm"></i>
                                </div>
                                <div class="text-left">
                                    <span class="text-[10px] text-slate-400 font-tech tracking-wider font-bold block">EMAIL ADDRESS</span>
                                    <a href="mailto:Nonglukkluanthaisong@gmail.com" class="text-slate-700 hover:text-brandBlue-600 text-sm font-sans font-semibold transition-colors">
                                        Nonglukkluanthaisong@gmail.com
                                    </a>
                                </div>
                            </div>
                            
                            <!-- Detail 2 -->
                            <div class="flex items-center gap-3">
                                <div class="w-11 h-11 rounded-lg bg-white flex items-center justify-center text-brandBlue-600 border border-slate-100 shadow-sm">
                                    <i class="fa-solid fa-phone text-sm"></i>
                                </div>
                                <div class="text-left">
                                    <span class="text-[10px] text-slate-400 font-tech tracking-wider font-bold block">CONTACT NUMBER</span>
                                    <a href="tel:0945705055" class="text-slate-700 hover:text-brandBlue-600 text-sm font-sans font-semibold transition-colors">
                                        094-570-5055
                                    </a>
                                </div>
                            </div>

                            <!-- Detail 3 -->
                            <div class="flex items-center gap-3">
                                <div class="w-11 h-11 rounded-lg bg-white flex items-center justify-center text-brandBlue-600 border border-slate-100 shadow-sm">
                                    <i class="fa-brands fa-line text-sm"></i>
                                </div>
                                <div class="text-left">
                                    <span class="text-[10px] text-slate-400 font-tech tracking-wider font-bold block">LINE ID DIRECTORY</span>
                                    <span class="text-slate-700 text-sm font-sans font-semibold">nongluk_ing</span>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- Right: Minimalist Terminal Form -->
                    <div class="lg:col-span-7 bg-white p-6 sm:p-8 rounded-xl border border-slate-100 space-y-4 shadow-sm">
                        <div class="flex items-center justify-between border-b border-slate-100 pb-2 mb-2 text-[10px] tracking-widest text-slate-400 font-tech font-bold">
                            <span>[ TERMINAL_MAILER: ACTIVE ]</span>
                            <span class="w-3 h-3 rounded-full bg-emerald-500/20 flex items-center justify-center">
                                <span class="w-1.5 h-1.5 rounded-full bg-emerald-500 animate-pulse"></span>
                            </span>
                        </div>
                        
                        <form id="contact-form" class="space-y-4" onsubmit="event.preventDefault();">
                            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                                <div class="space-y-1.5">
                                    <label class="text-[10px] text-slate-400 tracking-wider font-tech uppercase font-bold block">Full Name</label>
                                    <input type="text" placeholder="John Doe" class="w-full bg-slate-50 border border-slate-100 rounded-lg px-3 py-2.5 text-sm text-slate-800 placeholder-slate-400 focus:outline-none focus:border-brandBlue-500 focus:bg-white transition-all" required>
                                </div>
                                <div class="space-y-1.5">
                                    <label class="text-[10px] text-slate-400 tracking-wider font-tech uppercase font-bold block">Email Address</label>
                                    <input type="email" placeholder="john@example.com" class="w-full bg-slate-50 border border-slate-100 rounded-lg px-3 py-2.5 text-sm text-slate-800 placeholder-slate-400 focus:outline-none focus:border-brandBlue-500 focus:bg-white transition-all" required>
                                </div>
                            </div>
                            <div class="space-y-1.5">
                                <label class="text-[10px] text-slate-400 tracking-wider font-tech uppercase font-bold block">Message</label>
                                <textarea rows="4" placeholder="สวัสดีค่ะ คุณนงลักษณ์..." class="w-full bg-slate-50 border border-slate-100 rounded-lg px-3 py-2.5 text-sm text-slate-800 placeholder-slate-400 focus:outline-none focus:border-brandBlue-500 focus:bg-white transition-all" required></textarea>
                            </div>
                            <button type="submit" class="w-full py-3.5 rounded-lg bg-brandBlue-600 text-white font-tech font-bold text-xs tracking-widest hover:bg-brandBlue-700 transition-colors uppercase shadow-sm">
                                [ SEND MESSAGE VIA SMTP ]
                            </button>
                        </form>
                    </div>
                </div>
            </section>

        </main>

        <!-- Footer System -->
        <footer class="border-t border-slate-100 py-6 text-center text-[10px] text-slate-400 bg-white/40 font-tech z-10">
            <div class="max-w-[1440px] mx-auto px-6 flex flex-col sm:flex-row items-center justify-between gap-4 font-bold">
                <p>&copy; 2026 NGL.KLUANTHAI. ALL METRICS CONFIRMED SYSTEM_OK.</p>
                <div class="flex items-center gap-4 text-[9px] tracking-widest">
                    <span>LAT_LON: 16.25, 103.25</span>
                    <span class="w-1.5 h-1.5 rounded-full bg-brandBlue-500 animate-ping"></span>
                    <span>ONLINE DATA STREAM</span>
                </div>
            </div>
        </footer>

    </div>

    <!-- Advanced Animation Systems & Intersection Observers -->
    <script>
        // Mathematical Constellation Background Mechanics (Adjusted for white-blue light theme)
        const canvas = document.getElementById('neural-canvas');
        const ctx = canvas.getContext('2d');
        let points = [];
        let mouseX = 0;
        let mouseY = 0;
        
        function resizeCanvas() {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
            initPoints();
        }

        function initPoints() {
            points = [];
            const count = Math.min(Math.floor(window.innerWidth / 15), 110);
            for (let i = 0; i < count; i++) {
                points.push({
                    x: Math.random() * canvas.width,
                    y: Math.random() * canvas.height,
                    vx: (Math.random() - 0.5) * 0.22,
                    vy: (Math.random() - 0.5) * 0.22,
                    r: Math.random() * 1.5 + 1
                });
            }
        }

        function animateConstellation() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            
            // Render connections with math matrix
            for (let i = 0; i < points.length; i++) {
                const p1 = points[i];
                p1.x += p1.vx;
                p1.y += p1.vy;

                // Wall Collision
                if (p1.x < 0 || p1.x > canvas.width) p1.vx *= -1;
                if (p1.y < 0 || p1.y > canvas.height) p1.vy *= -1;

                // Connect logic with mouse magnet tracking
                const dxMouse = mouseX - p1.x;
                const dyMouse = mouseY - p1.y;
                const distMouse = Math.sqrt(dxMouse * dxMouse + dyMouse * dyMouse);
                if (distMouse < 180) {
                    p1.x += dxMouse * 0.012;
                    p1.y += dyMouse * 0.012;
                }

                // Render Node Point
                ctx.beginPath();
                ctx.arc(p1.x, p1.y, p1.r, 0, Math.PI * 2);
                ctx.fillStyle = 'rgba(2, 132, 199, 0.4)';
                ctx.fill();

                for (let j = i + 1; j < points.length; j++) {
                    const p2 = points[j];
                    const dx = p1.x - p2.x;
                    const dy = p1.y - p2.y;
                    const dist = Math.sqrt(dx * dx + dy * dy);

                    if (dist < 110) {
                        ctx.beginPath();
                        ctx.moveTo(p1.x, p1.y);
                        ctx.lineTo(p2.x, p2.y);
                        ctx.strokeStyle = `rgba(14, 165, 233, ${0.12 * (1 - dist / 110)})`;
                        ctx.lineWidth = 0.55;
                        ctx.stroke();
                    }
                }
            }
            requestAnimationFrame(animateConstellation);
        }

        window.addEventListener('mousemove', (e) => {
            mouseX = e.clientX;
            mouseY = e.clientY;
        });

        window.addEventListener('resize', resizeCanvas);
        window.addEventListener('load', () => {
            resizeCanvas();
            animateConstellation();
        });

        // Smart Header Hide/Show Mechanics
        let lastScrollTop = 0;
        const mainHeader = document.getElementById('main-header');
        
        window.addEventListener('scroll', () => {
            let scrollTop = window.pageYOffset || document.documentElement.scrollTop;
            
            // Hide on down scroll, Show on up scroll
            if (scrollTop > lastScrollTop && scrollTop > 100) {
                mainHeader.classList.add('header-hidden');
            } else {
                mainHeader.classList.remove('header-hidden');
            }
            lastScrollTop = scrollTop <= 0 ? 0 : scrollTop;
            
            // Render scroll progress
            const totalHeight = document.documentElement.scrollHeight - window.innerHeight;
            const progress = (scrollTop / totalHeight) * 100;
            document.getElementById('scroll-progress').style.width = `${progress}%`;
        });

        // Mobile Menu Interactivity
        const mobileToggle = document.getElementById('mobile-toggle');
        const mobileDropdown = document.getElementById('mobile-dropdown');
        
        mobileToggle.addEventListener('click', () => {
            mobileDropdown.classList.toggle('hidden');
        });

        document.querySelectorAll('.mobile-link').forEach(link => {
            link.addEventListener('click', () => {
                mobileDropdown.classList.add('hidden');
            });
        });

        // Silky Smooth Sliding Underline Tracker & Section Highlight
        const navLinks = document.querySelectorAll('.nav-link');
        const indicator = document.getElementById('underline-indicator');
        const sections = document.querySelectorAll('section');

        function updateTrackerPosition(activeLink) {
            if (!activeLink) {
                indicator.style.width = '0px';
                return;
            }
            const rect = activeLink.getBoundingClientRect();
            const parentRect = activeLink.parentElement.getBoundingClientRect();
            
            indicator.style.width = `${rect.width}px`;
            indicator.style.left = `${rect.left - parentRect.left}px`;
        }

        // Observer engine for highlight and scroll reveal transitions
        const observerOptions = {
            root: null,
            rootMargin: '-24% 0px -24% 0px', // Precise threshold for smoother trigger zones
            threshold: 0.12
        };

        const activeSectionObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    const secId = entry.target.getAttribute('id');
                    
                    // Highlight header link
                    navLinks.forEach(link => {
                        if (link.getAttribute('data-sec') === secId) {
                            link.classList.add('text-slate-900');
                            link.classList.remove('text-slate-600');
                            updateTrackerPosition(link);
                        } else {
                            link.classList.remove('text-slate-900');
                            link.classList.add('text-slate-600');
                        }
                    });
                }
            });
        }, observerOptions);

        sections.forEach(section => {
            activeSectionObserver.observe(section);
        });

        // Set up active link tracker on window resizing
        window.addEventListener('resize', () => {
            const activeLink = document.querySelector('.nav-link.text-slate-900');
            updateTrackerPosition(activeLink);
        });

        // Scroll Reveal Handler with Ease-Out-Cubic curves
        const revealObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('active');
                }
            });
        }, {
            root: null,
            rootMargin: '0px 0px -8% 0px',
            threshold: 0.08
        });

        document.querySelectorAll('.reveal-element').forEach(el => {
            revealObserver.observe(el);
        });
    </script>
</body>
</html>
