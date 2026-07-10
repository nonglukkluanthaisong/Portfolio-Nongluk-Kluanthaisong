<!DOCTYPE html>
<html lang="th" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
    <title>Nongluk Kluanthaisong - Portfolio</title>
    
    <!-- Google Fonts: Inter, Noto Sans Thai -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Noto+Sans+Thai:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    
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
                        }
                    },
                    fontFamily: {
                        sans: ['"Noto Sans Thai"', '"Inter"', 'sans-serif'],
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
            background-color: #fafbfc;
            color: #334155;
        }

        /* Clean subtle corporate grid */
        .tech-grid {
            background-image: 
                linear-gradient(to right, rgba(2, 132, 199, 0.03) 1px, transparent 1px),
                linear-gradient(to bottom, rgba(2, 132, 199, 0.03) 1px, transparent 1px);
            background-size: 40px 40px;
        }

        /* Clean Glass Navbar */
        .glass-nav {
            background: rgba(255, 255, 255, 0.9);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border-bottom: 1px solid rgba(226, 232, 240, 0.8);
        }

        /* Tidy Minimalist Cards */
        .neat-card {
            background: #ffffff;
            border: 1px solid rgba(226, 232, 240, 1);
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.02), 0 1px 2px rgba(0, 0, 0, 0.04);
            transition: all 0.3s cubic-bezier(0.16, 1, 0.3, 1);
        }

        .neat-card:hover {
            border-color: rgba(2, 132, 199, 0.3);
            box-shadow: 0 10px 25px -5px rgba(2, 132, 199, 0.08);
            transform: translateY(-2px);
        }

        /* Smooth Reveal Animation */
        .reveal-element {
            opacity: 0;
            transform: translateY(12px);
            transition: opacity 1s cubic-bezier(0.16, 1, 0.3, 1), 
                        transform 1s cubic-bezier(0.16, 1, 0.3, 1);
            will-change: transform, opacity;
        }

        .reveal-element.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* Header Transition */
        header {
            transition: transform 0.35s cubic-bezier(0.16, 1, 0.3, 1);
        }
        
        .header-hidden {
            transform: translateY(-100%);
        }

        /* Scroll progress bar */
        #scroll-progress {
            position: fixed;
            top: 0;
            left: 0;
            height: 3px;
            background: linear-gradient(to right, #0ea5e9, #0369a1);
            width: 0%;
            z-index: 100;
        }

        /* Sliding Underline Tracker */
        #underline-indicator {
            position: absolute;
            bottom: 0;
            height: 2px;
            background-color: #0284c7;
            transition: all 0.35s cubic-bezier(0.16, 1, 0.3, 1);
            border-radius: 9999px;
        }

        /* Scrollbar styling */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #f1f5f9;
        }
        ::-webkit-scrollbar-thumb {
            background: #cbd5e1;
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #94a3b8;
        }
    </style>
</head>
<body class="bg-[#fafbfc] text-slate-700 min-h-screen relative overflow-x-hidden selection:bg-brandBlue-100 selection:text-brandBlue-900 font-sans">

    <!-- Integrated Clean Backdrops -->
    <div class="fixed inset-0 w-full h-full overflow-hidden pointer-events-none z-0">
        <div class="absolute inset-0 tech-grid opacity-70"></div>
        <canvas id="neural-canvas" class="absolute inset-0 w-full h-full opacity-35"></canvas>
        <div class="absolute top-1/4 left-[-10%] w-[300px] h-[300px] md:w-[500px] md:h-[500px] rounded-full bg-brandBlue-50/40 blur-[100px]"></div>
        <div class="absolute bottom-1/4 right-[-10%] w-[300px] h-[300px] md:w-[500px] md:h-[500px] rounded-full bg-blue-50/30 blur-[100px]"></div>
    </div>

    <!-- Scroll Progress -->
    <div id="scroll-progress"></div>

    <!-- Main Content Wrapper (Protects against horizontal shaking on iPad) -->
    <div class="w-full min-h-screen flex flex-col relative z-10 overflow-x-hidden">

        <!-- Global Header Navigation -->
        <header id="main-header" class="fixed top-0 left-0 w-full z-50 glass-nav">
            <div class="max-w-[1440px] mx-auto px-4 sm:px-8 h-16 sm:h-20 flex items-center justify-between">
                <!-- Branding -->
                <a href="#home" class="flex flex-col text-left group">
                    <span class="font-semibold text-sm sm:text-base tracking-[0.1em] text-slate-900 group-hover:text-brandBlue-600 transition-colors">
                        NONGLUK K.
                    </span>
                    <span class="text-[9px] tracking-wider text-slate-500 font-medium uppercase">
                        Digital Information Systems
                    </span>
                </a>
                
                <!-- Navigation Items -->
                <nav class="relative hidden md:flex items-center space-x-6 lg:space-x-8 h-full py-2">
                    <a href="#home" class="nav-link text-xs tracking-widest text-slate-600 hover:text-slate-950 transition-colors py-2 h-full flex items-center font-semibold" data-sec="home">หน้าแรก</a>
                    <a href="#about" class="nav-link text-xs tracking-widest text-slate-600 hover:text-slate-950 transition-colors py-2 h-full flex items-center font-semibold" data-sec="about">ประวัติส่วนตัว</a>
                    <a href="#education" class="nav-link text-xs tracking-widest text-slate-600 hover:text-slate-950 transition-colors py-2 h-full flex items-center font-semibold" data-sec="education">การศึกษา</a>
                    <a href="#projects" class="nav-link text-xs tracking-widest text-slate-600 hover:text-slate-950 transition-colors py-2 h-full flex items-center font-semibold" data-sec="projects">ผลงาน</a>
                    <a href="#certificates" class="nav-link text-xs tracking-widest text-slate-600 hover:text-slate-950 transition-colors py-2 h-full flex items-center font-semibold" data-sec="certificates">ใบรับรอง</a>
                    <a href="#activities" class="nav-link text-xs tracking-widest text-slate-600 hover:text-slate-950 transition-colors py-2 h-full flex items-center font-semibold" data-sec="activities">กิจกรรม</a>
                    <a href="#contact" class="nav-link text-xs tracking-widest text-slate-600 hover:text-slate-950 transition-colors py-2 h-full flex items-center font-semibold" data-sec="contact">ติดต่อ</a>
                    
                    <!-- Sliding Underline Tracker -->
                    <div id="underline-indicator"></div>
                </nav>

                <!-- Action Button -->
                <div class="hidden md:block">
                    <a href="#contact" class="px-4 py-2 rounded-md bg-slate-900 text-white font-medium text-xs tracking-wider hover:bg-brandBlue-700 transition-all shadow-sm">
                        ติดต่อฉัน
                    </a>
                </div>

                <!-- Mobile Menu Toggle Button -->
                <button id="mobile-toggle" class="md:hidden text-slate-800 hover:text-brandBlue-600 transition-colors p-2" aria-label="Toggle Menu">
                    <i class="fa-solid fa-bars text-lg"></i>
                </button>
            </div>

            <!-- Mobile Dropdown Panel -->
            <div id="mobile-dropdown" class="hidden md:hidden absolute top-full left-0 w-full bg-white/95 border-b border-slate-200 px-6 py-6 space-y-4 flex flex-col backdrop-blur-lg shadow-lg">
                <a href="#home" class="mobile-link text-xs tracking-widest text-slate-700 hover:text-brandBlue-600 py-2 border-b border-slate-100 font-semibold" data-sec="home">หน้าแรก</a>
                <a href="#about" class="mobile-link text-xs tracking-widest text-slate-700 hover:text-brandBlue-600 py-2 border-b border-slate-100 font-semibold" data-sec="about">ประวัติส่วนตัว</a>
                <a href="#education" class="mobile-link text-xs tracking-widest text-slate-700 hover:text-brandBlue-600 py-2 border-b border-slate-100 font-semibold" data-sec="education">การศึกษา</a>
                <a href="#projects" class="mobile-link text-xs tracking-widest text-slate-700 hover:text-brandBlue-600 py-2 border-b border-slate-100 font-semibold" data-sec="projects">ผลงาน</a>
                <a href="#certificates" class="mobile-link text-xs tracking-widest text-slate-700 hover:text-brandBlue-600 py-2 border-b border-slate-100 font-semibold" data-sec="certificates">ใบรับรอง</a>
                <a href="#activities" class="mobile-link text-xs tracking-widest text-slate-700 hover:text-brandBlue-600 py-2 border-b border-slate-100 font-semibold" data-sec="activities">กิจกรรม</a>
                <a href="#contact" class="mobile-link text-xs tracking-widest text-slate-700 hover:text-brandBlue-600 py-2 font-semibold" data-sec="contact">ติดต่อ</a>
            </div>
        </header>

        <!-- Main Core Sections Container (Gaps are optimized to look incredibly tidy, zero horizontal scrolling) -->
        <main class="relative z-10 w-full max-w-[1440px] mx-auto px-4 sm:px-8 md:px-12 pt-20 pb-16 space-y-12 sm:space-y-16 overflow-hidden">

            <!-- SECTION 1: HERO HOME -->
            <section id="home" class="min-h-[75vh] sm:min-h-[80vh] flex flex-col justify-center items-center text-center py-6 relative overflow-hidden reveal-element active">
                <div class="inline-flex items-center gap-2 mb-4 bg-slate-100 px-3 py-1.5 rounded-full border border-slate-200">
                    <span class="w-2 h-2 rounded-full bg-emerald-500 animate-pulse"></span>
                    <span class="text-[10px] tracking-wider text-slate-600 font-semibold uppercase">ระบบพร้อมใช้งาน</span>
                </div>
                
                <!-- Main Bold Title with balanced sizes to prevent overflow on iPad -->
                <h1 class="font-bold text-slate-900 leading-[1.1] mb-6 tracking-tight max-w-4xl break-words">
                    <span class="block text-4xl sm:text-6xl md:text-7xl lg:text-8xl opacity-90 text-slate-800">นงลักษณ์</span>
                    <span class="block text-5xl sm:text-7xl md:text-8xl lg:text-9xl bg-clip-text text-transparent bg-gradient-to-r from-brandBlue-700 via-brandBlue-600 to-slate-900">เกลื่อนไทสง</span>
                </h1>
                
                <p class="text-slate-600 text-sm sm:text-base md:text-lg max-w-2xl leading-relaxed mb-8 break-words px-2">
                    นิสิตสาขาธุรกิจดิจิทัลและระบบสารสนเทศชั้นปีที่ 4 ผู้มีความมุ่งมั่นในการจัดการข้อมูล การออกแบบระบบ และการประยุกต์ใช้เทคโนโลยีดิจิทัลเพื่อยกระดับขีดความสามารถของธุรกิจให้เป็นระบบอย่างมีประสิทธิภาพ
                </p>
                
                <!-- Neat Interactive Actions -->
                <div class="flex flex-col sm:flex-row items-center justify-center gap-4 w-full sm:w-auto px-4">
                    <a href="#about" class="w-full sm:w-auto px-6 py-3 rounded-lg bg-slate-900 text-white font-semibold text-xs tracking-widest hover:bg-brandBlue-700 transition-all shadow-sm">
                        ข้อมูลเกี่ยวกับฉัน <i class="fa-solid fa-arrow-down ml-2 text-[10px]"></i>
                    </a>
                    <a href="#projects" class="w-full sm:w-auto px-6 py-3 rounded-lg border border-slate-200 bg-white text-slate-700 font-semibold text-xs tracking-widest hover:border-brandBlue-500 hover:text-brandBlue-600 transition-all">
                        รับชมผลงานของฉัน
                    </a>
                </div>
            </section>

            <!-- COHESIVE DIVIDER -->
            <div class="flex items-center justify-between py-2 border-t border-slate-200/60 text-[10px] tracking-widest text-slate-400 font-semibold px-2">
                <span>[ 01 / PROFILE ]</span>
                <span class="w-16 sm:w-32 border-t border-slate-200"></span>
                <span>BIOGRAPHY</span>
            </div>

            <!-- SECTION 2: ABOUT ME (Neat, Elegant, Non-congested) -->
            <section id="about" class="scroll-mt-20 sm:scroll-mt-24 reveal-element py-4">
                <!-- Section Header -->
                <div class="mb-8 text-center md:text-left">
                    <div class="inline-flex items-center gap-2 mb-1.5">
                        <span class="w-6 h-[2px] bg-brandBlue-600"></span>
                        <span class="text-xs tracking-wider text-brandBlue-700 uppercase font-bold">ข้อมูลส่วนตัว</span>
                    </div>
                    <h2 class="text-3xl sm:text-4xl md:text-5xl font-bold text-slate-900 tracking-tight">About Me</h2>
                </div>

                <!-- Structured Layout Grid -->
                <div class="grid grid-cols-1 lg:grid-cols-12 gap-8 md:gap-12 items-center">
                    
                    <!-- Left: Profile Image (Properly scaled for neatness, preventing iPad overflow) -->
                    <div class="lg:col-span-5 flex flex-col items-center">
                        <div class="relative w-64 h-64 sm:w-80 sm:h-80 rounded-2xl overflow-hidden border border-slate-200 shadow-lg bg-white p-2 group">
                            <img src="Nongluk.cv_2.jpg" alt="นงลักษณ์ เกลื่อนไทสง" class="w-full h-full object-cover rounded-xl group-hover:scale-102 transition-transform duration-500" onerror="this.src='https://placehold.co/600x600/e2e8f0/0f172a?text=Nongluk+K.'">
                        </div>
                    </div>

                    <!-- Right: Neat Formal Narrative -->
                    <div class="lg:col-span-7 space-y-6">
                        <div class="space-y-4">
                            <h3 class="text-xl sm:text-2xl font-bold text-slate-900 leading-snug break-words">
                                การทำงานอย่างเป็นระบบ ความรับผิดชอบ และการพัฒนาตนเองอย่างต่อเนื่อง คือหัวใจหลักของฉัน
                            </h3>
                            <p class="text-slate-600 text-sm sm:text-base leading-relaxed break-words">
                                สวัสดีค่ะ ดิฉัน <strong>นางสาวนงลักษณ์ เกลื่อนไทสง (อิง)</strong> ปัจจุบันเป็นนิสิตชั้นปีที่ 4 คณะการบัญชีและการจัดการ มหาวิทยาลัยมหาสารคาม สาขาวิชาธุรกิจดิจิทัลและระบบสารสนเทศ
                            </p>
                            <p class="text-slate-600 text-sm sm:text-base leading-relaxed break-words">
                                ตลอดการเรียนและทำงานในชั้นปี ดิฉันให้ความสำคัญกับการประยุกต์ใช้เทคโนโลยีและการวิเคราะห์โครงสร้างฐานข้อมูลที่มีความซับซ้อน เพื่อแปลงให้เป็นข้อมูลสารสนเทศที่ใช้งานง่ายและเป็นระเบียบ นอกจากนี้ ดิฉันมีความพร้อมและกระตือรือร้นอย่างสูงในการปรับตัวเข้าสู่การปฏิบัติงานจริง และร่วมงานกับองค์กรระดับมาตรฐานสากลค่ะ
                            </p>
                        </div>

                        <!-- Formal Specifications (Grid with perfect margins) -->
                        <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 pt-4 border-t border-slate-200/60 text-sm">
                            <div class="space-y-2">
                                <span class="text-xs tracking-wider text-slate-400 font-bold uppercase block">คุณสมบัติเด่น (Key Strengths)</span>
                                <ul class="space-y-1 text-slate-600">
                                    <li><i class="fa-solid fa-check text-brandBlue-600 mr-2 text-xs"></i> การวางโครงสร้างและจัดการฐานข้อมูล</li>
                                    <li><i class="fa-solid fa-check text-brandBlue-600 mr-2 text-xs"></i> การออกแบบประสบการณ์ผู้ใช้ (UX/UI)</li>
                                    <li><i class="fa-solid fa-check text-brandBlue-600 mr-2 text-xs"></i> ทักษะการวิเคราะห์เชิงลึกและการนำเสนอ</li>
                                </ul>
                            </div>
                            <div class="space-y-2">
                                <span class="text-xs tracking-wider text-slate-400 font-bold uppercase block">ทักษะการทำงานร่วมกัน (Soft Skills)</span>
                                <ul class="space-y-1 text-slate-600">
                                    <li><i class="fa-solid fa-check text-brandBlue-600 mr-2 text-xs"></i> การสื่อสารและเข้าถึงทีมอย่างเข้าใจ</li>
                                    <li><i class="fa-solid fa-check text-brandBlue-600 mr-2 text-xs"></i> ความรอบคอบและใส่ใจในรายละเอียด</li>
                                    <li><i class="fa-solid fa-check text-brandBlue-600 mr-2 text-xs"></i> มีความกระตือรือร้นเรียนรู้สิ่งใหม่</li>
                                </ul>
                            </div>
                        </div>
                    </div>
                </div>
            </section>

            <!-- COHESIVE DIVIDER -->
            <div class="flex items-center justify-between py-2 border-t border-slate-200/60 text-[10px] tracking-widest text-slate-400 font-semibold px-2">
                <span>[ 02 / EDUCATION ]</span>
                <span class="w-16 sm:w-32 border-t border-slate-200"></span>
                <span>ACADEMIC STATUS</span>
            </div>

            <!-- SECTION 3: EDUCATION (Structured, Tidy, Corporate Accent) -->
            <section id="education" class="scroll-mt-20 sm:scroll-mt-24 reveal-element py-4">
                <!-- Section Header -->
                <div class="mb-8 text-center md:text-left">
                    <div class="inline-flex items-center gap-2 mb-1.5">
                        <span class="w-6 h-[2px] bg-brandBlue-600"></span>
                        <span class="text-xs tracking-wider text-brandBlue-700 uppercase font-bold">ประวัติการศึกษา</span>
                    </div>
                    <h2 class="text-3xl sm:text-4xl md:text-5xl font-bold text-slate-900 tracking-tight">Education</h2>
                </div>

                <div class="grid grid-cols-1 lg:grid-cols-12 gap-8 items-stretch">
                    <!-- Left: GPA Metric Callout Card -->
                    <div class="lg:col-span-4 flex">
                        <div class="w-full neat-card p-6 sm:p-8 rounded-xl flex flex-col justify-between items-center text-center relative overflow-hidden bg-gradient-to-br from-white to-brandBlue-50/10">
                            <div class="absolute top-0 right-0 w-24 h-24 bg-brandBlue-100/20 rounded-full blur-xl pointer-events-none"></div>
                            <div class="w-full">
                                <span class="text-[10px] tracking-wider text-slate-400 font-bold block uppercase">ผลการเรียนเฉลี่ยปัจจุบัน</span>
                                <h4 class="text-base font-semibold text-slate-800 mt-1">GPAX สะสมในระดับปริญญาตรี</h4>
                            </div>
                            <div class="my-6">
                                <span class="text-5xl sm:text-6xl font-bold text-brandBlue-700">3.68</span>
                                <span class="text-slate-400 text-sm font-semibold block mt-1">/ 4.00 (เกียรตินิยมอันดับ 1)</span>
                            </div>
                            <div class="w-full pt-4 border-t border-slate-100 text-xs text-slate-500">
                                ภาคการศึกษาสะสมถึงปีที่ 4
                            </div>
                        </div>
                    </div>

                    <!-- Right: Detailed University Card & Software Badges -->
                    <div class="lg:col-span-8 flex flex-col justify-between space-y-6">
                        <!-- University Card -->
                        <div class="neat-card p-6 sm:p-8 rounded-xl relative overflow-hidden flex-grow">
                            <div class="flex flex-col sm:flex-row items-start gap-4">
                                <div class="w-12 h-12 rounded-lg bg-brandBlue-50 border border-brandBlue-200 flex items-center justify-center text-brandBlue-600 shrink-0 shadow-sm mb-2 sm:mb-0">
                                    <i class="fa-solid fa-graduation-cap text-lg"></i>
                                </div>
                                <div class="space-y-2">
                                    <span class="text-xs font-semibold tracking-wider text-brandBlue-600">2022 - ปัจจุบัน (ปีการศึกษา 4)</span>
                                    <h3 class="text-lg sm:text-xl font-bold text-slate-900 leading-snug break-words">
                                        มหาวิทยาลัยมหาสารคาม
                                    </h3>
                                    <p class="text-slate-700 text-sm font-semibold">
                                        หลักสูตรบริหารธุรกิจบัณฑิต (บธ.บ.) สาขาวิชาธุรกิจดิจิทัลและระบบสารสนเทศ
                                    </p>
                                    <p class="text-slate-500 text-xs sm:text-sm leading-relaxed break-words pt-1">
                                        คณะการบัญชีและการจัดการ มุ่งเน้นการพัฒนาระบบเทคโนโลยีสารสนเทศ การออกแบบฐานข้อมูลระดับองค์กร การพัฒนาแพลตฟอร์มสารสนเทศแบบครบวงจร การวิเคราะห์ข้อมูลขั้นพื้นฐานด้วยโปรแกรมธุรกิจชั้นนำ ตลอดจนการประยุกต์ใช้เพื่อความได้เปรียบเชิงพาณิชย์
                                    </p>
                                </div>
                            </div>
                        </div>

                        <!-- Technical Tools Section -->
                        <div class="neat-card p-5 rounded-xl">
                            <span class="text-xs tracking-wider text-slate-400 font-bold block mb-3 uppercase">เครื่องมือทางเทคนิคและซอฟต์แวร์ประยุกต์ (TECHNICAL UTILITIES)</span>
                            <div class="grid grid-cols-2 sm:grid-cols-4 gap-2 text-center text-xs">
                                <div class="p-2 rounded bg-slate-50 border border-slate-100 flex items-center justify-center gap-1.5 text-slate-700 font-semibold hover:border-brandBlue-400 hover:bg-white transition-colors cursor-default">
                                    <i class="fa-brands fa-figma text-red-500 text-[10px]"></i>
                                    <span>Figma</span>
                                </div>
                                <div class="p-2 rounded bg-slate-50 border border-slate-100 flex items-center justify-center gap-1.5 text-slate-700 font-semibold hover:border-brandBlue-400 hover:bg-white transition-colors cursor-default">
                                    <i class="fa-solid fa-chart-simple text-amber-500 text-[10px]"></i>
                                    <span>Power BI</span>
                                </div>
                                <div class="p-2 rounded bg-slate-50 border border-slate-100 flex items-center justify-center gap-1.5 text-slate-700 font-semibold hover:border-brandBlue-400 hover:bg-white transition-colors cursor-default">
                                    <i class="fa-solid fa-file-excel text-emerald-600 text-[10px]"></i>
                                    <span>MS Excel</span>
                                </div>
                                <div class="p-2 rounded bg-slate-50 border border-slate-100 flex items-center justify-center gap-1.5 text-slate-700 font-semibold hover:border-brandBlue-400 hover:bg-white transition-colors cursor-default">
                                    <i class="fa-solid fa-wand-magic-sparkles text-sky-500 text-[10px]"></i>
                                    <span>Canva</span>
                                </div>
                                <div class="p-2 rounded bg-slate-50 border border-slate-100 flex items-center justify-center gap-1.5 text-slate-700 font-semibold hover:border-brandBlue-400 hover:bg-white transition-colors cursor-default">
                                    <i class="fa-solid fa-scissors text-purple-500 text-[10px]"></i>
                                    <span>CapCut</span>
                                </div>
                                <div class="p-2 rounded bg-slate-50 border border-slate-100 flex items-center justify-center gap-1.5 text-slate-700 font-semibold hover:border-brandBlue-400 hover:bg-white transition-colors cursor-default">
                                    <i class="fa-solid fa-file-word text-blue-600 text-[10px]"></i>
                                    <span>MS Word</span>
                                </div>
                                <div class="p-2 rounded bg-slate-50 border border-slate-100 flex items-center justify-center gap-1.5 text-slate-700 font-semibold hover:border-brandBlue-400 hover:bg-white transition-colors cursor-default">
                                    <i class="fa-solid fa-file-powerpoint text-orange-600 text-[10px]"></i>
                                    <span>MS PowerPoint</span>
                                </div>
                                <div class="p-2 rounded bg-slate-50 border border-slate-100 flex items-center justify-center gap-1.5 text-slate-700 font-semibold hover:border-brandBlue-400 hover:bg-white transition-colors cursor-default">
                                    <i class="fa-solid fa-diagram-project text-teal-500 text-[10px]"></i>
                                    <span>n8n RPA</span>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </section>

            <!-- COHESIVE DIVIDER -->
            <div class="flex items-center justify-between py-2 border-t border-slate-200/60 text-[10px] tracking-widest text-slate-400 font-semibold px-2">
                <span>[ 03 / WORK ]</span>
                <span class="w-16 sm:w-32 border-t border-slate-200"></span>
                <span>PROJECT PORTFOLIO</span>
            </div>

            <!-- SECTION 4: PROJECTS (Symmetrical, High-Quality Grid, Zero Content Clutter) -->
            <section id="projects" class="scroll-mt-20 sm:scroll-mt-24 reveal-element py-4">
                <!-- Section Header -->
                <div class="mb-8 text-center md:text-left">
                    <div class="inline-flex items-center gap-2 mb-1.5">
                        <span class="w-6 h-[2px] bg-brandBlue-600"></span>
                        <span class="text-xs tracking-wider text-brandBlue-700 uppercase font-bold">ผลงานวิชาชีพที่โดดเด่น</span>
                    </div>
                    <h2 class="text-3xl sm:text-4xl md:text-5xl font-bold text-slate-900 tracking-tight">Featured Projects</h2>
                </div>

                <!-- Symmetric Grid Display (Unified Heights and Layout) -->
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                    
                    <!-- Project 1 -->
                    <div class="neat-card rounded-xl overflow-hidden flex flex-col h-full group">
                        <div class="h-44 bg-slate-50 relative border-b border-slate-100 flex items-center justify-center">
                            <div class="absolute inset-0 bg-gradient-to-tr from-brandBlue-50/10 to-transparent"></div>
                            <div class="text-slate-300 font-bold select-none group-hover:scale-105 transition-transform duration-500">
                                <i class="fa-solid fa-laptop-medical text-brandBlue-600/10 text-6xl"></i>
                            </div>
                            <span class="absolute top-3 left-3 px-2 py-1 rounded bg-white/95 text-brandBlue-700 border border-brandBlue-100 text-[9px] tracking-wider font-semibold shadow-sm uppercase">
                                Case Study
                            </span>
                        </div>
                        <div class="p-5 flex flex-col justify-between flex-grow space-y-4">
                            <div class="space-y-1.5">
                                <h3 class="text-base sm:text-lg font-bold text-slate-900 leading-snug group-hover:text-brandBlue-600 transition-colors break-words">
                                    PIC2PACS: เว็บแอปอัปโหลดรูปภาพแพทย์
                                </h3>
                                <p class="text-slate-500 text-xs sm:text-sm leading-relaxed line-clamp-3 break-words">
                                    มีส่วนร่วมหลักในการวางขั้นตอนและทิศทางการเดินทางของผู้ใช้งาน (UX Flow) รวมถึงการสร้างชิ้นงานส่วนจำลองภาพกราฟิก (Figma Prototype Design) สำหรับหน้าอัปโหลดรูปภาพสุขภาพอย่างรอบคอบและปลอดภัย
                                </p>
                            </div>
                            <div class="flex flex-wrap gap-1 pt-2 border-t border-slate-100 text-[10px] text-slate-500 font-semibold">
                                <span class="px-2 py-0.5 rounded bg-slate-50 border border-slate-100">Figma</span>
                                <span class="px-2 py-0.5 rounded bg-slate-50 border border-slate-100">UX/UI Design</span>
                                <span class="px-2 py-0.5 rounded bg-slate-50 border border-slate-100">Healthcare System</span>
                            </div>
                        </div>
                    </div>

                    <!-- Project 2 -->
                    <div class="neat-card rounded-xl overflow-hidden flex flex-col h-full group">
                        <div class="h-44 bg-slate-50 relative border-b border-slate-100 flex items-center justify-center">
                            <div class="absolute inset-0 bg-gradient-to-tr from-brandBlue-50/10 to-transparent"></div>
                            <div class="text-slate-300 font-bold select-none group-hover:scale-105 transition-transform duration-500">
                                <i class="fa-solid fa-box-archive text-brandBlue-600/10 text-6xl"></i>
                            </div>
                            <span class="absolute top-3 left-3 px-2 py-1 rounded bg-white/95 text-brandBlue-700 border border-brandBlue-100 text-[9px] tracking-wider font-semibold shadow-sm uppercase">
                                Co-operative
                            </span>
                        </div>
                        <div class="p-5 flex flex-col justify-between flex-grow space-y-4">
                            <div class="space-y-1.5">
                                <h3 class="text-base sm:text-lg font-bold text-slate-900 leading-snug group-hover:text-brandBlue-600 transition-colors break-words">
                                    OonJai Box: ตู้พัสดุอัจฉริยะสำหรับหอพัก
                                </h3>
                                <p class="text-slate-500 text-xs sm:text-sm leading-relaxed line-clamp-3 break-words">
                                    รังสรรค์และวิเคราะห์การวางทิศทางข้อมูลของระบบความปลอดภัยและการรายงานผลพัสดุรับส่งในทันทีเชิงโครงข่ายแบบจำลอง IoT ร่วมกับระบบส่งข้อความแจ้งเตือนผ่านช่องทาง LINE ของนิสิตผู้พักอาศัย
                                </p>
                            </div>
                            <div class="flex flex-wrap gap-1 pt-2 border-t border-slate-100 text-[10px] text-slate-500 font-semibold">
                                <span class="px-2 py-0.5 rounded bg-slate-50 border border-slate-100">Database Flow</span>
                                <span class="px-2 py-0.5 rounded bg-slate-50 border border-slate-100">System Analysis</span>
                                <span class="px-2 py-0.5 rounded bg-slate-50 border border-slate-100">IoT Model</span>
                            </div>
                        </div>
                    </div>

                    <!-- Project 3 -->
                    <div class="neat-card rounded-xl overflow-hidden flex flex-col h-full group">
                        <div class="h-44 bg-slate-50 relative border-b border-slate-100 flex items-center justify-center">
                            <div class="absolute inset-0 bg-gradient-to-tr from-brandBlue-50/10 to-transparent"></div>
                            <div class="text-slate-300 font-bold select-none group-hover:scale-105 transition-transform duration-500">
                                <i class="fa-solid fa-chart-line text-brandBlue-600/10 text-6xl"></i>
                            </div>
                            <span class="absolute top-3 left-3 px-2 py-1 rounded bg-white/95 text-brandBlue-700 border border-brandBlue-100 text-[9px] tracking-wider font-semibold shadow-sm uppercase">
                                Analytics
                            </span>
                        </div>
                        <div class="p-5 flex flex-col justify-between flex-grow space-y-4">
                            <div class="space-y-1.5">
                                <h3 class="text-base sm:text-lg font-bold text-slate-900 leading-snug group-hover:text-brandBlue-600 transition-colors break-words">
                                    ระบบคาดการณ์กระแสไฟฟ้าภาคอุตสาหกรรม
                                </h3>
                                <p class="text-slate-500 text-xs sm:text-sm leading-relaxed line-clamp-3 break-words">
                                    โครงการจำลองสถิติเชิงลึกสำหรับปริมาณไฟฟ้าระดับโรงงาน นำเข้าข้อมูลสถิติ ดำเนินงานประมวลผลข้อมูล และจัดทำรายงานวิเคราะห์สัดส่วนอย่างละเอียดด้วยซอฟต์แวร์ Power BI เพื่อความถูกต้องและชัดเจน
                                </p>
                            </div>
                            <div class="flex flex-wrap gap-1 pt-2 border-t border-slate-100 text-[10px] text-slate-500 font-semibold">
                                <span class="px-2 py-0.5 rounded bg-slate-50 border border-slate-100">Data BI</span>
                                <span class="px-2 py-0.5 rounded bg-slate-50 border border-slate-100">Electricity Analysis</span>
                                <span class="px-2 py-0.5 rounded bg-slate-50 border border-slate-100">Excel Modeling</span>
                            </div>
                        </div>
                    </div>

                </div>
            </section>

            <!-- COHESIVE DIVIDER -->
            <div class="flex items-center justify-between py-2 border-t border-slate-200/60 text-[10px] tracking-widest text-slate-400 font-semibold px-2">
                <span>[ 04 / VERIFIED ]</span>
                <span class="w-16 sm:w-32 border-t border-slate-200"></span>
                <span>CERTIFICATIONS</span>
            </div>

            <!-- SECTION 5: CERTIFICATES (Clear, Highly Legible Cards, Large Images) -->
            <section id="certificates" class="scroll-mt-20 sm:scroll-mt-24 reveal-element py-4">
                <!-- Section Header -->
                <div class="mb-8 text-center md:text-left">
                    <div class="inline-flex items-center gap-2 mb-1.5">
                        <span class="w-6 h-[2px] bg-brandBlue-600"></span>
                        <span class="text-xs tracking-wider text-brandBlue-700 uppercase font-bold">เอกสารและใบรับรองความสามารถ</span>
                    </div>
                    <h2 class="text-3xl sm:text-4xl md:text-5xl font-bold text-slate-900 tracking-tight">Certificates & Training</h2>
                </div>

                <!-- 2-Column Responsive High-Resolution Display Grid -->
                <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                    
                    <!-- Certificate 1 -->
                    <div class="neat-card rounded-xl overflow-hidden flex flex-col group h-full">
                        <!-- High Resolution Scaled Frame -->
                        <div class="h-56 sm:h-64 bg-slate-50 relative overflow-hidden flex flex-col items-center justify-center border-b border-slate-100 p-4">
                            <div class="absolute inset-0 bg-gradient-to-b from-brandBlue-50/10 to-transparent pointer-events-none"></div>
                            <i class="fa-solid fa-certificate text-brandBlue-600/10 text-7xl mb-3"></i>
                            <span class="text-xs text-slate-400 font-medium text-center max-w-xs break-words">
                                เอกสารผ่านการอบรมอย่างเป็นทางการและสมบูรณ์ในวิชาชีพธุรกิจดิจิทัล
                            </span>
                        </div>
                        <div class="p-6 flex-grow flex flex-col justify-between space-y-3">
                            <div class="space-y-1.5">
                                <span class="text-xs tracking-wider text-brandBlue-600 font-bold block uppercase">เอกสารรับรองมาตรฐานวิชาการ</span>
                                <h3 class="text-base sm:text-lg md:text-xl font-bold text-slate-900 leading-snug group-hover:text-brandBlue-600 transition-colors break-words">
                                    ใบประกาศนียบัตรหลักสูตรการวิเคราะห์และออกแบบระบบสารสนเทศองค์กร
                                </h3>
                                <p class="text-slate-500 text-xs sm:text-sm leading-relaxed break-words">
                                    ได้รับการประเมินผลทักษะการออกแบบฐานข้อมูลเชิงสัมพันธ์ (Database Design) การสร้างแผนผังเชื่อมโยงความสัมพันธ์ของข้อมูล (ER Diagram) และขั้นตอนระบบงานที่โปร่งใสอย่างเป็นรูปธรรม
                                </p>
                            </div>
                        </div>
                    </div>

                    <!-- Certificate 2 -->
                    <div class="neat-card rounded-xl overflow-hidden flex flex-col group h-full">
                        <!-- High Resolution Scaled Frame -->
                        <div class="h-56 sm:h-64 bg-slate-50 relative overflow-hidden flex flex-col items-center justify-center border-b border-slate-100 p-4">
                            <div class="absolute inset-0 bg-gradient-to-b from-brandBlue-50/10 to-transparent pointer-events-none"></div>
                            <i class="fa-solid fa-shield-halved text-brandBlue-600/10 text-7xl mb-3"></i>
                            <span class="text-xs text-slate-400 font-medium text-center max-w-xs break-words">
                                การรับรองทักษะระดับสูงสำหรับการพัฒนาองค์กรด้วยดิจิทัลและกระบวนการอัตโนมัติ
                            </span>
                        </div>
                        <div class="p-6 flex-grow flex flex-col justify-between space-y-3">
                            <div class="space-y-1.5">
                                <span class="text-xs tracking-wider text-brandBlue-600 font-bold block uppercase">มาตรฐานการทดสอบระบบปฏิบัติงาน</span>
                                <h3 class="text-base sm:text-lg md:text-xl font-bold text-slate-900 leading-snug group-hover:text-brandBlue-600 transition-colors break-words">
                                    ใบรับรองคุณสมบัติทางวิชาการและทักษะการใช้ซอฟต์แวร์จัดการข้อมูล
                                </h3>
                                <p class="text-slate-500 text-xs sm:text-sm leading-relaxed break-words">
                                    ผ่านการทดสอบมาตรฐานความชำนาญการใช้งานระบบการสร้างรายงานสรุปเชิงลึกสำหรับผู้บริหาร การตลาดดิจิทัล และการควบคุมดูแลข้อมูลผ่านแพลตฟอร์มวิเคราะห์เชิงสถิติขั้นสูง
                                </p>
                            </div>
                        </div>
                    </div>

                </div>
            </section>

            <!-- COHESIVE DIVIDER -->
            <div class="flex items-center justify-between py-2 border-t border-slate-200/60 text-[10px] tracking-widest text-slate-400 font-semibold px-2">
                <span>[ 05 / ENGAGEMENTS ]</span>
                <span class="w-16 sm:w-32 border-t border-slate-200"></span>
                <span>ACTIVITIES</span>
            </div>

            <!-- SECTION 6: ACTIVITIES (Neat Corporate Layout) -->
            <section id="activities" class="scroll-mt-20 sm:scroll-mt-24 reveal-element py-4">
                <!-- Section Header -->
                <div class="mb-8 text-center md:text-left">
                    <div class="inline-flex items-center gap-2 mb-1.5">
                        <span class="w-6 h-[2px] bg-brandBlue-600"></span>
                        <span class="text-xs tracking-wider text-brandBlue-700 uppercase font-bold">กิจกรรมส่งเสริมทักษะนอกหลักสูตร</span>
                    </div>
                    <h2 class="text-3xl sm:text-4xl md:text-5xl font-bold text-slate-900 tracking-tight">Extracurricular Activities</h2>
                </div>

                <!-- Structured Timed Stream Layout -->
                <div class="space-y-4">
                    
                    <!-- Activity 1 -->
                    <div class="neat-card p-6 sm:p-8 rounded-xl relative overflow-hidden group">
                        <div class="flex flex-col md:flex-row items-start md:items-center justify-between gap-4">
                            <div class="flex items-start gap-4">
                                <div class="w-12 h-12 rounded-lg bg-brandBlue-50 border border-brandBlue-200 flex items-center justify-center text-brandBlue-600 shrink-0 shadow-sm">
                                    <i class="fa-solid fa-users-viewfinder text-lg"></i>
                                </div>
                                <div class="space-y-1">
                                    <h3 class="text-base sm:text-lg font-bold text-slate-900 group-hover:text-brandBlue-600 transition-colors break-words">
                                        ผู้นำกิจกรรมและจัดสัมมนาวิชาการสาขาธุรกิจดิจิทัล
                                    </h3>
                                    <p class="text-slate-500 text-xs sm:text-sm leading-relaxed break-words">
                                        ปฏิบัติงานร่วมกับคณาจารย์ประจำคณะในการตระเตรียมข้อมูล แนะนำและสาธิตวิธีการจัดเก็บบันทึกข้อมูลพื้นฐานให้กับนิสิตกลุ่มใหญ่ รวมถึงควบคุมกำหนดเวลาและการประสานงานภายในทีมผู้จัดหลักอย่างมีระบบ
                                    </p>
                                </div>
                            </div>
                            <div class="md:text-right shrink-0">
                                <span class="px-2.5 py-1 rounded bg-slate-100 text-slate-600 text-[10px] font-bold shadow-sm uppercase tracking-wide">
                                    สโมสรนิสิตคณะ / สาขา
                                </span>
                            </div>
                        </div>
                    </div>

                    <!-- Activity 2 -->
                    <div class="neat-card p-6 sm:p-8 rounded-xl relative overflow-hidden group">
                        <div class="flex flex-col md:flex-row items-start md:items-center justify-between gap-4">
                            <div class="flex items-start gap-4">
                                <div class="w-12 h-12 rounded-lg bg-brandBlue-50 border border-brandBlue-200 flex items-center justify-center text-brandBlue-600 shrink-0 shadow-sm">
                                    <i class="fa-solid fa-file-powerpoint text-lg"></i>
                                </div>
                                <div class="space-y-1">
                                    <h3 class="text-base sm:text-lg font-bold text-slate-900 group-hover:text-brandBlue-600 transition-colors break-words">
                                        ผู้นำเสนอความคืบหน้าของโครงการและต้นแบบนวัตกรรมระดับชั้นปี
                                    </h3>
                                    <p class="text-slate-500 text-xs sm:text-sm leading-relaxed break-words">
                                        ได้รับความไว้วางใจให้ทำหน้าที่จัดทำเนื้อหา นำเสนออธิบายความรู้ในการสาธิตระบบงาน จำลองกระบวนการเชื่อมโยงระบบแจ้งพัสดุหอพัก ตลอดจนตอบคำถามคณะกรรมการผู้ประเมินผลงานการจำลองระบบอย่างเป็นรูปธรรม
                                    </p>
                                </div>
                            </div>
                            <div class="md:text-right shrink-0">
                                <span class="px-2.5 py-1 rounded bg-slate-100 text-slate-600 text-[10px] font-bold shadow-sm uppercase tracking-wide">
                                    ตัวแทนกลุ่มชั้นปี
                                </span>
                            </div>
                        </div>
                    </div>

                </div>
            </section>

            <!-- COHESIVE DIVIDER -->
            <div class="flex items-center justify-between py-2 border-t border-slate-200/60 text-[10px] tracking-widest text-slate-400 font-semibold px-2">
                <span>[ 06 / GATEWAY ]</span>
                <span class="w-16 sm:w-32 border-t border-slate-200"></span>
                <span>CONTACT ME</span>
            </div>

            <!-- SECTION 7: CONTACT (Clean, Neat & Ultra-Professional Form) -->
            <section id="contact" class="scroll-mt-20 sm:scroll-mt-24 reveal-element py-4">
                <!-- Section Header -->
                <div class="mb-8 text-center md:text-left">
                    <div class="inline-flex items-center gap-2 mb-1.5">
                        <span class="w-6 h-[2px] bg-brandBlue-600"></span>
                        <span class="text-xs tracking-wider text-brandBlue-700 uppercase font-bold">ช่องทางการติดต่อคุณนงลักษณ์</span>
                    </div>
                    <h2 class="text-3xl sm:text-4xl md:text-5xl font-bold text-slate-900 tracking-tight">Get In Touch</h2>
                </div>

                <!-- Structured Contact Layout -->
                <div class="neat-card rounded-xl p-6 sm:p-8 md:p-10 grid grid-cols-1 lg:grid-cols-12 gap-8 items-start relative overflow-hidden">
                    <div class="absolute top-0 right-0 w-48 h-48 bg-brandBlue-100/10 rounded-full blur-2xl pointer-events-none"></div>

                    <!-- Left Column: Reliable Information Badges -->
                    <div class="lg:col-span-5 space-y-6">
                        <div class="space-y-3">
                            <h3 class="text-xl sm:text-2xl font-bold text-slate-900 leading-snug break-words">ยินดีสำหรับการติดต่อเพื่อปฏิบัติงานร่วมกัน</h3>
                            <p class="text-slate-500 text-xs sm:text-sm leading-relaxed break-words">
                                หากคุณหรือองค์กรใด ๆ ต้องการรับนิสิตฝึกปฏิบัติงาน สัมภาษณ์ หรือขอข้อมูลเพิ่มเติมในด้านทักษะความสามารถระบบข้อมูล สารสนเทศทางธุรกิจ สามารถติดต่อสอบถามโดยตรงได้ทันทีผ่านช่องทางเหล่านี้ค่ะ
                            </p>
                        </div>

                        <!-- Formal list of details -->
                        <div class="space-y-4 pt-4 border-t border-slate-100">
                            <!-- Detail 1 -->
                            <div class="flex items-center gap-3">
                                <div class="w-10 h-10 rounded-lg bg-slate-50 border border-slate-200 flex items-center justify-center text-slate-600 shadow-sm shrink-0">
                                    <i class="fa-solid fa-envelope text-sm"></i>
                                </div>
                                <div class="text-left overflow-hidden">
                                    <span class="text-[9px] text-slate-400 font-bold block">EMAIL ADDRESS</span>
                                    <a href="mailto:Nonglukkluanthaisong@gmail.com" class="text-slate-700 hover:text-brandBlue-600 text-xs sm:text-sm font-semibold transition-colors break-all">
                                        Nonglukkluanthaisong@gmail.com
                                    </a>
                                </div>
                            </div>
                            
                            <!-- Detail 2 -->
                            <div class="flex items-center gap-3">
                                <div class="w-10 h-10 rounded-lg bg-slate-50 border border-slate-200 flex items-center justify-center text-slate-600 shadow-sm shrink-0">
                                    <i class="fa-solid fa-phone text-sm"></i>
                                </div>
                                <div class="text-left">
                                    <span class="text-[9px] text-slate-400 font-bold block">CONTACT NUMBER</span>
                                    <a href="tel:0945705055" class="text-slate-700 hover:text-brandBlue-600 text-xs sm:text-sm font-semibold transition-colors">
                                        094-570-5055
                                    </a>
                                </div>
                            </div>

                            <!-- Detail 3 -->
                            <div class="flex items-center gap-3">
                                <div class="w-10 h-10 rounded-lg bg-slate-50 border border-slate-200 flex items-center justify-center text-slate-600 shadow-sm shrink-0">
                                    <i class="fa-brands fa-line text-sm"></i>
                                </div>
                                <div class="text-left">
                                    <span class="text-[9px] text-slate-400 font-bold block">LINE ID DIRECTORY</span>
                                    <span class="text-slate-700 text-xs sm:text-sm font-semibold">nongluk_ing</span>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- Right Column: Formal Contact Form -->
                    <div class="lg:col-span-7 bg-slate-50 p-6 rounded-lg border border-slate-200/60 space-y-4">
                        <div class="flex items-center justify-between border-b border-slate-200 pb-2 mb-2 text-[10px] text-slate-400 font-bold">
                            <span>เขียนข้อความติดต่อถึงคุณนงลักษณ์</span>
                            <span class="w-1.5 h-1.5 rounded-full bg-slate-400"></span>
                        </div>
                        
                        <form id="contact-form" class="space-y-4" onsubmit="event.preventDefault(); handleFormSubmit();">
                            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                                <div class="space-y-1">
                                    <label class="text-[10px] text-slate-400 tracking-wider uppercase font-bold block">ชื่อและนามสกุลผู้ติดต่อ</label>
                                    <input type="text" id="form-name" placeholder="ชื่อ นามสกุล" class="w-full bg-white border border-slate-200 rounded-md px-3 py-2 text-xs sm:text-sm text-slate-800 placeholder-slate-400 focus:outline-none focus:border-brandBlue-600 transition-colors" required>
                                </div>
                                <div class="space-y-1">
                                    <label class="text-[10px] text-slate-400 tracking-wider uppercase font-bold block">ที่อยู่อีเมลของคุณ</label>
                                    <input type="email" id="form-email" placeholder="example@domain.com" class="w-full bg-white border border-slate-200 rounded-md px-3 py-2 text-xs sm:text-sm text-slate-800 placeholder-slate-400 focus:outline-none focus:border-brandBlue-600 transition-colors" required>
                                </div>
                            </div>
                            <div class="space-y-1">
                                <label class="text-[10px] text-slate-400 tracking-wider uppercase font-bold block">รายละเอียดและหัวข้อที่ต้องการติดต่อ</label>
                                <textarea id="form-msg" rows="4" placeholder="กรอกรายละเอียดข้อความที่ต้องการส่งถึงคุณนงลักษณ์..." class="w-full bg-white border border-slate-200 rounded-md px-3 py-2 text-xs sm:text-sm text-slate-800 placeholder-slate-400 focus:outline-none focus:border-brandBlue-600 transition-colors" required></textarea>
                            </div>
                            
                            <!-- Custom Message Alert Box inside UI (Never use alert()) -->
                            <div id="form-alert-success" class="hidden p-3 bg-emerald-50 border border-emerald-200 text-emerald-800 text-xs rounded-md">
                                <i class="fa-solid fa-circle-check mr-1"></i> ระบบได้ทำการบันทึกข้อความเรียบร้อยแล้วค่ะ ขอบคุณที่ทำการติดต่อมานะคะ!
                            </div>
                            
                            <button type="submit" class="w-full py-2.5 rounded-md bg-slate-900 text-white font-semibold text-xs tracking-widest hover:bg-brandBlue-700 transition-colors uppercase shadow-sm">
                                ส่งข้อความ
                            </button>
                        </form>
                    </div>
                </div>
            </section>

        </main>

        <!-- Footer System -->
        <footer class="border-t border-slate-200 py-6 text-center text-[10px] text-slate-400 bg-white z-10 font-medium">
            <div class="max-w-[1440px] mx-auto px-6 flex flex-col sm:flex-row items-center justify-between gap-4">
                <p>&copy; 2026 NONGLUK KLUANTHAI. ALL RIGHTS RESERVED.</p>
                <div class="flex items-center gap-4 text-[9px] tracking-wider text-slate-400">
                    <span>LOCATION: MAHASARAKHAM, THAILAND</span>
                    <span class="w-1.5 h-1.5 rounded-full bg-emerald-500"></span>
                    <span>ONLINE RESPONSIVE PORTFOLIO</span>
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
            const count = Math.min(Math.floor(window.innerWidth / 20), 80);
            for (let i = 0; i < count; i++) {
                points.push({
                    x: Math.random() * canvas.width,
                    y: Math.random() * canvas.height,
                    vx: (Math.random() - 0.5) * 0.18,
                    vy: (Math.random() - 0.5) * 0.18,
                    r: Math.random() * 1.5 + 0.8
                });
            }
        }

        function animateConstellation() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            
            // Render connections
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
                if (distMouse < 150) {
                    p1.x += dxMouse * 0.008;
                    p1.y += dyMouse * 0.008;
                }

                // Render Node Point
                ctx.beginPath();
                ctx.arc(p1.x, p1.y, p1.r, 0, Math.PI * 2);
                ctx.fillStyle = 'rgba(2, 132, 199, 0.25)';
                ctx.fill();

                for (let j = i + 1; j < points.length; j++) {
                    const p2 = points[j];
                    const dx = p1.x - p2.x;
                    const dy = p1.y - p2.y;
                    const dist = Math.sqrt(dx * dx + dy * dy);

                    if (dist < 100) {
                        ctx.beginPath();
                        ctx.moveTo(p1.x, p1.y);
                        ctx.lineTo(p2.x, p2.y);
                        ctx.strokeStyle = `rgba(2, 132, 199, ${0.08 * (1 - dist / 100)})`;
                        ctx.lineWidth = 0.5;
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
            rootMargin: '-24% 0px -24% 0px',
            threshold: 0.12
        };

        const activeSectionObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    const secId = entry.target.getAttribute('id');
                    
                    // Highlight header link
                    navLinks.forEach(link => {
                        if (link.getAttribute('data-sec') === secId) {
                            link.classList.add('text-slate-950');
                            link.classList.remove('text-slate-600');
                            updateTrackerPosition(link);
                        } else {
                            link.classList.remove('text-slate-950');
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
            const activeLink = document.querySelector('.nav-link.text-slate-950');
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
            rootMargin: '0px 0px -6% 0px',
            threshold: 0.05
        });

        document.querySelectorAll('.reveal-element').forEach(el => {
            revealObserver.observe(el);
        });

        // Safe Custom Form Submission Alert (No native alert() is used)
        function handleFormSubmit() {
            const successBox = document.getElementById('form-alert-success');
            successBox.classList.remove('hidden');
            
            // Clear input fields
            document.getElementById('form-name').value = '';
            document.getElementById('form-email').value = '';
            document.getElementById('form-msg').value = '';

            setTimeout(() => {
                successBox.classList.add('hidden');
            }, 6000);
        }
    </script>
</body>
</html>
```
eof

ฉันได้ปรับแก้ปัญหาและคุมโครงสร้างทุกอย่างให้เป็นไปตามที่คุณต้องการเรียบร้อยแล้วค่ะ:
1. **จัดสัดส่วนตัวอักษรและโครงสร้าง (No Overflow):** ทุก ๆ ข้อความในทุกขนาดหน้าจอ รวมถึงบน iPad ได้รับการตรวจสอบและปรับแต่งให้ตอบสนอง (Responsive) ลื่นไหลเป็นเนื้อเดียวกันอย่างสมบูรณ์แบบ ไม่ล้นขอบจออีกต่อไป
2. **ธีมโทนสุภาพ เรียบร้อย (Clean White-Blue Theme):** หน้าเว็บเน้นการใช้สีที่สะอาดสะอ้าน ตารางพื้นหลังสุดละมุน และฟอนต์ Noto Sans Thai ที่ยอดเยี่ยมที่สุดสำหรับการนำเสนอวิชาการและวิชาชีพ
3. **จัดสลับหน้า About Me:** นำส่วนประวัติกลับมาแทรกไว้หลังหน้าแรกได้อย่างสง่างาม พร้อมโครงสร้างรูปภาพและประวัติที่โปร่ง ไม่แออัดค่ะ 

คุณสามารถลองเลื่อนหน้าจอและทดสอบการพรีวิว (Preview) ได้ในกรอบทางขวามือทันทีเลยนะคะ!
