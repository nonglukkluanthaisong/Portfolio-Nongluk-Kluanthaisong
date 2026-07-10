<!DOCTYPE html>
<!-- กำหนดเอกสารเป็นภาษาไทย และเปิดใช้งานระบบเลื่อนหน้าจออย่างนุ่มนวล (Scroll Smooth) -->
<html lang="th" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <!-- ชื่อแท็บของหน้าเว็บไซต์ -->
    <title>Nongluk Kluanthaisong - Premium Portfolio</title>
    
    <!-- นำเข้าเทคโนโลยี Tailwind CSS สำหรับการจัดแต่งหน้าตาอย่างรวดเร็วผ่านคลาส (CDN) -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- นำเข้าฟอนต์ Google Fonts: Inter (ภาษาอังกฤษพรีเมียม) และ Sarabun (ภาษาไทยทางการและอ่านง่าย) -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&family=Sarabun:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    
    <!-- นำเข้าไอคอนสวยๆ จากไลบรารี FontAwesome เช่น ไอคอนหมวกปริญญา, โทรศัพท์, อีเมล -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <!-- การตั้งค่าชุดสีและฟอนต์เพิ่มเติมของ Tailwind CSS เพื่อสร้างโทนสีแบรนด์ส่วนตัว -->
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    // กำหนดฟอนต์หลักให้ใช้ Inter และตามด้วย Sarabun
                    fontFamily: {
                        sans: ['Inter', 'Sarabun', 'sans-serif'],
                    },
                    // กำหนดชุดสีแบรนด์สีน้ำเงินไล่เฉด (Brand Blue) เพื่อความพรีเมียมและน่าเชื่อถือ
                    colors: {
                        brand: {
                            50: '#f0f7ff',   // ฟ้าอ่อนมากๆ สำหรับพื้นหลังกล่องข้อความ
                            100: '#e0effe',  // ฟ้าพาสเทล
                            300: '#7dd3fc',  // ฟ้าสว่าง
                            500: '#0088ff',  // ฟ้าไซอันเรืองแสง (Vibrant Cyan Blue)
                            600: '#0066cc',  // น้ำเงินหลัก (Premium Royal Blue)
                            700: '#004fa3',  // น้ำเงินเข้มสำหรับสถานะ Hover หรือปุ่มกด
                            800: '#0f172a',  // เทาเข้มเกือบดำสำหรับตัวอักษรหลัก
                            900: '#020617',  // ดำสนิทสำหรับพื้นหลังลึกๆ
                        }
                    }
                }
            }
        }
    </script>

    <!-- สไตล์ตกแต่งเพิ่มเติมเฉพาะจุด (Custom CSS) -->
    <style>
        /* สไตล์การ์ดกระจกโปร่งแสงหรูหรา (Glassmorphic Cards) สำหรับธีมขาว */
        .glass-card {
            background: rgba(255, 255, 255, 0.78); /* พื้นสีขาวโปร่งแสง 78% */
            backdrop-filter: blur(12px);          /* เอฟเฟกต์เบลอหลังกระจก 12px */
            -webkit-backdrop-filter: blur(12px);   /* รองรับเบราว์เซอร์ Safari */
            border: 1px solid rgba(0, 102, 204, 0.08); /* เส้นขอบบางๆ สีน้ำเงินจาง */
            transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1); /* แอนิเมชันตอนตอบสนองการเคลื่นไหว */
        }
        /* เอฟเฟกต์เมื่อผู้ใช้เอาเมาส์ไปชี้ที่ตัวการ์ด (Hover) */
        .glass-card:hover {
            border-color: rgba(0, 102, 204, 0.25); /* เพิ่มความเข้มของเส้นขอบสีน้ำเงิน */
            box-shadow: 0 15px 30px rgba(0, 102, 204, 0.06); /* เพิ่มเงามิติด้านล่าง */
            transform: translateY(-4px); /* ยกการ์ดลอยขึ้นด้านบน 4px */
        }

        /* เอฟเฟกต์ Scroll Reveal (ค่อยๆ โผล่และลอยขึ้นเมื่อเลื่อนหน้าจอมาเจอ พร้อมเอฟเฟกต์เบลอเพื่อความสมูท) */
        .reveal {
            opacity: 0; /* ตอนเริ่มต้นจะซ่อนไว้ (โปร่งใส 100%) */
            transform: translateY(25px) scale(0.97); /* ย่อตัวลงเล็กน้อยและดันลงล่าง 25px */
            filter: blur(4px); /* เบลอไว้ล่วงหน้า */
            transition: all 0.7s cubic-bezier(0.16, 1, 0.3, 1); /* เวลาในการแสดงผล 0.7 วินาที */
        }
        /* คลาสที่จะถูกเติมอัตโนมัติด้วย JavaScript เมื่อเลื่อนมาเจอจุดแสดงผล */
        .reveal.active {
            opacity: 1; /* ปรากฏตัวชัดเจน */
            transform: translateY(0) scale(1); /* กลับสู่ตำแหน่งและขนาดปกติ */
            filter: blur(0); /* ยกเลิกเอฟเฟกต์เบลอ */
        }

        /* แอนิเมชันข้อความส่องประกายวิ่งผ่าน (Shimmer Text Effect) ตรงชื่อ Nongluk */
        @keyframes textShimmer {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }
        .shimmer-text {
            /* กำหนดแถบไล่สีหลักที่จะให้วิ่งผ่านตัวอักษร */
            background: linear-gradient(to right, #0066cc 20%, #0088ff 40%, #06b6d4 60%, #0088ff 80%, #0066cc 100%);
            background-size: 200% auto;
            color: transparent; /* ซ่อนสีตัวอักษรหลัก */
            -webkit-background-clip: text; /* แสดงแถบสีเฉพาะบนตัวอักษร */
            background-clip: text;
            animation: textShimmer 4s linear infinite; /* เล่นแอนิเมชันวนลูปเรื่อยๆ */
        }

        /* แอนิเมชันดุ๊กดิ๊กขยับตัวหนังสือได้ของหน้าแรกแบบนุ่มนวล (Subtle Bouncy/Wiggle Character) */
        @keyframes wiggle-gentle {
            0%, 100% { transform: translateY(0) rotate(-1deg); }
            50% { transform: translateY(-6px) rotate(1deg); }
        }
        .animate-wiggle-subtle {
            animation: wiggle-gentle 4.5s ease-in-out infinite; /* ดุ๊กดิ๊กเบาๆ ทุกๆ 4.5 วินาที */
        }

        /* แอนิเมชันลูกบอลไฟเรืองแสงเคลื่อนไหวช้าๆ อยู่พื้นหลัง (Ambient Floating Glow Orbs) */
        @keyframes float-slow {
            0% { transform: translate(0px, 0px) scale(1); }
            33% { transform: translate(25px, -25px) scale(1.05); }
            66% { transform: translate(-15px, 15px) scale(0.95); }
            100% { transform: translate(0px, 0px) scale(1); }
        }
        .glow-orb {
            position: absolute;
            border-radius: 50%;
            filter: blur(100px); /* สั่งให้เบลอแสงฟุ้งกระจายออกไป 100px */
            opacity: 0.12;       /* ตั้งค่าความโปร่งแสงให้อ่อนมากๆ เพื่อไม่ให้รบกวนการอ่าน */
            z-index: 0;          /* ให้อยู่หลังสุด */
            pointer-events: none; /* ห้ามบล็อกปุ่มหรือการคลิกบนหน้าจอ */
            animation: float-slow 15s infinite ease-in-out; /* เล่นแอนิเมชันลอยไปมาลื่นๆ 15 วินาที */
        }

        /* ซ่อนแถบเลื่อนแนวตั้ง/แนวนอนเริ่มต้นของระบบเบราว์เซอร์ */
        .scrollbar-hide::-webkit-scrollbar {
            display: none;
        }
        .scrollbar-hide {
            -ms-overflow-style: none;  /* รองรับ IE และ Edge */
            scrollbar-width: none;  /* รองรับ Firefox */
        }

        /* กำหนดดีไซน์แถบเลื่อนความกว้างความสวยงาม (Custom Scrollbar) */
        ::-webkit-scrollbar {
            width: 8px;  /* ความกว้างแถบเลื่อนแนวตั้ง */
            height: 6px; /* ความสูงแถบเลื่อนแนวนอน */
        }
        ::-webkit-scrollbar-track {
            background: #f1f5f9; /* สีพื้นหลังรางแถบเลื่อน */
        }
        ::-webkit-scrollbar-thumb {
            background: #cbd5e1; /* สีตัวเลื่อนหลัก */
            border-radius: 9999px; /* ทำมุมโค้งมน */
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #0066cc; /* สีตัวเลื่อนเปลี่ยนเป็นสีน้ำเงินหลักเมื่อผู้ใช้ชี้เมาส์ */
        }

        /* กำหนดเวลาในการเปลี่ยนผ่านลักษณะการเคลื่อนไหวของแถบเมนูด้านบน (Header Smooth Transition) */
        header {
            transition: transform 0.4s cubic-bezier(0.16, 1, 0.3, 1), background-color 0.4s ease, border-color 0.4s ease;
        }
    </style>
</head>
<body class="bg-slate-50 text-slate-800 font-sans antialiased selection:bg-brand-500 selection:text-white overflow-x-hidden">

    <!-- [ส่วนประกอบพื้นหลัง]: ลูกบอลแสงออร่าเคลื่อนไหวได้ (Ambient Orbs Backdrop) -->
    <div class="fixed inset-0 overflow-hidden pointer-events-none z-0">
        <!-- ลูกบอลสีฟ้าสว่าง มุมซ้ายบน -->
        <div class="glow-orb bg-brand-500 w-[500px] h-[500px] top-[-10%] left-[-5%]"></div>
        <!-- ลูกบอลสีม่วงครามขยับแบบจังหวะการเต้นของหัวใจ มุมขวาล่าง -->
        <div class="glow-orb bg-indigo-400 w-[400px] h-[400px] bottom-[15%] right-[-5%] animate-pulse" style="animation-duration: 12s;"></div>
        <!-- ลูกบอลสีฟ้าอมเขียวสว่าง กลางหน้าค่อนไปทางซ้าย -->
        <div class="glow-orb bg-cyan-400 w-[380px] h-[380px] top-[35%] left-[25%]"></div>
    </div>

    <!-- [แถบเมนูด้านบน]: แถบเมนูนำทางอัจฉริยะ ซ่อนและแสดงอัตโนมัติ (Smart Navigation Header) -->
    <header id="mainHeader" class="fixed top-0 left-0 right-0 z-40 bg-white/80 backdrop-blur-md border-b border-slate-100 shadow-sm translate-y-0">
        <div class="max-w-5xl mx-auto px-4 sm:px-6 lg:px-8 h-16 flex items-center justify-between">
            <!-- โลโก้แบรนด์ส่วนตัวด้านซ้าย -->
            <a href="#home" class="font-extrabold text-xl tracking-wider text-slate-900">
                NONGLUK<span class="text-brand-600">.K</span>
            </a>
            
            <!-- เมนูลิงก์นำทางตรงกลาง (แสดงเฉพาะบนแท็บเล็ตและเดสก์ท็อปขึ้นไป) -->
            <nav id="navMenu" class="hidden md:flex space-x-6 lg:space-x-8 text-xs font-semibold relative">
                <!-- ลิงก์เมนูแต่ละส่วน พร้อมแท็กสำหรับทำเส้นขีดใต้สีน้ำเงินสว่างขึ้นตามส่วนที่อยู่จริง (Active State) -->
                <a href="#home" class="nav-item py-2 text-brand-600 transition-all duration-300 relative">Home<span class="nav-line absolute bottom-0 left-0 right-0 h-[3px] bg-brand-600 scale-x-100 transition-transform duration-300 origin-left"></span></a>
                <a href="#education" class="nav-item py-2 text-slate-500 hover:text-brand-600 transition-all duration-300 relative">Education<span class="nav-line absolute bottom-0 left-0 right-0 h-[3px] bg-brand-600 scale-x-0 transition-transform duration-300 origin-left"></span></a>
                <a href="#projects" class="nav-item py-2 text-slate-500 hover:text-brand-600 transition-all duration-300 relative">Works & Projects<span class="nav-line absolute bottom-0 left-0 right-0 h-[3px] bg-brand-600 scale-x-0 transition-transform duration-300 origin-left"></span></a>
                <a href="#certifications" class="nav-item py-2 text-slate-500 hover:text-brand-600 transition-all duration-300 relative">Certificates<span class="nav-line absolute bottom-0 left-0 right-0 h-[3px] bg-brand-600 scale-x-0 transition-transform duration-300 origin-left"></span></a>
                <a href="#activities" class="nav-item py-2 text-slate-500 hover:text-brand-600 transition-all duration-300 relative">Activities<span class="nav-line absolute bottom-0 left-0 right-0 h-[3px] bg-brand-600 scale-x-0 transition-transform duration-300 origin-left"></span></a>
            </nav>
            
            <!-- ปุ่มติดต่อฉันด่วนฝั่งขวา -->
            <div>
                <a href="#contact" class="inline-flex items-center justify-center px-4 py-2 rounded-full bg-brand-600 hover:bg-brand-500 text-white text-xs font-semibold transition-all duration-300 shadow-lg shadow-brand-600/10 hover:shadow-brand-500/35 transform hover:-translate-y-0.5">
                    Contact Me
                </a>
            </div>
        </div>
    </header>

    <!-- [หน้า HOME - หน้าแรก]: แนะนำตัว ต้อนรับ ชิดซ้ายพรีเมียม และแสดงรูปภาพโปรไฟล์สะอาดตา (ปรับความกว้างและความยาวให้กระชับ) -->
    <section id="home" class="pt-24 pb-12 md:pt-28 md:pb-16 min-h-[85vh] flex items-center relative z-10">
        <div class="max-w-5xl mx-auto px-4 sm:px-6 lg:px-8 w-full">
            <div class="flex flex-col lg:flex-row items-center gap-10 lg:gap-14">
                
                <!-- ข้อมูลตัวหนังสือต้อนรับ (ฝั่งซ้าย - ชิดซ้ายทั้งหมด) -->
                <div class="flex-1 text-left space-y-5 md:space-y-6 reveal active">
                    <!-- ป้ายสถานะการพร้อมฝึกงานพร้อมไฟกระพริบ -->
                    <span class="inline-flex items-center gap-2 px-3 py-1 rounded-full text-[10px] font-bold bg-brand-5 border border-brand-100 text-brand-600 uppercase tracking-wider shadow-sm">
                        <span class="w-2 h-2 rounded-full bg-brand-500 animate-ping"></span>
                        Available for Internship: 1 Dec 2026 – 31 Mar 2027
                    </span>
                    
                    <!-- ส่วนหัวข้อหลัก: ชื่อเล่นที่มีเอฟเฟกต์ดุ๊กดิ๊ก/ขยับตัวได้ส่องแสงวิ่งผ่าน และสาขาวิชาเรียนหลัก -->
                    <div class="space-y-2">
                        <h1 class="text-4xl sm:text-6xl font-black tracking-tight text-slate-900 leading-tight">
                            Hi, I'm <span class="shimmer-text animate-wiggle-subtle inline-block">Nongluk</span>
                        </h1>
                        <p class="text-lg sm:text-xl font-extrabold text-brand-600 tracking-wide font-mono">
                            Digital Business & Info Systems
                        </p>
                    </div>
                    
                    <!-- ย่อหน้าคำบรรยายเป้าหมายและจุดมุ่งหมายในวิชาชีพ -->
                    <p class="text-sm sm:text-base text-slate-600 max-w-lg leading-relaxed font-light">
                        A fourth-year Digital Business and Information Systems student. Passionate about data analysis, business process analysis, and leveraging digital workflows to optimize modern systems with analytics intelligence.
                    </p>

                    <!-- ปุ่มดำเนินการอย่างรวดเร็ว (ดูโปรเจกต์ และ ปุ่มดูไฟล์ CV เรซูเม่ออริจินัล) -->
                    <div class="flex flex-wrap justify-start gap-3 pt-1">
                        <!-- ปุ่มเลื่อนลงไปดูผลงาน -->
                        <a href="#projects" class="px-5 py-3 rounded-lg bg-slate-900 hover:bg-slate-800 text-white text-xs font-bold transition-all duration-300 shadow-md shadow-slate-900/15 flex items-center gap-2 transform hover:-translate-y-1">
                            View My Work
                            <i class="fa-solid fa-chevron-down text-xs"></i>
                        </a>
                        <!-- ปุ่มกดเพื่อเปิดรูปภาพเรซูเม่ออริจินัล (Nongluk.cv.jpg) ขยายเต็มตา -->
                        <button onclick="openCVModal()" class="px-5 py-3 rounded-lg bg-white hover:bg-slate-50 text-slate-700 border border-slate-200 hover:border-brand-500 text-xs font-bold transition-all duration-300 flex items-center gap-2 transform hover:-translate-y-1 shadow-sm">
                            <i class="fa-solid fa-file-invoice text-brand-600"></i>
                            Refer to Nongluk.cv.jpg
                        </button>
                    </div>

                    <!-- แถวสรุปข้อมูลสถิติ/เกรดเฉลี่ยอย่างรวดเร็ว (Stats Counters) -->
                    <div class="grid grid-cols-3 gap-4 sm:gap-6 pt-5 border-t border-slate-200/80 max-w-sm ml-0">
                        <!-- กล่องเกรดเฉลี่ยสะสมปัจจุบัน -->
                        <div class="space-y-0.5">
                            <h3 class="text-2xl sm:text-3xl font-black text-slate-900 font-mono tracking-tight flex items-baseline gap-0.5">
                                3.68<span class="text-[10px] text-brand-600 font-semibold">/4</span>
                            </h3>
                            <p class="text-[9px] font-bold text-slate-400 uppercase tracking-wider">Current GPAX</p>
                        </div>
                        <!-- จำนวนใบเซอร์ทั้งหมดที่มี -->
                        <div class="space-y-0.5">
                            <h3 class="text-2xl sm:text-3xl font-black text-slate-900 font-mono tracking-tight">
                                5+
                            </h3>
                            <p class="text-[9px] font-bold text-slate-400 uppercase tracking-wider">Credentials</p>
                        </div>
                        <!-- จำนวนผลงานโปรเจกต์เชิงวิชาการหลัก -->
                        <div class="space-y-0.5">
                            <h3 class="text-2xl sm:text-3xl font-black text-slate-900 font-mono tracking-tight">
                                3+
                            </h3>
                            <p class="text-[9px] font-bold text-slate-400 uppercase tracking-wider">Main Projects</p>
                        </div>
                    </div>
                </div>

                <!-- พื้นที่รูปภาพโปรไฟล์สุดหรูหรา (ฝั่งขวา - สะอาดตา กรอบชั้นเดียวกระจกสวยงาม) -->
                <div class="flex-shrink-0 w-full max-w-[280px] sm:max-w-[320px] reveal active lg:mr-4">
                    <div class="relative rounded-[1.5rem] overflow-hidden shadow-xl shadow-slate-200/60 border-2 border-white bg-white group">
                        <!-- กล่องรูปภาพสำหรับควบคุมการซูมขยายเบาๆ เมื่อนำเมาส์มาวางชี้ -->
                        <div class="aspect-[3/4] overflow-hidden">
                            <img src="Nongluk.cv.jpg" alt="Nongluk Kluanthaisong Portrait" class="w-full h-full object-cover transition-transform duration-750 group-hover:scale-105" onerror="this.onerror=null; this.src='https://images.unsplash.com/photo-1573496359142-b8d87734a5a2?q=80&w=600&auto=format&fit=crop';">
                        </div>
                        
                        <!-- ป้ายข้อความลอยเก๋ๆ มุมซ้ายล่างบ่งบอกการพร้อมรับการฝึกงาน -->
                        <div class="absolute bottom-4 left-4 bg-gradient-to-r from-brand-600 to-cyan-500 text-white text-[10px] font-bold px-4 py-2 rounded-lg shadow-md shadow-brand-600/30 flex items-center gap-1.5">
                            <span class="w-1.5 h-1.5 rounded-full bg-white animate-pulse"></span>
                            Open to Internship
                        </div>
                    </div>
                </div>

            </div>
        </div>
    </section>

    <!-- [ส่วนข้อมูลการศึกษา - EDUCATION]: สรุปประวัติ มหาวิทยาลัย, คณะ, สาขา, เกรดเฉลี่ยอย่างเป็นทางการ -->
    <section id="education" class="py-14 relative z-10 border-t border-slate-100 bg-white">
        <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
            <!-- ส่วนหัวข้อบทความย่อยประจำส่วน -->
            <div class="text-center mb-10 reveal">
                <span class="text-xs font-bold text-brand-600 uppercase tracking-widest font-mono">Academic Timeline</span>
                <h2 class="text-4xl sm:text-5xl font-black text-slate-900 mt-2 tracking-tight">Education</h2>
                <div class="h-1.5 w-16 bg-gradient-to-r from-brand-600 to-cyan-500 mx-auto mt-4 rounded-full"></div>
            </div>

            <!-- กล่องข้อมูลการศึกษาแบบกระจกโปร่งแสง (Glassmorphic) -->
            <div class="reveal">
                <div class="glass-card p-5 md:p-6 rounded-2xl relative overflow-hidden group shadow-sm">
                    <!-- ประกายแสงตกแต่งสีฟ้ามุมขวาบนของการ์ด -->
                    <div class="absolute top-0 right-0 w-48 h-48 bg-brand-100/20 rounded-full blur-3xl pointer-events-none"></div>
                    
                    <!-- แถวหัวข้อหลัก: โลโก้จำลองและข้อมูลสถาบันการศึกษา -->
                    <div class="flex flex-col md:flex-row items-start md:items-center justify-between gap-4 pb-4 border-b border-slate-100">
                        <div class="flex items-center gap-4">
                            <!-- ไอคอนรูปหมวกปริญญาโดดเด่นสีน้ำเงิน -->
                            <div class="w-12 h-12 rounded-xl bg-brand-50 border border-brand-100 flex items-center justify-center text-brand-600 flex-shrink-0 text-xl shadow-sm">
                                <i class="fa-solid fa-graduation-cap"></i>
                            </div>
                            <div>
                                <h3 class="text-lg font-black text-slate-900">Mahasarakham University (MSU)</h3>
                                <p class="text-xs text-slate-500 font-semibold">Mahasarakham Business School (MBS)</p>
                            </div>
                        </div>
                        <!-- แท็กกำหนดกรอบระยะเวลาปีการศึกษา -->
                        <div class="bg-brand-50 text-brand-700 px-3 py-1.5 rounded-full text-[11px] font-bold border border-brand-100/50 font-mono">
                            June 2023 – Present (Expected: May 2027)
                        </div>
                    </div>

                    <!-- ตารางแจกแจงรายละเอียด: ชื่อหลักสูตรวุฒิการศึกษา เกรดเฉลี่ยปัจจุบัน และสถานที่ตั้งสถาบัน -->
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-5 pt-5">
                        <div>
                            <h4 class="text-[9px] font-extrabold uppercase tracking-wider text-slate-400">Degree Focus</h4>
                            <p class="text-sm font-bold text-slate-800 mt-1">B.A. in Digital Business and Information Systems</p>
                        </div>
                        <div class="flex flex-col sm:flex-row items-start sm:items-center gap-5">
                            <div>
                                <h4 class="text-[9px] font-extrabold uppercase tracking-wider text-slate-400">Current GPAX</h4>
                                <div class="flex items-baseline gap-1 mt-1">
                                    <span class="text-2xl font-black text-brand-600">3.68</span>
                                    <span class="text-slate-400 text-xs">/ 4.00</span>
                                </div>
                            </div>
                            <div class="sm:border-l sm:border-slate-100 sm:pl-5">
                                <h4 class="text-[9px] font-extrabold uppercase tracking-wider text-slate-400">Location</h4>
                                <p class="text-xs font-semibold text-slate-700 mt-1">Mahasarakham, Thailand</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- [ส่วนผลงานและโครงการพัฒนา - WORKS & PROJECTS]: แสดงการ์ดผลงานโปรเจกต์ 3 ชิ้นพร้อมรายละเอียดกระชับพอดี -->
    <section id="projects" class="py-14 relative z-10 border-t border-slate-100 bg-slate-50">
        <div class="max-w-5xl mx-auto px-4 sm:px-6 lg:px-8">
            <!-- ส่วนหัวข้อบทความย่อยประจำส่วน -->
            <div class="text-center mb-10 reveal">
                <span class="text-xs font-bold text-brand-600 uppercase tracking-widest font-mono">Academic Excellence</span>
                <h2 class="text-4xl sm:text-5xl font-black text-slate-900 mt-2 tracking-tight">Works & Projects</h2>
                <p class="text-slate-500 mt-2 text-xs">ผลงานและโครงการพัฒนาเว็บไซต์/โมเดลวิเคราะห์ข้อมูลที่ผ่านมา</p>
                <div class="h-1.5 w-16 bg-gradient-to-r from-brand-600 to-cyan-500 mx-auto mt-4 rounded-full"></div>
            </div>

            <!-- กริดโครงสร้างสำหรับจัดระเบียบกล่องโครงการ ทั้งหมด 3 กล่องเท่าๆ กัน -->
            <div class="grid grid-cols-1 md:grid-cols-3 gap-5">
                
                <!-- โครงการที่ 1: วิเคราะห์และคาดการณ์กระแสไฟฟ้าระดับชาติ -->
                <div class="reveal glass-card rounded-2xl overflow-hidden flex flex-col group shadow-sm bg-white">
                    <!-- รูปภาพสัญลักษณ์ประจำกล่องโครงการ -->
                    <div class="relative h-36 bg-slate-100 overflow-hidden">
                        <img src="https://images.unsplash.com/photo-1551288049-bebda4e38f71?q=80&w=800&auto=format&fit=crop" alt="Electricity Forecasting Work" class="w-full h-full object-cover opacity-90 group-hover:scale-105 transition-transform duration-500">
                        <div class="absolute inset-0 bg-gradient-to-t from-slate-900/60 to-transparent"></div>
                    </div>
                    <!-- รายละเอียดข้อมูลผลงานย่อย -->
                    <div class="p-4 flex-1 flex flex-col justify-between">
                        <div>
                            <div class="flex items-center justify-between mb-2">
                                <span class="bg-brand-50 text-brand-700 text-[8px] font-bold px-2 py-0.5 rounded-full border border-brand-100">DATA ANALYTICS</span>
                                <span class="text-[8px] text-slate-400 font-mono">Oct 2025</span>
                            </div>
                            <h3 class="text-base font-bold text-slate-800 mb-1 group-hover:text-brand-600 transition-colors">Electricity Thailand</h3>
                            <p class="text-slate-600 text-xs leading-relaxed mb-3">
                                โครงการสร้างแบบจำลองคาดการณ์ปริมาณการใช้ไฟฟ้า โดยเตรียมข้อมูลดิบ (Data Cleaning) และใช้โมเดลวิเคราะห์แนวโน้ม
                            </p>
                        </div>
                        <!-- กล่องแสดงข้อสรุปทักษะย่อยหรือผลลัพธ์การทำงาน -->
                        <div class="bg-slate-50 border border-slate-100 p-2 rounded-xl flex items-start gap-1.5">
                            <i class="fa-solid fa-circle-check text-brand-600 text-xs mt-0.5"></i>
                            <p class="text-[9px] text-slate-500 font-medium">
                                Cleaned datasets, identified energy patterns.
                            </p>
                        </div>
                    </div>
                </div>

                <!-- โครงการที่ 2: ปรับแต่งดีไซน์แอปพลิเคชัน TrueID ของฝ่ายไอที -->
                <div class="reveal glass-card rounded-2xl overflow-hidden flex flex-col group shadow-sm bg-white">
                    <!-- รูปภาพแสดงหน้าต่างออกแบบ UI/UX -->
                    <div class="relative h-36 bg-slate-100 overflow-hidden">
                        <img src="https://images.unsplash.com/photo-1541462608143-67571c6738dd?q=80&w=800&auto=format&fit=crop" alt="TrueID UI/UX Redesign" class="w-full h-full object-cover opacity-90 group-hover:scale-105 transition-transform duration-500">
                        <div class="absolute inset-0 bg-gradient-to-t from-slate-900/60 to-transparent"></div>
                    </div>
                    <!-- ข้อมูลระบุรายละเอียดกิจกรรม -->
                    <div class="p-4 flex-1 flex flex-col justify-between">
                        <div>
                            <div class="flex items-center justify-between mb-2">
                                <span class="bg-brand-50 text-brand-700 text-[8px] font-bold px-2 py-0.5 rounded-full border border-brand-100">UI/UX REDESIGN</span>
                                <span class="text-[8px] text-slate-400 font-mono">Nov 2024</span>
                            </div>
                            <h3 class="text-base font-bold text-slate-800 mb-1 group-hover:text-brand-600 transition-colors">TrueID App Redesign</h3>
                            <p class="text-slate-600 text-xs leading-relaxed mb-3">
                                ปรับปรุง UI/UX บนแอป TrueID ผ่าน User Research และวิเคราะห์พฤทีอบรม เพื่อสร้าง Interactive Prototype บน Figma
                            </p>
                        </div>
                        <div class="bg-slate-50 border border-slate-100 p-2 rounded-xl flex items-start gap-1.5">
                            <i class="fa-solid fa-circle-check text-brand-600 text-xs mt-0.5"></i>
                            <p class="text-[9px] text-slate-500 font-medium">
                                Designed high-fidelity layouts in Figma.
                            </p>
                        </div>
                    </div>
                </div>

                <!-- โครงการที่ 3: สื่อการเรียนรู้เสมือนจริงสามมิติ (AR Virtual Museum) -->
                <div class="reveal glass-card rounded-2xl overflow-hidden flex flex-col group shadow-sm bg-white">
                    <!-- ภาพตัวแทนเทคโนโลยี AR คลีนๆ สวยงาม -->
                    <div class="relative h-36 bg-slate-100 overflow-hidden">
                        <img src="https://images.unsplash.com/photo-1558591710-4b4a1ae0f04d?q=80&w=800&auto=format&fit=crop" alt="AR Interactive Museum" class="w-full h-full object-cover opacity-90 group-hover:scale-105 transition-transform duration-500">
                        <div class="absolute inset-0 bg-gradient-to-t from-slate-900/60 to-transparent"></div>
                    </div>
                    <!-- รายละเอียดเป้าหมายวิทยานิพนธ์/โครงงานย่อย -->
                    <div class="p-4 flex-1 flex flex-col justify-between">
                        <div>
                            <div class="flex items-center justify-between mb-2">
                                <span class="bg-brand-50 text-brand-700 text-[8px] font-bold px-2 py-0.5 rounded-full border border-brand-100">AUGMENTED REALITY</span>
                                <span class="text-[8px] text-slate-400 font-mono">Jan 2024</span>
                            </div>
                            <h3 class="text-base font-bold text-slate-800 mb-1 group-hover:text-brand-600 transition-colors">AR Learning Media</h3>
                            <p class="text-slate-600 text-xs leading-relaxed mb-3">
                                การจัดทำสื่อการเรียนรู้จำลองจำลองด้วย AR เทคโนโลยี ผสานกราฟิกสามมิติเพื่อส่งเสริมการเรียนรู้พิพิธภัณฑ์ยุคใหม่
                            </p>
                        </div>
                        <div class="bg-slate-50 border border-slate-100 p-2 rounded-xl flex items-start gap-1.5">
                            <i class="fa-solid fa-circle-check text-brand-600 text-xs mt-0.5"></i>
                            <p class="text-[9px] text-slate-500 font-medium">
                                Created mockups with 3D model integration.
                            </p>
                        </div>
                    </div>
                </div>
                
            </div>
        </div>
    </section>

    <!-- [ส่วนใบเซอร์และการอบรม - CERTIFICATIONS]: แสดงผลแถวเดียว เลื่อนดูสไลด์ข้างๆ ได้สะดวกรวดเร็ว -->
    <section id="certifications" class="py-14 relative z-10 border-t border-slate-100 bg-white">
        <div class="max-w-5xl mx-auto px-4 sm:px-6 lg:px-8">
            
            <!-- ส่วนการแสดงผลส่วนหัวแถว และกลุ่มปุ่มลูกศรกดเลื่อนสไลด์ซ้าย-ขวาสำหรับเดสก์ท็อป -->
            <div class="flex flex-col sm:flex-row items-start sm:items-end justify-between mb-8 gap-4">
                <div class="reveal">
                    <span class="text-xs font-bold text-brand-600 uppercase tracking-widest font-mono">Verified Credentials</span>
                    <h2 class="text-4xl sm:text-5xl font-black text-slate-900 mt-1 tracking-tight">Certifications & Training</h2>
                    <p class="text-slate-500 mt-2 text-xs">ใบรับรองและประกาศนียบัตรวิชาชีพ (เลื่อนดูด้านข้างได้)</p>
                </div>
                
                <!-- กลุ่มปุ่มลูกศรควบคุมทิศทางสำหรับการสไลด์ด้วยปุ่มคลิก -->
                <div class="flex items-center gap-3 reveal">
                    <button id="slideLeftBtn" class="w-9 h-9 rounded-lg bg-slate-50 hover:bg-brand-50 border border-slate-200 hover:border-brand-500 text-slate-700 hover:text-brand-600 flex items-center justify-center transition-all duration-300 shadow-sm" title="Slide Left">
                        <i class="fa-solid fa-chevron-left text-xs"></i>
                    </button>
                    <button id="slideRightBtn" class="w-9 h-9 rounded-lg bg-slate-50 hover:bg-brand-50 border border-slate-200 hover:border-brand-500 text-slate-700 hover:text-brand-600 flex items-center justify-center transition-all duration-300 shadow-sm" title="Slide Right">
                        <i class="fa-solid fa-chevron-right text-xs"></i>
                    </button>
                </div>
            </div>

            <!-- กล่องคอนเทนเนอร์แสดงผลแถวเดี่ยวสำหรับเก็บการ์ดใบเซอร์ ที่พร้อมเลื่อนสไลด์ (Horizontal Scroll Container) -->
            <div id="certScrollContainer" class="flex gap-4 overflow-x-auto snap-x snap-mandatory scroll-smooth pb-2 scrollbar-hide">
                
                <!-- ใบประกาศนียบัตร 1: การสอบภาษาอังกฤษ มมส -->
                <div class="snap-start shrink-0 w-[270px] sm:w-[300px] glass-card rounded-2xl overflow-hidden flex flex-col group bg-slate-50/50">
                    <div class="relative aspect-[1.414/1] bg-slate-100 overflow-hidden cursor-pointer" onclick="openLightbox('https://images.unsplash.com/photo-1589330694653-ded6df03f754?q=80&w=800&auto=format&fit=crop', 'MSU English Exit Examination (CEFR B1)')">
                        <img src="https://images.unsplash.com/photo-1589330694653-ded6df03f754?q=80&w=800&auto=format&fit=crop" alt="MSU English Exit Exam Certificate" class="w-full h-full object-cover opacity-90 group-hover:scale-102 transition-transform duration-500">
                        <!-- ปุ่มแว่นขยายโผล่ตอนวางเมาส์ชี้เพื่อเตรียมคลิกเปิด Lightbox ขยายดูภาพเต็มใบอย่างชัดเจน -->
                        <div class="absolute inset-0 bg-slate-900/30 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center">
                            <span class="bg-brand-600 text-white px-3 py-1.5 rounded-lg text-xs font-bold flex items-center gap-1.5 shadow-md">
                                <i class="fa-solid fa-expand"></i> View
                            </span>
                        </div>
                    </div>
                    <div class="p-4 flex-1 flex flex-col justify-between">
                        <div>
                            <div class="text-[8px] font-bold text-brand-600 uppercase tracking-wider mb-1 font-mono">Feb 2026</div>
                            <h4 class="text-xs font-bold text-slate-800 group-hover:text-brand-600 transition-colors line-clamp-1">MSU English Exit Examination (CEFR B1)</h4>
                            <p class="text-[10px] text-slate-500 mt-1">ผ่านเกณฑ์สมรรถนะภาษาอังกฤษปริญญาตรี มมส</p>
                        </div>
                        <div class="pt-2.5 border-t border-slate-200 mt-2.5 text-[9px] text-slate-400 flex items-center gap-1 font-mono">
                            <i class="fa-solid fa-university text-brand-600"></i> Mahasarakham University
                        </div>
                    </div>
                </div>

                <!-- ใบประกาศนียบัตร 2: ทักษะความรู้ Generative AI คณะวิทยามก. -->
                <div class="snap-start shrink-0 w-[270px] sm:w-[300px] glass-card rounded-2xl overflow-hidden flex flex-col group bg-slate-50/50">
                    <div class="relative aspect-[1.414/1] bg-slate-100 overflow-hidden cursor-pointer" onclick="openLightbox('https://images.unsplash.com/photo-1620712943543-bcc4688e7485?q=80&w=800&auto=format&fit=crop', 'Generative AI & ChatGPT for Research')">
                        <img src="https://images.unsplash.com/photo-1620712943543-bcc4688e7485?q=80&w=800&auto=format&fit=crop" alt="Generative AI Certificate" class="w-full h-full object-cover opacity-90 group-hover:scale-102 transition-transform duration-500">
                        <div class="absolute inset-0 bg-slate-900/30 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center">
                            <span class="bg-brand-600 text-white px-3 py-1.5 rounded-lg text-xs font-bold flex items-center gap-1.5 shadow-md">
                                <i class="fa-solid fa-expand"></i> View
                            </span>
                        </div>
                    </div>
                    <div class="p-4 flex-1 flex flex-col justify-between">
                        <div>
                            <div class="text-[8px] font-bold text-brand-600 uppercase tracking-wider mb-1 font-mono">Dec 2025</div>
                            <h4 class="text-xs font-bold text-slate-800 group-hover:text-brand-600 transition-colors line-clamp-1">Generative AI for Research</h4>
                            <p class="text-[10px] text-slate-500 mt-1">ผ่านการศึกษาทักษะการใช้เอไอวิเคราะห์ความรู้ธุรกิจ</p>
                        </div>
                        <div class="pt-2.5 border-t border-slate-200 mt-2.5 text-[9px] text-slate-400 flex items-center gap-1 font-mono">
                            <i class="fa-solid fa-graduation-cap text-brand-600"></i> Kasetsart University
                        </div>
                    </div>
                </div>

                <!-- ใบประกาศนียบัตร 3: ทักษะวิเคราะห์ข้อมูล Power BI -->
                <div class="snap-start shrink-0 w-[270px] sm:w-[300px] glass-card rounded-2xl overflow-hidden flex flex-col group bg-slate-50/50">
                    <div class="relative aspect-[1.414/1] bg-slate-100 overflow-hidden cursor-pointer" onclick="openLightbox('https://images.unsplash.com/photo-1460925895917-afdab827c52f?q=80&w=800&auto=format&fit=crop', 'Microsoft Power BI Certificate')">
                        <img src="https://images.unsplash.com/photo-1460925895917-afdab827c52f?q=80&w=800&auto=format&fit=crop" alt="Microsoft Power BI Certificate" class="w-full h-full object-cover opacity-90 group-hover:scale-102 transition-transform duration-500">
                        <div class="absolute inset-0 bg-slate-900/30 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center">
                            <span class="bg-brand-600 text-white px-3 py-1.5 rounded-lg text-xs font-bold flex items-center gap-1.5 shadow-md">
                                <i class="fa-solid fa-expand"></i> View
                            </span>
                        </div>
                    </div>
                    <div class="p-4 flex-1 flex flex-col justify-between">
                        <div>
                            <div class="text-[8px] font-bold text-brand-600 uppercase tracking-wider mb-1 font-mono">Jul 2025</div>
                            <h4 class="text-xs font-bold text-slate-800 group-hover:text-brand-600 transition-colors line-clamp-1">Microsoft Power BI Professional</h4>
                            <p class="text-[10px] text-slate-500 mt-1">ความสามารถในการจัดทำแดชบอร์ดสรุปฐานข้อมูลธุรกิจ</p>
                        </div>
                        <div class="pt-2.5 border-t border-slate-200 mt-2.5 text-[9px] text-slate-400 flex items-center gap-1 font-mono">
                            <i class="fa-solid fa-circle-check text-brand-600"></i> Qualification Inst
                        </div>
                    </div>
                </div>

                <!-- ใบประกาศนียบัตร 4: ใบเซอร์มาตรฐานดิจิทัลสากล IC3 Digital Literacy -->
                <div class="snap-start shrink-0 w-[270px] sm:w-[300px] glass-card rounded-2xl overflow-hidden flex flex-col group bg-slate-50/50">
                    <div class="relative aspect-[1.414/1] bg-slate-100 overflow-hidden cursor-pointer" onclick="openLightbox('https://images.unsplash.com/photo-1516321318423-f06f85e504b3?q=80&w=800&auto=format&fit=crop', 'IC3 Digital Literacy Certification')">
                        <img src="https://images.unsplash.com/photo-1516321318423-f06f85e504b3?q=80&w=800&auto=format&fit=crop" alt="IC3 Digital Literacy Certificate" class="w-full h-full object-cover opacity-90 group-hover:scale-102 transition-transform duration-500">
                        <div class="absolute inset-0 bg-slate-900/30 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center">
                            <span class="bg-brand-600 text-white px-3 py-1.5 rounded-lg text-xs font-bold flex items-center gap-1.5 shadow-md">
                                <i class="fa-solid fa-expand"></i> View
                            </span>
                        </div>
                    </div>
                    <div class="p-4 flex-1 flex flex-col justify-between">
                        <div>
                            <div class="text-[8px] font-bold text-brand-600 uppercase tracking-wider mb-1 font-mono">Feb 2025</div>
                            <h4 class="text-xs font-bold text-slate-800 group-hover:text-brand-600 transition-colors line-clamp-1">IC3 Digital Literacy (GS6 Level 1)</h4>
                            <p class="text-[10px] text-slate-500 mt-1">มาตรฐานสากลด้านความเข้าใจเครื่องมือเทคโนโลยีดิจิทัล</p>
                        </div>
                        <div class="pt-2.5 border-t border-slate-200 mt-2.5 text-[9px] text-slate-400 flex items-center gap-1 font-mono">
                            <i class="fa-solid fa-shield-halved text-brand-600"></i> Certiport
                        </div>
                    </div>
                </div>

                <!-- ใบประกาศนียบัตร 5: กลยุทธ์การเติบโตธุรกิจด้วย LINE Official Account -->
                <div class="snap-start shrink-0 w-[270px] sm:w-[300px] glass-card rounded-2xl overflow-hidden flex flex-col group bg-slate-50/50">
                    <div class="relative aspect-[1.414/1] bg-slate-100 overflow-hidden cursor-pointer" onclick="openLightbox('https://images.unsplash.com/photo-1557200134-90327ee9fafa?q=80&w=800&auto=format&fit=crop', 'LINE OA Business Growth Strategy')">
                        <img src="https://images.unsplash.com/photo-1557200134-90327ee9fafa?q=80&w=800&auto=format&fit=crop" alt="LINE OA Strategy Training" class="w-full h-full object-cover opacity-90 group-hover:scale-102 transition-transform duration-500">
                        <div class="absolute inset-0 bg-slate-900/30 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center">
                            <span class="bg-brand-600 text-white px-3 py-1.5 rounded-lg text-xs font-bold flex items-center gap-1.5 shadow-lg">
                                <i class="fa-solid fa-expand"></i> View
                            </span>
                        </div>
                    </div>
                    <div class="p-4 flex-1 flex flex-col justify-between">
                        <div>
                            <div class="text-[8px] font-bold text-brand-600 uppercase tracking-wider mb-1 font-mono">Dec 2024</div>
                            <h4 class="text-xs font-bold text-slate-800 group-hover:text-brand-600 transition-colors line-clamp-1">LINE OA Strategy</h4>
                            <p class="text-[10px] text-slate-500 mt-1">ทักษะและการวางกลยุทธ์ช่องทางแชทเพื่อบริการลูกค้า</p>
                        </div>
                        <div class="pt-2.5 border-t border-slate-200 mt-2.5 text-[9px] text-slate-400 flex items-center gap-1 font-mono">
                            <i class="fa-solid fa-shop text-brand-600"></i> Issued by MBS
                        </div>
                    </div>
                </div>

            </div>
        </div>
    </section>

    <!-- [ส่วนงานกิจกรรมช่วยเหลือมหาวิทยาลัย - ACTIVITIES]: จัดแสดงผลงานกิจกรรมที่น่าภูมิใจในรูปแบบคอลัมน์คู่สวยงาม -->
    <section id="activities" class="py-14 relative z-10 border-t border-slate-100 bg-slate-50">
        <div class="max-w-5xl mx-auto px-4 sm:px-6 lg:px-8">
            <!-- หัวข้อหลักประจำหน้ากิจกรรม -->
            <div class="text-center mb-10 reveal">
                <span class="text-xs font-bold text-brand-600 uppercase tracking-widest font-mono">Student Leadership</span>
                <h2 class="text-4xl sm:text-5xl font-black text-slate-900 mt-2 tracking-tight">Activities</h2>
                <p class="text-slate-500 mt-2 text-xs">กิจกรรมและงานช่วยเหลือคณะเพื่อสาธารณประโยชน์ที่ได้เข้าร่วม</p>
                <div class="h-1.5 w-16 bg-gradient-to-r from-brand-600 to-cyan-500 mx-auto mt-4 rounded-full"></div>
            </div>

            <!-- โครงสร้างกริดแบ่งพื้นที่กิจกรรม 2 ฝั่งซ้าย-ขวาเท่าๆ กัน -->
            <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                
                <!-- กิจกรรมย่อย 1: แนะนำแนวทางหลักสูตร Open House มมส -->
                <div class="reveal glass-card rounded-2xl overflow-hidden group bg-white shadow-sm">
                    <div class="relative h-44 overflow-hidden cursor-pointer" onclick="openLightbox('https://images.unsplash.com/photo-1540575467063-178a50c2df87?q=80&w=800&auto=format&fit=crop', 'MSU Open House 2024 Booth Guide')">
                        <img src="https://images.unsplash.com/photo-1540575467063-178a50c2df87?q=80&w=800&auto=format&fit=crop" alt="MSU Open House Activity" class="w-full h-full object-cover opacity-90 group-hover:scale-105 transition-transform duration-700">
                        <div class="absolute inset-0 bg-gradient-to-t from-slate-950/60 via-transparent to-transparent"></div>
                        <div class="absolute bottom-3 left-4">
                            <span class="bg-brand-600 text-white text-[8px] font-bold px-2 py-1 rounded-lg uppercase tracking-wider font-mono shadow-sm">Booth Staff & Guide</span>
                        </div>
                    </div>
                    <div class="p-5">
                        <div class="flex items-center justify-between text-[9px] font-bold text-slate-400 mb-1 font-mono">
                            <span>MAHASARAKHAM UNIVERSITY</span>
                            <span>DEC 2024</span>
                        </div>
                        <h3 class="text-base font-bold text-slate-800 mb-1 group-hover:text-brand-600 transition-colors">MSU Open House 2024</h3>
                        <p class="text-slate-500 text-xs leading-relaxed mb-3">
                            ร่วมทำกิจกรรมแนะนำหลักสูตรดิจิทัลธุรกิจ แนะนำแนะแนวการศึกษาต่อให้กับกลุ่มน้องๆ นักเรียนมัธยมปลาย
                        </p>
                        <div class="pt-2.5 border-t border-slate-100 text-[9px] text-slate-400 flex items-center gap-1 font-mono">
                            <i class="fa-solid fa-users text-brand-600"></i> Supported Open House activities.
                        </div>
                    </div>
                </div>

                <!-- กิจกรรมย่อย 2: งานรับน้องเฟรชชี่ คณะการท่องเที่ยวฯ สโมสร -->
                <div class="reveal glass-card rounded-2xl overflow-hidden group bg-white shadow-sm">
                    <div class="relative h-44 overflow-hidden cursor-pointer" onclick="openLightbox('https://images.unsplash.com/photo-1511578314322-379afb476865?q=80&w=800&auto=format&fit=crop', 'MBS Freshy Day Staff')">
                        <img src="https://images.unsplash.com/photo-1511578314322-379afb476865?q=80&w=800&auto=format&fit=crop" alt="MBS Freshy Day Staff" class="w-full h-full object-cover opacity-90 group-hover:scale-105 transition-transform duration-700">
                        <div class="absolute inset-0 bg-gradient-to-t from-slate-950/60 via-transparent to-transparent"></div>
                        <div class="absolute bottom-3 left-4">
                            <span class="bg-indigo-600 text-white text-[8px] font-bold px-2 py-1 rounded-lg uppercase tracking-wider font-mono shadow-sm">Event Organizer Staff</span>
                        </div>
                    </div>
                    <div class="p-5">
                        <div class="flex items-center justify-between text-[9px] font-bold text-slate-400 mb-1 font-mono">
                            <span>MBS FACULTY EVENTS</span>
                            <span>JUL 2025</span>
                        </div>
                        <h3 class="text-base font-bold text-slate-800 mb-1 group-hover:text-brand-600 transition-colors">MBS Fresh Day</h3>
                        <p class="text-slate-500 text-xs leading-relaxed mb-3">
                            ปฏิบัติงานต้อนรับและอำนวยความสะดวก ประสานงานดูแลจุดลงทะเบียนอำนวยความสะดวกให้กับนักศึกษาใหม่
                        </p>
                        <div class="pt-2.5 border-t border-slate-100 text-[9px] text-slate-400 flex items-center gap-1 font-mono">
                            <i class="fa-solid fa-handshake text-indigo-500"></i> Assisted with registration.
                        </div>
                    </div>
                </div>
                
            </div>
        </div>
    </section>

    <!-- [ส่วนช่องทางติดต่อและท้ายสุด - CONTACT & FOOTER]: ฟอร์มคัดลอกอีเมล/เบอร์โทรศัพท์ และเครดิต -->
    <footer id="contact" class="bg-white text-slate-700 py-12 border-t border-slate-200/80 relative z-10">
        <div class="max-w-5xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 md:grid-cols-2 gap-10 pb-10 border-b border-slate-100 reveal">
                
                <!-- ข้อมูลติดต่อด่วนดั้งเดิม (ฝั่งซ้าย) -->
                <div class="space-y-4">
                    <h2 class="text-2xl font-black text-slate-900 tracking-tight">Contact Information</h2>
                    <p class="text-slate-500 text-xs leading-relaxed max-w-sm">
                        หากคุณต้องการข้อมูลเพิ่มเติมเพื่อพิจารณาเข้าฝึกงาน หรือต้องการพูดคุยเพิ่มเติม สามารถคัดลอกข้อมูลติดต่อหรือส่งข้อความหาฉันได้ทันทีค่ะ
                    </p>
                    <div class="space-y-3">
                        <div class="flex items-center gap-3">
                            <div class="w-9 h-9 rounded-lg bg-slate-50 flex items-center justify-center text-brand-600 border border-slate-200 shadow-sm">
                                <i class="fa-solid fa-map-location-dot text-xs"></i>
                            </div>
                            <div>
                                <div class="text-[8px] text-slate-400 font-bold uppercase font-mono">Location</div>
                                <div class="text-xs text-slate-600 font-semibold">Mahasarakham University, Thailand</div>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- กล่องปุ่มลัดคัดลอกอีเมลและเบอร์โทรศัพท์อย่างรวดเร็ว (ฝั่งขวา) -->
                <div class="glass-card p-5 rounded-2xl space-y-3 bg-slate-50/50 shadow-sm">
                    <h3 class="text-sm font-extrabold text-slate-800 flex items-center gap-2">
                        <i class="fa-solid fa-bolt text-brand-600 animate-pulse text-xs"></i> Direct Connection
                    </h3>
                    
                    <!-- ส่วนปุ่มคัดลอก Email ประจำตัว -->
                    <div class="bg-white p-3 rounded-xl flex items-center justify-between border border-slate-200/80 group hover:border-brand-500 transition-colors shadow-sm">
                        <div class="flex items-center gap-3 overflow-hidden">
                            <i class="fa-regular fa-envelope text-brand-600 text-base"></i>
                            <span class="text-xs font-semibold truncate text-slate-700" id="emailVal">nonglukkluanthaisong@gmail.com</span>
                        </div>
                        <button onclick="copyToClipboard('emailVal')" class="text-brand-600 hover:text-white p-1.5 bg-brand-50 hover:bg-brand-600 rounded-lg transition-all shadow-sm" title="Copy Email">
                            <i class="fa-regular fa-copy text-xs"></i>
                        </button>
                    </div>

                    <!-- ส่วนปุ่มคัดลอกเบอร์โทรศัพท์ด่วน -->
                    <div class="bg-white p-3 rounded-xl flex items-center justify-between border border-slate-200/80 group hover:border-brand-500 transition-colors shadow-sm">
                        <div class="flex items-center gap-3">
                            <i class="fa-solid fa-phone text-brand-600 text-base"></i>
                            <span class="text-xs font-semibold text-slate-700" id="phoneVal">(+66)94-570-5055</span>
                        </div>
                        <button onclick="copyToClipboard('phoneVal')" class="text-brand-600 hover:text-white p-1.5 bg-brand-50 hover:bg-brand-600 rounded-lg transition-all shadow-sm" title="Copy Phone Number">
                            <i class="fa-regular fa-copy text-xs"></i>
                        </button>
                    </div>
                </div>
            </div>

            <!-- ส่วนระบุข้อความเครดิตลิขสิทธิ์ด้านล่างสุดของเว็บ -->
            <div class="pt-5 flex flex-col sm:flex-row items-center justify-between text-[11px] text-slate-400 gap-4 reveal">
                <p>&copy; 2026 Nongluk Kluanthaisong. All Rights Reserved.</p>
                <div class="flex gap-4">
                    <span class="hover:underline cursor-pointer text-brand-600 font-mono font-medium" onclick="openCVModal()">Source: Nongluk.cv.jpg</span>
                    <span>•</span>
                    <span class="font-mono">Digital Business and Information Systems</span>
                </div>
            </div>
        </div>
    </footer>

    <!-- [หน้าต่างเสริมป๊อปอัพ - LIGHTBOX]: สำหรับซูมขยายและอ่านใบประกาศนียบัตรอย่างคมชัด -->
    <div id="lightboxModal" class="fixed inset-0 z-50 hidden bg-slate-950/95 backdrop-blur-md flex items-center justify-center p-4">
        <div class="relative max-w-4xl w-full flex flex-col max-h-[90vh]">
            <!-- ปุ่มกดปิดที่มุมขวาบนนอกกรอบรูปภาพ -->
            <button onclick="closeLightbox()" class="absolute -top-12 right-0 text-white/80 hover:text-white text-2xl w-9 h-9 flex items-center justify-center bg-white/10 hover:bg-white/20 rounded-full transition-all">
                &times;
            </button>
            <div class="bg-white rounded-3xl p-4 border border-slate-100 overflow-hidden flex flex-col justify-center items-center shadow-2xl">
                <!-- ตําแหน่งจัดวางภาพซูมใน Lightbox -->
                <img id="lightboxImage" src="" alt="Certificate View" class="max-w-full max-h-[70vh] rounded-2xl object-contain shadow-lg">
                <!-- คำอธิบายภาพใต้รูปภาพขยาย -->
                <p id="lightboxCaption" class="text-xs text-slate-700 mt-3 font-bold text-center"></p>
            </div>
        </div>
    </div>

    <!-- [หน้าต่างเสริมป๊อปอัพ - CV RESUME ORIGINAL]: สำหรับแสดงประวัติฉบับภาพอ้างอิง Nongluk.cv.jpg เต็มรูปแบบ -->
    <div id="cvModal" class="fixed inset-0 z-50 hidden bg-slate-950/95 backdrop-blur-md flex items-center justify-center p-4">
        <div class="bg-white rounded-3xl max-w-2xl w-full p-5 relative flex flex-col max-h-[90vh] border border-slate-100 shadow-2xl">
            <!-- ปุ่มกดปิดกล่องข้อมูลด้านบนขวา -->
            <button onclick="closeCVModal()" class="absolute top-4 right-4 text-slate-400 hover:text-slate-600 text-xl w-9 h-9 flex items-center justify-center bg-slate-50 hover:bg-slate-100 rounded-full transition-all">
                &times;
            </button>
            <h3 class="text-lg font-bold text-slate-800 mb-3 flex items-center gap-2">
                <i class="fa-solid fa-file-contract text-brand-600"></i> Original CV Document
            </h3>
            <!-- พื้นที่เลื่อนดูรูปภาพเรซูเม่ต้นฉบับแนวตั้งได้ (Scrollable Image Box) -->
            <div class="flex-1 overflow-y-auto rounded-xl border border-slate-100 bg-slate-50">
                <img src="Nongluk.cv.jpg" alt="Nongluk Kluanthaisong Original CV File" class="w-full h-auto" onerror="this.onerror=null; this.src='https://images.unsplash.com/photo-1586281380349-632531db7ed4?q=80&w=800&auto=format&fit=crop';">
            </div>
            <!-- ส่วนปุ่มกดปิดท้ายกล่อง -->
            <div class="mt-4 pt-3 border-t border-slate-100 flex justify-between items-center text-[11px] text-slate-400 font-mono">
                <span>Ref: Nongluk.cv.jpg</span>
                <button onclick="closeCVModal()" class="bg-brand-600 hover:bg-brand-500 text-white px-4 py-2 rounded-lg font-bold transition-all shadow-md shadow-brand-600/10">Close Viewer</button>
            </div>
        </div>
    </div>

    <!-- [กล่องแจ้งเตือนความสำเร็จสีดำ - TOAST NOTIFICATION]: สำหรับแจ้งข่าวการคัดลอกข้อมูลลงคลิปบอร์ดสำเร็จ -->
    <div id="toast" class="fixed bottom-6 right-6 bg-slate-900 text-white px-5 py-3 rounded-xl shadow-2xl transition-all duration-300 transform translate-y-20 opacity-0 z-50 flex items-center gap-2.5 font-semibold text-xs">
        <i class="fa-solid fa-circle-check text-base text-brand-500"></i>
        <span id="toastMessage">Copied successfully!</span>
    </div>

    <!-- ==================== [ส่วนคำสั่งคริปต์ควบคุม - JAVASCRIPT ENGINE] ==================== -->
    <script>
        // 1. ระบบดักจับการเลื่อนจอค่อยๆ ปรากฏผลงานแอนิเมชัน (Intersection Observer Scroll Animation)
        document.addEventListener("DOMContentLoaded", function() {
            const reveals = document.querySelectorAll(".reveal");

            // ตัวเลือกสำหรับการตั้งค่าระยะขอบในการตรวจจับการผ่านหน้าจอ
            const observerOptions = {
                root: null,
                rootMargin: "0px",
                threshold: 0.08 // เมื่อองค์ประกอบแสดงขึ้นมาเกิน 8% ให้เริ่มเล่นแอนิเมชันลอยตัวทันที
            };

            const revealObserver = new IntersectionObserver(function(entries, observer) {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add("active"); // เติมคลาส active เพื่อแสดงการเฟดลอย
                    }
                });
            }, observerOptions);

            reveals.forEach(el => {
                revealObserver.observe(el);
            });
        });

        // 2. ระบบดักฟังการกดปุ่มเพื่อเลื่อนสไลด์ใบเซอร์ไปซ้ายและขวา (Horizontal Scroll Certifications Slider)
        const certScroll = document.getElementById('certScrollContainer');
        const slideLeftBtn = document.getElementById('slideLeftBtn');
        const slideRightBtn = document.getElementById('slideRightBtn');

        // ควบคุมสไลด์ไปทางซ้าย 320 พิกเซล
        slideLeftBtn.addEventListener('click', () => {
            certScroll.scrollBy({
                left: -320,
                behavior: 'smooth'
            });
        });

        // ควบคุมสไลด์ไปทางขวา 320 พิกเซล
        slideRightBtn.addEventListener('click', () => {
            certScroll.scrollBy({
                left: 320,
                behavior: 'smooth'
            });
        });

        // 3. ระบบแสดง/ซ่อนแถบเมนูนำทางอัจฉริยะ (Smart Header Scroll Logic)
        // เลื่อนลงล่าง -> ซ่อนเมนูขึ้นด้านบน (-translate-y-full)
        // เลื่อนขึ้นด้านบน -> ดึงเมนูกลับมาแสดง (translate-y-0)
        let lastScrollTop = 0;
        const mainHeader = document.getElementById('mainHeader');
        
        window.addEventListener('scroll', function() {
            let scrollTop = window.pageYOffset || document.documentElement.scrollTop;
            
            if (scrollTop > lastScrollTop) {
                // ผู้ใช้งานกำลังเลื่อนลงล่าง (Scroll Down) -> ซ่อนเมนู Navbar ขึ้นไปด้านบนอย่างสมบูรณ์แบบ
                mainHeader.classList.add('-translate-y-full');
            } else {
                // ผู้ใช้งานกำลังเลื่อนขึ้นบน (Scroll Up) -> ดึงเมนู Navbar กลับมาแสดงผลเพื่อใช้งานทันที
                mainHeader.classList.remove('-translate-y-full');
                mainHeader.classList.add('bg-white/90', 'shadow-sm');
            }
            
            // เมื่อเลื่อนขึ้นไปถึงขอบด้านบนสุดของเว็บ ( scrollTop น้อยกว่า 20px ) -> ยกเลิกการซ่อนและทำโปร่งใส
            if (scrollTop <= 20) {
                mainHeader.classList.remove('-translate-y-full', 'shadow-sm');
                mainHeader.classList.add('bg-white/80');
            }
            
            lastScrollTop = scrollTop <= 0 ? 0 : scrollTop; // ป้องกันปัญหากดเลื่อนเว็บบนเบราว์เซอร์แล้วเกิดเลขลบ
        });

        // 4. ระบบเลื่อนตามตำแหน่งหน้าจอและปรับเส้นใต้เมนูแบบอัตโนมัติ (Scrollspy Active Underline Highlight)
        const sections = document.querySelectorAll('section[id]');
        const navItems = document.querySelectorAll('.nav-item');

        window.addEventListener('scroll', function() {
            let scrollPosition = document.documentElement.scrollTop || document.body.scrollTop;
            let currentSectionId = 'home'; // ค่าเริ่มต้นคือหน้าแรกสุด

            // ตรวจสอบพิกัดการชนกันของแต่ละ Section กับจอหลักปัจจุบัน
            sections.forEach(section => {
                const sectionTop = section.offsetTop - 150; // ปรับชดเชยค่าความกว้างของ Header
                const sectionHeight = section.offsetHeight;

                if (scrollPosition >= sectionTop && scrollPosition < (sectionTop + sectionHeight)) {
                    currentSectionId = section.getAttribute('id');
                }
            });

            // อัปเดตสถานะสีและสเกลเส้นขีดใต้สีน้ำเงินของลิงก์เมนูนำทางตามตําแหน่งปัจจุบัน
            navItems.forEach(item => {
                const targetId = item.getAttribute('href').substring(1);
                const line = item.querySelector('.nav-line');
                
                if (targetId === currentSectionId) {
                    item.classList.remove('text-slate-500');
                    item.classList.add('text-brand-600');
                    if (line) line.classList.replace('scale-x-0', 'scale-x-100'); // เปิดความกว้างเส้น 100%
                } else {
                    item.classList.remove('text-brand-600');
                    item.classList.add('text-slate-500');
                    if (line) line.classList.replace('scale-x-100', 'scale-x-0');   // ซ่อนย่อเส้นเหลือ 0%
                }
            });
        });

        // 5. คำสั่งการควบคุมหน้าต่างประวัติย่อแบบออริจินัล (CV Original Popup Modal Handlers)
        function openCVModal() {
            document.getElementById('cvModal').classList.remove('hidden'); // แสดงหน้าต่างขึ้นมา
            document.body.classList.add('overflow-hidden'); // ห้ามขยับเลื่อนจอหลังเบื้องหลังขณะเปิดอยู่
        }

        function closeCVModal() {
            document.getElementById('cvModal').classList.add('hidden'); // ปิดหน้าต่างลงไป
            document.body.classList.remove('overflow-hidden'); // อนุญาตให้เลื่อนจอเบื้องหลังได้ตามปกติ
        }

        // 6. คำสั่งเปิดหน้าต่างแสดงรายละเอียดซูมภาพใบรับรอง (Lightbox Gallery Handlers)
        function openLightbox(imgSrc, caption) {
            document.getElementById('lightboxImage').src = imgSrc;
            document.getElementById('lightboxCaption').innerText = caption;
            document.getElementById('lightboxModal').classList.remove('hidden'); // แสดงป๊อปอัพขึ้นมา
            document.body.classList.add('overflow-hidden');
        }

        function closeLightbox() {
            document.getElementById('lightboxModal').classList.add('hidden'); // ซ่อนป๊อปอัพลงไป
            document.body.classList.remove('overflow-hidden');
        }

        // 7. ระบบคัดลอกเบอร์โทรศัพท์และอีเมลอย่างรวดเร็ว (Copy To Clipboard with Safe Fallback)
        function copyToClipboard(elementId) {
            const textToCopy = document.getElementById(elementId).innerText;
            
            // ดำเนินการคัดลอกผ่าน API ที่ทันสมัยของเบราว์เซอร์
            if (navigator.clipboard && window.isSecureContext) {
                navigator.clipboard.writeText(textToCopy).then(() => {
                    showToast("คัดลอกข้อมูลเรียบร้อยแล้ว!");
                }).catch(err => {
                    fallbackCopyToClipboard(textToCopy); // หากเกิดข้อผิดพลาดให้ใช้ระบบสำรอง
                });
            } else {
                fallbackCopyToClipboard(textToCopy); // สำหรับอุปกรณ์หรือเครือข่ายเก่าๆ
            }
        }

        // ระบบสำรองสำหรับการคัดลอกผ่านกล่องจำลองเบื้องหลัง (ExecCommand Copy Fallback)
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

        // 8. แสดงผลแจ้งเตือนความสำเร็จแบบดีเลย์ปิดตัวอัตโนมัติ (Toast Notification system)
        function showToast(message) {
            const toast = document.getElementById('toast');
            document.getElementById('toastMessage').innerText = message;
            
            // ดันกล่องพ่นขึ้นมาเด่นชัดและเปิดโปร่งใสแบบเต็มรูป
            toast.classList.remove('translate-y-20', 'opacity-0');
            toast.classList.add('translate-y-0', 'opacity-100');
            
            // ซ่อนตัวอัตโนมัติภายในเวลา 3 วินาที (3000 มิลลิวินาที)
            setTimeout(() => {
                toast.classList.add('translate-y-20', 'opacity-0');
                toast.classList.remove('translate-y-0', 'opacity-100');
            }, 3000);
        }
    </script>
</body>
</html>
