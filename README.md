<!DOCTYPE html>
<html lang="bg">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gentle Tales - Нежни приказки за деца</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --cream: #F5F1E8;
            --sage: #A8C5B4;
            --terracotta: #D4A574;
            --charcoal: #4A4A4A;
            --white: #FDFCF9;
            --light-sage: #C8D9CF;
            --soft-peach: #F2E9E1;
            --warm-cream: #EDE7DD;
        }

        body {
            font-family: 'Georgia', serif;
            color: var(--charcoal);
            background: var(--cream);
            line-height: 1.7;
        }

        /* Mobile Menu Toggle */
        .menu-toggle {
            display: none;
            background: none;
            border: none;
            font-size: 1.8em;
            color: var(--charcoal);
            cursor: pointer;
            padding: 10px;
        }

        /* Navigation */
        nav {
            background: var(--soft-peach);
            padding: 15px 0;
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 8px rgba(0,0,0,0.08);
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.3em;
            font-weight: bold;
            color: var(--sage);
            text-decoration: none;
        }

        .nav-menu {
            display: flex;
            list-style: none;
            gap: 25px;
            align-items: center;
        }

        .nav-menu a {
            color: var(--charcoal);
            text-decoration: none;
            font-size: 0.95em;
            transition: color 0.3s;
            white-space: nowrap;
        }

        .nav-menu a:hover {
            color: var(--sage);
        }

        .lang-btn {
            background: var(--sage);
            color: white;
            border: none;
            padding: 8px 18px;
            border-radius: 20px;
            cursor: pointer;
            font-size: 0.9em;
            transition: background 0.3s;
        }

        .lang-btn:hover {
            background: var(--terracotta);
        }

        /* Hero with Background Image */
        .hero {
            position: relative;
            height: 85vh;
            min-height: 500px;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            overflow: hidden;
        }

        .hero-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(168, 197, 180, 0.85) 0%, rgba(139, 125, 107, 0.75) 100%),
                        url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 800"><rect fill="%23A8C5B4" width="1200" height="800"/><circle cx="200" cy="150" r="120" fill="%23C8D9CF" opacity="0.3"/><circle cx="900" cy="600" r="150" fill="%23D4A574" opacity="0.2"/><circle cx="1000" cy="200" r="100" fill="%23F5F1E8" opacity="0.4"/></svg>');
            background-size: cover;
            background-position: center;
            z-index: 0;
        }

        .hero-content {
            position: relative;
            z-index: 1;
            max-width: 800px;
            padding: 0 20px;
            color: var(--white);
        }

        .hero h1 {
            font-size: 3em;
            margin-bottom: 20px;
            font-weight: normal;
            line-height: 1.2;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.2);
        }

        .hero p {
            font-size: 1.4em;
            margin-bottom: 35px;
            opacity: 0.95;
        }

        .hero-buttons {
            display: flex;
            gap: 15px;
            justify-content: center;
            flex-wrap: wrap;
        }

        .btn {
            padding: 14px 32px;
            border-radius: 30px;
            text-decoration: none;
            font-size: 1.05em;
            transition: all 0.3s;
            display: inline-block;
            cursor: pointer;
            border: none;
        }

        .btn-primary {
            background: white;
            color: var(--sage);
            font-weight: bold;
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.25);
        }

        .btn-secondary {
            background: transparent;
            color: white;
            border: 2px solid white;
        }

        .btn-secondary:hover {
            background: white;
            color: var(--sage);
        }

        /* Section Styles */
        section {
            padding: 70px 20px;
        }

        .container {
            max-width: 1100px;
            margin: 0 auto;
        }

        .section-white {
            background: var(--warm-cream);
        }

        .section-title {
            text-align: center;
            font-size: 2.3em;
            margin-bottom: 45px;
            color: var(--sage);
            font-weight: normal;
        }

        /* Why Cards */
        .why-cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
            margin-bottom: 40px;
        }

        .card {
            background: var(--soft-peach);
            padding: 35px 25px;
            border-radius: 12px;
            text-align: center;
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 20px rgba(0,0,0,0.1);
        }

        .card-icon {
            font-size: 3.5em;
            margin-bottom: 20px;
        }

        .card h3 {
            color: var(--sage);
            margin-bottom: 15px;
            font-size: 1.25em;
        }

        .card p {
            font-size: 1.05em;
            line-height: 1.6;
        }

        .principles {
            text-align: center;
            margin-top: 50px;
            font-size: 1.15em;
            font-style: italic;
            color: var(--charcoal);
        }

        .principles p {
            margin: 12px 0;
        }

        /* About Content */
        .about-content {
            max-width: 850px;
            margin: 0 auto;
            font-size: 1.1em;
            line-height: 1.9;
        }

        .about-content p {
            margin-bottom: 25px;
        }

        .about-highlight {
            font-size: 1.3em;
            text-align: center;
            margin: 40px 0;
            font-style: italic;
            color: var(--sage);
        }

        .future-box {
            background: var(--soft-peach);
            padding: 35px;
            border-radius: 12px;
            margin: 40px 0;
        }

        .future-box h3 {
            text-align: center;
            color: var(--sage);
            margin-bottom: 25px;
            font-size: 1.3em;
        }

        .future-list {
            list-style: none;
            text-align: center;
            line-height: 2.3;
        }

        .closing-quote {
            font-size: 1.25em;
            text-align: center;
            font-style: italic;
            color: var(--sage);
            margin-top: 45px;
            line-height: 1.7;
        }

        /* Stories Section */
        .stories-intro {
            text-align: center;
            max-width: 600px;
            margin: 0 auto 50px;
        }

        .stories-values {
            list-style: none;
            font-size: 1.2em;
            margin: 30px 0;
        }

        .stories-values li {
            margin: 12px 0;
        }

        .btn-stories {
            background: var(--sage);
            color: white;
            margin-top: 30px;
        }

        .btn-stories:hover {
            background: var(--terracotta);
        }

        /* For Whom */
        .audience-tags {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 20px;
            max-width: 900px;
            margin: 0 auto;
        }

        .tag {
            background: var(--soft-peach);
            padding: 18px 35px;
            border-radius: 25px;
            font-size: 1.05em;
            color: var(--sage);
            transition: all 0.3s;
        }

        .tag:hover {
            background: var(--sage);
            color: white;
            transform: scale(1.05);
        }

        /* CTA Section */
        .cta-section {
            background: linear-gradient(135deg, var(--terracotta) 0%, var(--sage) 100%);
            color: white;
            text-align: center;
            padding: 80px 20px;
        }

        .cta-section h2 {
            font-size: 2em;
            margin-bottom: 35px;
            font-weight: normal;
            line-height: 1.5;
        }

        .btn-cta {
            background: white;
            color: var(--sage);
            font-size: 1.15em;
            padding: 16px 40px;
            font-weight: bold;
        }

        /* Contact Form */
        .contact-form {
            max-width: 600px;
            margin: 0 auto;
            background: var(--soft-peach);
            padding: 40px;
            border-radius: 12px;
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            color: var(--sage);
            font-weight: bold;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 12px 15px;
            border: 2px solid var(--light-sage);
            border-radius: 8px;
            font-family: Georgia, serif;
            font-size: 1em;
            background: var(--white);
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--sage);
        }

        .form-group textarea {
            min-height: 120px;
            resize: vertical;
        }

        .btn-submit {
            background: var(--sage);
            color: white;
            width: 100%;
            padding: 14px;
            font-size: 1.1em;
            cursor: pointer;
        }

        .btn-submit:hover {
            background: var(--terracotta);
        }

        /* Footer */
        footer {
            background: var(--charcoal);
            color: white;
            padding: 50px 20px 25px;
        }

        .footer-grid {
            max-width: 1100px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 35px;
            margin-bottom: 35px;
        }

        .footer-section h3 {
            margin-bottom: 18px;
            color: var(--light-sage);
        }

        .footer-section a {
            color: rgba(255,255,255,0.8);
            text-decoration: none;
            display: block;
            margin: 10px 0;
            transition: color 0.3s;
        }

        .footer-section a:hover {
            color: white;
        }

        .footer-section ul {
            list-style: none;
        }

        .footer-bottom {
            text-align: center;
            padding-top: 25px;
            border-top: 1px solid rgba(255,255,255,0.2);
            opacity: 0.7;
        }

        /* Language Toggle */
        .lang-bg, .lang-en {
            display: none;
        }

        .lang-bg.active, .lang-en.active {
            display: block;
        }

        .lang-bg.active.inline, .lang-en.active.inline {
            display: inline;
        }

        /* Mobile Responsive */
        @media (max-width: 768px) {
            .menu-toggle {
                display: block;
            }

            .nav-menu {
                position: fixed;
                top: 60px;
                left: -100%;
                width: 100%;
                height: calc(100vh - 60px);
                background: var(--soft-peach);
                flex-direction: column;
                padding: 30px 0;
                transition: left 0.3s;
                box-shadow: 2px 0 10px rgba(0,0,0,0.1);
            }

            .nav-menu.active {
                left: 0;
            }

            .nav-menu li {
                width: 100%;
                text-align: center;
                padding: 10px 0;
            }

            .hero {
                height: 70vh;
                min-height: 400px;
            }

            .hero h1 {
                font-size: 2em;
            }

            .hero p {
                font-size: 1.15em;
            }

            .section-title {
                font-size: 1.8em;
            }

            .why-cards {
                grid-template-columns: 1fr;
            }

            .contact-form {
                padding: 25px;
            }
        }

        @media (max-width: 480px) {
            .hero h1 {
                font-size: 1.6em;
            }

            .hero-buttons {
                flex-direction: column;
            }

            .btn {
                width: 100%;
                max-width: 280px;
            }
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav>
        <div class="nav-container">
            <a href="#home" class="logo">🌿 Gentle Tales</a>
            <button class="menu-toggle" onclick="toggleMenu()">☰</button>
            <ul class="nav-menu" id="navMenu">
                <li><a href="#home"><span class="lang-bg active">Начало</span><span class="lang-en">Home</span></a></li>
                <li><a href="#stories"><span class="lang-bg active">Приказки</span><span class="lang-en">Stories</span></a></li>
                <li><a href="#about"><span class="lang-bg active">За проекта</span><span class="lang-en">About</span></a></li>
                <li><a href="#resources"><span class="lang-bg active">Ресурси</span><span class="lang-en">Resources</span></a></li>
                <li><a href="#contact"><span class="lang-bg active">Контакт</span><span class="lang-en">Contact</span></a></li>
                <li><button class="lang-btn" onclick="toggleLanguage()">
                    <span class="lang-bg active inline">EN</span><span class="lang-en inline">БГ</span>
                </button></li>
            </ul>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="hero-bg"></div>
        <div class="hero-content">
            <div class="lang-bg active">
                <h1>Нежни приказки за деца</h1>
                <p>Място за спокойствие, въображение и емоционална сигурност</p>
                <div class="hero-buttons">
                    <a href="#stories" class="btn btn-primary">▶ Гледай приказките</a>
                    <a href="#about" class="btn btn-secondary">🌿 Научи повече</a>
                </div>
            </div>
            <div class="lang-en">
                <h1>Gentle stories for children</h1>
                <p>A safe space for calm, imagination, and emotional balance</p>
                <div class="hero-buttons">
                    <a href="#stories" class="btn btn-primary">▶ Watch the stories</a>
                    <a href="#about" class="btn btn-secondary">🌿 Learn more</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Why Section -->
    <section class="section-white">
        <div class="container">
            <div class="lang-bg active">
                <h2 class="section-title">Защо тези приказки</h2>
                <div class="why-cards">
                    <div class="card">
                        <div class="card-icon">🛡️</div>
                        <h3>Да се чувстват в безопасност</h3>
                        <p>Всяка история създава защитено пространство за изследване на емоциите</p>
                    </div>
                    <div class="card">
                        <div class="card-icon">💝</div>
                        <h3>Да разпознават емоциите си</h3>
                        <p>Децата учат да именуват и приемат своите чувства</p>
                    </div>
                    <div class="card">
                        <div class="card-icon">🌸</div>
                        <h3>Да намират вътрешен баланс</h3>
                        <p>Приказките водят към успокоение и увереност</p>
                    </div>
                </div>
                <div class="principles">
                    <p>Без поучения.</p>
                    <p>Без натиск.</p>
                    <p>С много нежност.</p>
                </div>
            </div>
            <div class="lang-en">
                <h2 class="section-title">Why these stories</h2>
                <div class="why-cards">
                    <div class="card">
                        <div class="card-icon">🛡️</div>
                        <h3>Feel safe and supported</h3>
                        <p>Each story creates a protected space to explore emotions</p>
                    </div>
                    <div class="card">
                        <div class="card-icon">💝</div>
                        <h3>Recognize their emotions</h3>
                        <p>Children learn to name and embrace their feelings</p>
                    </div>
                    <div class="card">
                        <div class="card-icon">🌸</div>
                        <h3>Find inner balance</h3>
                        <p>Stories guide toward peace and confidence</p>
                    </div>
                </div>
                <div class="principles">
                    <p>Without lessons.</p>
                    <p>Without pressure.</p>
                    <p>With gentleness and care.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about">
        <div class="container">
            <div class="lang-bg active">
                <h2 class="section-title">За проекта</h2>
                <div class="about-content">
                    <p class="about-highlight">Добре дошли в едно спокойно и защитено пространство, където историите лекуват.</p>
                    
                    <p>Този проект е създаден с едно просто, но силно убеждение: <strong>приказките могат да бъдат сигурно място за детските емоции.</strong></p>
                    
                    <p>Тук ще откриете приказки, създадени да подкрепят емоционалното развитие, самопознанието и вътрешния баланс на децата. Всяка история е внимателно написана, за да помогне на малките читатели да се срещнат с чувства като страх, тъга, гняв, самота или несигурност – чрез топлина, въображение и нежно водене.</p>
                    
                    <p>Проектът е създаден и воден от <strong>сертифициран арт терапевт</strong>, с опит в работата с деца и техния емоционален свят. Историите са вдъхновени от принципите на арт терапията, емоционалното разказване и емоционалното възпитание, като съчетават творчество и психологична чувствителност.</p>
                    
                    <p>Приказките са съзнателно без лица, за да може всяко дете да вложи в тях своите собствени преживявания, емоции и вътрешен свят. Това създава по-дълбока връзка с историята и усещане за сигурност, без натиск и претоварване.</p>
                    
                    <p><strong>Целта на проекта не е да дава готови поуки, а да предложи пространство, в което спокойствието, разбирането и увереността да се развиват естествено.</strong></p>
                    
                    <div class="future-box">
                        <h3>В бъдеще платформата ще се развива и ще включва:</h3>
                        <ul class="future-list">
                            <li>🎨 видеа и водени арт упражнения</li>
                            <li>✨ творчески практики за емоционално изразяване</li>
                            <li>📄 материали за печат и арт ресурси</li>
                            <li>🛍️ внимателно подбрани партньорски продукти</li>
                        </ul>
                    </div>
                    
                    <p class="closing-quote">Това не е просто колекция от приказки.<br>Това е покана за забавяне, за вслушване и за свързване – със себе си и с децата, за които се грижим.</p>
                </div>
            </div>
            <div class="lang-en">
                <h2 class="section-title">About the Project</h2>
                <div class="about-content">
                    <p class="about-highlight">Welcome to a calm and safe space where stories can heal.</p>
                    
                    <p>This project is created with one simple but powerful belief: <strong>stories can be a safe place for children's emotions.</strong></p>
                    
                    <p>Here you will find stories designed to support children's emotional development, self-awareness, and inner balance. Each story is thoughtfully written to help children gently explore emotions such as fear, sadness, anger, loneliness, or uncertainty — through warmth, imagination, and gentle guidance.</p>
                    
                    <p>The project is created and guided by a <strong>certified art therapist</strong>, with experience in working with children and their emotional world. The stories are inspired by principles of art therapy, emotional storytelling, and emotional education, combining creativity with psychological sensitivity.</p>
                    
                    <p>The stories are intentionally faceless, allowing each child to project their own feelings, experiences, and inner world into the narrative. This creates a deeper emotional connection and a sense of safety, without pressure or overstimulation.</p>
                    
                    <p><strong>The goal of the project is not to offer direct lessons, but to create a space where calm, understanding, and confidence can grow naturally.</strong></p>
                    
                    <div class="future-box">
                        <h3>In the future, the platform will expand to include:</h3>
                        <ul class="future-list">
                            <li>🎨 videos and guided art exercises</li>
                            <li>✨ creative practices for emotional expression</li>
                            <li>📄 printable materials and art-based resources</li>
                            <li>🛍️ carefully selected affiliate products</li>
                        </ul>
                    </div>
                    
                    <p class="closing-quote">This is not just a collection of stories.<br>It is an invitation to slow down, listen, and connect — with ourselves and with the children we care for.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Stories Section -->
    <section class="section-white" id="stories">
        <div class="container">
            <div class="lang-bg active">
                <h2 class="section-title">Приказките</h2>
                <div class="stories-intro">
                    <h3 style="color: var(--sage); font-size: 1.4em;">Всяка приказка е тиха покана към:</h3>
                    <ul class="stories-values">
                        <li>спокойствие</li>
                        <li>свързване</li>
                        <li>доверие</li>
                    </ul>
                    <a href="https://youtube.com/@yourusername" target="_blank" class="btn btn-stories">▶ Разгледай всички приказки</a>
                </div>
            </div>
            <div class="lang-en">
                <h2 class="section-title">The Stories</h2>
                <div class="stories-intro">
                    <h3 style="color: var(--sage); font-size: 1.4em;">Each story is a gentle invitation to:</h3>
                    <ul class="stories-values">
                        <li>calm</li>
                        <li>connection</li>
                        <li>trust</li>
                    </ul>
                    <a href="https://youtube.com/@yourusername" target="_blank" class="btn btn-stories">▶ Explore all stories</a>
                </div>
            </div>
        </div>
    </section>

    <!-- For Whom Section -->
    <section>
        <div class="container">
            <div class="lang-bg active">
                <h2 class="section-title">За кого е подходящо</h2>
                <div class="audience-tags">
                    <div class="tag">деца (4-10 г.)</div>
                    <div class="tag">родители</div>
                    <div class="tag">арт терапевти</div>
                    <div class="tag">психолози</div>
                    <div class="tag">педагози</div>
                </div>
            </div>
            <div class="lang-en">
                <h2 class="section-title">Who is this for</h2>
                <div class="audience-tags">
                    <div class="tag">children (4-10 y.o.)</div>
                    <div class="tag">parents</div>
                    <div class="tag">art therapists</div>
                    <div class="tag">psychologists</div>
                    <div class="tag">educators</div>
                </div>
            </div>
        </div>
    </section>

    <!-- Resources Section -->
    <section class="section-white" id="resources">
        <div class="container">
            <div class="lang-bg active">
                <h2 class="section-title">Ресурси</h2>
                <div style="text-align: center; font-size: 1.2em; color: var(--charcoal); font-style: italic;">
                    <p>Скоро тук ще намерите внимателно подбрани материали за рисуване, книги и творчески комплекти.</p>
                    <p style="margin-top: 20px; color: var(--sage);">Coming soon 🌿</p>
                </div>
            </div>
            <div class="lang-en">
                <h2 class="section-title">Resources</h2>
                <div style="text-align: center; font-size: 1.2em; color: var(--charcoal); font-style: italic;">
                    <p>Soon you'll find carefully selected drawing materials, books and creative kits here.</p>
                    <p style="margin-top: 20px; color: var(--sage);">Coming soon 🌿</p>
                </div>
            </div>
        </div>
    </section>

    <!-- CTA Section -->
    <section class="cta-section">
        <div class="container">
            <div class="lang-bg active">
                <h2>Понякога една приказка е достатъчна,<br>за да се почувстваме по-спокойни.</h2>
                <a href="#stories" class="btn btn-cta">▶ Започни с първата приказка</a>
            </div>
            <div class="lang-en">
                <h2>Sometimes one story is enough<br>to bring calm.</h2>
                <a href="#stories" class="btn btn-cta">▶ Start with the first story</a>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="section-white" id="contact">
        <div class="container">
            <div class="lang-bg active">
                <h2 class="section-title">Свържете се с нас</h2>
                <form class="contact-form" onsubmit="handleSubmit(event)">
                    <div class="form-group">
                        <label for="name">Име *</label>
                        <input type="text" id="name" name="name" required>
                    </div>
                    <div class="form-group">
                        <label for="lastname">Фамилия</label>
                        <input type="text" id="lastname" name="lastname">
                    </div>
                    <div class="form-group">
                        <label for="email">Email *</label>
                        <input type="email" id="email" name="email" required>
                    </div>
                    <div class="form-group">
                        <label for="message">Съобщение *</label>
                        <textarea id="message" name="message" required></textarea>
                    </div>
                    <button type="submit" class="btn btn-submit">Изпрати</button>
                </form>
            </div>
            <div class="lang-en">
                <h2 class="section-title">Contact Us</h2>
                <form class="contact-form" onsubmit="handleSubmit(event)">
                    <div class="form-group">
                        <label for="name-en">Name *</label>
                        <input type="text" id="name-en" name="name" required>
                    </div>
                    <div class="form-group">
                        <label for="lastname-en">Last name</label>
                        <input type="text" id="lastname-en" name="lastname">
                    </div>
                    <div class="form-group">
                        <label for="email-en">Email *</label>
                        <input type="email" id="email-en" name="email" required>
                    </div>
                    <div class="form-group">
                        <label for="message-en">Message *</label>
                        <textarea id="message-en" name="message" required></textarea>
                    </div>
                    <button type="submit" class="btn btn-submit">Submit</button>
                </form>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-grid">
                <div class="footer-section">
                    <div class="lang-bg active">
                        <h3>Навигация</h3>
                        <ul>
                            <li><a href="#home">Начало</a></li>
                            <li><a href="#stories">Приказки</a></li>
                            <li><a href="#about">За проекта</a></li>
                            <li><a href="#resources">Ресурси</a></li>
                            <li><a href="#contact">Контакт</a></li>
                        </ul>
                    </div>
                    <div class="lang-en">
                        <h3>Navigation</h3>
                        <ul>
                            <li><a href="#home">Home</a></li>
                            <li><a href="#stories">Stories</a></li>
                            <li><a href="#about">About</a></li>
                            <li><a href="#resources">Resources</a></li>
                            <li><a href="#contact">Contact</a></li>
                        </ul>
                    </div>
                </div>
                <div class="footer-section">
                    <div class="lang-bg active">
                        <h3>Контакти</h3>
                        <p>Email
