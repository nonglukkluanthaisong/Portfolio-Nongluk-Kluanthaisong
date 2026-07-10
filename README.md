<!-- ... existing code ... -->
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        html, body {
            width: 100%;
            max-width: 100%;
            overflow-x: hidden;
            -webkit-overflow-scrolling: touch; /* Smooth scrolling for touch devices */
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Noto Sans Thai', 'Inter', sans-serif;
            background-color: #030712;
            color: #f3f4f6;
        }

        /* Set elegant Serif styles for premium editorial accents */
        .serif-title {
            font-family: 'Playfair Display', serif;
        }
<!-- ... existing code ... -->
        /* Smoothbar and safety wrapper styling */
        ::-webkit-scrollbar {
            width: 6px;
        }
        ::-webkit-scrollbar-track {
            background: #030712;
        }
        ::-webkit-scrollbar-thumb {
            background: #1f2937;
            border-radius: 3px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #3b82f6;
        }
    </style>
</head>
<body class="bg-[#030712] text-gray-100 min-h-screen relative overflow-x-hidden selection:bg-brandBlue-800 selection:text-white">

    <!-- Ambient Glow & Technical Background Wrapper (Strictly contained to prevent horizontal stretching) -->
    <div class="fixed inset-0 w-full h-full overflow-hidden pointer-events-none z-0">
        <!-- Technical Grid Overlay (Faint sci-fi pattern) -->
        <div class="absolute inset-0 bg-[linear-gradient(to_right,#1f29370f_1px,transparent_1px),linear-gradient(to_bottom,#1f29370f_1px,transparent_1px)] bg-[size:4rem_4rem] [mask-image:radial-gradient(ellipse_60%_50%_at_50%_0%,#000_70%,transparent_100%)] opacity-60"></div>
        
        <!-- Subtle Glow Elements -->
        <div class="ambient-glow w-[300px] h-[300px] md:w-[500px] md:h-[500px] bg-brandBlue-900/15 top-[-100px] left-[-100px]"></div>
        <div class="ambient-glow w-[350px] h-[350px] md:w-[600px] md:h-[600px] bg-blue-950/10 bottom-[10%] right-[-150px]"></div>
    </div>

    <!-- Scroll Progress Indicator -->
    <div id="scroll-progress" class="no-print"></div>

    <!-- Main Wrapper enclosing everything in a responsive viewport-safe container -->
    <div class="w-full min-h-screen flex flex-col relative overflow-hidden z-10">

        <!-- Header Navigation -->
        <header id="main-header" class="fixed top-0 left-0 w-full z-50 glass-nav no-print">
<!-- ... existing code ... -->
        <!-- Main Wrapper with Wide-Screen Support & Touch padding safety -->
        <main class="relative z-10 w-full max-w-[1440px] mx-auto px-4 sm:px-6 md:px-8 pt-28 sm:pt-32 pb-24 space-y-24 sm:space-y-32 overflow-hidden">

            <!-- Clean Text-Only Hero Section with Interactive Neural AI Canvas Background -->
            <section id="home" class="min-h-[80vh] flex flex-col justify-center items-center text-center py-12 sm:py-16 relative overflow-hidden reveal-element">
<!-- ... existing code ... -->
            <!-- Contact Section -->
            <section id="contact" class="scroll-mt-24 reveal-element">
                <div class="glass-card rounded-2xl p-6 sm:p-8 md:p-12 grid grid-cols-1 lg:grid-cols-12 gap-8 lg:gap-12 items-center relative overflow-hidden">
                    <div class="absolute inset-0 bg-gradient-to-tr from-brandBlue-950/20 to-transparent pointer-events-none"></div>
                    
                    <div class="lg:col-span-5 space-y-6">
<!-- ... existing code ... -->
                    </div>
                </div>
            </section>

        </main>

        <!-- Footer -->
        <footer class="border-t border-gray-800/60 py-8 text-center text-[11px] text-gray-500 bg-gray-950/40 no-print sans-tech z-10">
            <p>&copy; 2026 นงลักษณ์ เกลื่อนไทสง. จัดทำตามมาตรฐานการออกแบบระดับสูงแบบตอบสนองเต็มรูปแบบ (Responsive Design)</p>
        </footer>

    </div> <!-- End Main Wrapper -->

    <!-- INTERACTIVE PRINT-READY RESUME MODAL -->
<!-- ... existing code ... -->
