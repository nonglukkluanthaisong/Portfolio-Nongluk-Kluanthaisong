<!DOCTYPE html>
<html lang="th" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nongluk Kluanthaisong - Premium Portfolio</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts (Inter & Sarabun) -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&family=Sarabun:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
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
                            100: '#e0f2fe',
                            300: '#7dd3fc',
                            500: '#0066cc',
                            600: '#0052a3',
                            700: '#1d4ed8',
                            800: '#1e40af',
                            900: '#0f172a',
                            950: '#020617',
                        }
                    }
                }
            }
        }
    </script>

    <style>
        /* Smooth Fade-in & Slide-up Scroll Animations */
        .reveal {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s cubic-bezier(0.16, 1, 0.3, 1);
        }
        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* Glassmorphism Styles for Light Theme */
        .glass-card {
            background: rgba(255, 255, 255, 0.85);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border: 1px solid rgba(226, 232, 240, 0.8);
        }
        
        /* Premium Blue Hover Glows on White BG */
        .glow-blue:hover {
            box-shadow: 0 15px 30px rgba(0, 102, 204, 0.08);
            border-color: rgba(0, 102, 204, 0.3);
        }

        /* Custom Scrollbar for modern feel */
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
            background: #0066cc;
        }

        /* Smooth Transition for Navbar hiding */
        header {
            transition: transform 0.3s ease-in-out, background-color 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
        }
    </style>
</head>
<body class="bg-slate-50 text-slate-800 font-sans antialiased selection:bg-brand-500 selection:text-white overflow-x-hidden">

    <!-- Floating Luxury Header (Hides on Scroll Up, Shows on Scroll Down) -->
    <header id="mainHeader" class="fixed top-0 left-0 right-0 z-40 bg-white/90 backdrop-blur-md border-b border-slate-100 shadow-sm translate-y-0">
        <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8 h-20 flex items-center justify-between">
            <a href="#home" class="font-extrabold text-2xl tracking-wider text-slate-900">
                NONGLUK<span class="text-brand-500">.K</span>
            </a>
            <!-- Nav Menu with Active Indicator Line -->
            <nav id="navMenu" class="hidden md:flex space-x-6 lg:space-x-8 text-sm font-semibold">
                <a href="#home" class="nav-item py-2 text-brand-600 border-b-2 border-brand-600 transition-all duration-200">Home</a>
                <a href="#about" class="nav-item py-2 text-slate-600 hover:text-brand-500 border-b-2 border-transparent transition-all duration-200">About</a>
                <a href="#education" class="nav-item py-2 text-slate-600 hover:text-brand-500 border-b-2 border-transparent transition-all duration-200">Education</a>
                <a href="#projects" class="nav-item py-2 text-slate-600 hover:text-brand-500 border-b-2 border-transparent transition-all duration-200">Works & Projects</a>
                <a href="#certifications" class="nav-item py-2 text-slate-600 hover:text-brand-500 border-b-2 border-transparent transition-all duration-200">Certificates</a>
                <a href="#activities" class="nav-item py-2 text-slate-600 hover:text-brand-500 border-b-2 border-transparent transition-all duration-200">Activities</a>
            </nav>
            <div>
                <a href="#contact" class="relative inline-flex items-center justify-center p-0.5 overflow-hidden text-sm font-semibold rounded-full group bg-gradient-to-br from-cyan-500 to-brand-600 text-white hover:text-white focus:ring-4 focus:outline-none focus:ring-blue-300">
                    <span class="relative px-5 py-2 transition-all ease-in duration-75 bg-white text-slate-900 rounded-full group-hover:bg-opacity-0 group-hover:text-white">
                        Contact Me
                    </span>
                </a>
            </div>
        </div>
    </header>

    <!-- Home Section (First Page) -->
    <section id="home" class="pt-32 pb-20 md:pt-40 md:pb-32 overflow-hidden relative min-h-screen flex items-center bg-white">
        <!-- Subtle Background Glows (Light Theme) -->
        <div class="absolute top-1/4 left-1/10 w-[400px] h-[400px] bg-brand-100 rounded-full blur-[120px] opacity-40 pointer-events-none"></div>
        <div class="absolute bottom-1/4 right-1/10 w-[500px] h-[500px] bg-cyan-50 rounded-full blur-[140px] opacity-50 pointer-events-none"></div>

        <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10 w-full">
            <div class="flex flex-col lg:flex-row items-center gap-16">
                <!-- Hero Info (Left) -->
                <div class="flex-1 text-center lg:text-left space-y-8 reveal active">
                    <span class="inline-flex items-center gap-2 px-4 py-1.5 rounded-full text-xs font-bold bg-brand-50 border border-brand-100 text-brand-600 uppercase tracking-widest">
                        <span class="w-2.5 h-2.5 rounded-full bg-brand-500 animate-pulse"></span>
                        Digital Business & Info Systems
                    </span>
                    
                    <h1 class="text-4xl sm:text-6xl font-extrabold tracking-tight text-slate-900 leading-none">
                        Welcome to <br />
                        My Digital <span class="text-transparent bg-clip-text bg-gradient-to-r from-brand-500 to-cyan-500">Portfolio</span>
                    </h1>
                    
                    <p class="text-lg text-slate-600 max-w-xl mx-auto lg:mx-0 leading-relaxed">
                        สวัสดีค่ะ ยินดีต้อนรับสู่พื้นที่รวบรวมผลงานและประวัติของดิฉัน <strong>นงลักษณ์ ควรไทยสง</strong> นิสิตชั้นปีที่ 4 มหาวิทยาลัยมหาสารคาม มุ่งมั่นพร้อมก้าวสู่สายงานวิเคราะห์ข้อมูลและการจัดการข้อมูลดิจิทัล
                    </p>

                    <!-- Quick Navigation Cards -->
                    <div class="grid grid-cols-2 gap-4 max-w-md mx-auto lg:mx-0">
                        <a href="#about" class="p-4 bg-slate-50 hover:bg-brand-50 border border-slate-200 hover:border-brand-300 rounded-2xl transition-all duration-300 text-left group">
                            <i class="fa-solid fa-user-tie text-brand-500 text-lg mb-2"></i>
                            <h4 class="font-bold text-slate-800 text-sm">ประวัติส่วนตัว</h4>
                            <p class="text-xs text-slate-500 mt-1">ข้อมูลทั่วไปและเป้าหมาย</p>
                        </a>
                        <a href="#projects" class="p-4 bg-slate-50 hover:bg-brand-50 border border-slate-200 hover:border-brand-300 rounded-2xl transition-all duration-300 text-left group">
                            <i class="fa-solid fa-diagram-project text-brand-500 text-lg mb-2"></i>
                            <h4 class="font-bold text-slate-800 text-sm">ผลงานวิชาการ</h4>
                            <p class="text-xs text-slate-500 mt-1">โปรเจกต์ที่เคยเข้าร่วม</p>
                        </a>
                    </div>

                    <!-- CTA Buttons -->
                    <div class="flex flex-wrap justify-center lg:justify-start gap-4 pt-2">
                        <a href="#about" class="px-8 py-4 rounded-xl bg-brand-600 hover:bg-brand-500 text-white font-bold transition-all duration-200 transform hover:translate-y-[-2px] flex items-center gap-3 shadow-md">
                            เริ่มทำความรู้จัก
                            <i class="fa-solid fa-arrow-right"></i>
                        </a>
                        <button onclick="openCVModal()" class="px-8 py-4 rounded-xl bg-slate-100 hover:bg-slate-200 text-slate-800 border border-slate-200 font-bold transition-all duration-200 flex items-center gap-3">
                            <i class="fa-solid fa-file-invoice text-brand-500"></i>
                            ดูใบเรซูเม่อ้างอิง (Nongluk.cv.jpg)
                        </button>
                    </div>
                </div>

                <!-- Profile Card Mockup (Right) -->
                <div class="flex-shrink-0 w-full max-w-[340px] lg:max-w-[380px] reveal active">
                    <div class="relative bg-white p-5 rounded-3xl shadow-xl border border-slate-200 transform hover:scale-[1.01] transition-all duration-300">
                        <!-- Student Portrait Frame -->
                        <div class="aspect-[3/4] bg-slate-100 rounded-2xl overflow-hidden relative group">
                            <div class="absolute inset-0 bg-gradient-to-t from-slate-900/40 via-transparent to-transparent z-10"></div>
                            <img src="Nongluk.cv.jpg" alt="Nongluk Kluanthaisong Portrait" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-700" onerror="this.onerror=null; this.src='https://images.unsplash.com/photo-1573496359142-b8d87734a5a2?q=80&w=600&auto=format&fit=crop';">
                            
                            <div class="absolute bottom-6 left-6 right-6 z-20 text-white">
                                <p class="text-xs font-bold uppercase tracking-widest text-brand-200">Mahasarakham University</p>
                                <h3 class="text-2xl font-extrabold mt-1">Nongluk K.</h3>
                                <p class="text-sm text-slate-100 mt-0.5">Digital Business Student</p>
                            </div>
                        </div>
                        
                        <!-- Contact Quick Access -->
                        <div class="mt-5 space-y-3.5 text-sm">
                            <div class="flex items-center gap-4 text-slate-600">
                                <div class="w-9 h-9 rounded-xl bg-brand-50 flex items-center justify-center text-brand-600 border border-brand-100">
                                    <i class="fa-regular fa-envelope"></i>
                                </div>
                                <span class="break-all font-medium">nonglukkluanthaisong@gmail.com</span>
                            </div>
                            <div class="flex items-center gap-4 text-slate-600">
                                <div class="w-9 h-9 rounded-xl bg-brand-50 flex items-center justify-center text-brand-600 border border-brand-100">
                                    <i class="fa-solid fa-phone"></i>
                                </div>
                                <span class="font-medium">(+66) 94-570-5055</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section with Executive Summary -->
    <section id="about" class="py-24 bg-slate-50 border-t border-slate-100 relative">
        <div class="max-w-4xl mx-auto px-4 sm:px-6 relative z-10 reveal">
            <div class="text-center space-y-6">
                <div class="inline-block p-1 rounded-full bg-brand-50 border border-brand-100 text-xs text-brand-600 font-bold uppercase tracking-widest px-4 py-1.5">
                    Professional Bio
                </div>
                <h2 class="text-4xl font-extrabold text-slate-900 tracking-tight">Executive Summary</h2>
                <div class="h-1 w-20 bg-gradient-to-r from-brand-500 to-cyan-500 mx-auto rounded-full"></div>
                <p class="text-xl text-slate-600 leading-relaxed font-light italic pt-4">
                    "A fourth-year Digital Business and Information Systems student with a strong interest in data analysis, business process analysis, data and document management, and leveraging digital technologies to improve work efficiency. Passionate about combining analytical thinking with creativity to solve complex problems and develop effective solutions."
                </p>
                <div class="pt-8 flex flex-wrap justify-center gap-3">
                    <span class="bg-white border border-slate-200 text-brand-600 px-4 py-1.5 rounded-full text-xs font-semibold shadow-sm">Data Analytics</span>
                    <span class="bg-white border border-slate-200 text-brand-600 px-4 py-1.5 rounded-full text-xs font-semibold shadow-sm">Business Processes</span>
                    <span class="bg-white border border-slate-200 text-brand-600 px-4 py-1.5 rounded-full text-xs font-semibold shadow-sm">Digital Workflows</span>
                    <span class="bg-white border border-slate-200 text-brand-600 px-4 py-1.5 rounded-full text-xs font-semibold shadow-sm">Analytical Intelligence</span>
                </div>
            </div>
        </div>
    </section>

    <!-- Education Section -->
    <section id="education" class="py-24 bg-white relative border-t border-slate-100">
        <div class="max-w-5xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
            <div class="text-center mb-16 reveal">
                <span class="text-xs font-bold text-brand-500 uppercase tracking-widest">Academic Timeline</span>
                <h2 class="text-4xl font-extrabold text-slate-900 tracking-tight mt-2">Education</h2>
                <div class="h-1 w-12 bg-gradient-to-r from-brand-500 to-cyan-500 mx-auto mt-4 rounded-full"></div>
            </div>

            <div class="reveal">
                <div class="glass-card border border-slate-200 p-8 md:p-10 rounded-3xl shadow-md hover:shadow-lg transition-all duration-300">
                    <div class="flex flex-col md:flex-row items-start md:items-center justify-between gap-6 pb-8 border-b border-slate-100">
                        <div class="flex items-center gap-5">
                            <div class="w-16 h-16 rounded-2xl bg-brand-50 border border-brand-100 flex items-center justify-center text-brand-600 flex-shrink-0 text-3xl">
                                <i class="fa-solid fa-graduation-cap"></i>
                            </div>
                            <div>
                                <h3 class="text-2xl font-extrabold text-slate-900">Mahasarakham University (MSU)</h3>
                                <p class="text-slate-500 font-medium">Mahasarakham Business School (MBS)</p>
                            </div>
                        </div>
                        <div class="bg-brand-50 text-brand-600 px-5 py-2 rounded-full text-xs font-bold border border-brand-100">
                            June 2023 – Present (Expected: May 2027)
                        </div>
                    </div>

                    <div class="grid grid-cols-1 md:grid-cols-2 gap-8 pt-8">
                        <div>
                            <h4 class="text-xs font-bold uppercase tracking-wider text-slate-400">Degree</h4>
                            <p class="text-lg font-bold text-slate-800 mt-1">B.A. in Digital Business and Information Systems</p>
                        </div>
                        <div class="flex flex-col sm:flex-row items-start sm:items-center gap-8">
                            <div>
                                <h4 class="text-xs font-bold uppercase tracking-wider text-slate-400">Current GPAX</h4>
                                <div class="flex items-baseline gap-1.5 mt-1">
                                    <span class="text-4xl font-black text-transparent bg-clip-text bg-gradient-to-r from-brand-600 to-cyan-500">3.68</span>
                                    <span class="text-slate-400 text-sm">/ 4.00</span>
                                </div>
                            </div>
                            <div class="sm:border-l sm:border-slate-200 sm:pl-8">
                                <h4 class="text-xs font-bold uppercase tracking-wider text-slate-400">Location</h4>
                                <p class="text-base font-semibold text-slate-700 mt-1.5">Mahasarakham, Thailand</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Academic Projects & Works Section -->
    <section id="projects" class="py-24 bg-slate-50 relative border-t border-slate-100">
        <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
            <div class="text-center mb-16 reveal">
                <span class="text-xs font-bold text-brand-500 uppercase tracking-widest font-mono">Academic Excellence</span>
                <h2 class="text-4xl font-extrabold text-slate-900 tracking-tight mt-2">Works & Projects</h2>
                <p class="text-slate-500 mt-2">ผลงานและโครงการพัฒนาเว็บไซต์/โมเดลวิเคราะห์ข้อมูลที่ผ่านมา</p>
                <div class="h-1 w-12 bg-gradient-to-r from-brand-500 to-cyan-500 mx-auto mt-4 rounded-full"></div>
            </div>

            <div class="grid grid-cols-1 gap-12">
                <!-- Project 1 -->
                <div class="reveal glass-card rounded-3xl overflow-hidden border border-slate-200 hover:border-brand-300 transition-all duration-300 flex flex-col lg:flex-row glow-blue shadow-sm">
                    <div class="lg:w-2/5 relative h-64 lg:h-auto min-h-[250px] bg-slate-100 overflow-hidden">
                        <!-- Dynamic Work Image -->
                        <img src="https://images.unsplash.com/photo-1551288049-bebda4e38f71?q=80&w=800&auto=format&fit=crop" alt="Electricity Forecasting Work" class="w-full h-full object-cover opacity-90 hover:scale-105 transition-transform duration-500">
                        <div class="absolute inset-0 bg-gradient-to-t lg:bg-gradient-to-r from-slate-50/50 via-transparent to-transparent"></div>
                    </div>
                    <div class="lg:w-3/5 p-8 flex flex-col justify-between bg-white">
                        <div>
                            <div class="flex flex-wrap items-center justify-between gap-4 mb-4">
                                <div class="flex gap-2">
                                    <span class="bg-blue-50 text-brand-600 text-[10px] font-bold px-3 py-1 rounded-full border border-blue-100 uppercase tracking-wider">Data Analytics</span>
                                    <span class="bg-teal-50 text-teal-600 text-[10px] font-bold px-3 py-1 rounded-full border border-teal-100 uppercase tracking-wider">Machine Learning</span>
                                </div>
                                <span class="text-xs font-bold text-slate-400 flex items-center gap-1.5">
                                    <i class="fa-regular fa-calendar-check"></i> Oct 2025
                                </span>
                            </div>
                            <h3 class="text-2xl font-bold text-slate-900 mb-3">Electricity Consumption Forecasting in Thailand</h3>
                            <p class="text-slate-600 text-sm leading-relaxed mb-6">
                                โครงการวิเคราะห์และสร้างแบบจำลองคาดการณ์ปริมาณการใช้ไฟฟ้าในประเทศไทย โดยการรวบรวมข้อมูล จัดเตรียมข้อมูลดิบ (Data Cleaning) และใช้โมเดลทางสถิติวิเคราะห์แนวโน้มเพื่อจัดทำเอกสารพยากรณ์โครงสร้างพื้นฐานพลังงาน
                            </p>
                        </div>
                        <div class="bg-slate-50 border border-slate-100 p-4 rounded-2xl flex items-start gap-3">
                            <i class="fa-solid fa-circle-check text-brand-500 mt-1"></i>
                            <p class="text-xs text-slate-500 font-medium leading-relaxed">
                                Collected, cleaned, and analyzed project data to identify key energy patterns, delivering advanced presentation materials to key stakeholders.
                            </p>
                        </div>
                    </div>
                </div>

                <!-- Project 2 -->
                <div class="reveal glass-card rounded-3xl overflow-hidden border border-slate-200 hover:border-brand-300 transition-all duration-300 flex flex-col lg:flex-row-reverse glow-blue shadow-sm">
                    <div class="lg:w-2/5 relative h-64 lg:h-auto min-h-[250px] bg-slate-100 overflow-hidden">
                        <!-- TrueID UI/UX Mock Image -->
                        <img src="https://images.unsplash.com/photo-1541462608143-67571c6738dd?q=80&w=800&auto=format&fit=crop" alt="TrueID UI/UX Redesign" class="w-full h-full object-cover opacity-90 hover:scale-105 transition-transform duration-500">
                        <div class="absolute inset-0 bg-gradient-to-t lg:bg-gradient-to-l from-slate-50/50 via-transparent to-transparent"></div>
                    </div>
                    <div class="lg:w-3/5 p-8 flex flex-col justify-between bg-white">
                        <div>
                            <div class="flex flex-wrap items-center justify-between gap-4 mb-4">
                                <div class="flex gap-2">
                                    <span class="bg-indigo-50 text-indigo-600 text-[10px] font-bold px-3 py-1 rounded-full border border-indigo-100 uppercase tracking-wider">UI/UX Redesign</span>
                                    <span class="bg-purple-50 text-purple-600 text-[10px] font-bold px-3 py-1 rounded-full border border-purple-100 uppercase tracking-wider">Figma Prototype</span>
                                </div>
                                <span class="text-xs font-bold text-slate-400 flex items-center gap-1.5">
                                    <i class="fa-regular fa-calendar-check"></i> Nov 2024
                                </span>
                            </div>
                            <h3 class="text-2xl font-bold text-slate-900 mb-3">TrueID App Redesign for Elevated Experience</h3>
                            <p class="text-slate-600 text-sm leading-relaxed mb-6">
                                การปรับปรุง UI/UX บนแอปพลิเคชัน TrueID ผ่านกระบวนการสัมภาษณ์ผู้ใช้ (User Research) วิเคราะห์ Pain Point เพื่อเสนอตัวต้นแบบ (Interactive Figma Prototype) ที่ใช้งานง่ายและเพิ่มความสะดวกยิ่งขึ้น
                            </p>
                        </div>
                        <div class="bg-slate-50 border border-slate-100 p-4 rounded-2xl flex items-start gap-3">
                            <i class="fa-solid fa-circle-check text-brand-500 mt-1"></i>
                            <p class="text-xs text-slate-500 font-medium leading-relaxed">
                                Redesigned client journey and application interfaces based on data-driven persona modeling, generating full-fidelity user flows and Figma components.
                            </p>
                        </div>
                    </div>
                </div>

                <!-- Project 3 -->
                <div class="reveal glass-card rounded-3xl overflow-hidden border border-slate-200 hover:border-brand-300 transition-all duration-300 flex flex-col lg:flex-row glow-blue shadow-sm">
                    <div class="lg:w-2/5 relative h-64 lg:h-auto min-h-[250px] bg-slate-100 overflow-hidden">
                        <!-- AR Museum Mock Image -->
                        <img src="https://images.unsplash.com/photo-1558591710-4b4a1ae0f04d?q=80&w=800&auto=format&fit=crop" alt="AR/VR Interactive Work" class="w-full h-full object-cover opacity-90 hover:scale-105 transition-transform duration-500">
                        <div class="absolute inset-0 bg-gradient-to-t lg:bg-gradient-to-r from-slate-50/50 via-transparent to-transparent"></div>
                    </div>
                    <div class="lg:w-3/5 p-8 flex flex-col justify-between bg-white">
                        <div>
                            <div class="flex flex-wrap items-center justify-between gap-4 mb-4">
                                <div class="flex gap-2">
                                    <span class="bg-rose-50 text-rose-600 text-[10px] font-bold px-3 py-1 rounded-full border border-rose-100 uppercase tracking-wider">Augmented Reality</span>
                                    <span class="bg-amber-50 text-amber-600 text-[10px] font-bold px-3 py-1 rounded-full border border-amber-100 uppercase tracking-wider">Interactive Media</span>
                                </div>
                                <span class="text-xs font-bold text-slate-400 flex items-center gap-1.5">
                                    <i class="fa-regular fa-calendar-check"></i> Jan 2024
                                </span>
                            </div>
                            <h3 class="text-2xl font-bold text-slate-900 mb-3">AR/VR Interactive Learning for Museum</h3>
                            <p class="text-slate-600 text-sm leading-relaxed mb-6">
                                การจัดทำสื่อการเรียนรู้จำลองสายพันธุ์ไดโนเสาร์ในพิพิธภัณฑ์ด้วย AR เทคโนโลยี ผสานกราฟิกสามมิติ คอนเทนต์เสียง เพื่อให้เด็กและผู้เข้าชมโต้ตอบข้อมูลบนหน้าจอได้อย่างสนุกสนาน
                            </p>
                        </div>
                        <div class="bg-slate-50 border border-slate-100 p-4 rounded-2xl flex items-start gap-3">
                            <i class="fa-solid fa-circle-check text-brand-500 mt-1"></i>
                            <p class="text-xs text-slate-500 font-medium leading-relaxed">
                                Formulated high-interaction UX logic templates, enabling mobile-based camera scanning mechanics to unlock virtual models on site.
                            </p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Certificates & Licenses (With Light-themed Previews!) -->
    <section id="certifications" class="py-24 bg-white relative border-t border-slate-100">
        <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
            <div class="text-center mb-16 reveal">
                <span class="text-xs font-bold text-brand-500 uppercase tracking-widest font-mono">Verified Credentials</span>
                <h2 class="text-4xl font-extrabold text-slate-900 tracking-tight mt-2">Certifications & Training</h2>
                <p class="text-slate-500 mt-2">ใบรับรองและประกาศนียบัตรวิชาชีพ (คลิกที่ภาพเพื่อขยายใหญ่ได้)</p>
                <div class="h-1 w-12 bg-gradient-to-r from-brand-500 to-cyan-500 mx-auto mt-4 rounded-full"></div>
            </div>

            <!-- Grid of Beautiful Certs -->
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                <!-- Cert 1 -->
                <div class="reveal glass-card rounded-3xl overflow-hidden border border-slate-200 hover:border-brand-300 transition-all duration-300 flex flex-col glow-blue group shadow-sm bg-white">
                    <div class="relative aspect-[1.414/1] bg-slate-100 overflow-hidden cursor-pointer" onclick="openLightbox('https://images.unsplash.com/photo-1589330694653-ded6df03f754?q=80&w=800&auto=format&fit=crop', 'MSU English Exit Examination (CER B1)')">
                        <img src="https://images.unsplash.com/photo-1589330694653-ded6df03f754?q=80&w=800&auto=format&fit=crop" alt="MSU English Exit Exam Certificate" class="w-full h-full object-cover opacity-90 group-hover:scale-105 transition-transform duration-500">
                        <div class="absolute inset-0 bg-slate-900/10 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center">
                            <span class="bg-brand-600/90 text-white px-4 py-2 rounded-xl text-xs font-bold flex items-center gap-2 shadow-md">
                                <i class="fa-solid fa-expand"></i> View Certificate
                            </span>
                        </div>
                    </div>
                    <div class="p-6 flex-1 flex flex-col justify-between">
                        <div>
                            <div class="text-xs font-bold text-brand-500 uppercase tracking-wider mb-1">Feb 2026</div>
                            <h4 class="text-lg font-bold text-slate-800 group-hover:text-brand-500 transition-colors">MSU English Exit Examination (CEFR B1)</h4>
                            <p class="text-xs text-slate-500 mt-2">ประเมินผ่านเกณฑ์สมรรถนะภาษาอังกฤษสำหรับนิสิตระดับปริญญาตรี มหาวิทยาลัยมหาสารคาม</p>
                        </div>
                        <div class="pt-4 border-t border-slate-100 mt-4 text-xs text-slate-400 flex items-center gap-1.5">
                            <i class="fa-solid fa-university text-brand-500"></i> Issued by Mahasarakham University
                        </div>
                    </div>
                </div>

                <!-- Cert 2 -->
                <div class="reveal glass-card rounded-3xl overflow-hidden border border-slate-200 hover:border-brand-300 transition-all duration-300 flex flex-col glow-blue group shadow-sm bg-white">
                    <div class="relative aspect-[1.414/1] bg-slate-100 overflow-hidden cursor-pointer" onclick="openLightbox('https://images.unsplash.com/photo-1620712943543-bcc4688e7485?q=80&w=800&auto=format&fit=crop', 'Generative AI & ChatGPT for Research')">
                        <img src="https://images.unsplash.com/photo-1620712943543-bcc4688e7485?q=80&w=800&auto=format&fit=crop" alt="Generative AI Certificate" class="w-full h-full object-cover opacity-90 group-hover:scale-105 transition-transform duration-500">
                        <div class="absolute inset-0 bg-slate-900/10 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center">
                            <span class="bg-brand-600/90 text-white px-4 py-2 rounded-xl text-xs font-bold flex items-center gap-2 shadow-md">
                                <i class="fa-solid fa-expand"></i> View Certificate
                            </span>
                        </div>
                    </div>
                    <div class="p-6 flex-1 flex flex-col justify-between">
                        <div>
                            <div class="text-xs font-bold text-violet-500 uppercase tracking-wider mb-1">Dec 2025</div>
                            <h4 class="text-lg font-bold text-slate-800 group-hover:text-brand-500 transition-colors">Generative AI & ChatGPT for Research</h4>
                            <p class="text-xs text-slate-500 mt-2">ผ่านการศึกษาทักษะการสั่งการเอไอสำหรับงานเอกสารและการวิจัยเชิงพาณิชย์และธุรกิจดิจิทัล</p>
                        </div>
                        <div class="pt-4 border-t border-slate-100 mt-4 text-xs text-slate-400 flex items-center gap-1.5">
                            <i class="fa-solid fa-graduation-cap text-violet-500"></i> Issued by Kasetsart University (KUMOOC)
                        </div>
                    </div>
                </div>

                <!-- Cert 3 -->
                <div class="reveal glass-card rounded-3xl overflow-hidden border border-slate-200 hover:border-brand-300 transition-all duration-300 flex flex-col glow-blue group shadow-sm bg-white">
                    <div class="relative aspect-[1.414/1] bg-slate-100 overflow-hidden cursor-pointer" onclick="openLightbox('https://images.unsplash.com/photo-1460925895917-afdab827c52f?q=80&w=800&auto=format&fit=crop', 'Microsoft Power BI Certificate')">
                        <img src="https://images.unsplash.com/photo-1460925895917-afdab827c52f?q=80&w=800&auto=format&fit=crop" alt="Microsoft Power BI Certificate" class="w-full h-full object-cover opacity-90 group-hover:scale-105 transition-transform duration-500">
                        <div class="absolute inset-0 bg-slate-900/10 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center">
                            <span class="bg-brand-600/90 text-white px-4 py-2 rounded-xl text-xs font-bold flex items-center gap-2 shadow-md">
                                <i class="fa-solid fa-expand"></i> View Certificate
                            </span>
                        </div>
                    </div>
                    <div class="p-6 flex-1 flex flex-col justify-between">
                        <div>
                            <div class="text-xs font-bold text-emerald-500 uppercase tracking-wider mb-1">Jul 2025</div>
                            <h4 class="text-lg font-bold text-slate-800 group-hover:text-brand-500 transition-colors">Microsoft Power BI Professional Training</h4>
                            <p class="text-xs text-slate-500 mt-2">การอบรมพัฒนาความสามารถในการจัดทำแดชบอร์ดสรุปผลข้อมูล และจัดหมวดหมู่ฐานข้อมูลธุรกิจ</p>
                        </div>
                        <div class="pt-4 border-t border-slate-100 mt-4 text-xs text-slate-400 flex items-center gap-1.5">
                            <i class="fa-solid fa-circle-check text-emerald-500"></i> Issued by Professional Qualification Institute
                        </div>
                    </div>
                </div>

                <!-- Cert 4 -->
                <div class="reveal glass-card rounded-3xl overflow-hidden border border-slate-200 hover:border-brand-300 transition-all duration-300 flex flex-col glow-blue group shadow-sm bg-white">
                    <div class="relative aspect-[1.414/1] bg-slate-100 overflow-hidden cursor-pointer" onclick="openLightbox('https://images.unsplash.com/photo-1516321318423-f06f85e504b3?q=80&w=800&auto=format&fit=crop', 'IC3 Digital Literacy Certification')">
                        <img src="https://images.unsplash.com/photo-1516321318423-f06f85e504b3?q=80&w=800&auto=format&fit=crop" alt="IC3 Digital Literacy Certificate" class="w-full h-full object-cover opacity-90 group-hover:scale-105 transition-transform duration-500">
                        <div class="absolute inset-0 bg-slate-900/10 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center">
                            <span class="bg-brand-600/90 text-white px-4 py-2 rounded-xl text-xs font-bold flex items-center gap-2 shadow-md">
                                <i class="fa-solid fa-expand"></i> View Certificate
                            </span>
                        </div>
                    </div>
                    <div class="p-6 flex-1 flex flex-col justify-between">
                        <div>
                            <div class="text-xs font-bold text-cyan-500 uppercase tracking-wider mb-1">Feb 2025</div>
                            <h4 class="text-lg font-bold text-slate-800 group-hover:text-brand-500 transition-colors">IC3 Digital Literacy (GS6 Level 1)</h4>
                            <p class="text-xs text-slate-500 mt-2">ใบอนุญาตมาตรฐานสากลด้านความรู้ความเข้าใจเกี่ยวกับการประยุกต์ใช้เทคโนโลยีดิจิทัล</p>
                        </div>
                        <div class="pt-4 border-t border-slate-100 mt-4 text-xs text-slate-400 flex items-center gap-1.5">
                            <i class="fa-solid fa-shield-halved text-cyan-500"></i> Certiport (Pearson VUE)
                        </div>
                    </div>
                </div>

                <!-- Cert 5 -->
                <div class="reveal glass-card rounded-3xl overflow-hidden border border-slate-200 hover:border-brand-300 transition-all duration-300 flex flex-col glow-blue group md:col-span-2 lg:col-span-1 shadow-sm bg-white">
                    <div class="relative aspect-[1.414/1] bg-slate-100 overflow-hidden cursor-pointer" onclick="openLightbox('https://images.unsplash.com/photo-1557200134-90327ee9fafa?q=80&w=800&auto=format&fit=crop', 'LINE OA Business Growth Strategy')">
                        <img src="https://images.unsplash.com/photo-1557200134-90327ee9fafa?q=80&w=800&auto=format&fit=crop" alt="LINE OA Strategy Training" class="w-full h-full object-cover opacity-90 group-hover:scale-105 transition-transform duration-500">
                        <div class="absolute inset-0 bg-slate-900/10 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center">
                            <span class="bg-brand-600/90 text-white px-4 py-2 rounded-xl text-xs font-bold flex items-center gap-2 shadow-lg">
                                <i class="fa-solid fa-expand"></i> View Certificate
                            </span>
                        </div>
                    </div>
                    <div class="p-6 flex-1 flex flex-col justify-between">
                        <div>
                            <div class="text-xs font-bold text-pink-500 uppercase tracking-wider mb-1">Dec 2024</div>
                            <h4 class="text-lg font-bold text-slate-800 group-hover:text-brand-500 transition-colors">LINE Official Account (LINE OA) Strategy</h4>
                            <p class="text-xs text-slate-500 mt-2">ทักษะและการวางกลยุทธ์ช่องทางแชทบรอดแคสต์ เพื่อขยายสัดส่วนผู้ติดตามและบริการลูกค้า</p>
                        </div>
                        <div class="pt-4 border-t border-slate-100 mt-4 text-xs text-slate-400 flex items-center gap-1.5">
                            <i class="fa-solid fa-shop text-pink-500"></i> Issued by MBS, MSU
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Activities & Community Section -->
    <section id="activities" class="py-24 bg-slate-50 relative border-t border-slate-100">
        <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
            <div class="text-center mb-16 reveal">
                <span class="text-xs font-bold text-brand-500 uppercase tracking-widest font-mono">Student Leadership</span>
                <h2 class="text-4xl font-extrabold text-slate-900 tracking-tight mt-2">Activities</h2>
                <p class="text-slate-500 mt-2">กิจกรรมและงานช่วยเหลือคณะเพื่อสาธารณประโยชน์ที่ได้เข้าร่วม</p>
                <div class="h-1 w-12 bg-gradient-to-r from-brand-500 to-cyan-500 mx-auto mt-4 rounded-full"></div>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 gap-10">
                <!-- Activity 1 -->
                <div class="reveal glass-card rounded-3xl overflow-hidden border border-slate-200 hover:border-brand-300 transition-all duration-300 glow-blue group bg-white shadow-sm">
                    <div class="relative h-64 overflow-hidden">
                        <!-- Activity Photo Slot -->
                        <img src="https://images.unsplash.com/photo-1540575467063-178a50c2df87?q=80&w=800&auto=format&fit=crop" alt="MSU Open House Activity" class="w-full h-full object-cover opacity-90 group-hover:scale-105 transition-transform duration-700">
                        <div class="absolute inset-0 bg-gradient-to-t from-white via-transparent to-transparent"></div>
                        <div class="absolute bottom-4 left-6 right-6">
                            <span class="bg-brand-500 text-white text-[10px] font-bold px-3 py-1 rounded-full uppercase tracking-wider">Booth Staff & Guide</span>
                        </div>
                    </div>
                    <div class="p-8">
                        <div class="flex items-center justify-between text-xs font-bold text-slate-400 mb-2">
                            <span>MAHASARAKHAM UNIVERSITY</span>
                            <span>DEC 2024</span>
                        </div>
                        <h3 class="text-xl font-bold text-slate-900 mb-3 group-hover:text-brand-500 transition-colors">MSU Open House 2024</h3>
                        <p class="text-slate-600 text-sm leading-relaxed mb-4">
                            ร่วมทำกิจกรรมในบูธนิทรรศการหลักสูตรวิชาดิจิทัลธุรกิจ ช่วยเหลือ แนะนำความรู้ และชี้แจงแนวทางการศึกษาต่อให้กับกลุ่มน้องๆ นักเรียนมัธยมศึกษาที่สนใจเข้าเรียนในคณะการบัญชีและการจัดการ
                        </p>
                        <div class="pt-4 border-t border-slate-100 text-xs text-slate-400 flex items-center gap-2">
                            <i class="fa-solid fa-users text-brand-500"></i> Supported Open House Booth activities & guidance.
                        </div>
                    </div>
                </div>

                <!-- Activity 2 -->
                <div class="reveal glass-card rounded-3xl overflow-hidden border border-slate-200 hover:border-brand-300 transition-all duration-300 glow-blue group bg-white shadow-sm">
                    <div class="relative h-64 overflow-hidden">
                        <!-- Activity Photo Slot 2 -->
                        <img src="https://images.unsplash.com/photo-1511578314322-379afb476865?q=80&w=800&auto=format&fit=crop" alt="MBS Freshy Day Staff" class="w-full h-full object-cover opacity-90 group-hover:scale-105 transition-transform duration-700">
                        <div class="absolute inset-0 bg-gradient-to-t from-white via-transparent to-transparent"></div>
                        <div class="absolute bottom-4 left-6 right-6">
                            <span class="bg-pink-500 text-white text-[10px] font-bold px-3 py-1 rounded-full uppercase tracking-wider">Event Organizer Staff</span>
                        </div>
                    </div>
                    <div class="p-8">
                        <div class="flex items-center justify-between text-xs font-bold text-slate-400 mb-2">
                            <span>MBS FACULTY EVENTS</span>
                            <span>JUL 2025</span>
                        </div>
                        <h3 class="text-xl font-bold text-slate-900 mb-3 group-hover:text-brand-500 transition-colors">MBS Fresh Day & Fresh Night</h3>
                        <p class="text-slate-600 text-sm leading-relaxed mb-4">
                            ปฏิบัติงานต้อนรับ ณ จุดลงทะเบียน ประสานงานดูแลความสงบเรียบร้อยและความสะดวกให้กับนักศึกษาใหม่ในคณะการบัญชีและการจัดการ ตลอดกระบวนการดำเนินกิจกรรมสันทนาการ
                        </p>
                        <div class="pt-4 border-t border-slate-100 text-xs text-slate-400 flex items-center gap-2">
                            <i class="fa-solid fa-handshake text-pink-500"></i> Assisted with venue coordination & registration flow.
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Premium Footer / Contact Section -->
    <footer id="contact" class="bg-slate-900 text-slate-300 py-20 border-t border-slate-100 relative">
        <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
            <div class="grid grid-cols-1 md:grid-cols-2 gap-16 pb-16 border-b border-slate-800 reveal">
                <div class="space-y-6">
                    <h2 class="text-3xl font-extrabold text-white tracking-tight">Contact Information</h2>
                    <p class="text-slate-400 leading-relaxed max-w-sm">
                        หากท่านผู้ประกอบการหรือผู้คัดเลือกบุคลากร (HR) ต้องการข้อมูลเพิ่มเติมเกี่ยวกับการเริ่มฝึกงาน สามารถกรอกหรือติดต่อผ่านรายละเอียดเหล่านี้ได้ทันทีค่ะ
                    </p>
                    <div class="space-y-4">
                        <div class="flex items-center gap-4">
                            <div class="w-12 h-12 rounded-xl bg-white/5 flex items-center justify-center text-brand-400 border border-white/10">
                                <i class="fa-solid fa-map-location-dot"></i>
                            </div>
                            <div>
                                <div class="text-xs text-slate-500 font-bold uppercase">Location</div>
                                <div class="text-sm text-slate-300">Mahasarakham University, Thailand</div>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Instant Copy Cards -->
                <div class="bg-slate-950 p-8 rounded-3xl border border-slate-800 space-y-6">
                    <h3 class="text-lg font-bold text-white flex items-center gap-2">
                        <i class="fa-solid fa-bolt text-brand-400"></i> Direct Connection
                    </h3>
                    
                    <!-- Copy Email Action -->
                    <div class="bg-slate-900 p-4 rounded-2xl flex items-center justify-between border border-slate-800 group hover:border-brand-500 transition-colors">
                        <div class="flex items-center gap-3">
                            <i class="fa-regular fa-envelope text-brand-400 text-xl"></i>
                            <span class="text-sm font-semibold break-all text-slate-200" id="emailVal">nonglukkluanthaisong@gmail.com</span>
                        </div>
                        <button onclick="copyToClipboard('emailVal')" class="text-brand-400 hover:text-brand-300 p-2.5 bg-white/5 hover:bg-white/10 rounded-xl transition-all" title="Copy Email">
                            <i class="fa-regular fa-copy"></i>
                        </button>
                    </div>

                    <!-- Copy Phone Action -->
                    <div class="bg-slate-900 p-4 rounded-2xl flex items-center justify-between border border-slate-800 group hover:border-brand-500 transition-colors">
                        <div class="flex items-center gap-3">
                            <i class="fa-solid fa-phone text-brand-400 text-xl"></i>
                            <span class="text-sm font-semibold text-slate-200" id="phoneVal">(+66)94-570-5055</span>
                        </div>
                        <button onclick="copyToClipboard('phoneVal')" class="text-brand-400 hover:text-brand-300 p-2.5 bg-white/5 hover:bg-white/10 rounded-xl transition-all" title="Copy Phone Number">
                            <i class="fa-regular fa-copy"></i>
                        </button>
                    </div>
                </div>
            </div>

            <!-- Copyright and Image References -->
            <div class="pt-8 flex flex-col sm:flex-row items-center justify-between text-xs text-slate-500 gap-4 reveal">
                <p>&copy; 2026-2027 Nongluk Kluanthaisong. All Rights Reserved.</p>
                <div class="flex gap-4">
                    <span class="hover:underline cursor-pointer text-brand-400" onclick="openCVModal()">Source: Nongluk.cv.jpg</span>
                    <span>•</span>
                    <span>Digital Business and Information Systems</span>
                </div>
            </div>
        </div>
    </footer>

    <!-- Premium Image Lightbox Viewer (For Certificates & Works) -->
    <div id="lightboxModal" class="fixed inset-0 z-50 hidden bg-slate-900/95 backdrop-blur-md flex items-center justify-center p-4">
        <div class="relative max-w-4xl w-full flex flex-col max-h-[90vh]">
            <!-- Close Button -->
            <button onclick="closeLightbox()" class="absolute -top-14 right-0 text-slate-300 hover:text-white text-3xl w-10 h-10 flex items-center justify-center bg-white/5 hover:bg-white/10 rounded-full transition-all">
                &times;
            </button>
            <div class="bg-white rounded-3xl p-4 border border-slate-200 overflow-hidden flex flex-col justify-center items-center">
                <img id="lightboxImage" src="" alt="Certificate View" class="max-w-full max-h-[70vh] rounded-2xl object-contain shadow-2xl">
                <p id="lightboxCaption" class="text-sm text-slate-700 mt-4 font-bold text-center"></p>
            </div>
        </div>
    </div>

    <!-- Original CV Resume Modal -->
    <div id="cvModal" class="fixed inset-0 z-50 hidden bg-slate-900/95 backdrop-blur-md flex items-center justify-center p-4">
        <div class="bg-white rounded-3xl max-w-2xl w-full p-6 relative flex flex-col max-h-[90vh] border border-slate-200">
            <button onclick="closeCVModal()" class="absolute top-4 right-4 text-slate-500 hover:text-slate-800 text-2xl w-10 h-10 flex items-center justify-center bg-slate-100 rounded-full transition-all">
                &times;
            </button>
            <h3 class="text-xl font-bold text-slate-900 mb-4">Original CV Document</h3>
            <div class="flex-1 overflow-y-auto rounded-2xl border border-slate-200 bg-slate-50">
                <img src="Nongluk.cv.jpg" alt="Nongluk Kluanthaisong Original CV File" class="w-full h-auto" onerror="this.onerror=null; this.src='https://images.unsplash.com/photo-1586281380349-632531db7ed4?q=80&w=800&auto=format&fit=crop';">
            </div>
            <div class="mt-5 pt-4 border-t border-slate-200 flex justify-between items-center text-xs text-slate-500">
                <span>Ref: Nongluk.cv.jpg</span>
                <button onclick="closeCVModal()" class="bg-brand-600 hover:bg-brand-500 text-white px-5 py-2.5 rounded-xl font-bold transition-all">Close Viewer</button>
            </div>
        </div>
    </div>

    <!-- Alert Toast Notification for Actions -->
    <div id="toast" class="fixed bottom-6 right-6 bg-brand-600 text-white px-6 py-4 rounded-2xl shadow-2xl transition-all duration-300 transform translate-y-20 opacity-0 z-50 flex items-center gap-3 font-semibold text-sm">
        <i class="fa-solid fa-circle-check text-lg"></i>
        <span id="toastMessage">Copied successfully!</span>
    </div>

    <!-- Script Operations for Custom Scroll Reveal & Copy Functionality -->
    <script>
        // Intersection Observer Scroll Animations Engine
        document.addEventListener("DOMContentLoaded", function() {
            const reveals = document.querySelectorAll(".reveal");

            const observerOptions = {
                root: null,
                rootMargin: "0px",
                threshold: 0.12 // Trigger reveal when 12% of the element is in view
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

        // Smart Header Navigation: Hide on Scroll Up, Show on Scroll Down
        let lastScrollTop = 0;
        const mainHeader = document.getElementById('mainHeader');
        
        window.addEventListener('scroll', function() {
            let scrollTop = window.pageYOffset || document.documentElement.scrollTop;
            
            if (scrollTop > lastScrollTop) {
                // Scroll DOWN -> SHOW the header
                mainHeader.classList.remove('-translate-y-full');
                mainHeader.classList.add('shadow-md');
            } else {
                // Scroll UP -> HIDE the header
                mainHeader.classList.add('-translate-y-full');
            }
            
            // Keep header visible at the absolute top of the page
            if (scrollTop <= 15) {
                mainHeader.classList.remove('-translate-y-full', 'shadow-md');
            }
            
            lastScrollTop = scrollTop <= 0 ? 0 : scrollTop; // For Mobile or negative scrolling
        });

        // Scrollspy Active Navigation Indicator
        const sections = document.querySelectorAll('section[id]');
        const navItems = document.querySelectorAll('.nav-item');

        window.addEventListener('scroll', function() {
            let scrollPosition = document.documentElement.scrollTop || document.body.scrollTop;
            let currentSectionId = 'home';

            sections.forEach(section => {
                const sectionTop = section.offsetTop - 120; // safe area threshold
                const sectionHeight = section.offsetHeight;

                if (scrollPosition >= sectionTop && scrollPosition < (sectionTop + sectionHeight)) {
                    currentSectionId = section.getAttribute('id');
                }
            });

            navItems.forEach(item => {
                const targetId = item.getAttribute('href').substring(1);
                
                if (targetId === currentSectionId) {
                    item.classList.remove('text-slate-600', 'border-transparent');
                    item.classList.add('text-brand-600', 'border-brand-600');
                } else {
                    item.classList.remove('text-brand-600', 'border-brand-600');
                    item.classList.add('text-slate-600', 'border-transparent');
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
            
            // Modern Clipboard API
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

        // Fallback for secure environment restrictions
        function fallbackCopyToClipboard(text) {
            const textArea = document.createElement("textarea");
            textArea.value = text;
            textArea.style.position = "fixed";  // Avoid scrolling to bottom
            document.body.appendChild(textArea);
            textArea.focus();
            textArea.select();
            try {
                document.execCommand('copy');
                showToast("คัดลอกข้อมูลเรียบร้อยแล้ว!");
            } catch (err) {
                console.error('Fallback failed', err);
            }
            document.body.removeChild(textArea);
        }

        // Custom Premium Toast Trigger
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
