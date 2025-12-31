<!DOCTYPE html>
<html lang="ms" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Doa & Harapan Tahun Baru | Edisi Korporat</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Amiri:ital,wght@0,400;0,700;1,400&family=Cinzel:wght@400;700&family=Playfair+Display:wght@400;700&family=Plus+Jakarta+Sans:wght@300;400;600&display=swap" rel="stylesheet">
    <!-- Lucide Icons -->
    <script src="https://unpkg.com/lucide@latest"></script>
    
    <style>
        /* Custom Font Settings */
        .font-amiri { font-family: 'Amiri', serif; }
        .font-cinzel { font-family: 'Cinzel', serif; } /* Corporate/Regal Font */
        .font-playfair { font-family: 'Playfair Display', serif; }
        .font-body { font-family: 'Plus Jakarta Sans', sans-serif; }

        /* background Texture - Subtle Noise for Professionalism */
        .bg-corporate {
            background-color: #020617;
            background-image: url("https://www.transparenttextures.com/patterns/cubes.png");
        }

        /* Gold Gradient Text - The "Corporate" Standard */
        .text-gold-gradient {
            background: linear-gradient(to right, #bf953f, #fcf6ba, #b38728, #fbf5b7, #aa771c);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        /* Elegant Glow (Less Neon, More Halo) */
        .glow-gold {
            text-shadow: 0 0 10px rgba(191, 149, 63, 0.5), 0 0 20px rgba(191, 149, 63, 0.3);
        }

        /* Card Hover Effects - Professional Lift */
        .prayer-card {
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            border: 1px solid rgba(255, 255, 255, 0.05);
        }
        .prayer-card:hover {
            transform: translateY(-5px);
            border-color: #b38728;
            box-shadow: 0 10px 30px -10px rgba(179, 135, 40, 0.3);
        }

        /* Checkbox Customization - Gold Accent */
        .checkbox-wrapper input:checked + div {
            background-color: #b38728;
            border-color: #b38728;
        }
        .checkbox-wrapper input:checked + div svg {
            display: block;
        }
        
        /* Fireworks Canvas */
        #fireworks-canvas {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 0;
            pointer-events: none;
        }

        /* Countdown Box Style */
        .countdown-box {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255, 215, 0, 0.2);
        }
        
        /* Custom File Input */
        .file-upload-label {
            cursor: pointer;
            transition: all 0.3s ease;
        }
        .file-upload-label:hover {
            border-color: #b38728;
            background-color: rgba(179, 135, 40, 0.05);
        }
    </style>
</head>
<body class="font-body bg-corporate text-slate-100 antialiased selection:bg-yellow-600 selection:text-white pb-10">

    <!-- Fireworks Background -->
    <canvas id="fireworks-canvas"></canvas>

    <!-- Navbar -->
    <nav class="fixed w-full z-50 bg-[#020617]/95 backdrop-blur-md border-b border-white/10 shadow-lg">
        <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-20">
                <div class="flex items-center space-x-3">
                    <div class="bg-gradient-to-br from-yellow-400 to-yellow-700 p-2 rounded-lg">
                        <i data-lucide="star" class="text-white w-5 h-5 fill-current"></i>
                    </div>
                    <div>
                        <span class="font-cinzel text-xl md:text-2xl text-white tracking-widest font-bold">NUR<span class="text-yellow-500">JADID</span></span>
                        <p class="text-[10px] text-slate-400 tracking-wider uppercase">Edisi Korporat</p>
                    </div>
                </div>
                <div class="hidden md:flex space-x-8">
                    <a href="#doa" class="text-slate-300 hover:text-yellow-400 transition text-xs uppercase tracking-widest font-semibold">Doa Pilihan</a>
                    <a href="#kad" class="text-slate-300 hover:text-yellow-400 transition text-xs uppercase tracking-widest font-semibold">Kad Korporat</a>
                    <a href="#resolusi" class="text-slate-300 hover:text-yellow-400 transition text-xs uppercase tracking-widest font-semibold">Resolusi</a>
                </div>
                <!-- Mobile Menu Button -->
                <button id="mobile-menu-btn" class="md:hidden text-slate-300 p-2 rounded-md hover:bg-white/10 transition">
                    <i data-lucide="menu" class="w-6 h-6"></i>
                </button>
            </div>
        </div>
        <!-- Mobile Dropdown -->
        <div id="mobile-menu" class="md:hidden hidden bg-[#020617] border-b border-white/10">
            <div class="px-4 pt-2 pb-4 space-y-2">
                <a href="#doa" class="block px-3 py-3 rounded-md text-sm text-slate-300 hover:text-yellow-400 uppercase tracking-wide">Doa Pilihan</a>
                <a href="#kad" class="block px-3 py-3 rounded-md text-sm text-slate-300 hover:text-yellow-400 uppercase tracking-wide">Kad Korporat</a>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <header class="relative pt-32 pb-20 lg:pt-52 lg:pb-32 overflow-hidden px-4">
        <!-- Elegant Light Effects -->
        <div class="absolute top-0 left-1/2 -translate-x-1/2 w-full h-[500px] bg-yellow-600/10 blur-[120px] rounded-full pointer-events-none"></div>
        
        <div class="relative max-w-5xl mx-auto text-center z-10">
            <!-- Hijri Date Badge -->
            <div class="inline-flex items-center gap-2 mb-6 px-5 py-2 rounded-full border border-yellow-500/30 bg-yellow-500/5 backdrop-blur-sm">
                <i data-lucide="calendar" class="w-4 h-4 text-yellow-500"></i>
                <p id="hijri-date" class="font-amiri text-lg text-yellow-200">Loading Date...</p>
            </div>
            
            <h1 id="hero-title" class="font-cinzel text-4xl sm:text-5xl md:text-7xl font-bold mb-6 leading-tight tracking-wider px-2 text-white">
                Membuka Lembaran <br>
                <span class="text-gold-gradient glow-gold drop-shadow-2xl">TAHUN BARU</span>
            </h1>
            
            <p class="font-playfair text-lg md:text-2xl text-slate-300 italic mb-10 tracking-wide max-w-3xl mx-auto">
                "Melangkah ke hadapan dengan visi yang jelas, iman yang teguh, dan profesionalisme yang utuh."
            </p>

            <!-- Countdown Timer -->
            <div class="flex flex-wrap justify-center gap-4 md:gap-8 mb-12 font-cinzel text-yellow-500">
                <div class="countdown-box p-4 rounded-lg min-w-[80px]">
                    <span id="days" class="text-3xl md:text-4xl font-bold block text-white">00</span>
                    <span class="text-xs text-slate-400 uppercase tracking-widest">Hari</span>
                </div>
                <div class="countdown-box p-4 rounded-lg min-w-[80px]">
                    <span id="hours" class="text-3xl md:text-4xl font-bold block text-white">00</span>
                    <span class="text-xs text-slate-400 uppercase tracking-widest">Jam</span>
                </div>
                <div class="countdown-box p-4 rounded-lg min-w-[80px]">
                    <span id="minutes" class="text-3xl md:text-4xl font-bold block text-white">00</span>
                    <span class="text-xs text-slate-400 uppercase tracking-widest">Minit</span>
                </div>
            </div>

            <div class="flex flex-col sm:flex-row justify-center gap-5 px-6">
                <a href="#doa" class="group relative px-8 py-4 bg-gradient-to-r from-yellow-700 to-yellow-600 text-white font-cinzel font-bold tracking-widest text-sm rounded-sm hover:from-yellow-600 hover:to-yellow-500 transition shadow-lg shadow-yellow-900/40 overflow-hidden">
                    <span class="relative z-10 flex items-center justify-center gap-2"><i data-lucide="book-open" class="w-4 h-4"></i> BACA DOA</span>
                    <div class="absolute inset-0 bg-white/20 translate-y-full group-hover:translate-y-0 transition-transform duration-300"></div>
                </a>
                <a href="#kad" class="group px-8 py-4 bg-transparent border border-yellow-500/50 text-yellow-500 font-cinzel font-bold tracking-widest text-sm rounded-sm hover:bg-yellow-500/10 transition backdrop-blur-sm">
                    <span class="flex items-center justify-center gap-2"><i data-lucide="pen-tool" class="w-4 h-4"></i> KAD KORPORAT</span>
                </a>
            </div>
        </div>
    </header>

    <!-- Section 1: Himpunan Doa -->
    <section id="doa" class="py-20 bg-black/20 border-y border-white/5 relative">
        <div class="max-w-4xl mx-auto px-4 relative z-10">
            <div class="text-center mb-16">
                <h2 class="font-cinzel text-3xl md:text-4xl font-bold text-white mb-3 tracking-widest"><span class="text-yellow-500">DOA</span> PILIHAN</h2>
                <div class="h-[1px] w-24 bg-gradient-to-r from-transparent via-yellow-500 to-transparent mx-auto"></div>
                <p class="mt-4 text-slate-400 font-playfair italic">Munajat dan harapan untuk keberkatan organisasi dan peribadi.</p>
            </div>

            <div class="grid gap-8">
                <!-- Card 1 -->
                <div class="prayer-card bg-slate-900/60 rounded-lg p-8 md:p-10 relative overflow-hidden group">
                    <div class="absolute top-0 right-0 w-32 h-32 bg-yellow-500/5 rounded-bl-full transition-all group-hover:bg-yellow-500/10"></div>
                    <div class="absolute top-6 right-6 opacity-20 text-yellow-500">
                        <i data-lucide="moon" class="w-12 h-12"></i>
                    </div>
                    
                    <div class="flex items-center gap-3 mb-6">
                        <div class="h-8 w-1 bg-yellow-600"></div>
                        <h3 class="font-cinzel font-bold text-yellow-500 text-lg md:text-xl tracking-wide">Doa Kesejahteraan Sejagat</h3>
                    </div>

                    <p class="font-amiri text-3xl md:text-4xl text-right leading-loose mb-8 text-white drop-shadow-md" dir="rtl">
                        رَبَّنَا آتِنَا فِي الدُّنْيَا حَسَنَةً وَفِي الْآخِرَةِ حَسَنَةً وَقِنَا عَذَابَ النَّارِ
                    </p>
                    <p class="text-slate-300 italic mb-4 font-playfair border-l-2 border-slate-700 pl-4">"Rabbana atina fid-dunya hasanah wa fil 'akhirati hasanah waqina 'adhaban-nar."</p>
                    <p class="text-slate-400 text-sm leading-relaxed font-light">
                        "Ya Tuhan kami, berilah kami kebaikan di dunia dan kebaikan di akhirat dan peliharalah kami dari siksa neraka." (Surah Al-Baqarah: 201)
                    </p>
                </div>

                <!-- Card 2 -->
                <div class="prayer-card bg-slate-900/60 rounded-lg p-8 md:p-10 relative overflow-hidden">
                    <div class="flex items-center gap-3 mb-6">
                        <div class="h-8 w-1 bg-yellow-600"></div>
                        <h3 class="font-cinzel font-bold text-yellow-500 text-lg md:text-xl tracking-wide">Doa Ketetapan Hati</h3>
                    </div>
                    <p class="font-amiri text-3xl md:text-4xl text-right leading-loose mb-8 text-white drop-shadow-md" dir="rtl">
                        يَا مُقَلِّبَ الْقُلُوبِ ثَبِّتْ قَلْبِي عَلَى دِينِكَ
                    </p>
                    <p class="text-slate-300 italic mb-4 font-playfair border-l-2 border-slate-700 pl-4">"Ya Muqallibal qulub, thabbit qalbi 'ala dinik."</p>
                    <p class="text-slate-400 text-sm leading-relaxed font-light">
                        "Wahai Dzat yang membolak-balikkan hati, tetapkanlah hatiku di atas agama-Mu."
                    </p>
                </div>
            </div>
        </div>
    </section>

    <!-- Section 2: Kad Ucapan Generator (Corporate Edition) -->
    <section id="kad" class="py-20 relative scroll-mt-20">
        <div class="max-w-6xl mx-auto px-4">
            <div class="grid md:grid-cols-2 gap-12 items-start">
                
                <!-- Input Column -->
                <div class="order-2 md:order-1">
                    <h2 id="card-title" class="font-cinzel text-3xl md:text-4xl font-bold text-white mb-2 text-center md:text-left">KAD <span class="text-yellow-500">KORPORAT</span></h2>
                    <p class="text-slate-400 mb-8 text-center md:text-left text-sm font-light">Jana kad ucapan rasmi dengan logo syarikat anda.</p>
                    
                    <div class="space-y-6 bg-slate-900/40 p-6 md:p-8 rounded-xl border border-white/10 shadow-2xl backdrop-blur-sm relative">
                        <!-- Decorative corner -->
                        <div class="absolute top-0 left-0 w-20 h-20 border-t-2 border-l-2 border-yellow-500/20 rounded-tl-xl pointer-events-none"></div>

                        <div>
                            <label class="block text-xs font-bold text-yellow-500 uppercase tracking-widest mb-2">Nama Pengirim</label>
                            <input type="text" id="senderName" placeholder="Cth: En. Azman" maxlength="25" 
                                class="w-full px-4 py-3 bg-[#020617] border border-slate-700 text-white placeholder-slate-600 focus:border-yellow-500 focus:ring-1 focus:ring-yellow-500 outline-none transition text-sm rounded-sm" 
                                oninput="updateCanvas()">
                        </div>

                        <div>
                            <label class="block text-xs font-bold text-yellow-500 uppercase tracking-widest mb-2">Nama Organisasi / Syarikat</label>
                            <input type="text" id="companyName" placeholder="Cth: Maju Holdings Sdn Bhd" maxlength="30" 
                                class="w-full px-4 py-3 bg-[#020617] border border-slate-700 text-white placeholder-slate-600 focus:border-yellow-500 focus:ring-1 focus:ring-yellow-500 outline-none transition text-sm rounded-sm" 
                                oninput="updateCanvas()">
                        </div>
                        
                        <!-- NEW: Logo Upload -->
                        <div>
                            <label class="block text-xs font-bold text-yellow-500 uppercase tracking-widest mb-2">Muat Naik Logo Syarikat (PNG/JPG)</label>
                            <label class="file-upload-label flex items-center justify-center w-full px-4 py-3 bg-[#020617] border border-dashed border-slate-600 rounded-sm text-slate-400 hover:text-white group">
                                <input type="file" id="logoUpload" accept="image/*" class="hidden" onchange="handleLogoUpload(this)">
                                <span class="text-sm flex items-center gap-2">
                                    <i data-lucide="upload-cloud" class="w-4 h-4 group-hover:text-yellow-500 transition-colors"></i> 
                                    <span id="logoFileName">Pilih Fail Logo...</span>
                                </span>
                            </label>
                        </div>

                        <div>
                            <label class="block text-xs font-bold text-yellow-500 uppercase tracking-widest mb-2">Pilih Ucapan Profesional</label>
                            <select id="messageSelect" class="w-full px-4 py-3 bg-[#020617] border border-slate-700 text-white focus:border-yellow-500 focus:ring-1 focus:ring-yellow-500 outline-none text-sm rounded-sm" onchange="updateCanvas()">
                                <option value="Semoga tahun baru ini membawa kejayaan dan keberkatan berpanjangan.">Kejayaan & Keberkatan</option>
                                <option value="Terus melangkah cemerlang dengan visi dan misi yang jelas.">Visi & Misi Jelas</option>
                                <option value="Selamat Tahun Baru. Semoga kerjasama kita terus utuh dan diberkati.">Kerjasama Utuh</option>
                                <option value="Maaf zahir batin. Mari buka lembaran produktiviti yang baru.">Lembaran Produktiviti</option>
                            </select>
                        </div>

                        <div>
                            <label class="block text-xs font-bold text-yellow-500 uppercase tracking-widest mb-2">Tema Warna</label>
                             <div class="flex gap-4">
                                 <!-- Gold Theme -->
                                 <button onclick="changeTheme('#b38728', '#fcf6ba')" class="w-12 h-12 bg-gradient-to-br from-yellow-600 to-yellow-800 border border-yellow-400 hover:scale-105 transition shadow-lg"></button>
                                 <!-- Emerald Theme -->
                                 <button onclick="changeTheme('#047857', '#6ee7b7')" class="w-12 h-12 bg-gradient-to-br from-emerald-800 to-emerald-950 border border-emerald-500 hover:scale-105 transition shadow-lg"></button>
                                 <!-- Royal Blue Theme -->
                                 <button onclick="changeTheme('#1e3a8a', '#93c5fd')" class="w-12 h-12 bg-gradient-to-br from-blue-900 to-slate-900 border border-blue-500 hover:scale-105 transition shadow-lg"></button>
                                 <!-- Black Tie Theme -->
                                 <button onclick="changeTheme('#333333', '#e2e8f0')" class="w-12 h-12 bg-gradient-to-br from-gray-800 to-black border border-gray-500 hover:scale-105 transition shadow-lg"></button>
                             </div>
                        </div>

                        <button onclick="downloadCard()" class="w-full py-4 bg-yellow-600 hover:bg-yellow-500 text-white font-cinzel font-bold tracking-widest rounded-sm shadow-lg transition flex justify-center items-center gap-2 mt-4 group">
                            <i data-lucide="download" class="group-hover:translate-y-1 transition-transform"></i> MUAT TURUN KAD
                        </button>
                    </div>
                </div>

                <!-- Preview Column -->
                <div class="flex justify-center order-1 md:order-2">
                    <div class="relative w-full max-w-[400px]">
                        <div class="shadow-2xl overflow-hidden border border-yellow-500/20 shadow-yellow-500/10">
                            <canvas id="cardCanvas" width="1080" height="1080" class="w-full h-auto bg-[#0f172a]"></canvas>
                        </div>
                        <p class="text-center text-[10px] uppercase tracking-widest text-slate-500 mt-4">Pratonton Dijana Automatik</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Section 3: Resolusi Korporat -->
    <!-- Added 'relative z-10' to bring this section to the front -->
    <section id="resolusi" class="py-20 bg-[#000000]/40 border-t border-white/5 scroll-mt-20 relative z-10">
        <div class="max-w-4xl mx-auto px-4">
            <div class="text-center mb-12">
                <i data-lucide="list-checks" class="w-10 h-10 mx-auto text-yellow-600 mb-4"></i>
                <h2 class="font-cinzel text-3xl md:text-4xl font-bold mb-4 text-white">RESOLUSI <span class="text-yellow-500">TAHUNAN</span></h2>
                <p class="text-slate-400 font-light">Senarai semak untuk kejayaan duniawi dan ukhrawi.</p>
            </div>
            
            <div class="space-y-4">
                <label class="checkbox-wrapper flex items-start p-5 bg-slate-900/50 border border-white/5 hover:border-yellow-500/30 transition cursor-pointer group">
                    <input type="checkbox" class="hidden peer">
                    <div class="w-5 h-5 border border-slate-500 flex-shrink-0 flex items-center justify-center mr-4 mt-1 transition-colors group-hover:border-yellow-500">
                        <svg class="w-3 h-3 text-white hidden pointer-events-none" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="3" d="M5 13l4 4L19 7"></path></svg>
                    </div>
                    <span class="text-slate-300 group-hover:text-yellow-100 transition peer-checked:text-yellow-500 peer-checked:line-through">Meningkatkan integriti dan amanah dalam pekerjaan.</span>
                </label>
                
                <label class="checkbox-wrapper flex items-start p-5 bg-slate-900/50 border border-white/5 hover:border-yellow-500/30 transition cursor-pointer group">
                    <input type="checkbox" class="hidden peer">
                    <div class="w-5 h-5 border border-slate-500 flex-shrink-0 flex items-center justify-center mr-4 mt-1 transition-colors group-hover:border-yellow-500">
                        <svg class="w-3 h-3 text-white hidden pointer-events-none" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="3" d="M5 13l4 4L19 7"></path></svg>
                    </div>
                    <span class="text-slate-300 group-hover:text-yellow-100 transition peer-checked:text-yellow-500 peer-checked:line-through">Menjaga solat 5 waktu dan hubungan sesama rakan sekerja.</span>
                </label>

                <label class="checkbox-wrapper flex items-start p-5 bg-slate-900/50 border border-white/5 hover:border-yellow-500/30 transition cursor-pointer group">
                    <input type="checkbox" class="hidden peer">
                    <div class="w-5 h-5 border border-slate-500 flex-shrink-0 flex items-center justify-center mr-4 mt-1 transition-colors group-hover:border-yellow-500">
                        <svg class="w-3 h-3 text-white hidden pointer-events-none" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="3" d="M5 13l4 4L19 7"></path></svg>
                    </div>
                    <span class="text-slate-300 group-hover:text-yellow-100 transition peer-checked:text-yellow-500 peer-checked:line-through">Mengeluarkan zakat pendapatan dan bersedekah secara konsisten.</span>
                </label>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-black py-8 border-t border-white/10 text-center relative z-10">
        <p class="text-yellow-600/80 text-xs tracking-widest uppercase font-cinzel">hak cipta terpelihara &copy; Muhamadjais 2025/2026</p>
    </footer>

    <!-- Scripts -->
    <script>
        lucide.createIcons();
        
        // --- HIJRI DATE ---
        function updateHijriDate() {
             const date = new Date();
             const options = {
                 day: 'numeric',
                 month: 'long',
                 year: 'numeric',
                 calendar: 'islamic-umalqura'
             };
             try {
                // Formatting for Malaysia/Indonesia Locale
                const hijri = new Intl.DateTimeFormat('ms-MY-u-ca-islamic', options).format(date);
                // Clean up string if necessary (remove "AH" if present and replace with "H")
                const formattedHijri = hijri.replace('AH', 'H') + " H"; 
                document.getElementById('hijri-date').innerText = formattedHijri;
             } catch (e) {
                 document.getElementById('hijri-date').innerText = "1447H"; // Fallback
             }
        }
        updateHijriDate();
        
        // --- COUNTDOWN TIMER ---
        const targetDate = new Date("January 1, 2026 00:00:00").getTime();
        
        function updateCountdown() {
            const now = new Date().getTime();
            const distance = targetDate - now;
            
            const days = Math.floor(distance / (1000 * 60 * 60 * 24));
            const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
            
            document.getElementById("days").innerText = days.toString().padStart(2, '0');
            document.getElementById("hours").innerText = hours.toString().padStart(2, '0');
            document.getElementById("minutes").innerText = minutes.toString().padStart(2, '0');
        }
        setInterval(updateCountdown, 1000);
        updateCountdown();

        // --- MOBILE MENU ---
        function toggleMenu() {
            const menu = document.getElementById('mobile-menu');
            if (menu.classList.contains('hidden')) {
                menu.classList.remove('hidden');
            } else {
                menu.classList.add('hidden');
            }
        }
        document.getElementById('mobile-menu-btn').addEventListener('click', toggleMenu);

        // --- REFINED FIREWORKS (ELEGANT GOLD/WHITE) ---
        const fwCanvas = document.getElementById('fireworks-canvas');
        const fwCtx = fwCanvas.getContext('2d');
        const heroTitle = document.getElementById('hero-title');
        const cardTitle = document.getElementById('card-title');
        let fwWidth, fwHeight, particles = [];

        function resizeFwCanvas() {
            fwWidth = window.innerWidth;
            fwHeight = window.innerHeight;
            fwCanvas.width = fwWidth;
            fwCanvas.height = fwHeight;
        }
        window.addEventListener('resize', resizeFwCanvas);
        resizeFwCanvas();

        class Particle {
            constructor(x, y, color) {
                this.x = x; this.y = y; this.color = color;
                const angle = Math.random() * Math.PI * 2;
                const speed = Math.random() * 3 + 1; 
                this.vx = Math.cos(angle) * speed;
                this.vy = Math.sin(angle) * speed;
                this.alpha = 1; 
                this.decay = Math.random() * 0.01 + 0.005; 
                this.gravity = 0.03; // Slower gravity for elegance
            }
            update() { 
                this.x += this.vx; this.y += this.vy; 
                this.vy += this.gravity; this.alpha -= this.decay; 
            }
            draw(ctx) { 
                ctx.save(); 
                ctx.globalAlpha = this.alpha; 
                ctx.fillStyle = this.color; 
                ctx.beginPath(); 
                ctx.arc(this.x, this.y, 1.5, 0, Math.PI * 2); // Smaller particles
                ctx.fill(); 
                ctx.restore(); 
            }
        }

        function createFirework(tx, ty) {
            const x = tx !== undefined ? tx : Math.random() * fwWidth;
            const y = ty !== undefined ? ty : Math.random() * (fwHeight / 2);
            
            // Corporate Colors: Gold, White, Cyan, Emerald (No Pink/Red/Orange)
            const colors = ['#fcd34d', '#ffffff', '#fbbf24', '#34d399', '#f0f9ff'];
            const color = colors[Math.floor(Math.random() * colors.length)];
            const particleCount = tx !== undefined ? 80 : 30;
            
            for (let i = 0; i < particleCount; i++) {
                particles.push(new Particle(x, y, color));
            }
        }

        let tick = 0;
        function animateFireworks() {
            fwCtx.fillStyle = 'rgba(2, 6, 23, 0.2)'; // Dark Corporate Background
            fwCtx.fillRect(0, 0, fwWidth, fwHeight);
            
            tick++;
            if (Math.random() < 0.02) createFirework();
            
            if (tick % 100 === 0 && heroTitle) {
                const rect = heroTitle.getBoundingClientRect();
                if (rect.top >= -rect.height && rect.bottom <= window.innerHeight + rect.height) {
                    createFirework(rect.left + rect.width / 2, rect.top + rect.height / 2);
                }
            }
            if (tick % 100 === 50 && cardTitle) {
                const rect = cardTitle.getBoundingClientRect();
                if (rect.top >= -rect.height && rect.bottom <= window.innerHeight + rect.height) {
                    createFirework(rect.left + rect.width / 2, rect.top + rect.height / 2);
                }
            }

            for (let i = particles.length - 1; i >= 0; i--) {
                const p = particles[i]; p.update(); p.draw(fwCtx);
                if (p.alpha <= 0) particles.splice(i, 1);
            }
            requestAnimationFrame(animateFireworks);
        }
        animateFireworks();

        // --- CORPORATE CARD GENERATOR ---
        const canvas = document.getElementById('cardCanvas');
        const ctx = canvas.getContext('2d');
        const nameInput = document.getElementById('senderName');
        const companyInput = document.getElementById('companyName'); 
        const messageSelect = document.getElementById('messageSelect');
        const logoInput = document.getElementById('logoUpload');
        
        let themeMain = '#b38728'; // Gold Dark
        let themeAccent = '#fcf6ba'; // Gold Light
        let uploadedLogo = null; // Store image object

        function changeTheme(main, accent) {
            themeMain = main;
            themeAccent = accent;
            updateCanvas();
        }

        // Handle Image Upload
        function handleLogoUpload(input) {
            const file = input.files[0];
            if (file) {
                document.getElementById('logoFileName').innerText = file.name.substring(0, 20) + (file.name.length > 20 ? '...' : '');
                
                const reader = new FileReader();
                reader.onload = function(e) {
                    const img = new Image();
                    img.onload = function() {
                        uploadedLogo = img;
                        updateCanvas();
                    }
                    img.src = e.target.result;
                }
                reader.readAsDataURL(file);
            }
        }

        function wrapText(context, text, x, y, maxWidth, lineHeight) {
            if(!text) return;
            var words = text.split(' ');
            var line = '';
            var lines = [];
            for(var n = 0; n < words.length; n++) {
                var testLine = line + words[n] + ' ';
                var metrics = context.measureText(testLine);
                if (metrics.width > maxWidth && n > 0) { lines.push(line); line = words[n] + ' '; }
                else { line = testLine; }
            }
            lines.push(line);
            let startY = y - ((lines.length - 1) * lineHeight) / 2;
            for (var k = 0; k < lines.length; k++) { context.fillText(lines[k], x, startY + (k * lineHeight)); }
        }

        function updateCanvas() {
            const width = canvas.width;
            const height = canvas.height;
            const name = nameInput.value.trim() ? nameInput.value : "Nama Anda";
            const company = companyInput.value.trim() ? companyInput.value.toUpperCase() : ""; // Company Name
            const message = messageSelect.value;

            // 1. Background (Elegant Dark Gradient)
            const grd = ctx.createLinearGradient(0, 0, width, height);
            grd.addColorStop(0, "#0f172a"); grd.addColorStop(1, "#020617");
            ctx.fillStyle = grd; ctx.fillRect(0, 0, width, height);

            // 2. Pattern Overlay (Dots)
            ctx.fillStyle = "rgba(255,255,255,0.03)";
            for(let i=0; i<width; i+=40) {
                for(let j=0; j<height; j+=40) {
                    ctx.beginPath(); ctx.arc(i, j, 2, 0, Math.PI*2); ctx.fill();
                }
            }

            // 3. Elegant Border
            ctx.lineWidth = 4; ctx.strokeStyle = themeMain; 
            ctx.strokeRect(50, 50, width - 100, height - 100);
            
            // Corner Accents
            ctx.lineWidth = 15;
            ctx.beginPath();
            ctx.moveTo(50, 150); ctx.lineTo(50, 50); ctx.lineTo(150, 50); // Top Left
            ctx.moveTo(width-50, 150); ctx.lineTo(width-50, 50); ctx.lineTo(width-150, 50); // Top Right
            ctx.moveTo(50, height-150); ctx.lineTo(50, height-50); ctx.lineTo(150, height-50); // Bottom Left
            ctx.moveTo(width-50, height-150); ctx.lineTo(width-50, height-50); ctx.lineTo(width-150, height-50); // Bottom Right
            ctx.stroke();

            // Text Setup
            ctx.textAlign = "center";

            // LOGO RENDER (Top Center)
            if (uploadedLogo) {
                // Calculate Aspect Ratio to fit in 150x150 box
                const maxDim = 150;
                let logoW = uploadedLogo.width;
                let logoH = uploadedLogo.height;
                const ratio = Math.min(maxDim / logoW, maxDim / logoH);
                logoW = logoW * ratio;
                logoH = logoH * ratio;
                
                ctx.drawImage(uploadedLogo, (width/2) - (logoW/2), 120, logoW, logoH);
            } else {
                 // Placeholder Bismillah if no logo
                ctx.font = "50px 'Amiri'"; ctx.fillStyle = themeAccent; 
                ctx.fillText("بِسْمِ ٱللَّٰهِ ٱلرَّحْمَٰنِ ٱلرَّحِيمِ", width / 2, 200);
            }

            // "SELAMAT TAHUN BARU"
            // Push text down slightly if logo exists
            const textOffset = uploadedLogo ? 50 : 0;
            
            ctx.font = "bold 80px 'Cinzel'"; ctx.fillStyle = "#ffffff";
            ctx.fillText("SELAMAT TAHUN BARU", width / 2, 350 + textOffset);

            // Year 2026 (Large Watermark Style)
            ctx.font = "bold 250px 'Cinzel'"; 
            ctx.fillStyle = themeMain; ctx.globalAlpha = 0.15;
            ctx.fillText("2026", width / 2, 580 + textOffset);
            ctx.globalAlpha = 1.0;

            // Message
            ctx.font = "italic 45px 'Playfair Display'"; ctx.fillStyle = "#cbd5e1";
            wrapText(ctx, '"' + message + '"', width / 2, 600 + textOffset, width - 250, 70);

            // Line Separator
            ctx.beginPath(); ctx.moveTo(width/2 - 100, 750 + textOffset); ctx.lineTo(width/2 + 100, 750 + textOffset);
            ctx.strokeStyle = themeMain; ctx.lineWidth = 2; ctx.stroke();

            // Sender Details
            ctx.font = "30px 'Cinzel'"; ctx.fillStyle = "#94a3b8"; 
            ctx.fillText("IKHLAS DARIPADA:", width / 2, 820 + textOffset);

            // Name
            ctx.font = "bold 70px 'Cinzel'"; ctx.fillStyle = themeAccent;
            ctx.fillText(name, width / 2, 900 + textOffset);
            
            // Company Name (If exists)
            if (company) {
                ctx.font = "40px 'Plus Jakarta Sans'"; ctx.fillStyle = "#ffffff";
                ctx.fillText(company, width / 2, 960 + textOffset);
            }
        }

        function downloadCard() {
            const link = document.createElement('a');
            const name = document.getElementById('senderName').value || 'korporat';
            link.download = 'kad-tahun-baru-' + name + '.png';
            link.href = canvas.toDataURL("image/png");
            link.click();
        }

        document.fonts.ready.then(function () { updateCanvas(); });
        updateCanvas();
    </script>
</body>
</html>
