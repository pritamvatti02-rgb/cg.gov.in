<!DOCTYPE html>
<html lang="hi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ONLINE CG - Pritam Vatti</title>
    <!-- प्रीमियम और मॉडर्न फॉन्ट्स -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;500;700;900&family=Mukta:wght@500;700;800&family=Orbitron:wght@700;900&display=swap" rel="stylesheet">
    
    <style>
        /* --- बेसिक रिसेट --- */
        * { margin: 0; padding: 0; box-sizing: border-box; }
        html { scroll-behavior: smooth; }
        
        body {
            /* यहाँ बैकग्राउंड इमेज और डार्क ओवरले लगाया गया है */
            background: linear-gradient(rgba(5, 5, 5, 0.75), rgba(5, 5, 5, 0.85)), 
                        url('https://images.unsplash.com/photo-1626244605995-520e5ebf87bf?q=80&w=1920&auto=format&fit=crop') no-repeat center center fixed;
            background-size: cover;
            color: #ffffff;
            font-family: 'Inter', sans-serif;
            overflow-x: hidden;
            -webkit-font-smoothing: antialiased;
        }

        /* --- मॉडर्न नेविगेशन --- */
        nav {
            position: fixed;
            top: 0; width: 100%;
            padding: 15px 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: rgba(0, 0, 0, 0.4);
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
            z-index: 1000;
            animation: slideDown 1s ease-out;
        }

        /* नया लोगो डिज़ाइन (नया फॉन्ट) */
        .logo {
            font-family: 'Orbitron', sans-serif; /* नया फ्यूचरिस्टिक फॉन्ट */
            font-size: 1.8rem;
            font-weight: 900;
            letter-spacing: 2px;
            background: linear-gradient(90deg, #fff, #00ffcc);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-transform: uppercase;
        }

        /* नेविगेशन लिंक्स (Right Side) */
        .nav-links { 
            display: flex; 
            gap: 30px; 
        }
        
        .nav-links a {
            color: #dddddd;
            text-decoration: none;
            font-size: 0.95rem;
            font-weight: 500;
            transition: color 0.3s;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .nav-links a:hover { color: #00ffcc; }

        /* --- हीरो सेक्शन --- */
        .hero {
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 0 20px;
        }

        /* एनिमेटेड ग्रैडिएंट टेक्स्ट */
        .hero h1 {
            font-family: 'Mukta', sans-serif;
            font-size: 7vw; 
            font-weight: 800;
            line-height: 1.1;
            letter-spacing: -2px;
            background: linear-gradient(270deg, #00ffcc, #ffffff, #00ffcc);
            background-size: 400% 400%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: gradientText 6s ease infinite, fadeInUp 1.2s ease-out;
            margin-bottom: 15px;
            text-shadow: 0px 10px 30px rgba(0,0,0,0.5);
        }

        .hero p {
            font-size: 1.2rem;
            color: #e0e0e0;
            max-width: 550px;
            line-height: 1.6;
            animation: fadeInUp 1.5s ease-out;
            font-family: 'Mukta', sans-serif;
        }

        /* --- छोटे और कॉम्पैक्ट Bento Grid --- */
        .bento-section {
            padding: 80px 5%;
            max-width: 900px; 
            margin: 0 auto;
        }

        .bento-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px; 
        }

        /* बॉक्स का डिज़ाइन */
        .bento-box {
            background: rgba(10, 10, 10, 0.4); 
            border: 1px solid rgba(255, 255, 255, 0.15);
            border-radius: 20px;
            padding: 30px; 
            transition: all 0.4s ease;
            position: relative;
            backdrop-filter: blur(15px);
            -webkit-backdrop-filter: blur(15px);
        }

        .bento-box:hover {
            transform: translateY(-5px);
            background: rgba(20, 20, 20, 0.6);
            border-color: rgba(0, 255, 204, 0.5);
            box-shadow: 0 10px 30px rgba(0, 255, 204, 0.1);
        }

        .bento-box h2 {
            font-size: 1.8rem; 
            margin-bottom: 15px;
            font-weight: 700;
            color: #fff;
        }

        .bento-box h2 span { color: #00ffcc; }

        .bento-box p {
            color: #dddddd;
            font-size: 1rem; 
            line-height: 1.6;
            font-family: 'Mukta', sans-serif;
        }

        .highlight-text {
            color: #fff;
            font-weight: 700;
        }

        /* --- छोटा इंस्टाग्राम बटन --- */
        .modern-btn {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            margin-top: 20px;
            padding: 12px 30px;
            background: linear-gradient(45deg, #00ffcc, #0066ff);
            color: #000;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 800;
            font-size: 0.95rem;
            transition: all 0.4s;
        }

        .modern-btn:hover {
            transform: scale(1.05);
            box-shadow: 0 8px 20px rgba(0, 255, 204, 0.4);
            color: #fff;
        }

        /* --- स्क्रॉल रिवील एनिमेशन --- */
        .reveal {
            opacity: 0;
            transform: translateY(40px);
            transition: all 0.8s cubic-bezier(0.5, 0, 0, 1);
        }

        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* --- कीफ्रेम्स --- */
        @keyframes gradientText {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        @keyframes slideDown {
            from { transform: translateY(-100%); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }

        @keyframes fadeInUp {
            from { transform: translateY(30px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }

        @media (max-width: 768px) {
            .hero h1 { font-size: 12vw; }
            .nav-links { gap: 15px; } /* मोबाइल में लिंक्स का गैप कम किया */
            .nav-links a { font-size: 0.8rem; }
            .logo { font-size: 1.3rem; }
        }
    </style>
</head>
<body>

    <!-- नेविगेशन -->
    <nav>
        <div class="logo">ONLINE CG</div>
        <div class="nav-links">
            <a href="#home">Home</a>
            <a href="#contact">Contact</a>
        </div>
    </nav>

    <!-- हीरो सेक्शन -->
    <section class="hero" id="home">
        <h1>जोहार छत्तीसगढ़</h1>
        <p>डिजिटल दुनिया में छत्तीसगढ़ की एक नई पहचान।</p>
    </section>

    <!-- छोटे बॉक्स (About & Contact) -->
    <section class="bento-section">
        <div class="bento-grid">
            
            <!-- About Box -->
            <div class="bento-box reveal" id="about">
                <h2>About <span>Me.</span></h2>
                <p>
                    जय जोहार! मेरा नाम <span class="highlight-text">प्रीतम वट्टी</span> है और मैं <span class="highlight-text">केशकाल, छत्तीसगढ़</span> से हूँ। 
                    मैंने यह पेज अपनी डिजिटल क्रिएटिविटी और ऑनलाइन जर्नी को शेयर करने के लिए बनाया है।
                </p>
            </div>

            <!-- Contact Box -->
            <div class="bento-box reveal" id="contact">
                <h2>Connect.</h2>
                <p>
                    मुझसे संपर्क करने, किसी भी जानकारी या सहयोग  के लिए आप मुझे सीधे मेरे इंस्टाग्राम पर मैसेज कर सकते हैं।
                </p>
                <a href="https://instagram.com/pritamvattii" target="_blank" class="modern-btn">
                    @pritamvattii ↗
                </a>
            </div>

        </div>
    </section>

    <!-- स्क्रॉल एनिमेशन के लिए जावास्क्रिप्ट -->
    <script>
        function reveal() {
            var reveals = document.querySelectorAll(".reveal");

            for (var i = 0; i < reveals.length; i++) {
                var windowHeight = window.innerHeight;
                var elementTop = reveals[i].getBoundingClientRect().top;
                var elementVisible = 50; 

                if (elementTop < windowHeight - elementVisible) {
                    reveals[i].classList.add("active");
                }
            }
        }

        window.addEventListener("scroll", reveal);
        reveal(); // पेज लोड पर चेक
    </script>

</body>
</html>
