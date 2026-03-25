<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Variety Catering & Events | Premium Digital Menu</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@700;800&family=Inter:wght@400;500;600&display=swap" rel="stylesheet">
    
    <style>
        :root {
            --accent-orange: #f59e0b;
            --glass-bg: rgba(255, 255, 255, 0.03);
            --orange-glow: linear-gradient(145deg, rgba(245, 158, 11, 0.15), rgba(0, 0, 0, 0.95));
        }

        body { 
            font-family: 'Inter', sans-serif; 
            background: #080808; 
            color: #efefef; 
            margin: 0; 
            overflow-x: hidden; 
            scroll-behavior: smooth; 
        }

        h1, h2, h3 { font-family: 'Poppins', sans-serif; }

        /* Modern Glassmorphism */
        .glass-premium { 
            background: var(--glass-bg); 
            backdrop-filter: blur(15px); 
            -webkit-backdrop-filter: blur(15px);
            border: 1px solid rgba(255, 255, 255, 0.08); 
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.4);
        }

        /* Gradient Glow Card */
        .glow-card {
            background: var(--orange-glow);
            border: 1px solid rgba(245, 158, 11, 0.2);
            box-shadow: 0 10px 40px rgba(245, 158, 11, 0.15);
        }

        /* Visual Menu Cards */
        .visual-card { 
            height: 240px; 
            position: relative; 
            border-radius: 32px; 
            overflow: hidden; 
            margin-bottom: 24px; 
            cursor: pointer;
            border: 1px solid rgba(255,255,255,0.05);
            transition: 0.5s cubic-bezier(0.4, 0, 0.2, 1);
        }
        .visual-card img { width: 100%; height: 100%; object-fit: cover; filter: brightness(0.4); transition: 0.8s; }
        .visual-card:hover img { transform: scale(1.1); filter: brightness(0.6); }

        /* Animations */
        @keyframes floating { 0%, 100% { transform: translateY(0); } 50% { transform: translateY(-12px); } }
        .animate-float { animation: floating 6s ease-in-out infinite; }

        .intro-screen { position: fixed; inset: 0; z-index: 999; background: #000; display: flex; align-items: center; justify-content: center; transition: 0.8s; }
        .page-content { display: none; padding-bottom: 120px; min-height: 100vh; }
        .active-page { display: block !important; animation: fadeIn 0.6s ease-out; }

        .back-btn { background: rgba(255, 255, 255, 0.05); padding: 12px 20px; border-radius: 18px; font-weight: 600; display: inline-flex; align-items: center; gap: 8px; margin-bottom: 30px; border: 1px solid rgba(255,255,255,0.1); }
        .no-scrollbar::-webkit-scrollbar { display: none; }

        /* Item Cards */
        .item-card { background: rgba(255,255,255,0.03); border-radius: 24px; padding: 24px; margin-bottom: 16px; border-left: 3px solid var(--accent-orange); transition: 0.3s; }
        .item-card:hover { background: rgba(255,255,255,0.06); transform: translateX(5px); }
    </style>
</head>
<body>

    <div id="intro-page" class="intro-screen flex-col text-center p-6">
        <div class="animate__animated animate__fadeIn">
            <h1 class="text-6xl font-black tracking-tighter text-white mb-2">VARIETY</h1>
            <div class="h-1 w-12 bg-orange-500 mx-auto mb-4"></div>
            <p class="text-[9px] tracking-[0.8em] text-gray-500 uppercase font-medium">Taste of Traditions</p>
        </div>
        <button onclick="startExperience()" class="mt-24 glass-premium text-white px-12 py-4 rounded-full font-bold tracking-widest text-xs border border-orange-500/20 active:scale-95 transition-all">
            EXPLORE MENU
        </button>
    </div>

    <div id="main-app" class="hidden">
        
        <header class="p-6 flex justify-between items-center sticky top-0 z-50 bg-black/80 backdrop-blur-xl border-b border-white/5">
            <h1 class="text-xl font-black text-white tracking-tighter">VARIETY<span class="text-orange-500">.</span></h1>
            <div class="flex gap-6">
                <a href="tel:918594060114" class="text-gray-400 hover:text-orange-500 transition-colors"><i class="fas fa-phone-alt"></i></a>
                <a href="https://wa.me/918594060114" class="bg-orange-500/10 text-orange-500 px-4 py-2 rounded-xl text-sm font-bold border border-orange-500/20">Chat</a>
            </div>
        </header>

        <main id="home-page" class="page-content active-page p-6">
            <div class="mb-10 mt-4">
                <p class="text-orange-500 text-[10px] tracking-[0.4em] font-bold uppercase mb-2">Since 1996</p>
                <h2 class="text-4xl font-black text-white leading-tight">Digital <span class="text-gray-500 italic">Curated</span> Menu</h2>
            </div>
            
            <div class="visual-card" onclick="navigateTo('drinks-page')">
                <img src="https://images.unsplash.com/photo-1513558161293-cdaf765ed2fd?w=800">
                <div class="absolute inset-0 bg-gradient-to-t from-black/90 to-transparent"></div>
                <div class="absolute bottom-6 left-6"><h3 class="text-2xl font-bold">Welcome Drinks</h3><div class="h-0.5 w-8 bg-orange-500 mt-1"></div></div>
            </div>

            <div class="visual-card" onclick="navigateTo('main-page')">
                <img src="https://images.unsplash.com/photo-1589302168068-964664d93dc0?w=800">
                <div class="absolute inset-0 bg-gradient-to-t from-black/90 to-transparent"></div>
                <div class="absolute bottom-6 left-6"><h3 class="text-2xl font-bold">Main Course</h3><div class="h-0.5 w-8 bg-orange-500 mt-1"></div></div>
            </div>

            <div class="visual-card" onclick="navigateTo('live-page')">
                <img src="https://images.unsplash.com/photo-1594631252845-29fc4586c567?w=800">
                <div class="absolute inset-0 bg-gradient-to-t from-black/90 to-transparent"></div>
                <div class="absolute bottom-6 left-6"><h3 class="text-2xl font-bold">Live Counters</h3><div class="h-0.5 w-8 bg-orange-500 mt-1"></div></div>
            </div>

            <section class="mt-12">
                <div class="glow-card p-10 rounded-[40px] text-center animate-float">
                    <span class="text-5xl text-orange-500/30 block mb-4 font-serif italic">“</span>
                    <p class="text-lg leading-relaxed text-gray-200 font-medium italic mb-8 leading-relaxed">
                        "ഏറ്റവും മികച്ച രുചിയും, കുടുംബത്തിന്റെ സ്നേഹവും ചേർന്ന അനുഭവം നിങ്ങൾക്ക് സമ്മാനിക്കാൻ സാധിക്കുന്നതിൽ ഞങ്ങൾ അതിയായി സന്തോഷിക്കുന്നു."
                    </p>
                    <h4 class="text-lg font-extrabold tracking-widest text-white uppercase">Shihab</h4>
                    <p class="text-[9px] text-orange-500 font-bold tracking-[0.3em] uppercase">Variety Catering & Events</p>
                </div>
            </section>

            <section class="mt-16">
                <h3 class="text-2xl font-black mb-8">Guest <span class="text-gray-500 italic">Feedback</span></h3>
                <div class="flex overflow-x-auto gap-4 pb-6 no-scrollbar">
                    <div class="min-w-[280px] glass-premium p-8 rounded-[35px]">
                        <p class="text-sm text-gray-400 italic mb-4">"Nalla tasty food aayirunnu. Variety-ne trust cheyyaam!"</p>
                        <h5 class="text-[10px] font-bold text-white uppercase tracking-widest">— Rahul K</h5>
                    </div>
                    <div class="min-w-[280px] glass-premium p-8 rounded-[35px]">
                        <p class="text-sm text-gray-400 italic mb-4">"Live counter biryani poli aanu. Professional service."</p>
                        <h5 class="text-[10px] font-bold text-white uppercase tracking-widest">— Ameer</h5>
                    </div>
                </div>
                <button onclick="navigateTo('reviews-page')" class="w-full mt-4 py-4 glass-premium rounded-2xl text-[10px] font-bold tracking-[0.3em] text-orange-500 uppercase">Read All Stories <i class="fas fa-arrow-right ml-2"></i></button>
            </section>
        </main>

        <section id="drinks-page" class="page-content p-6">
            <button onclick="navigateTo('home-page')" class="back-btn"><i class="fas fa-chevron-left text-xs"></i> BACK</button>
            <h2 class="text-4xl font-black mb-8 text-white">Welcome <span class="text-orange-500">Drinks</span></h2>
            <div class="item-card"><h4 class="font-bold text-lg mb-1">Mint Lime Cooler</h4><p class="text-xs text-gray-500">Refreshing mint and lime blend.</p></div>
            <div class="item-card"><h4 class="font-bold text-lg mb-1">Blue Curacao Punch</h4><p class="text-xs text-gray-500">Premium tropical experience.</p></div>
        </section>

        <section id="main-page" class="page-content p-6">
            <button onclick="navigateTo('home-page')" class="back-btn"><i class="fas fa-chevron-left text-xs"></i> BACK</button>
            <h2 class="text-4xl font-black mb-8 text-white">Main <span class="text-orange-500">Course</span></h2>
            <div class="item-card"><h4 class="font-bold text-lg mb-1">Chicken Lagoon Biryani</h4><p class="text-xs text-gray-500">Our signature premium biryani.</p></div>
            <div class="item-card"><h4 class="font-bold text-lg mb-1">Beef Surbiyan</h4><p class="text-xs text-gray-500">Authentic Arabian style beef.</p></div>
        </section>

        <section id="live-page" class="page-content p-6">
            <button onclick="navigateTo('home-page')" class="back-btn"><i class="fas fa-chevron-left text-xs"></i> BACK</button>
            <h2 class="text-4xl font-black mb-8 text-white">Live <span class="text-orange-500">Counters</span></h2>
            <div class="item-card"><h4 class="font-bold text-lg mb-1">Live Porotta</h4><p class="text-xs text-gray-500">Freshly made hot porottas.</p></div>
            <div class="item-card"><h4 class="font-bold text-lg mb-1">Live Tea Station</h4><p class="text-xs text-gray-500">8 varieties of special tea.</p></div>
        </section>

        <section id="reviews-page" class="page-content p-6">
            <button onclick="navigateTo('home-page')" class="back-btn"><i class="fas fa-chevron-left text-xs"></i> BACK</button>
            <h2 class="text-4xl font-black mb-10 text-white">Guest <span class="text-orange-500">Journal</span></h2>
            <div class="glow-card p-8 rounded-[35px] mb-10 text-center">
                <p class="text-sm text-gray-300 mb-6 font-medium italic">"Ningalude abhiprayam njangalkku valare vilappettathaanu."</p>
                <a href="https://wa.me/918594060114?text=Hi Variety Catering, my feedback is: " class="flex items-center justify-center gap-3 bg-orange-500 text-black py-4 rounded-2xl font-black text-xs tracking-widest uppercase"><i class="fab fa-whatsapp text-lg"></i> SEND FEEDBACK</a>
            </div>
            <div class="space-y-6">
                <div class="glass-premium p-8 rounded-[35px] border-l-2 border-orange-500">
                    <p class="text-sm text-gray-300 italic mb-4 leading-relaxed">"Variety-ne trust cheyyaam! Professionalism at its best. Food nalla tasty aayirunnu."</p>
                    <h5 class="text-[10px] font-bold text-white uppercase tracking-widest">— Rahul K, Kozhikode</h5>
                </div>
            </div>
        </section>

        <section id="about-page" class="page-content p-6">
            <button onclick="navigateTo('home-page')" class="back-btn"><i class="fas fa-chevron-left text-xs"></i> BACK</button>
            <h2 class="text-3xl font-black mb-8 text-white">Our <span class="text-orange-500">Location</span></h2>
            <div class="glass-premium p-8 rounded-[2.5rem] mb-6 border-l-4 border-orange-500 shadow-2xl">
                <h4 class="font-bold text-2xl mb-2">Variety Catering</h4>
                <p class="text-gray-400 text-lg leading-snug">Karuvanpoyil, Koduvally,<br>Kozhikode, Kerala.</p>
                <div class="mt-8 flex gap-4">
                    <a href="tel:918594060114" class="flex-1 bg-orange-600 py-4 rounded-2xl font-bold flex items-center justify-center gap-2"><i class="fas fa-phone-alt"></i> Call</a>
                    <a href="https://wa.me/918594060114" class="flex-1 bg-green-600 py-4 rounded-2xl font-bold flex items-center justify-center gap-2"><i class="fab fa-whatsapp"></i> Chat</a>
                </div>
            </div>
        </section>

        <nav class="fixed bottom-8 left-8 right-8 h-20 glass-premium rounded-[32px] flex items-center justify-around z-[100] border-white/10 shadow-2xl">
            <button onclick="navigateTo('home-page')" class="text-xl text-orange-500"><i class="fas fa-home"></i></button>
            <button onclick="navigateTo('about-page')" class="text-xl text-gray-500"><i class="fas fa-map-marker-alt"></i></button>
            <a href="https://wa.me/918594060114" class="text-xl text-green-500 animate-bounce"><i class="fab fa-whatsapp"></i></a>
        </nav>
    </div>

    <script>
        function startExperience() {
            const intro = document.getElementById('intro-page');
            const main = document.getElementById('main-app');
            intro.style.opacity = '0';
            setTimeout(() => {
                intro.style.display = 'none';
                main.classList.remove('hidden');
                main.classList.add('animate__animated', 'animate__fadeIn');
            }, 800);
        }

        function navigateTo(pageId) {
            document.querySelectorAll('.page-content').forEach(p => p.classList.remove('active-page'));
            const target = document.getElementById(pageId);
            if(target) {
                target.classList.add('active-page');
                window.scrollTo({ top: 0, behavior: 'smooth' });
            }
        }
    </script>
</body>
</html>
