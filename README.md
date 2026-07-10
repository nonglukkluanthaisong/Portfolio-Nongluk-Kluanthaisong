<!DOCTYPE html>
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
        /* ─── รีเซ็ตขอบหน้าเว็บทั้งหมดเพื่อลดช่องว่างส่วนเกิน ─── */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        /* ─── บังคับขนาดและเอฟเฟกต์สำหรับหัวข้อหน้าปกแรก ─── */
        .hero-title {
            font-size: 3rem !important; /* 48px สำหรับจอเล็ก */
            font-weight: 900 !important;
            letter-spacing: -0.025em !important;
            color: #0f172a !important; /* Slate 900 */
            line-height: 1.15 !important;
        }
        @media (min-width: 640px) {
            .hero-title {
                font-size: 4.5rem !important; /* 72px สำหรับจอแท็บเล็ต/คอมพิวเตอร์ */
            }
        }

        /* ─── เอฟเฟกต์หัวข้อใหญ่ใหม่ที่มีมิติและ "มีอะไรพิเศษ" (Fancy Header & Backlight Glow) ─── */
        .fancy-header {
            font-size: 2.25rem !important; /* 36px สำหรับมือถือ */
            font-weight: 900 !important;
            letter-spacing: -0.025em !important;
            line-height: 1.2 !important;
            position: relative;
            display: inline-block;
            /* ไล่เฉดสีกราเดียนท์พรีเมียมแบบเงาโลหะ Slate-Blue */
            background: linear-gradient(135deg, #0f172a 30%, #0066cc 70%, #0088ff 100%);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent !important;
            transition: all 0.5s cubic-bezier(0.16, 1, 0.3, 1);
            cursor: default;
        }
        @media (min-width: 640px) {
            .fancy-header {
                font-size: 3rem !important; /* 48px */
            }
        }
        @media (min-width: 768px) {
            .fancy-header {
                font-size: 3.75rem !important; /* 60px ขยายใหญ่สมเกียรติและเด่นชัดสุดๆ */
            }
        }
        /* เมื่อเอาเมาส์มาวางชี้: ตัวหนังสือขยายสเกลและเปลี่ยนเฉดสีเป็นฟ้าไซอันพร้อมยกตัวขึ้น */
        .fancy-header:hover {
            transform: scale(1.02) translateY(-2px);
            background: linear-gradient(135deg, #0066cc 0%, #0088ff 50%, #06b6d4 100%);
            -webkit-background-clip: text;
            background-clip: text;
            /* เพิ่มเงาสะท้อนลอยเบาๆ */
            filter: drop-shadow(0 4px 8px rgba(0, 102, 204, 0.12));
        }

        /* กล่องเก็บหัวข้อสำหรับควบคุมแผงแสงออร่าเรืองแสงด้านหลัง */
        .fancy-header-container {
            position: relative;
            display: inline-block;
        }
        /* สร้างวงกลมแสงเงาบางเบาสีฟ้า ซ่อนไว้ด้านหลังตัวหนังสือ */
        .fancy-header-container::before {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 120%;
            height: 120%;
            background: radial-gradient(circle, rgba(0, 102, 204, 0.12) 0%, transparent 70%);
            z-index: -1;
            opacity: 0;
            transition: opacity 0.6s cubic-bezier(0.16, 1, 0.3, 1);
            pointer-events: none; /* เพื่อไม่ให้ขัดขวางการชี้เมาส์ */
        }
        /* เมื่อชี้เมาส์ที่แถบหัวข้อ แสงออร่าด้านหลังจะค่อยๆ สว่างเรืองแสงขึ้นมา */
        .fancy-header-container:hover::before {
            opacity: 1;
        }

        /* ─── เอฟเฟกต์การ์ดและภาพรวมทั่วไป ─── */
        /* สไตล์การ์ดกระจกโปร่งแสงหรูหรา (Glassmorphic Cards) สำหรับธีมขาว */
        .glass-card {
            background: rgba(255, 255, 255, 0.78); /* พื้นสีขาวโปร่งแสง 78% */
            backdrop-filter: blur(12px);          /* เอฟเฟกต์เบลอหลังกระจก 12px */
            -webkit-backdrop-filter: blur(12px);   /* รองรับเบราว์เซอร์ Safari */
            border: 1px solid rgba(0, 102, 204, 0.08); /* เส้นขอบบางๆ สีน้ำเงินจาง */
            transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1); /* แอนิเมชันตอนตอบสนองการเคลื่อนไหว */
        }
        /* เอฟเฟกต์เมื่อผู้ใช้เอาเมาส์ไปชี้ที่ตัวการ์ด (Hover) */
        .glass-card:hover {
            border-color: rgba(0, 102, 204, 0.25); /* เพิ่มความเข้มของเส้นขอบสีน้ำเงิน */
            box-shadow: 0 15px 30px rgba(0, 102, 204, 0.06); /* เพิ่มเงามิติด้านล่าง */
            transform: translateY(-4px); /* ยกการ์ดลอยขึ้นด้านบน 4px */
        }

        /* เอฟเฟกต์ Scroll Reveal เด้งๆ สปริงแบบยืดหยุ่น (Bouncy Elastic Scroll Reveal Effect) */
        .reveal {
            opacity: 0; /* ตอนเริ่มต้นจะซ่อนไว้ (โปร่งใส 100%) */
            transform: translateY(40px) scale(0.95); /* ย่อตัวลงเล็กน้อยและดันลงล่าง 40px */
            filter: blur(4px); /* ปรับเอฟเฟกต์เบลอให้ตื่นตาตื่นใจตอนเปิด */
            transition: opacity 0.8s cubic-bezier(0.34, 1.56, 0.64, 1), 
                        transform 0.8s cubic-bezier(0.34, 1.56, 0.64, 1), 
                        filter 0.8s cubic-bezier(0.34, 1.56, 0.64, 1); /* แอนิเมชันเด้งสปริงแบบ Back-Out */
        }
        /* คลาสที่จะถูกเติมอัตโนมัติด้วย JavaScript เมื่อเลื่อนมาเจอจุดแสดงผล */
        .reveal.active {
            opacity: 1; /* ปรากฏตัวชัดเจน */
            transform: translateY(0) scale(1); /* กลับสู่ตำแหน่งและขนาดปกติแบบเด้ง */
            filter: blur(0px); /* สลายความเบลอออก */
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

        /* แอนิเมชันลูกบอลไฟเรืองแสงเคลื่อนไหวช้าๆ อยู่พื้นหลัง (Ambient Floating Glow Orbs) */
        @keyframes float-slow {
            0% { transform: translate(0px, 0px) scale(1); }
            33% { transform: translate(30px, -30px) scale(1.05); }
            66% { transform: translate(-20px, 20px) scale(0.95); }
            100% { transform: translate(0px, 0px) scale(1); }
        }
        .glow-orb {
            position: absolute;
            border-radius: 50%;
            filter: blur(100px); /* สั่งให้เบลอแสงฟุ้งกระจายออกไป 100px */
            opacity: 0.14;       /* ตั้งค่าความโปร่งแสงให้อ่อนมากๆ เพื่อไม่ให้รบกวนการอ่าน */
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

        /* 定义滚动条样式 (Custom Scrollbar) */
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

        /* ─── แอนิเมชันตัวอักษรลอยขึ้นลงแบบคลื่นอย่างนุ่มนวล (Soft Float Animation) ─── */
        @keyframes float-text {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-8px); }
        }
        .float-animated-text {
            display: inline-block;
            animation: float-text 3.5s ease-in-out infinite;
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

    <!-- [แถบเมนูด้านบน]: แถบเมนูนำทางอัจฉริยะ แสดงค้างตลอดแต่มีสไตล์ (Navigation Header) -->
    <header id="mainHeader" class="fixed top-0 left-0 right-0 z-40 bg-white/80 backdrop-blur-md border-b border-slate-100 shadow-sm translate-y-0">
        <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8 h-20 flex items-center justify-between">
            <!-- โลโก้แบรนด์ส่วนตัวด้านซ้าย -->
            <a href="#home" class="font-extrabold text-2xl tracking-wider text-slate-900">
                NONGLUK<span class="text-brand-600">.K</span>
            </a>
            
            <!-- เมนูลิงก์นำทางตรงกลาง (แสดงตลอดเวลา ไม่หายไปไหน) -->
            <nav id="navMenu" class="hidden md:flex space-x-6 lg:space-x-8 text-sm font-semibold relative">
                <!-- ลิงก์เมนูแต่ละส่วน พร้อมแท็กสำหรับทำเส้นขีดใต้สีน้ำเงินสว่างขึ้นตามส่วนที่อยู่จริง (Active State) -->
                <a href="#home" class="nav-item py-2 text-brand-600 transition-all duration-300 relative">Home<span class="nav-line absolute bottom-0 left-0 right-0 h-[3px] bg-brand-600 scale-x-100 transition-transform duration-300 origin-left"></span></a>
                <a href="#about" class="nav-item py-2 text-slate-500 hover:text-brand-600 transition-all duration-300 relative">About Me<span class="nav-line absolute bottom-0 left-0 right-0 h-[3px] bg-brand-600 scale-x-0 transition-transform duration-300 origin-left"></span></a>
                <a href="#education" class="nav-item py-2 text-slate-500 hover:text-brand-600 transition-all duration-300 relative">Education<span class="nav-line absolute bottom-0 left-0 right-0 h-[3px] bg-brand-600 scale-x-0 transition-transform duration-300 origin-left"></span></a>
                <a href="#projects" class="nav-item py-2 text-slate-500 hover:text-brand-600 transition-all duration-300 relative">Works & Projects<span class="nav-line absolute bottom-0 left-0 right-0 h-[3px] bg-brand-600 scale-x-0 transition-transform duration-300 origin-left"></span></a>
                <a href="#certifications" class="nav-item py-2 text-slate-500 hover:text-brand-600 transition-all duration-300 relative">Certificates<span class="nav-line absolute bottom-0 left-0 right-0 h-[3px] bg-brand-600 scale-x-0 transition-transform duration-300 origin-left"></span></a>
                <a href="#activities" class="nav-item py-2 text-slate-500 hover:text-brand-600 transition-all duration-300 relative">Activities<span class="nav-line absolute bottom-0 left-0 right-0 h-[3px] bg-brand-600 scale-x-0 transition-transform duration-300 origin-left"></span></a>
            </nav>
            
            <!-- ปุ่มติดต่อฉันด่วนฝั่งขวา -->
            <div>
                <a href="#contact" class="inline-flex items-center justify-center px-5 py-2.5 rounded-full bg-brand-600 hover:bg-brand-500 text-white text-sm font-semibold transition-all duration-300 shadow-lg shadow-brand-600/10 hover:shadow-brand-500/35 transform hover:-translate-y-0.5">
                    Contact Me
                </a>
            </div>
        </div>
    </header>

    <!-- [หน้า HOME - หน้าแรก]: ปรับระยะ padding-top (pt-24) และขอบบนให้กระชับขึ้นและแคบลงเรียบร้อยครับ -->
    <section id="home" class="pt-24 pb-16 md:pt-28 md:pb-24 min-h-screen flex items-center relative z-10">
        <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 w-full">
            <div class="flex flex-col lg:flex-row items-center gap-12 lg:gap-16">
