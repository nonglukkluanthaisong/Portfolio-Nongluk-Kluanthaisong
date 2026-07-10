<!DOCTYPE html>
<html lang="th" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nongluk Kluanthaisong | Personal Portfolio</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        brandBlue: {
                            50: '#f0f7ff',
                            100: '#e0effe',
                            200: '#bae0fd',
                            500: '#3b82f6',
                            600: '#2563eb',
                            700: '#1d4ed8',
                            800: '#1e40af',
                            900: '#1e3a8a',
                            950: '#0f172a',
                        },
                        slateBg: '#f8fafc',
                    }
                }
            }
        }
    </script>
    <!-- Google Fonts: Inter, Noto Sans Thai, Playfair Display, Montserrat for diverse and highly appropriate premium typography -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&family=Noto+Sans+Thai:wght@300;400;500;600;700;800&family=Playfair+Display:ital,wght@0,600;0,800;1,400&family=Montserrat:wght@700;800;900&display=swap" rel="stylesheet">
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        body {
            font-family: 'Noto Sans Thai', 'Inter', sans-serif;
            background-color: #f8fafc;
            color: #0f172a;
        }

        /* Set elegant Serif styles for premium editorial accents */
        .serif-title {
            font-family: 'Playfair Display', serif;
        }

        .sans-tech {
            font-family: 'Montserrat', 'Inter', sans-serif;
        }

        /* Smooth Reveal Animations on Scroll */
        .reveal-element {
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.8s cubic-bezier(0.16, 1, 0.3, 1), transform 0.8s cubic-bezier(0.16, 1, 0.3, 1);
            will-change: transform, opacity;
        }

        .reveal-element.active {
            opacity: 1;
            transform: translateY(0);
        }

        .reveal-left {
            opacity: 0;
            transform: translateX(-30px);
            transition: opacity 0.8s cubic-bezier(0.16, 1, 0.3, 1), transform 0.8s cubic-bezier(0.16, 1, 0.3, 1);
        }

        .reveal-left.active {
            opacity: 1;
            transform: translateX(0);
        }

        .reveal-right {
            opacity: 0;
            transform: translateX(30px);
            transition: opacity 0.8s cubic-bezier(0.16, 1, 0.3, 1), transform 0.8s cubic-bezier(0.16, 1, 0.3, 1);
        }

        .reveal-right.active {
            opacity: 1;
            transform: translateX(0);
        }

        /* Scroll Progress Bar */
        #scroll-progress {
            position: fixed;
            top: 0;
            left: 0;
            height: 3px;
            background: linear-gradient(to right, #2563eb, #3b82f6, #06b6d4);
            z-index: 100;
            width: 0%;
            transition: width 0.1s ease-out;
        }

        /* Glassmorphism Styles */
        .glass-nav {
            background: rgba(255, 255, 255, 0.85);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border-bottom: 1px solid rgba(37, 99, 235, 0.05);
            transition: transform 0.4s cubic-bezier(0.16, 1, 0.3, 1);
        }

        .glass-card {
            background: rgba(255, 255, 255, 0.7);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border: 1px solid rgba(37, 99, 235, 0.06);
            box-shadow: 0 10px 30px -10px rgba(37, 99, 235, 0.03);
            transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1);
        }

        /* Professional Global Hover Effects for Cards on All Pages */
        .glass-card:hover {
            border-color: rgba(37, 99, 235, 0.25);
            box-shadow: 0 20px 40px -15px rgba(37, 99, 235, 0.12), 0 0 20px 0 rgba(37, 99, 235, 0.05);
            transform: translateY(-6px) scale(1.015);
        }

        /* Interactive Image zoom within cards */
        .glass-card:hover img {
            transform: scale(1.06);
            filter: brightness(1.03);
        }

        /* Soft Glow Background Blobs */
        .ambient-glow {
            position: absolute;
            border-radius: 50%;
            filter: blur(120px);
            z-index: 0;
            pointer-events: none;
            opacity: 0.2;
            animation: floatSlowly 10s infinite alternate ease-in-out;
        }

        @keyframes floatSlowly {
            0% { transform: translate(0, 0) scale(1); }
            100% { transform: translate(20px, -20px) scale(1.05); }
        }

        /* Custom Interactive Badge Hover */
        .hover-badge {
            transition: all 0.3s cubic-bezier(0.16, 1, 0.3, 1);
        }
        .hover-badge:hover {
            background-color: #2563eb !important;
            color: #ffffff !important;
            transform: translateY(-3px) scale(1.05);
            box-shadow: 0 8px 16px -4px rgba(37, 99, 235, 0.3);
        }

        /* Scrollbar adjustment */
        ::-webkit-scrollbar {
            width: 6px;
        }
        ::-webkit-scrollbar-track {
            background: #f1f5f9;
        }
        ::-webkit-scrollbar-thumb {
            background: #cbd5e1;
            border-radius: 3px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #2563eb;
        }

        /* Hide elements when printing */
        @media print {
            body * {
                visibility: hidden;
            }
            #cv-modal-content, #cv-modal-content * {
                visibility: visible;
            }
            #cv-modal-content {
                position: absolute;
                left: 0;
                top: 0;
                width: 100%;
                background: white !important;
                color: black !important;
            }
            .no-print {
                display: none !important;
            }
        }
    </style>
</head>
<body class="bg-slateBg text-slate-900 min-h-screen relative overflow-x-hidden selection:bg-brandBlue-100 selection:text-brandBlue-900">

    <!-- Scroll Progress Indicator -->
    <div id="scroll-progress" class="no-print"></div>

    <!-- Background Glow Elements -->
    <div class="ambient-glow w-[500px] h-[500px] bg-brandBlue-100 top-[-100px] left-[-100px]"></div>
    <div class="ambient-glow w-[600px] h-[600px] bg-blue-50 bottom-[10%] right-[-150px] animation-delay-2000"></div>

    <!-- Header Navigation with Interactive Underline indicator -->
    <header id="main-header" class="fixed top-0 left-0 w-full z-50 glass-nav no-print">
        <div class="max-w-[1440px] mx-auto px-6 h-20 flex items-center justify-between">
            <a href="#home" class="flex items-center space-x-3 group">
                <div class="w-10 h-10 rounded-xl bg-gradient-to-tr from-brandBlue-600 to-brandBlue-500 flex items-center justify-center font-bold text-white text-xl shadow-md shadow-brandBlue-500/10 group-hover:scale-105 transition-transform">
                    NK
                </div>
                <span class="text-sm font-bold tracking-wider text-brandBlue-950 group-hover:text-brandBlue-600 transition-colors sans-tech">NONGLUK K.</span>
            </a>

            <!-- Mobile Menu Toggle Button -->
            <button onclick="toggleMobileMenu()" class="md:hidden text-slate-600 focus:outline-none" aria-label="Toggle Menu">
                <i class="fa-solid fa-bars text-2xl"></i>
            </button>

            <!-- Navigation Links with Underlines (Clean, No Pill) -->
            <nav class="hidden md:flex items-center space-x-2 text-sm font-semibold">
                <a href="#home" class="nav-link text-slate-600 hover:text-brandBlue-600 px-4 py-3 border-b-2 border-transparent transition-all duration-300">Home</a>
                <a href="#education" class="nav-link text-slate-600 hover:text-brandBlue-600 px-4 py-3 border-b-2 border-transparent transition-all duration-300">Education</a>
                <a href="#projects" class="nav-link text-slate-600 hover:text-brandBlue-600 px-4 py-3 border-b-2 border-transparent transition-all duration-300">Projects</a>
                <a href="#experience" class="nav-link text-slate-600 hover:text-brandBlue-600 px-4 py-3 border-b-2 border-transparent transition-all duration-300">Certificates</a>
                <a href="#activities" class="nav-link text-slate-600 hover:text-brandBlue-600 px-4 py-3 border-b-2 border-transparent transition-all duration-300">Activities</a>
                <a href="#contact" class="px-5 py-2.5 rounded-xl bg-brandBlue-600 text-white hover:bg-brandBlue-700 hover:scale-105 active:scale-95 transition-all font-bold shadow-sm ml-4">Contact</a>
            </nav>
        </div>

        <!-- Mobile Menu Dropdown -->
        <div id="mobile-menu" class="hidden md:hidden px-6 pb-6 bg-white/95 border-b border-slate-100 flex flex-col space-y-4">
            <a href="#home" onclick="toggleMobileMenu()" class="text-slate-600 hover:text-brandBlue-600 py-2 block font-medium">Home</a>
            <a href="#education" onclick="toggleMobileMenu()" class="text-slate-600 hover:text-brandBlue-600 py-2 block font-medium">Education</a>
            <a href="#projects" onclick="toggleMobileMenu()" class="text-slate-600 hover:text-brandBlue-600 py-2 block font-medium">Projects</a>
            <a href="#experience" onclick="toggleMobileMenu()" class="text-slate-600 hover:text-brandBlue-600 py-2 block font-medium">Certificates</a>
            <a href="#activities" onclick="toggleMobileMenu()" class="text-slate-600 hover:text-brandBlue-600 py-2 block font-medium">Activities</a>
            <a href="#contact" onclick="toggleMobileMenu()" class="block text-center py-2.5 rounded-xl bg-brandBlue-600 text-white font-bold">Contact</a>
        </div>
    </header>

    <!-- Main Wrapper with Wide-Screen Support -->
    <main class="relative z-10 max-w-[1440px] mx-auto px-6 pt-32 pb-24 space-y-32">

        <!-- Clean Text-Only Hero Section with Interactive Neural AI Canvas Background -->
        <section id="home" class="min-h-[85vh] flex flex-col justify-center items-center text-center py-16 relative overflow-hidden reveal-element">
            
            <!-- WebGL-style Interactive background -->
            <canvas id="neural-canvas" class="absolute inset-0 w-full h-full pointer-events-none opacity-40 z-0"></canvas>
            
            <div class="space-y-8 max-w-6xl mx-auto relative z-10 px-4">
                <!-- Status Tag with hover glow -->
                <div class="inline-flex items-center space-x-2 px-4 py-1.5 rounded-full bg-white border border-brandBlue-100 text-[10px] tracking-widest text-brandBlue-600 font-bold uppercase shadow-sm hover:shadow-md hover:border-brandBlue-300 transition-all cursor-default sans-tech">
                    <span class="w-2 h-2 rounded-full bg-green-500 inline-block animate-pulse"></span>
                    <span>สมัครฝึกงานช่วงเวลา: 1 ธ.ค. 2026 – 31 มี.ค. 2027</span>
                </div>

                <h2 class="text-xs font-bold tracking-[0.3em] text-brandBlue-600 uppercase block sans-tech">
                    Personal <span class="bg-brandBlue-50 px-2.5 py-0.5 rounded-md text-brandBlue-800">PORTFOLIO</span> 2026
                </h2>

                <h1 class="text-5xl sm:text-7xl md:text-8.5xl font-extrabold tracking-tight text-brandBlue-950 leading-[1.05] drop-shadow-sm select-none sans-tech">
                    CREATIVE TECHNOLOGIST <br class="hidden sm:inline">
                    <span class="bg-gradient-to-r from-brandBlue-600 via-brandBlue-700 to-cyan-600 bg-clip-text text-transparent hover:brightness-110 transition-all duration-300">
                        & AI INNOVATOR
                    </span>
                </h1>

                <p class="text-base sm:text-lg md:text-xl text-slate-500 max-w-2xl mx-auto font-light leading-relaxed">
                    ขับเคลื่อนโครงสร้างธุรกิจและการแพทย์ด้วยนวัตกรรมข้อมูล <strong class="text-slate-800 font-medium">AI & IoT</strong> ด้วยการคิดเชิงวิเคราะห์และการวางแผนกลยุทธ์ด้านเทคโนโลยีที่แม่นยำ
                </p>

                <!-- Clean Glass Action Buttons -->
                <div class="flex flex-col sm:flex-row items-center justify-center gap-4 pt-6 max-w-lg mx-auto">
                    <a href="#projects" class="w-full sm:w-auto px-8 py-4 rounded-xl bg-brandBlue-600 text-white font-semibold hover:bg-brandBlue-700 hover:scale-105 active:scale-95 transition-all text-center flex items-center justify-center space-x-2 text-sm shadow-md shadow-brandBlue-500/10">
                        <span>สำรวจผลงาน</span>
                        <i class="fa-solid fa-chevron-right text-xs"></i>
                    </a>
                    <button onclick="openCvModal()" class="w-full sm:w-auto px-8 py-4 rounded-xl bg-white border border-slate-200 text-slate-700 font-medium hover:bg-slate-50 hover:scale-105 active:scale-95 transition-all flex items-center justify-center space-x-2 text-sm shadow-sm">
                        <i class="fa-regular fa-file-pdf text-brandBlue-600"></i>
                        <span>ดาวน์โหลดไฟล์ CV / สั่งพิมพ์</span>
                    </button>
                </div>
            </div>

            <!-- Gentle bottom scroll hint -->
            <div class="absolute bottom-4 left-1/2 transform -translate-x-1/2 flex flex-col items-center space-y-1 opacity-50">
                <span class="text-[9px] uppercase tracking-widest text-slate-400 font-bold sans-tech">เลื่อนลงเพื่อดูเนื้อหา</span>
                <div class="w-1.5 h-4 rounded-full bg-brandBlue-600 animate-bounce"></div>
            </div>
        </section>

        <!-- Education Section: Newly Inserted Page between About & Projects -->
        <section id="education" class="scroll-mt-24 reveal-element">
            <div class="text-center max-w-3xl mx-auto mb-16">
                <div class="text-xs font-bold text-brandBlue-600 tracking-widest uppercase mb-3 sans-tech">ประวัติการศึกษา</div>
                <h2 class="text-4xl sm:text-5xl md:text-6xl font-extrabold text-brandBlue-950 tracking-tight serif-title">การศึกษาเชิงลึก (Education)</h2>
                <p class="text-slate-400 mt-3 text-xs tracking-wider">เส้นทางสถาบันมาตรฐานการเรียนรู้และการพัฒนาทักษะวิชาชีพ</p>
            </div>

            <div class="glass-card rounded-3xl p-8 md:p-12 relative overflow-hidden">
                <div class="absolute inset-0 bg-gradient-to-tr from-brandBlue-50/20 to-transparent pointer-events-none"></div>
                <div class="grid grid-cols-1 lg:grid-cols-12 gap-10 items-center">
                    
                    <!-- Left stats column -->
                    <div class="lg:col-span-4 space-y-6">
                        <div class="p-6 bg-slate-50/50 rounded-2xl border border-slate-100">
                            <span class="text-xs font-bold text-slate-400 uppercase tracking-widest block sans-tech">Academic Standing</span>
                            <span class="text-5xl sm:text-6xl font-black text-brandBlue-600 block mt-2 sans-tech">3.68</span>
                            <span class="text-xs text-slate-500 font-medium block mt-1">คะแนนเกรดเฉลี่ยสะสมปัจจุบัน (GPAX)</span>
                        </div>
                        <div class="p-6 bg-slate-50/50 rounded-2xl border border-slate-100">
                            <span class="text-xs font-bold text-slate-400 uppercase tracking-widest block sans-tech">Timeline Progress</span>
                            <span class="text-lg font-bold text-slate-800 block mt-2">นิสิตระดับปริญญาตรีปีที่ 4</span>
                            <span class="text-xs text-slate-500 block mt-0.5">คาดว่าจะสำเร็จการศึกษา: พฤษภาคม 2570</span>
                        </div>
                    </div>

                    <!-- Right detailed timeline -->
                    <div class="lg:col-span-8 space-y-8">
                        <div class="relative pl-8 border-l-2 border-brandBlue-100">
                            <!-- Bullet -->
                            <div class="absolute -left-[9px] top-1.5 w-4 h-4 rounded-full bg-brandBlue-600 border-4 border-white shadow-sm"></div>
                            
                            <span class="text-xs font-bold text-brandBlue-600 tracking-wider uppercase block sans-tech">Bachelor of Business Administration (B.B.A.)</span>
                            <h3 class="text-xl sm:text-2xl font-bold text-brandBlue-950 mt-1">สาขาธุรกิจดิจิทัลและระบบสารสนเทศ (บธ.บ.)</h3>
                            <p class="text-slate-500 text-sm mt-1">คณะการบัญชีและการจัดการ (Mahasarakham Business School)</p>
                            <p class="text-slate-600 text-sm mt-3 leading-relaxed">
                                หลักสูตรมุ่งเน้นการพัฒนาระบบไอทีเพื่อตอบโจทย์องค์กร การวิเคราะห์คลังข้อมูลขนาดใหญ่ (Data Analytics) การวิเคราะห์กระบวนการทางธุรกิจ ตลอดจนการประยุกต์ใช้เทคโนโลยีดิจิทัลสมัยใหม่เพื่อส่งมอบความคุ้มค่าและขยายสัดส่วนความคล่องตัวขององค์กร
                            </p>
                        </div>
                        
                        <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 pt-6 border-t border-slate-100">
                            <div>
                                <h4 class="text-xs font-bold text-slate-400 uppercase tracking-widest mb-2 sans-tech">Relevant Coursework</h4>
                                <ul class="text-xs text-slate-600 space-y-1.5 list-disc pl-4">
                                    <li>การวิเคราะห์ข้อมูลทางธุรกิจ</li>
                                    <li>การวิเคราะห์และออกแบบระบบงาน</li>
                                    <li>เทคโนโลยีสารสนเทศเพื่อการขับเคลื่อนองค์กร</li>
                                    <li>โครงข่ายอินเทอร์เน็ตของสรรพสิ่ง (IoT)</li>
                                </ul>
                            </div>
                            <div>
                                <h4 class="text-xs font-bold text-slate-400 uppercase tracking-widest mb-2 sans-tech">Key Academic Projects</h4>
                                <ul class="text-xs text-slate-600 space-y-1.5 list-disc pl-4">
                                    <li>พยากรณ์ไฟฟ้าในประเทศไทยด้วย ML</li>
                                    <li>ปรับปรุงโครงสร้าง UX/UI แอป TrueID</li>
                                    <li>แอปพลิเคชันทางการแพทย์ PIC2PACS</li>
                                </ul>
                            </div>
                        </div>
                    </div>

                </div>
            </div>
        </section>

        <!-- Projects Section: Uniform Symmetrical Grid Layout -->
        <section id="projects" class="scroll-mt-24 reveal-element">
            <div class="text-center max-w-3xl mx-auto mb-16">
                <div class="text-xs font-bold text-brandBlue-600 tracking-widest uppercase mb-2 sans-tech">ผลงานที่เคยมีส่วนร่วม</div>
                <h2 class="text-4xl sm:text-5xl md:text-6xl font-extrabold text-brandBlue-950 serif-title">โครงการและกรณีศึกษา (Projects)</h2>
                <p class="text-slate-500 mt-2 text-sm">ผลงานบูรณาการร่วมกันและการจำลองแนวทางแก้ไขปัญหาจริงที่จัดสัดส่วนขนาดการ์ดเท่ากันอย่างมีวินัย</p>
            </div>

            <!-- Symmetrical Equal Grid for all screens with global interactive shadow triggers -->
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                
                <!-- Project 1: PIC2PACS -->
                <div class="glass-card rounded-2xl p-5 flex flex-col justify-between group cursor-pointer">
                    <div class="space-y-3">
                        <div class="w-full h-40 bg-slate-100 rounded-xl overflow-hidden border border-slate-200/40 relative">
                            <img src="https://placehold.co/400x300/3b82f6/ffffff?text=PIC2PACS+Mockup" alt="PIC2PACS" class="w-full h-full object-cover transition-transform duration-500">
                        </div>
                        <span class="inline-block px-2 py-0.5 rounded-full bg-brandBlue-50 text-brandBlue-700 text-xs font-semibold tracking-wider uppercase sans-tech">Medical Interface & UI</span>
                        <h3 class="text-base font-bold text-brandBlue-950 group-hover:text-brandBlue-600 transition-colors">ระบบแอปพลิเคชัน PIC2PACS</h3>
                        <p class="text-slate-500 text-sm font-light leading-relaxed">
                            โครงร่างแอปพลิเคชันทางการแพทย์สำหรับการบันทึกภาพถ่ายจากโทรศัพท์มือถือเข้าสู่ระบบสารสนเทศของโรงพยาบาล (PACS) เพื่อช่วยลดความผิดพลาดในการจัดการเคสผู้ป่วย
                        </p>
                    </div>
                    <div class="border-t border-slate-100 pt-3 mt-4 flex justify-between items-center text-xs">
                        <span class="text-slate-400">Figma Interactive Design</span>
                        <span class="text-brandBlue-600 font-semibold">นวัตกรรมการแพทย์</span>
                    </div>
                </div>

                <!-- Project 2: OonJai Box -->
                <div class="glass-card rounded-2xl p-5 flex flex-col justify-between group cursor-pointer">
                    <div class="space-y-3">
                        <div class="w-full h-40 bg-slate-100 rounded-xl overflow-hidden border border-slate-200/40 relative">
                            <img src="https://placehold.co/400x300/8b5cf6/ffffff?text=OonJai+Box+IoT" alt="OonJai Box" class="w-full h-full object-cover transition-transform duration-500">
                        </div>
                        <span class="inline-block px-2 py-0.5 rounded-full bg-purple-50 text-purple-700 text-xs font-semibold tracking-wider uppercase sans-tech">IoT Smart Device</span>
                        <h3 class="text-base font-bold text-brandBlue-950 group-hover:text-brandBlue-600 transition-colors">กล่องยาอุ่นใจ (OonJai Box)</h3>
                        <p class="text-slate-500 text-sm font-light leading-relaxed">
                            ระบบกล่องจ่ายยาอัจฉริยะสำหรับควบคุมสมาธิและการจัดระเบียบตัวช่วยเตือนการทานยาของผู้สูงอายุ ส่งสัญญาณเตือนความจำตรงไปยัง Line Notify ของครอบครัว
                        </p>
                    </div>
                    <div class="border-t border-slate-100 pt-3 mt-4 flex justify-between items-center text-xs">
                        <span class="text-slate-400">บอร์ด NodeMCU & WebSockets</span>
                        <span class="text-purple-600 font-semibold">ระบบสารสนเทศเพื่อชุมชน</span>
                    </div>
                </div>

                <!-- Project 3: Electricity Forecasting -->
                <div class="glass-card rounded-2xl p-5 flex flex-col justify-between group cursor-pointer">
                    <div class="space-y-3">
                        <div class="w-full h-40 bg-slate-100 rounded-xl overflow-hidden border border-slate-200/40 relative">
                            <img src="https://placehold.co/400x300/0ea5e9/ffffff?text=Electricity+Forecast" alt="Electricity Forecasting" class="w-full h-full object-cover transition-transform duration-500">
                        </div>
                        <span class="inline-block px-2 py-0.5 rounded-full bg-cyan-50 text-cyan-700 text-xs font-semibold tracking-wider uppercase sans-tech">Machine Learning</span>
                        <h3 class="text-base font-bold text-brandBlue-950 group-hover:text-brandBlue-600 transition-colors">พยากรณ์ปริมาณการใช้ไฟฟ้า</h3>
                        <p class="text-slate-500 text-sm font-light leading-relaxed">
                            โครงการวิเคราะห์สถิติคลังข้อมูลและการพยากรณ์ปริมาณความต้องการและอัตราการใช้พลังงานไฟฟ้าของประเทศไทย เพื่อนำมาจำแนกพฤติกรรมผ่านภาพรายงาน Dashboard
                        </p>
                    </div>
                    <div class="border-t border-slate-100 pt-3 mt-4 flex justify-between items-center text-xs">
                        <span class="text-slate-400">Python (Pandas), Power BI</span>
                        <span class="text-cyan-600 font-semibold">การวิเคราะห์ข้อมูลเชิงลึก</span>
                    </div>
                </div>

                <!-- Project 4: TrueID App Redesign -->
                <div class="glass-card rounded-2xl p-5 flex flex-col justify-between group cursor-pointer">
                    <div class="space-y-3">
                        <div class="w-full h-40 bg-slate-100 rounded-xl overflow-hidden border border-slate-200/40 relative">
                            <img src="https://placehold.co/400x300/6366f1/ffffff?text=TrueID+Redesign" alt="TrueID UI UX Redesign" class="w-full h-full object-cover transition-transform duration-500">
                        </div>
                        <span class="inline-block px-2 py-0.5 rounded-full bg-indigo-50 text-indigo-700 text-xs font-semibold tracking-wider uppercase sans-tech">User Research & UX/UI</span>
                        <h3 class="text-base font-bold text-brandBlue-950 group-hover:text-brandBlue-600 transition-colors">ปรับปรุงดีไซน์ TrueID App</h3>
                        <p class="text-slate-500 text-sm font-light leading-relaxed">
                            การวิจัยศึกษาปัญหาการปฏิสัมพันธ์ของผู้ใช้งานดั้งเดิม ค้นหาจุดบกพร่อง แล้วประยุกต์จัดระบบหน้าจอแสดงผลข้อมูลเพื่อผลลัพธ์การใช้งานที่ลื่นไหลยิ่งขึ้น
                        </p>
                    </div>
                    <div class="border-t border-slate-100 pt-3 mt-4 flex justify-between items-center text-xs">
                        <span class="text-slate-400">Figma Interactive Mockup</span>
                        <span class="text-indigo-600 font-semibold">การออกแบบโครงสร้าง</span>
                    </div>
                </div>

                <!-- Project 5: EcoLoop -->
                <div class="glass-card rounded-2xl p-5 flex flex-col justify-between group cursor-pointer">
                    <div class="space-y-3">
                        <div class="w-full h-40 bg-slate-100 rounded-xl overflow-hidden border border-slate-200/40 relative">
                            <img src="https://placehold.co/400x300/10b981/ffffff?text=EcoLoop+System" alt="EcoLoop" class="w-full h-full object-cover transition-transform duration-500">
                        </div>
                        <span class="inline-block px-2 py-0.5 rounded-full bg-emerald-50 text-emerald-700 text-xs font-semibold tracking-wider uppercase sans-tech">Sustainable Business Solution</span>
                        <h3 class="text-base font-bold text-brandBlue-950 group-hover:text-brandBlue-600 transition-colors">แพลตฟอร์ม EcoLoop</h3>
                        <p class="text-slate-500 text-sm font-light leading-relaxed">
                            ระบบข้อมูลห่วงโซ่อุปทานแบบหมุนเวียน เพื่อคำนวณปริมาณคาร์บอนฟุตพริ้นท์สะสมและจัดการกระบวนการคัดกรองขยะกลับคืนในภาคธุรกิจอย่างยั่งยืน
                        </p>
                    </div>
                    <div class="border-t border-slate-100 pt-3 mt-4 flex justify-between items-center text-xs">
                        <span class="text-slate-400">Power BI Dashboard</span>
                        <span class="text-emerald-600 font-semibold">เทคโนโลยีสีเขียว</span>
                    </div>
                </div>

                <!-- Project 6: AR Dinosaur Museum -->
                <div class="glass-card rounded-2xl p-5 flex flex-col justify-between group cursor-pointer">
                    <div class="space-y-3">
                        <div class="w-full h-40 bg-slate-100 rounded-xl overflow-hidden border border-slate-200/40 relative">
                            <img src="https://placehold.co/400x300/f43f5e/ffffff?text=AR+Museum+Project" alt="AR VR Interactive Museum" class="w-full h-full object-cover transition-transform duration-500">
                        </div>
                        <span class="inline-block px-2 py-0.5 rounded-full bg-rose-50 text-rose-700 text-xs font-semibold tracking-wider uppercase sans-tech">Interactive Multimedia</span>
                        <h3 class="text-base font-bold text-brandBlue-950 group-hover:text-brandBlue-600 transition-colors">สื่อการสอน AR พิพิธภัณฑ์</h3>
                        <p class="text-slate-500 text-sm font-light leading-relaxed">
                            งานวิชาการจัดทำแบบจำลองไดโนเสาร์สามมิติที่ผู้เข้าชมสามารถแสกนข้อมูลโต้ตอบ สังเกตลักษณะเชิงสัณฐานวิทยาได้อย่างมีส่วนร่วม
                        </p>
                    </div>
                    <div class="border-t border-slate-100 pt-3 mt-4 flex justify-between items-center text-xs">
                        <span class="text-slate-400">Unity Game Development</span>
                        <span class="text-rose-600 font-semibold">สื่อสร้างสรรค์</span>
                    </div>
                </div>

            </div>
        </section>

        <!-- Certifications & Training Section: High-Fidelity Responsive Grid with Large visible Previews -->
        <section id="experience" class="scroll-mt-24 reveal-element">
            <div class="text-center max-w-3xl mx-auto mb-16">
                <div class="text-xs font-bold text-brandBlue-600 tracking-widest uppercase mb-2 sans-tech">มาตรฐานทักษะความรู้</div>
                <h2 class="text-4xl sm:text-5xl md:text-6xl font-extrabold text-brandBlue-950 serif-title">ใบประกาศนียบัตรที่ได้รับ (Certificates)</h2>
                <p class="text-slate-500 mt-2 text-sm">ได้รับการยืนยันและรับรองอย่างเป็นทางการทางด้านเทคนิคและการประมวลผลระบบสากลพร้อมตัวอย่างฉบับเต็ม</p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 gap-8 lg:gap-12">
                
                <!-- Cert 1: MSU Exit Exam -->
                <div class="glass-card rounded-3xl p-6 sm:p-8 flex flex-col justify-between reveal-left group cursor-pointer relative overflow-hidden">
                    <div class="space-y-4">
                        <!-- Large Certificate Image Container -->
                        <div class="w-full h-56 sm:h-64 bg-slate-100 rounded-2xl overflow-hidden border border-slate-200/60 shadow-inner shrink-0 relative group-hover:border-brandBlue-500/30 transition-colors">
                            <img src="https://placehold.co/600x450/eff6ff/1e3a8a?text=MSU+English+Exit+Examination+(CEFR+B1)" alt="MSU Certificate Preview" class="w-full h-full object-cover transition-transform duration-700 ease-out">
                            <div class="absolute inset-0 bg-brandBlue-900/10 opacity-0 group-hover:opacity-100 transition-opacity flex items-center justify-center">
                                <span class="px-4 py-2 bg-white/90 text-brandBlue-900 rounded-full text-xs font-bold shadow-md"><i class="fa-solid fa-magnifying-glass-plus mr-1.5"></i>ดูภาพขนาดใหญ่</span>
                            </div>
                        </div>

                        <div class="space-y-2">
                            <div class="flex items-center space-x-2">
                                <div class="w-10 h-10 rounded-xl bg-brandBlue-50 flex items-center justify-center text-brandBlue-600 group-hover:scale-110 transition-transform shadow-sm">
                                    <i class="fa-solid fa-graduation-cap text-base"></i>
                                </div>
                                <span class="text-xs font-bold text-brandBlue-600 tracking-wider uppercase sans-tech">Language Proficiency</span>
                            </div>
                            <h3 class="text-lg sm:text-xl font-extrabold text-brandBlue-950 leading-snug group-hover:text-brandBlue-600 transition-colors">ผลการสอบภาษาอังกฤษเกณฑ์มาตรฐาน (CEFR B1)</h3>
                            <p class="text-slate-600 text-sm sm:text-base font-light leading-relaxed">
                                ผ่านระดับการทดสอบภาษาอังกฤษสำหรับนิสิตระดับปริญญาตรี MSU English Exit Examination ยืนยันสมรรถนะการสื่อสารและอ่านเขียนวิชาการในระดับมาตรฐาน B1
                            </p>
                        </div>
                    </div>
                    <div class="border-t border-slate-100 pt-4 mt-6 flex justify-between items-center text-xs text-slate-400 font-medium">
                        <span>มหาวิทยาลัยมหาสารคาม</span>
                        <span class="bg-slate-100/80 px-2.5 py-1 rounded text-slate-600 sans-tech">กุมภาพันธ์ 2026</span>
                    </div>
                </div>

                <!-- Cert 2: KUMOOC AI -->
                <div class="glass-card rounded-3xl p-6 sm:p-8 flex flex-col justify-between reveal-right group cursor-pointer relative overflow-hidden">
                    <div class="space-y-4">
                        <!-- Large Certificate Image Container -->
                        <div class="w-full h-56 sm:h-64 bg-slate-100 rounded-2xl overflow-hidden border border-slate-200/60 shadow-inner shrink-0 relative group-hover:border-cyan-500/30 transition-colors">
                            <img src="https://placehold.co/600x450/ecfeff/0891b2?text=KUMOOC+Generative+AI+%26+ChatGPT+for+Research" alt="KU Certificate Preview" class="w-full h-full object-cover transition-transform duration-700 ease-out">
                            <div class="absolute inset-0 bg-brandBlue-900/10 opacity-0 group-hover:opacity-100 transition-opacity flex items-center justify-center">
                                <span class="px-4 py-2 bg-white/90 text-brandBlue-900 rounded-full text-xs font-bold shadow-md"><i class="fa-solid fa-magnifying-glass-plus mr-1.5"></i>ดูภาพขนาดใหญ่</span>
                            </div>
                        </div>

                        <div class="space-y-2">
                            <div class="flex items-center space-x-2">
                                <div class="w-10 h-10 rounded-xl bg-cyan-50 flex items-center justify-center text-cyan-600 group-hover:scale-110 transition-transform shadow-sm">
                                    <i class="fa-solid fa-robot text-base"></i>
                                </div>
                                <span class="text-xs font-bold text-cyan-600 tracking-wider uppercase sans-tech">Artificial Intelligence</span>
                            </div>
                            <h3 class="text-lg sm:text-xl font-extrabold text-brandBlue-950 leading-snug group-hover:text-brandBlue-600 transition-colors">Generative AI สำหรับการศึกษาวิจัยและการจัดการข้อมูล</h3>
                            <p class="text-slate-600 text-sm sm:text-base font-light leading-relaxed">
                                ได้รับประกาศนียบัตรหลักสูตรการประยุกต์ใช้โมเดล Generative AI และเทคโนโลยี ChatGPT ในโครงงานวิจัยเพื่อการสรุปสถิติ คลีนข้อมูล และร่างสตอรี่บอร์ดโครงสร้าง
                            </p>
                        </div>
                    </div>
                    <div class="border-t border-slate-100 pt-4 mt-6 flex justify-between items-center text-xs text-slate-400 font-medium">
                        <span>Kasetsart University (KUMOOC)</span>
                        <span class="bg-slate-100/80 px-2.5 py-1 rounded text-slate-600 sans-tech">ธันวาคม 2025</span>
                    </div>
                </div>

                <!-- Cert 3: Power BI -->
                <div class="glass-card rounded-3xl p-6 sm:p-8 flex flex-col justify-between reveal-left group cursor-pointer relative overflow-hidden">
                    <div class="space-y-4">
                        <!-- Large Certificate Image Container -->
                        <div class="w-full h-56 sm:h-64 bg-slate-100 rounded-2xl overflow-hidden border border-slate-200/60 shadow-inner shrink-0 relative group-hover:border-emerald-500/30 transition-colors">
                            <img src="https://placehold.co/600x450/f0fdf4/16a34a?text=Microsoft+Power+BI+Data+Visualization+Training" alt="Power BI Certificate Preview" class="w-full h-full object-cover transition-transform duration-700 ease-out">
                            <div class="absolute inset-0 bg-brandBlue-900/10 opacity-0 group-hover:opacity-100 transition-opacity flex items-center justify-center">
                                <span class="px-4 py-2 bg-white/90 text-brandBlue-900 rounded-full text-xs font-bold shadow-md"><i class="fa-solid fa-magnifying-glass-plus mr-1.5"></i>ดูภาพขนาดใหญ่</span>
                            </div>
                        </div>

                        <div class="space-y-2">
                            <div class="flex items-center space-x-2">
                                <div class="w-10 h-10 rounded-xl bg-emerald-50 flex items-center justify-center text-emerald-600 group-hover:scale-110 transition-transform shadow-sm">
                                    <i class="fa-solid fa-chart-line text-base"></i>
                                </div>
                                <span class="text-xs font-bold text-emerald-600 tracking-wider uppercase sans-tech">Business Intelligence</span>
                            </div>
                            <h3 class="text-lg sm:text-xl font-extrabold text-brandBlue-950 leading-snug group-hover:text-brandBlue-600 transition-colors">หลักสูตรฝึกอบรมการวิเคราะห์ Microsoft Power BI</h3>
                            <p class="text-slate-600 text-sm sm:text-base font-light leading-relaxed">
                                ผ่านระดับการประเมินทักษะจัดโครงสร้างคลีนนิ่งคลังข้อมูล เชื่อมโยง Data Model และประกอบภาพรายงานแดชบอร์ดสรุปทัศนวิสัยเพื่อประกอบกลยุทธ์ธุรกิจที่แม่นยำ
                            </p>
                        </div>
                    </div>
                    <div class="border-t border-slate-100 pt-4 mt-6 flex justify-between items-center text-xs text-slate-400 font-medium">
                        <span>สถาบันคุณวุฒิวิชาชีพ (องค์การมหาชน)</span>
                        <span class="bg-slate-100/80 px-2.5 py-1 rounded text-slate-600 sans-tech">กรกฎาคม 2025</span>
                    </div>
                </div>

                <!-- Cert 4: IC3 GS6 -->
                <div class="glass-card rounded-3xl p-6 sm:p-8 flex flex-col justify-between reveal-right group cursor-pointer relative overflow-hidden">
                    <div class="space-y-4">
                        <!-- Large Certificate Image Container -->
                        <div class="w-full h-56 sm:h-64 bg-slate-100 rounded-2xl overflow-hidden border border-slate-200/60 shadow-inner shrink-0 relative group-hover:border-purple-500/30 transition-colors">
                            <img src="https://placehold.co/600x450/faf5ff/9333ea?text=IC3+Digital+Literacy+Certification+GS6+Level+1" alt="IC3 Certificate Preview" class="w-full h-full object-cover transition-transform duration-700 ease-out">
                            <div class="absolute inset-0 bg-brandBlue-900/10 opacity-0 group-hover:opacity-100 transition-opacity flex items-center justify-center">
                                <span class="px-4 py-2 bg-white/90 text-brandBlue-900 rounded-full text-xs font-bold shadow-md"><i class="fa-solid fa-magnifying-glass-plus mr-1.5"></i>ดูภาพขนาดใหญ่</span>
                            </div>
                        </div>

                        <div class="space-y-2">
                            <div class="flex items-center space-x-2">
                                <div class="w-10 h-10 rounded-xl bg-purple-50 flex items-center justify-center text-purple-600 group-hover:scale-110 transition-transform shadow-sm">
                                    <i class="fa-solid fa-desktop text-base"></i>
                                </div>
                                <span class="text-xs font-bold text-purple-600 tracking-wider uppercase sans-tech">Digital Literacy</span>
                            </div>
                            <h3 class="text-lg sm:text-xl font-extrabold text-brandBlue-950 leading-snug group-hover:text-brandBlue-600 transition-colors">ประกาศนียบัตรสากลคอมพิวเตอร์ IC3 Digital Literacy</h3>
                            <p class="text-slate-600 text-sm sm:text-base font-light leading-relaxed">
                                ได้รับใบรับรองทักษะสากลทางเทคโนโลยีคอมพิวเตอร์และระบบเครือข่ายความมั่นคงปลอดภัยขั้นพื้นฐาน (GS6 Level 1) ยืนยันมาตรฐานการประยุกต์ใช้งานดิจิทัลซอฟต์แวร์สากล
                            </p>
                        </div>
                    </div>
                    <div class="border-t border-slate-100 pt-4 mt-6 flex justify-between items-center text-xs text-slate-400 font-medium">
                        <span>Certiport (Pearson VUE)</span>
                        <span class="bg-slate-100/80 px-2.5 py-1 rounded text-slate-600 sans-tech">กุมภาพันธ์ 2025</span>
                    </div>
                </div>

            </div>
        </section>

        <!-- Activities Section -->
        <section id="activities" class="scroll-mt-24 reveal-element">
            <div class="text-center max-w-3xl mx-auto mb-16">
                <div class="text-xs font-bold text-brandBlue-600 tracking-widest uppercase mb-2 sans-tech">กิจกรรมนอกตำรา</div>
                <h2 class="text-4xl sm:text-5xl md:text-6xl font-extrabold text-brandBlue-950 serif-title">กิจกรรมและบทบาทการทำงานร่วมกับผู้อื่น</h2>
                <p class="text-slate-500 mt-2 text-sm">ประสบการณ์การประสานงาน อำนวยความสะดวก และเผยแพร่องค์ความรู้ให้สังคมมหาวิทยาลัย</p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                
                <!-- Activity 1 -->
                <div class="glass-card rounded-2xl overflow-hidden flex flex-col justify-between group reveal-left cursor-pointer">
                    <div class="w-full h-52 bg-slate-100 overflow-hidden relative border-b border-slate-200/40">
                        <img src="https://placehold.co/600x400/2563eb/ffffff?text=MSU+Open+House+Event" alt="MSU Open House Helper" class="w-full h-full object-cover transition-transform duration-500">
                    </div>
                    <div class="p-5 space-y-2">
                        <div class="flex justify-between items-center">
                            <span class="text-xs text-brandBlue-600 font-bold uppercase tracking-wider sans-tech">ประชาสัมพันธ์และนำเสนอ</span>
                            <span class="text-xs text-slate-400 sans-tech">ธันวาคม 2024</span>
                        </div>
                        <h3 class="text-base font-bold text-brandBlue-950 group-hover:text-brandBlue-600 transition-colors">ผู้ช่วยดำเนินงาน MSU Open House</h3>
                        <p class="text-slate-500 text-sm leading-relaxed font-light">
                            ต้อนรับ แนะนำ และอธิบายขอบข่ายการเรียนการสอนด้านระบบธุรกิจดิจิทัล รวมถึงความรู้เบื้องต้นของ Dashboard และโมเดลอย่างลื่นไหลให้แก่เยาวชนระดับมัธยมศึกษาตอนปลาย
                        </p>
                    </div>
                </div>

                <!-- Activity 2 -->
                <div class="glass-card rounded-2xl overflow-hidden flex flex-col justify-between group reveal-right cursor-pointer">
                    <div class="w-full h-52 bg-slate-100 overflow-hidden relative border-b border-slate-200/40">
                        <img src="https://placehold.co/600x400/1e3a8a/ffffff?text=MBS+Fresh+Day+Management" alt="MBS Fresh Day Staff" class="w-full h-full object-cover transition-transform duration-500">
                    </div>
                    <div class="p-5 space-y-2">
                        <div class="flex justify-between items-center">
                            <span class="text-xs text-brandBlue-600 font-bold uppercase tracking-wider sans-tech">ฝ่ายจัดเตรียมสถานที่</span>
                            <span class="text-xs text-slate-400 sans-tech">กรกฎาคม 2025</span>
                        </div>
                        <h3 class="text-base font-bold text-brandBlue-950 group-hover:text-brandBlue-600 transition-colors">ผู้ช่วยประสานงาน MBS Fresh Day & Fresh Night</h3>
                        <p class="text-slate-500 text-sm leading-relaxed font-light">
                            ดูแลความสะอาดเรียบร้อย จัดตารางลงทะเบียนแถว และนำทางให้แก่นิสิตใหม่ของสถาบัน คณะการบัญชีและการจัดการ รวมยอดสมาชิกเข้าร่วมกิจกรรมกว่า 300 คน
                        </p>
                    </div>
                </div>

            </div>
        </section>

        <!-- Contact Section -->
        <section id="contact" class="scroll-mt-24 reveal-element">
            <div class="glass-card rounded-2xl p-8 md:p-12 grid grid-cols-1 lg:grid-cols-12 gap-12 items-center relative overflow-hidden">
                <div class="absolute inset-0 bg-gradient-to-tr from-brandBlue-50/40 to-transparent pointer-events-none"></div>
                
                <div class="lg:col-span-5 space-y-6">
                    <div>
                        <span class="text-xs font-bold text-brandBlue-600 tracking-widest uppercase mb-2 block sans-tech">ส่งข้อความหาฉัน</span>
                        <h2 class="text-3xl font-extrabold text-brandBlue-950 serif-title">ช่องทางติดต่อเสนอโอกาสฝึกงาน</h2>
                    </div>
                    <p class="text-slate-500 text-sm leading-relaxed font-light">
                        หากองค์กร หน่วยงาน หรือผู้ประกอบการใดสนใจพิจารณาและประเมินดิฉันเข้าฝึกงานช่วงเดือน ธ.ค. 2026 – มี.ค. 2027 สามารถกรอกข้อมูลผ่านโครงสร้างฟอร์มเพื่อการสื่อสารโดยเร็วที่สุดค่ะ
                    </p>

                    <div class="space-y-4 pt-4 border-t border-slate-100 text-xs text-slate-600">
                        <div class="flex items-center space-x-3">
                            <i class="fa-regular fa-envelope text-brandBlue-600 text-sm"></i>
                            <span class="text-sm">nonglukkluanthaisong@gmail.com</span>
                        </div>
                        <div class="flex items-center space-x-3">
                            <i class="fa-solid fa-phone text-brandBlue-600 text-sm"></i>
                            <span class="text-sm">(+66) 94-570-5055</span>
                        </div>
                        <div class="flex items-center space-x-3">
                            <i class="fa-solid fa-location-dot text-brandBlue-600 text-sm"></i>
                            <span class="text-sm">มหาวิทยาลัยมหาสารคาม, มหาสารคาม, ประเทศไทย</span>
                        </div>
                    </div>
                </div>

                <!-- Contact Simulation Form with interactive glowing inputs -->
                <div class="lg:col-span-7 bg-white p-6 md:p-8 rounded-xl border border-slate-100 shadow-sm">
                    <form onsubmit="submitForm(event)" class="space-y-4">
                        <div>
                            <label class="text-xs text-slate-500 block mb-1 uppercase font-bold sans-tech">ชื่อของคุณ / ชื่อหน่วยงาน</label>
                            <input required type="text" class="w-full bg-slate-50 border border-slate-200 rounded-lg px-4 py-2.5 text-sm focus:outline-none focus:border-brandBlue-500 focus:bg-white text-slate-800 transition-all">
                        </div>
                        <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                            <div>
                                <label class="text-xs text-slate-500 block mb-1 uppercase font-bold sans-tech">ที่อยู่อีเมลติดต่อกลับ</label>
                                <input required type="email" class="w-full bg-slate-50 border border-slate-200 rounded-lg px-4 py-2.5 text-sm focus:outline-none focus:border-brandBlue-500 focus:bg-white text-slate-800 transition-all">
                            </div>
                            <div>
                                <label class="text-xs text-slate-500 block mb-1 uppercase font-bold sans-tech">หัวข้ออีเมล</label>
                                <input required type="text" placeholder="เช่น การนัดสัมภาษณ์ฝึกงาน" class="w-full bg-slate-50 border border-slate-200 rounded-lg px-4 py-2.5 text-sm focus:outline-none focus:border-brandBlue-500 focus:bg-white text-slate-800 transition-all">
                            </div>
                        </div>
                        <div>
                            <label class="text-xs text-slate-500 block mb-1 uppercase font-bold sans-tech">เนื้อหารายละเอียดข้อความ</label>
                            <textarea required rows="4" class="w-full bg-slate-50 border border-slate-200 rounded-lg px-4 py-2.5 text-sm focus:outline-none focus:border-brandBlue-500 focus:bg-white text-slate-800 transition-all"></textarea>
                        </div>
                        <button type="submit" class="w-full py-3 rounded-lg bg-brandBlue-600 text-white font-bold hover:bg-brandBlue-700 hover:shadow-lg hover:scale-[1.02] active:scale-[0.98] transition-all text-center text-sm sans-tech">
                            ส่งข้อความติดต่อกลับโดยด่วน
                        </button>
                    </form>
                    <p id="form-success" class="hidden text-sm text-green-600 mt-3 font-semibold text-center"><i class="fa-solid fa-check mr-1.5"></i> ส่งข้อมูลเข้าสู่ระบบเรียบร้อยแล้วค่ะ! ขอขอบพระคุณเป็นอย่างยิ่ง</p>
                </div>

            </div>
        </section>

    </main>

    <!-- Footer -->
    <footer class="border-t border-slate-100 py-8 text-center text-[11px] text-slate-400 bg-white no-print sans-tech">
        <p>&copy; 2026 นงลักษณ์ เกลื่อนไทสง. จัดทำตามมาตรฐานการออกแบบระดับสูงแบบตอบสนองเต็มรูปแบบ (Responsive Design)</p>
    </footer>

    <!-- INTERACTIVE PRINT-READY RESUME MODAL -->
    <div id="cv-modal" class="fixed inset-0 z-50 overflow-y-auto hidden bg-brandBlue-950/40 backdrop-blur-md flex items-center justify-center p-4">
        <div class="bg-white text-slate-900 w-full max-w-4xl rounded-xl shadow-2xl relative overflow-hidden flex flex-col max-h-[90vh]">
            
            <!-- Modal Top Control Bar -->
            <div class="bg-slate-50 px-6 py-4 flex items-center justify-between border-b border-slate-200 no-print">
                <span class="font-bold text-xs text-slate-700 sans-tech">ส่งออก / สั่งพิมพ์ไฟล์เอกสารประวัติวิชาชีพทางการ (Resume)</span>
                <div class="flex items-center space-x-2">
                    <button onclick="window.print()" class="px-4 py-2 bg-brandBlue-600 text-white rounded-lg text-xs font-bold hover:bg-brandBlue-700 transition-colors flex items-center space-x-1 sans-tech">
                        <i class="fa-solid fa-print"></i>
                        <span>พิมพ์ หรือบันทึกเป็นไฟล์ PDF</span>
                    </button>
                    <button onclick="closeCvModal()" class="text-slate-400 hover:text-slate-700 font-bold text-lg">&times;</button>
                </div>
            </div>

            <!-- Print Content matching actual CV details -->
            <div id="cv-modal-content" class="p-8 md:p-12 overflow-y-auto bg-white flex-1 text-slate-900 font-sans leading-relaxed text-sm">
                
                <!-- CV Top Profile Section -->
                <div class="flex flex-col md:flex-row items-start md:items-center justify-between pb-6 border-b-2 border-brandBlue-700">
                    <div class="flex items-start space-x-6">
                        <!-- Portrait inside Print Document -->
                        <div class="w-24 h-24 rounded-full overflow-hidden border border-slate-200 shrink-0">
                            <img src="Nongluk.cv_2.jpg" alt="นงลักษณ์ เกลื่อนไทสง" class="w-full h-full object-cover" onerror="this.onerror=null; this.src='https://placehold.co/150x150/eff6ff/1e3a8a?text=Nongluk';">
                        </div>
                        <div>
                            <h1 class="text-xl font-black tracking-tight text-brandBlue-900 uppercase">นงลักษณ์ เกลื่อนไทสง (Nongluk Kluanthaisong)</h1>
                            <p class="text-xs font-bold text-slate-700 mt-1">ช่วงเวลาปฏิบัติงานฝึกอบรม: 1 ธันวาคม 2569 – 31 มีนาคม 2570</p>
                            
                            <!-- Address/Contact Specs -->
                            <div class="mt-2 grid grid-cols-1 md:grid-cols-2 gap-x-6 gap-y-1.5 text-[11px] text-slate-600">
                                <div><strong>ที่อยู่สถาบัน:</strong> คณะการบัญชีและการจัดการ มหาวิทยาลัยมหาสารคาม, มหาสารคาม</div>
                                <div><strong>โทรศัพท์ติดต่อ:</strong> (+66) 94-570-5055</div>
                                <div><strong>อีเมลทางการ:</strong> nonglukkluanthaisong@gmail.com</div>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Resume Summary -->
                <div class="mt-5">
                    <h2 class="text-xs font-bold text-brandBlue-900 uppercase tracking-widest border-b border-brandBlue-700/25 pb-1">ข้อมูลโดยสรุป (SUMMARY)</h2>
                    <p class="mt-1.5 text-slate-700 leading-relaxed text-justify">
                        นิสิตชั้นปีที่ 4 สาขาธุรกิจดิจิทัลและระบบสารสนเทศ คณะการบัญชีและการจัดการ มหาวิทยาลัยมหาสารคาม มุ่งมั่นและมีความตั้งใจอย่างยิ่งในสายงานการจัดการข้อมูลขนาดใหญ่ (Data Analysis), การประสานงานพัฒนาคลังเอกสาร ตลอดจนการบูรณาการระบบอัตโนมัติ (Business Process Automation) เพื่อประยุกต์ทักษะความคิดเชิงออกแบบร่วมกับกระบวนการวิจัยช่วยขยายผลสำเร็จของบริษัทร่วมงานอย่างปลอดภัยและคุ้มค่าที่สุด
                    </p>
                </div>

                <!-- Education Details -->
                <div class="mt-5">
                    <h2 class="text-xs font-bold text-brandBlue-900 uppercase tracking-widest border-b border-brandBlue-700/25 pb-1">การศึกษา (EDUCATION)</h2>
                    <div class="mt-2 flex justify-between items-start text-xs">
                        <div>
                            <strong class="text-slate-800 block text-xs">บริหารธุรกิจบัณฑิต (บธ.บ.) สาขาธุรกิจดิจิทัลและระบบสารสนเทศ</strong>
                            <span class="text-slate-600 block">คณะการบัญชีและการจัดการ มหาวิทยาลัยมหาสารคาม (MSU)</span>
                            <span class="text-slate-600 block mt-0.5">ผลการเรียนเฉลี่ยสะสมปัจจุบัน (GPAX): 3.68/4.00</span>
                        </div>
                        <div class="text-right text-slate-500 font-medium">มิถุนายน 2566 – ปัจจุบัน <br><span class="text-[9px]">คาดว่าจะสำเร็จการศึกษา: พฤษภาคม 2570</span></div>
                    </div>
                </div>

                <!-- Academic Projects -->
                <div class="mt-5">
                    <h2 class="text-xs font-bold text-brandBlue-900 uppercase tracking-widest border-b border-brandBlue-700/25 pb-1">โครงการวิชาการและผลงานเด่น (ACADEMIC PROJECTS)</h2>
                    <div class="mt-2.5 space-y-3.5">
                        <div>
                            <div class="flex justify-between items-start text-xs">
                                <strong class="text-slate-800 text-xs">โมเดลพยากรณ์ปริมาณการใช้ไฟฟ้าในประเทศไทยด้วยปัญญาประดิษฐ์ (Machine Learning | Power BI)</strong>
                                <span class="text-slate-500 font-medium">ตุลาคม 2568</span>
                            </div>
                            <ul class="list-disc list-inside mt-1.5 text-slate-700 space-y-0.5 pl-1">
                                <li>ดำเนินการเก็บรวบรวมข้อมูล จัดโครงสร้าง Clean Data และนำเสนอแนวคิดผ่าน Dashboard เพื่อทำความเข้าใจพฤติกรรมการจ่ายพลังงานอย่างเป็นระบบ</li>
                            </ul>
                        </div>
                        <div>
                            <div class="flex justify-between items-start text-xs">
                                <strong class="text-slate-800 text-xs">การออกแบบประสบการณ์ผู้ใช้ TrueID App UX/UI Redesign เพื่อพฤติกรรมการบริการผู้ใช้ที่รวดเร็ว</strong>
                                <span class="text-slate-500 font-medium">พฤศจิกายน 2567</span>
                            </div>
                            <ul class="list-disc list-inside mt-1.5 text-slate-700 space-y-0.5 pl-1">
                                <li>ออกแบบระบบทิศทางหน้าต่างของหน้าจอโดยค้นหาปัญหาดั้งเดิม (Pain points) เพื่อเสนอต้นแบบที่มีทัศนวิสัยเหมาะสมบนระบบซอฟต์แวร์ Figma</li>
                            </ul>
                        </div>
                        <div>
                            <div class="flex justify-between items-start text-xs">
                                <strong class="text-slate-800 text-xs">ชุดจำลองการเรียนรู้เสมือนจริง AR/VR สัตว์ดึกดำบรรพ์ในนิทรรศการพิพิธภัณฑ์</strong>
                                <span class="text-slate-500 font-medium">มกราคม 2567</span>
                            </div>
                            <ul class="list-disc list-inside mt-1.5 text-slate-700 space-y-0.5 pl-1">
                                <li>ออกแบบกระบวนการสื่อสารเชิงแอนิเมชันสามมิติของไดโนเสาร์แต่ละสายพันธุ์ เพื่อช่วยสนับสนุนสุนทรียศาสตร์และการรับข้อมูลในพิพิธภัณฑ์อย่างใกล้ชิด</li>
                            </ul>
                        </div>
                    </div>
                </div>

                <!-- Certifications section -->
                <div class="mt-5">
                    <h2 class="text-xs font-bold text-brandBlue-900 uppercase tracking-widest border-b border-brandBlue-700/25 pb-1">ใบรับรองและการฝึกอบรม (CERTIFICATIONS & TRAINING)</h2>
                    <ul class="mt-2 text-slate-700 space-y-1.5 pl-1">
                        <li class="flex justify-between">
                            <span>&bull; ผ่านการทดสอบภาษาอังกฤษเกณฑ์สถาบัน MSU English Exit Examination (ระดับความรู้ CEFR B1)</span>
                            <span class="text-slate-500">กุมภาพันธ์ 2569</span>
                        </li>
                        <li class="flex justify-between">
                            <span>&bull; ประกาศนียบัตร Generative AI & ChatGPT เพื่อการศึกษาวิจัยและการสรุปข้อมูลสถิติ &ndash; มหาวิทยาลัยเกษตรศาสตร์</span>
                            <span class="text-slate-500">ธันวาคม 2568</span>
                        </li>
                        <li class="flex justify-between">
                            <span>&bull; ใบรับรองมาตรฐาน Microsoft Power BI การสร้าง Dashboard &ndash; สถาบันคุณวุฒิวิชาชีพ (องค์การมหาชน)</span>
                            <span class="text-slate-500">กรกฎาคม 2568</span>
                        </li>
                        <li class="flex justify-between">
                            <span>&bull; ประกาศนียบัตรสากลคอมพิวเตอร์พื้นฐาน IC3 Digital Literacy Certification (GS6 Level 1) | Certiport</span>
                            <span class="text-slate-500">กุมภาพันธ์ 2568</span>
                        </li>
                        <li class="flex justify-between">
                            <span>&bull; แผนกลยุทธ์การขายธุรกิจยุคดิจิทัล LINE Official Account (LINE OA) เพื่อการส่งเสริมยอดการตลาด | MBS, MSU</span>
                            <span class="text-slate-500">ธันวาคม 2567</span>
                        </li>
                    </ul>
                </div>

                <!-- Extracurricular Activities -->
                <div class="mt-5">
                    <h2 class="text-xs font-bold text-brandBlue-900 uppercase tracking-widest border-b border-brandBlue-700/25 pb-1">กิจกรรมภายนอกและการประสานงานกลาง (ACTIVITIES)</h2>
                    <div class="mt-2 space-y-2.5">
                        <div>
                            <div class="flex justify-between items-start">
                                <strong class="text-slate-800">ผู้ช่วยเตรียมบูธและจัดแนะแนวโครงการ MSU OPEN HOUSE &ndash; MAHASARAKHAM UNIVERSITY</strong>
                                <span class="text-slate-500">ธันวาคม 2567</span>
                            </div>
                            <p class="text-slate-700 mt-0.5 pl-3">&bull; สนับสนุนอธิบายระบบการวิเคราะห์ข้อมูลและการใช้โครงร่างแผนกแดชบอร์ดแก่บุคคลภายนอกและกลุ่มนักเรียนในรอบแนะแนวหลักสูตร</p>
                        </div>
                        <div>
                            <div class="flex justify-between items-start">
                                <strong class="text-slate-800">ฝ่ายจัดสถานที่โครงการต้อนรับสมาชิกร่วมสโมสรนิสิต MBS Fresh Day & Fresh Night</strong>
                                <span class="text-slate-500">กรกฎาคม 2568</span>
                            </div>
                            <p class="text-slate-700 mt-0.5 pl-3">&bull; ดูแลจัดการทะเบียนแถว จัดเตรียมเอกสาร และอำนวยความสะดวกให้แก่สมาชิกร่วมงานจำนวนมากให้เป็นระบบเรียบร้อยตามมาตรฐานความปลอดภัย</p>
                        </div>
                    </div>
                </div>

                <!-- Skills & Skills -->
                <div class="mt-5 mb-4">
                    <h2 class="text-xs font-bold text-brandBlue-900 uppercase tracking-widest border-b border-brandBlue-700/25 pb-1">ทักษะและความสามารถทางภาษา (SKILLS & LANGUAGES)</h2>
                    <div class="mt-2 text-slate-700 space-y-1.5">
                        <p><strong>โปรแกรมและอุปกรณ์ทำงาน:</strong> Microsoft Office, Canva, Power BI, AI Studio, Figma, ระบบอัตโนมัติ n8n</p>
                        <p><strong>ความถนัดส่วนบุคคล:</strong> การคิดเชิงวิเคราะห์ (Analytical Thinking), ความเป็นหนึ่งเดียวของกลุ่ม (Team Collaboration), ความพิถีพิถันตรวจสอบคุณภาพคลังข้อมูล (Attention to Detail)</p>
                        <p><strong>ภาษาต่างประเทศ:</strong> ภาษาไทย (ภาษาหลัก), ภาษาอังกฤษระดับปานกลาง (CEFR B1) &ndash; ยืนยันสถิติโดยคะแนนสอบสถาบัน</p>
                    </div>
                </div>

            </div>
        </div>
    </div>

    <!-- JavaScript Code -->
    <script>
        document.addEventListener('DOMContentLoaded', () => {
            // Setup intersection observer for smooth animation transitions
            const observerOptions = {
                root: null,
                rootMargin: '0px',
                threshold: 0.1
            };

            const revealObserver = new IntersectionObserver((entries, observer) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('active');
                    }
                });
            }, observerOptions);

            const revealElements = document.querySelectorAll('.reveal-element, .reveal-left, .reveal-right');
            revealElements.forEach(el => revealObserver.observe(el));

            // Monitor window scroll state to update progress indicator
            window.addEventListener('scroll', () => {
                const winScroll = document.body.scrollTop || document.documentElement.scrollTop;
                const height = document.documentElement.scrollHeight - document.documentElement.clientHeight;
                const scrolled = (winScroll / height) * 100;
                const progressElement = document.getElementById('scroll-progress');
                if (progressElement) {
                    progressElement.style.width = scrolled + '%';
                }
            });

            // --- Scrollspy Hide & Show Header Logic ---
            let lastScrollY = window.scrollY;
            const header = document.getElementById('main-header');

            window.addEventListener('scroll', () => {
                const currentScrollY = window.scrollY;
                if (!header) return;

                if (currentScrollY > lastScrollY && currentScrollY > 120) {
                    // Scrolling down - Hide Header cleanly
                    header.style.transform = 'translateY(-100%)';
                } else {
                    // Scrolling up - Show Header
                    header.style.transform = 'translateY(0)';
                }
                lastScrollY = currentScrollY;
            });

            // --- ScrollSpy Active Underline Tracker Algorithm ---
            const sections = document.querySelectorAll('section[id]');
            const navLinks = document.querySelectorAll('.nav-link');

            function trackScrollSpy() {
                let currentSectionId = 'home';
                
                sections.forEach(section => {
                    const sectionTop = section.offsetTop - 150;
                    const sectionHeight = section.clientHeight;
                    if (window.scrollY >= sectionTop && window.scrollY < sectionTop + sectionHeight) {
                        currentSectionId = section.getAttribute('id');
                    }
                });

                navLinks.forEach(link => {
                    // Reset to initial clean state
                    link.className = "nav-link text-slate-600 hover:text-brandBlue-600 px-4 py-3 border-b-2 border-transparent transition-all duration-300";
                    
                    if (link.getAttribute('href') === `#${currentSectionId}`) {
                        // Apply the clean active underline style
                        link.className = "nav-link text-brandBlue-600 border-b-2 border-brandBlue-600 px-4 py-3 transition-all duration-300 font-bold";
                    }
                });
            }

            window.addEventListener('scroll', trackScrollSpy);
            trackScrollSpy(); // Trigger initially

            // Setup dynamic background with mouse magnetic features
            initNeuralBackground();
        });

        // HTML5 Canvas AI Neural Connections
        function initNeuralBackground() {
            const canvas = document.getElementById('neural-canvas');
            if (!canvas) return;
            const ctx = canvas.getContext('2d');
            
            let width = canvas.width = canvas.parentElement.clientWidth;
            let height = canvas.height = canvas.parentElement.clientHeight;
            
            const dots = [];
            const dotCount = Math.min(75, Math.floor((width * height) / 12000));
            const mouse = { x: null, y: null, radius: 200 }; // Expanded magnet radius for better user tracking

            window.addEventListener('resize', () => {
                if (canvas.parentElement) {
                    width = canvas.width = canvas.parentElement.clientWidth;
                    height = canvas.height = canvas.parentElement.clientHeight;
                }
            });

            window.addEventListener('mousemove', (e) => {
                const rect = canvas.getBoundingClientRect();
                mouse.x = e.clientX - rect.left;
                mouse.y = e.clientY - rect.top;
            });

            window.addEventListener('mouseleave', () => {
                mouse.x = null;
                mouse.y = null;
            });

            for (let i = 0; i < dotCount; i++) {
                dots.push({
                    x: Math.random() * width,
                    y: Math.random() * height,
                    vx: (Math.random() - 0.5) * 0.45,
                    vy: (Math.random() - 0.5) * 0.45,
                    radius: Math.random() * 2.5 + 1
                });
            }

            function animate() {
                ctx.clearRect(0, 0, width, height);
                
                dots.forEach(dot => {
                    dot.x += dot.vx;
                    dot.y += dot.vy;

                    if (dot.x < 0 || dot.x > width) dot.vx *= -1;
                    if (dot.y < 0 || dot.y > height) dot.vy *= -1;

                    if (mouse.x !== null && mouse.y !== null) {
                        const dx = mouse.x - dot.x;
                        const dy = mouse.y - dot.y;
                        const dist = Math.sqrt(dx * dx + dy * dy);
                        if (dist < mouse.radius) {
                            dot.x += dx * 0.02; // Enhanced smooth pull speed
                            dot.y += dy * 0.02;
                        }
                    }

                    ctx.beginPath();
                    ctx.arc(dot.x, dot.y, dot.radius, 0, Math.PI * 2);
                    ctx.fillStyle = 'rgba(37, 99, 235, 0.45)';
                    ctx.fill();
                });

                for (let i = 0; i < dots.length; i++) {
                    for (let j = i + 1; j < dots.length; j++) {
                        const dx = dots[i].x - dots[j].x;
                        const dy = dots[i].y - dots[j].y;
                        const dist = Math.sqrt(dx * dx + dy * dy);

                        if (dist < 120) {
                            ctx.beginPath();
                            ctx.moveTo(dots[i].x, dots[i].y);
                            ctx.lineTo(dots[j].x, dots[j].y);
                            ctx.strokeStyle = `rgba(37, 99, 235, ${0.15 * (1 - dist / 120)})`;
                            ctx.lineWidth = 0.9;
                            ctx.stroke();
                        }
                    }
                }

                requestAnimationFrame(animate);
            }

            animate();
        }

        // Hamburger mobile controller
        function toggleMobileMenu() {
            const menu = document.getElementById('mobile-menu');
            if (menu) {
                menu.classList.toggle('hidden');
            }
        }

        // Submit mock feedback form
        function submitForm(event) {
            event.preventDefault();
            const successMsg = document.getElementById('form-success');
            if (successMsg) {
                successMsg.classList.remove('hidden');
            }
            event.target.reset();
            setTimeout(() => {
                if (successMsg) {
                    successMsg.classList.add('hidden');
                }
            }, 5000);
        }

        // CV Modal open/close actions
        function openCvModal() {
            const modal = document.getElementById('cv-modal');
            if (modal) {
                modal.classList.remove('hidden');
                document.body.classList.add('overflow-hidden');
            }
        }

        // Close CV modal
        function closeCvModal() {
            const modal = document.getElementById('cv-modal');
            if (modal) {
                modal.classList.add('hidden');
                document.body.classList.remove('overflow-hidden');
            }
        }
    </script>
</body>
</html>
