<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>Md. Tasneem Al-Huzaifa Miraj | Web Developer & Da'i</title>
    <!-- Google Fonts & Font Awesome -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,600;14..32,700&family=Cairo:wght@400;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: #0A0C10;
            font-family: 'Inter', 'Cairo', sans-serif;
            color: #E5E9F0;
            line-height: 1.5;
            scroll-behavior: smooth;
        }

        /* main container */
        .github-profile {
            max-width: 1400px;
            margin: 0 auto;
            padding: 2rem 1.5rem;
        }

        /* gradient divider reusable */
        .gradient-divider {
            background: linear-gradient(90deg, transparent, #2D9C7A, #FF6B6B, #2D9C7A, transparent);
            height: 3px;
            width: 100%;
            margin: 2rem 0;
            border-radius: 3px;
            animation: shimmer 3s infinite;
        }

        @keyframes shimmer {
            0% { background-position: -200%; }
            100% { background-position: 200%; }
            background-size: 200% auto;
        }

        /* ========== ANIMATIONS ========== */
        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-12px); }
            100% { transform: translateY(0px); }
        }
        @keyframes pulse {
            0% { transform: scale(1); box-shadow: 0 0 0 0 rgba(45, 156, 122, 0.4);}
            70% { transform: scale(1.02); box-shadow: 0 0 0 12px rgba(45, 156, 122, 0);}
            100% { transform: scale(1); box-shadow: 0 0 0 0 rgba(45, 156, 122, 0);}
        }
        @keyframes glowText {
            0% { text-shadow: 0 0 2px #2D9C7A; }
            50% { text-shadow: 0 0 14px #2D9C7A, 0 0 6px #FF6B6B; }
            100% { text-shadow: 0 0 2px #2D9C7A; }
        }
        @keyframes slideIn {
            from { transform: translateX(40px); opacity: 0; }
            to { transform: translateX(0); opacity: 1; }
        }
        @keyframes fadeInLeft {
            from { opacity: 0; transform: translateX(-35px);}
            to { opacity: 1; transform: translateX(0);}
        }
        @keyframes fadeInRight {
            from { opacity: 0; transform: translateX(35px);}
            to { opacity: 1; transform: translateX(0);}
        }
        @keyframes bounce {
            0%,100%{ transform: translateY(0);}
            50%{ transform: translateY(-8px);}
        }
        @keyframes borderGlow {
            0% { border-left-color: #2D9C7A; box-shadow: 0 0 2px #2D9C7A;}
            50% { border-left-color: #FF6B6B; box-shadow: 0 0 14px rgba(255,107,107,0.4);}
            100% { border-left-color: #2D9C7A; box-shadow: 0 0 2px #2D9C7A;}
        }

        .float-animation { animation: float 4s ease-in-out infinite; }
        .pulse-border { animation: pulse 2.5s infinite; }
        .glow-animation { animation: glowText 2.2s ease-in-out infinite; }
        .slidein-card { animation: slideIn 0.6s ease-out; }
        .fade-left { animation: fadeInLeft 0.7s ease forwards; }
        .fade-right { animation: fadeInRight 0.7s ease forwards; }
        .bounce-hover { transition: transform 0.2s; display: inline-block; }
        .bounce-hover:hover { animation: bounce 0.5s ease; }

        /* Profile picture container */
        .profile-img-wrapper {
            display: flex;
            justify-content: center;
            align-items: center;
        }
        .profile-pic {
            width: 200px;
            height: 200px;
            object-fit: cover;
            border-radius: 50%;
            border: 4px solid #2D9C7A;
            box-shadow: 0 10px 25px -5px rgba(0,0,0,0.5);
            transition: all 0.3s;
        }

        /* responsive table / grid */
        .info-table {
            display: flex;
            flex-wrap: wrap;
            gap: 2rem;
            background: #11151C;
            border-radius: 28px;
            padding: 1.8rem;
            backdrop-filter: blur(2px);
            border: 1px solid #2D9C7A30;
        }
        .info-col {
            flex: 1;
            min-width: 260px;
        }
        .bio-text {
            text-align: justify;
            font-size: 1rem;
            color: #CDD9F0;
        }

        /* tech badges container */
        .tech-badge {
            display: inline-flex;
            align-items: center;
            gap: 6px;
            background: #1E2432;
            padding: 0.4rem 1rem;
            border-radius: 40px;
            font-size: 0.85rem;
            font-weight: 500;
            margin: 6px;
            transition: all 0.2s;
            border: 1px solid #2D9C7A40;
        }
        .tech-badge i {
            font-size: 1rem;
        }
        .tech-badge:hover {
            transform: translateY(-3px);
            background: #2D9C7A20;
            border-color: #2D9C7A;
        }

        /* routine cards */
        .routine-card {
            background: #11161f;
            border-radius: 24px;
            padding: 1.2rem;
            border: 1px solid #2D9C7A30;
            transition: all 0.2s;
        }
        .routine-card:hover {
            border-color: #2D9C7A;
            box-shadow: 0 10px 20px -5px #00000050;
        }
        .routine-list {
            list-style: none;
            margin-top: 1rem;
        }
        .routine-list li {
            margin: 0.75rem 0;
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 0.9rem;
        }

        /* blockquote */
        .verse-block {
            background: #0F131A;
            border-left: 5px solid #2D9C7A;
            padding: 1.4rem;
            border-radius: 20px;
            margin: 1.5rem 0;
            animation: borderGlow 3s infinite;
        }

        /* stats container */
        .stats-grid {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 1.2rem;
            margin: 1.5rem 0;
        }
        .stat-card {
            background: #0E121B;
            border-radius: 20px;
            padding: 0.6rem;
            transition: all 0.2s;
        }
        .stat-card img {
            max-width: 100%;
            border-radius: 14px;
        }

        /* social icons */
        .social-link {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            background: #1A1F2A;
            padding: 0.6rem 1.2rem;
            border-radius: 60px;
            margin: 0 0.4rem 0.8rem;
            transition: all 0.2s;
            color: #E5E9F0;
            text-decoration: none;
            font-weight: 500;
        }
        .social-link:hover {
            background: #2D9C7A;
            color: #0A0C10;
            transform: translateY(-3px);
        }

        /* footer animation */
        .footer-glow {
            text-align: center;
            margin-top: 2rem;
        }

        @media (max-width: 780px) {
            .github-profile { padding: 1rem; }
            .info-table { flex-direction: column; }
            .profile-pic { width: 140px; height: 140px; }
        }

        /* custom badge style for live counters */
        .badge-live {
            background: #0E121B;
            border-radius: 30px;
            padding: 0.2rem 0.9rem;
            font-size: 0.8rem;
            font-weight: 600;
        }

        h2, h3 {
            font-weight: 600;
            letter-spacing: -0.3px;
        }
        .arabic-text {
            font-family: 'Cairo', sans-serif;
            font-size: 1.2rem;
        }
        a {
            text-decoration: none;
        }
    </style>
</head>
<body>
<div class="github-profile">
    <!-- waving header with gradient text effect -->
    <div align="center">
        <img src="https://capsule-render.vercel.app/api?type=waving&height=220&color=gradient&text=MD%20TASNEM&fontAlign=50&fontAlignY=32&desc=Web%20Developer%20%7C%20Da'i%20%7C%20Arabic%20Literature%20Student&descAlign=50&descAlignY=52&animation=fadeIn&fontColor=ffffff" width="100%" alt="capsule header"/>
    </div>

    <!-- Multiple typing animations (recreated with static but smooth svg style) -->
    <div align="center" style="margin: 25px 0 10px;">
        <img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&weight=600&size=24&duration=2200&pause=500&color=2D9C7A&center=true&vCenter=true&width=750&lines=🚀+Full-Stack+Web+Developer;📚+Arabic+Literature+Scholar;🕋+Da'i+%26+Servant+of+Islam;🌍+Building+Bridge+Between+Islam+%26+Tech;💡+رَبِّ+زِدْنِي+عِلْمًا;⚡+Code+for+Allah's+Pleasure;🎯+Serving+the+Ummah" alt="typing1"/>
    </div>
    <div align="center">
        <img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&size=18&duration=2800&pause=700&color=FF6B6B&center=true&vCenter=true&width=650&lines=%22My+Lord%2C+increase+me+in+knowledge%22;%22Indeed%2C+prayer+prohibits+immorality%22;%22The+best+of+you+learn+the+Quran%22" alt="typing2"/>
    </div>

    <div class="gradient-divider"></div>

    <!-- Profile info with floating effect -->
    <div class="info-table">
        <div class="info-col" align="center">
            <div class="float-animation">
                <img class="profile-pic pulse-border" src="https://scontent.fird6-1.fna.fbcdn.net/v/t39.30808-6/668103074_980476521161596_7089596423633522897_n.jpg?_nc_cat=108&ccb=1-7&_nc_sid=1d70fc&_nc_ohc=aYCN3peWu1IQ7kNvwHd0lVf&_nc_oc=AdpBhqHj0qBEiGBLU1mS36PdV51WRGhh0sHccJOFsqAQh2uvZ1aKe1PnPOGuAMhGO1A&_nc_zt=23&_nc_ht=scontent.fird6-1.fna&_nc_gid=CfGTkDCfEKxaZDWs6VZ7jg&_nc_ss=7a3a8&oh=00_Af3dqB33x4H4S4bsHfrSgGeH3Fb_HpkwaARgLQeRs4VYZQ&oe=69E7CD35" alt="Tasneem profile"/>
            </div>
            <h2 class="glow-animation" style="margin-top: 1rem;">🎓 رَبِّ زِدْنِي عِلْمًا</h2>
            <h3>"My Lord, increase me in knowledge"</h3>
            <h4>Md. Tasneem Al-Huzaifa Miraj</h4>
            <p><b>Web Developer | Da'i | Arabic Literature Student</b></p>
            <img src="https://img.shields.io/badge/STATUS-ACTIVE-2D9C7A?style=for-the-badge&logo=github&logoColor=white&labelColor=0A0A0A" alt="status"/>
        </div>
        <div class="info-col slidein-card">
            <p class="bio-text"><b>Md. Tasneem Al-Huzaifa Miraj</b> was born in Barisal district. He completed his eighth grade from Darus Sunnat Kamil Madrasa, Charchina. Later, he passed the Dakhil and Alim exams from N.S. Kamil Madrasa, Jhalakathi. 
            <br><br>
            Currently, he is studying in the <b>Department of Arabic Language and Literature</b> at the Islamic University of Kushtia. Skilled in web development: HTML, CSS, JavaScript, React, MongoDB, Firebase, NodeJS, Next.js, Git, GitHub, Tailwind CSS. 
            <br><br>
            His life's goal is to serve the <b>Ummah</b> through a combination of religious knowledge and modern technology.
            <br><br>
            📍 <b>Address:</b> Islamic University, Kushtia, Bangladesh.<br>
            📞 <b>Contact:</b> +8801330989762<br>
            📧 <b>Email:</b> tasnimmuhammad51@gmail.com
            </p>
            <div align="center" style="margin-top: 20px;">
                <a href="#"><img src="https://img.shields.io/badge/📄_View_Full_CV-2D9C7A?style=for-the-badge&logo=readthedocs&logoColor=white" alt="CV"/></a>
                <a href="mailto:tasnimmuhammad51@gmail.com"><img src="https://img.shields.io/badge/📧_Professional_Contact-0077B5?style=for-the-badge&logo=email&logoColor=white" alt="Contact"/></a>
                <a href="#"><img src="https://img.shields.io/badge/⬇️_Download_Resume-FF6B6B?style=for-the-badge&logo=download&logoColor=white" alt="Resume"/></a>
            </div>
        </div>
    </div>

    <div class="gradient-divider"></div>

    <!-- Live Statistics area with spotify and profile cards -->
    <div align="center">
        <h2>📊 <b>LIVE STATISTICS</b> 📊</h2>
        <img src="https://spotify-github-profile.vercel.app/api/view?uid=31j2zmg63mey7zowj6nzg2clz3na&cover_image=true&theme=default&show_offline=false&background_color=121212&interchange=false" width="300" alt="spotify"/>
        <br/><br/>
        <div class="stats-grid">
            <div class="stat-card"><img src="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=MD-TASNEM&theme=github_dark" width="500" alt="summary"/></div>
        </div>
    </div>

    <div class="gradient-divider"></div>

    <!-- Biography with blockquote -->
    <div align="center">
        <h2>📜 My Biography</h2>
        <div class="verse-block">
            <p align="center"><i>“Who knew except Allah that a sick boy born in the lap of a sick mother would have such a long life? By the infinite mercy of Allah, so many years have passed. After passing through every stage of mother's death, aunt's shadow, father's family responsibilities, maktab-madrasa, today I want to become a web developer and servant of religion.”</i></p>
        </div>
    </div>

    <div class="info-table" style="margin-top: 0;">
        <div class="info-col fade-left">
            <h3>👨‍👧 Family Legacy</h3>
            <p><b>Father:</b> Born during independence, fatherless at a young age, managed the family on his own initiative.</p>
            <p><b>Mother:</b> A noble woman, passed away while pregnant, leaving me behind. Today I am moving forward with their memories.</p>
            <p><b>Father's Contribution:</b> Protection of property, opportunity to study in madrasa and education of self-reliance.</p>
            <p><b>Memory of my mother:</b> A plea at my mother's grave, which strengthened me on the path of religion.</p>
        </div>
        <div class="info-col fade-right">
            <h3>📚 Educational Journey</h3>
            <p>From maktab to hefaz, from dakhil to alim, I studied with utmost dedication. By the grace of Allah, today I am striving to build a bridge between Islam and technology.</p>
            <p>🎯 <b>Mission:</b> To play an effective role in the welfare of religious institutions and society through a combination of Arabic language and web development. Create Islamic content and da'wah platforms using modern tech.</p>
        </div>
    </div>

    <div class="gradient-divider"></div>

    <!-- Life Timeline animated badges -->
    <div align="center">
        <h2>📖 <b>LIFE TIMELINE</b> 📖</h2>
        <div style="display: flex; justify-content: center; gap: 15px; flex-wrap: wrap; margin: 1rem 0;">
            <div class="bounce-hover"><img src="https://img.shields.io/badge/📚_MAKTAB-Bayatibari_Masjid-FF6B6B?style=for-the-badge"/></div>
            <div class="bounce-hover"><img src="https://img.shields.io/badge/⭐_NOORANI-Dharalia_Noorani-4ECDC4?style=for-the-badge"/></div>
            <div class="bounce-hover"><img src="https://img.shields.io/badge/🕋_HAFIZ-5_Para_Achievement-45B7D1?style=for-the-badge"/></div>
            <div class="bounce-hover"><img src="https://img.shields.io/badge/📖_5TH-7TH-Khodabakhsa_Dakhil-96CEB4?style=for-the-badge"/></div>
            <div class="bounce-hover"><img src="https://img.shields.io/badge/✨_8TH_GRADE-Charchina_Alia-FFEAA7?style=for-the-badge"/></div>
            <div class="bounce-hover"><img src="https://img.shields.io/badge/🎓_DAKHIL-ALIM-Jhalkathi_NS-DFE6E9?style=for-the-badge"/></div>
            <div class="bounce-hover"><img src="https://img.shields.io/badge/🏛️_HONORS-Islamic_University-81ECEC?style=for-the-badge"/></div>
        </div>
    </div>

    <div class="gradient-divider"></div>

    <!-- Tech Stack -->
    <div align="center">
        <h2>💻 Tech Stack (Animated)</h2>
        <div style="margin: 1rem 0;">
            <div><h3>🚀 Frontend</h3>
                <div><span class="tech-badge"><i class="fab fa-html5"></i> HTML5</span>
                <span class="tech-badge"><i class="fab fa-css3-alt"></i> CSS3</span>
                <span class="tech-badge"><i class="fab fa-js"></i> JavaScript</span>
                <span class="tech-badge"><i class="fab fa-react"></i> React</span>
                <span class="tech-badge"><i class="fab fa-node-js"></i> Next.js</span>
                <span class="tech-badge"><i class="fab fa-tailwind"></i> Tailwind</span></div>
            </div>
            <div><h3>⚙️ Backend & DB</h3>
                <div><span class="tech-badge"><i class="fab fa-node"></i> Node.js</span>
                <span class="tech-badge"><i class="fas fa-code-branch"></i> Express</span>
                <span class="tech-badge"><i class="fas fa-database"></i> MongoDB</span>
                <span class="tech-badge"><i class="fas fa-fire"></i> Firebase</span></div>
            </div>
            <div><h3>🛠️ Tools</h3>
                <div><span class="tech-badge"><i class="fab fa-git-alt"></i> Git</span>
                <span class="tech-badge"><i class="fab fa-github"></i> GitHub</span>
                <span class="tech-badge"><i class="fas fa-cloud"></i> Vercel</span>
                <span class="tech-badge"><i class="fas fa-paint-brush"></i> Figma</span>
                <span class="tech-badge"><i class="fas fa-code"></i> VS Code</span></div>
            </div>
        </div>
    </div>

    <div class="gradient-divider"></div>

    <!-- GitHub Analytics with Stats Cards -->
    <div align="center">
        <h2>📊 <b>GITHUB ANALYTICS</b> 📊</h2>
        <div style="display: flex; justify-content: center; gap: 18px; flex-wrap: wrap;">
            <img width="49%" src="https://github-readme-stats.vercel.app/api?username=MD-TASNEM&show_icons=true&count_private=true&hide_border=true&title_color=2D9C7A&icon_color=2D9C7A&text_color=c9d1d9&bg_color=0d1117&include_all_commits=true&rank_icon=github&theme=radical" alt="stats"/>
            <img width="41%" src="https://github-readme-stats.vercel.app/api/top-langs/?username=MD-TASNEM&layout=donut&hide_border=true&title_color=2D9C7A&text_color=c9d1d9&bg_color=0d1117&langs_count=6&theme=radical" alt="langs"/>
        </div>
        <div style="display: flex; justify-content: center; gap: 20px; flex-wrap: wrap; margin: 20px 0;">
            <img width="45%" src="https://nirzak-streak-stats.vercel.app/?user=MD-TASNEM&theme=dark&hide_border=true&stroke=2D9C7A&ring=2D9C7A&fire=2D9C7A&currStreakNum=2D9C7A&sideNums=2D9C7A&currStreakLabel=2D9C7A&sideLabels=2D9C7A&dates=2D9C7A&background=0d1117" alt="streak"/>
            <img width="45%" src="https://github-readme-activity-graph.vercel.app/graph?username=MD-TASNEM&theme=react-dark&bg_color=0d1117&hide_border=true&area=true&color=2D9C7A&line=2D9C7A&point=2D9C7A&area_color=2D9C7A&custom_title=Contribution%20Activity" alt="graph"/>
        </div>
        <div><img src="https://github-profile-trophy.vercel.app/?username=MD-TASNEM&theme=radical&no-frame=false&no-bg=true&margin-w=12&margin-h=12&column=4" width="800" alt="trophies"/></div>
    </div>

    <div class="gradient-divider"></div>

    <!-- Daily Routine (Animated) -->
    <div align="center">
        <h2>⏰ <b>DAILY ROUTINE (ANIMATED)</b> ⏰</h2>
        <div style="display: flex; flex-wrap: wrap; gap: 1.5rem; justify-content: center; margin-top: 1rem;">
            <div class="routine-card" style="flex:1; min-width: 240px;">
                <h3>🌙 Night Schedule</h3>
                <ul class="routine-list">
                    <li><i class="fas fa-moon"></i> Tahajjud: 3:00 – 3:30 AM</li>
                    <li><i class="fas fa-book"></i> Arabic Learning: 3:30 – Fajr</li>
                    <li><i class="fas fa-quran"></i> Quran Recitation: Fajr – 08:00</li>
                    <li><i class="fas fa-hadith"></i> Hadith Study: 08:00 – 10:30</li>
                    <li><i class="fas fa-utensils"></i> Meals & Rest: 10:30 – 12:00</li>
                </ul>
            </div>
            <div class="routine-card" style="flex:1; min-width: 240px;">
                <h3>☀️ Day Schedule</h3>
                <ul class="routine-list">
                    <li><i class="fas fa-landmark"></i> Islamic Literature: 12:15 – 01:15</li>
                    <li><i class="fas fa-utensils"></i> Meals & Zuhr: 01:15 – 02:15</li>
                    <li><i class="fas fa-language"></i> Bengali Learning: 02:15 – 03:15</li>
                    <li><i class="fas fa-language"></i> English Learning: 03:15 – Asr</li>
                    <li><i class="fas fa-dumbbell"></i> Mutaa'ala / Training: Asr – Isha</li>
                    <li><i class="fas fa-pen"></i> Daily Exam: Isha – 03:00 AM</li>
                </ul>
            </div>
            <div class="routine-card" style="flex:0.8;">
                <h3>🍽️ Meals</h3>
                <ul class="routine-list">
                    <li>🍯 Morning: Honey + Dates</li>
                    <li>🍗 Afternoon: Protein Rich</li>
                    <li>🥛 Night: Milk + Bread</li>
                </ul>
                <img src="https://media.giphy.com/media/l0HlNaZ6zLfV6HnFe/giphy.gif?cid=790b7611hjvt1ukkj3v8il2tfn5f3u48y1j5dop2xj3d2d6r&ep=v1_gifs_search&rid=giphy.gif&ct=g" width="80" alt="food" style="border-radius: 20px;"/>
            </div>
        </div>
    </div>

    <div class="gradient-divider"></div>

    <!-- Quotes & Inspiration -->
    <div align="center">
        <h2>💡 <b>DAILY INSPIRATION</b> 💡</h2>
        <img src="https://quotes-github-readme.vercel.app/api?type=horizontal&theme=radical" alt="quote"/>
        <div style="margin: 1rem;"><img src="https://readme-jokes.vercel.app/api?theme=radical" width="500" alt="joke"/></div>
    </div>

    <div class="gradient-divider"></div>

    <!-- Connect with me -->
    <div align="center">
        <h2>🌐 <b>CONNECT WITH ME</b> 🌐</h2>
        <div>
            <a class="social-link bounce-hover" href="https://facebook.com/https://www.facebook.com/profile.php?id=61574382370566"><i class="fab fa-facebook-f"></i> Facebook</a>
            <a class="social-link bounce-hover" href="https://linkedin.com/in/https://www.linkedin.com/in/md-tasnem-%E0%A6%AE%E0%A6%BF%E0%A6%B0%E0%A6%BE%E0%A6%9C-161201294/"><i class="fab fa-linkedin-in"></i> LinkedIn</a>
            <a class="social-link bounce-hover" href="https://youtube.com/@https://www.youtube.com/@%E0%A6%AE%E0%A7%8B%E0%A6%83%E0%A6%A4%E0%A6%BE%E0%A6%B8%E0%A6%A8%E0%A6%BF%E0%A6%AE%E0%A6%AE%E0%A6%BF%E0%A6%B0%E0%A6%BE%E0%A6%9C"><i class="fab fa-youtube"></i> YouTube</a>
            <a class="social-link bounce-hover" href="mailto:tasnimmuhammad51@gmail.com"><i class="fas fa-envelope"></i> Gmail</a>
            <a class="social-link bounce-hover" href="https://github.com/MD-TASNEM"><i class="fab fa-github"></i> GitHub</a>
            <a class="social-link bounce-hover" href="#"><i class="fas fa-globe"></i> Portfolio</a>
        </div>
    </div>

    <div class="gradient-divider"></div>

    <!-- Support Section -->
    <div align="center">
        <h2>🤝 <b>SUPPORT MY WORK</b> 🤝</h2>
        <div style="display: flex; gap: 1rem; justify-content: center; flex-wrap: wrap;">
            <a href="https://buymeacoffee.com/tasnimmuhammad51@gmail.com" class="bounce-hover"><img src="https://img.shields.io/badge/Buy_Me_A_Coffee-FFDD00?style=for-the-badge&logo=buy-me-a-coffee&logoColor=black"/></a>
            <a href="#" class="bounce-hover"><img src="https://img.shields.io/badge/Ko--fi-F16061?style=for-the-badge&logo=ko-fi&logoColor=white"/></a>
            <a href="#" class="bounce-hover"><img src="https://img.shields.io/badge/Sponsor-2D9C7A?style=for-the-badge&logo=github-sponsors&logoColor=white"/></a>
        </div>
    </div>

    <!-- Animated Footer -->
    <div align="center" class="footer-glow">
        <img src="https://komarev.com/ghpvc/?username=MD-TASNEM&label=Profile%20Views&color=2D9C7A&style=flat-square" alt="views"/>
        <img src="https://img.shields.io/github/followers/MD-TASNEM?style=social" alt="followers"/>
        <img src="https://img.shields.io/github/stars/MD-TASNEM?style=social" alt="stars"/>
        <br/>
        <img src="https://github.com/MD-TASNEM/MD-TASNEM/blob/output/github-contribution-grid-snake.svg" width="100%" alt="snake"/>
        <div class="glow-animation" style="margin: 1rem 0;">
            <h3>⭐ رَبِّ زِدْنِي عِلْمًا ⭐</h3>
            <h4>"My Lord, increase me in knowledge" (Quran 20:114)</h4>
        </div>
        <p><i>Thank you for visiting my profile. May Allah accept our efforts.</i></p>
        <p><b>📅 Last Updated:</b> <img src="https://img.shields.io/badge/DATE-2026--04--17-2D9C7A?style=flat-square"/> &nbsp; <b>⏱️ Current Time:</b> <img src="https://img.shields.io/badge/TIME-ACTIVE-2D9C7A?style=flat-square"/></p>
        <img src="https://spotify-recently-played-readme.vercel.app/api?user=31j2zmg63mey7zowj6nzg2clz3na&count=3&width=600" alt="recently played"/>
        <br/><br/>
        <img src="https://capsule-render.vercel.app/api?type=waving&height=100&color=gradient&section=footer&animation=twinkle" width="100%"/>
    </div>
</div>
</body>
</html>
