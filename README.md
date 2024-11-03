<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>AUSTINWRAP - Unleash Creativity</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Raleway:wght@400;700&family=Orbitron:wght@700&display=swap" rel="stylesheet">
    <!-- Include Font Awesome for icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Particle.js Library -->
    <script src="https://cdn.jsdelivr.net/npm/particles.js@2.0.0/particles.min.js"></script>
    <style>
        /* Reset */
        *, *::before, *::after {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        /* Root Variables */
        :root {
            --primary-color: #0d0d0d;
            --secondary-color: #1a1a1a;
            --accent-color: #ff6ec7;
            --highlight-color: #00eaff;
            --text-color: #ffffff;
            --card-background: rgba(26, 26, 26, 0.9);
            --button-color: #ff6ec7;
            --button-hover-color: #ff2e97;
            --nav-height: 70px;
        }

        /* Body Styling */
        body {
            font-family: 'Raleway', sans-serif;
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            color: var(--text-color);
            min-height: 100vh;
            overflow-x: hidden;
            position: relative;
        }

        /* Background Animation */
        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at center, transparent, var(--accent-color));
            opacity: 0.05;
            animation: pulseBackground 10s infinite;
            z-index: -2;
        }

        @keyframes pulseBackground {
            0% { opacity: 0.05; }
            50% { opacity: 0.1; }
            100% { opacity: 0.05; }
        }

        /* Particle Animation */
        #particles-js {
            position: fixed;
            width: 100%;
            height: 100%;
            background: transparent;
            z-index: -1;
        }

        /* Container */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
            position: relative;
            z-index: 1;
        }

        /* Header */
        header {
            text-align: center;
            padding: 150px 20px 100px;
            color: #fff;
            position: relative;
        }
        header h1 {
            font-size: 5em;
            font-family: 'Orbitron', sans-serif;
            color: var(--button-color);
            text-shadow: 0 0 15px var(--button-color), 0 0 30px var(--button-color);
            animation: neonPulse 1.5s infinite alternate;
        }

        @keyframes neonPulse {
            from {
                text-shadow: 0 0 15px var(--button-color), 0 0 30px var(--button-color);
            }
            to {
                text-shadow: 0 0 25px var(--button-color), 0 0 50px var(--button-color);
            }
        }

        header p {
            font-size: 1.8em;
            margin-top: 30px;
            color: var(--highlight-color);
            animation: fadeIn 2s forwards;
            opacity: 0;
        }

        @keyframes fadeIn {
            to { opacity: 1; }
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            height: var(--nav-height);
            background: rgba(13, 13, 13, 0.9);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 100;
            backdrop-filter: blur(5px);
            border-bottom: 1px solid var(--button-color);
        }
        nav .container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        nav .logo {
            font-family: 'Orbitron', sans-serif;
            font-size: 1.8em;
            color: var(--text-color);
            text-decoration: none;
        }
        nav ul {
            display: flex;
            gap: 40px;
            list-style: none;
        }
        nav ul li {
            position: relative;
        }
        nav ul li a {
            color: var(--text-color);
            text-decoration: none;
            font-size: 1.2em;
            padding: 5px 0;
            transition: color 0.3s;
        }
        nav ul li a:hover {
            color: var(--button-color);
        }
        nav ul li a::after {
            content: '';
            position: absolute;
            width: 0%;
            height: 2px;
            background: var(--button-color);
            left: 50%;
            bottom: -5px;
            transition: width 0.3s ease, left 0.3s ease;
        }
        nav ul li a:hover::after {
            width: 100%;
            left: 0;
        }
        nav .menu-toggle {
            display: none;
            color: var(--text-color);
            font-size: 1.8em;
            cursor: pointer;
        }

        /* Sections */
        section {
            padding: 100px 0;
            position: relative;
        }
        section h2 {
            font-size: 3em;
            color: var(--highlight-color);
            text-align: center;
            margin-bottom: 80px;
            position: relative;
            z-index: 1;
            text-shadow: 0 0 10px var(--highlight-color);
            animation: fadeInDown 1s forwards;
            opacity: 0;
        }

        @keyframes fadeInDown {
            to { opacity: 1; transform: translateY(0); }
            from { opacity: 0; transform: translateY(-50px); }
        }

        /* Cards */
        .cards {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 50px;
        }
        .card {
            background: var(--card-background);
            border-radius: 15px;
            padding: 40px 30px;
            width: calc(33.333% - 50px);
            color: var(--text-color);
            box-shadow: 0 15px 30px rgba(0,0,0,0.3);
            position: relative;
            overflow: hidden;
            transition: transform 0.5s, box-shadow 0.5s;
        }
        .card:hover {
            transform: translateY(-20px);
            box-shadow: 0 25px 50px rgba(0,0,0,0.5);
        }
        .card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, var(--button-color), transparent);
            opacity: 0.1;
            transition: opacity 0.5s;
        }
        .card:hover::before {
            opacity: 0.3;
        }
        .card h3 {
            font-size: 2em;
            margin-bottom: 20px;
            font-family: 'Orbitron', sans-serif;
        }
        .card p {
            font-size: 1em;
            margin-bottom: 30px;
            line-height: 1.6;
        }
        .card a {
            display: inline-block;
            text-decoration: none;
            color: #fff;
            background: var(--button-color);
            padding: 15px 40px;
            border-radius: 50px;
            font-weight: bold;
            font-size: 1em;
            transition: background 0.3s, transform 0.3s;
        }
        .card a:hover {
            background: var(--button-hover-color);
            transform: translateY(-5px);
        }

        /* Footer */
        footer {
            text-align: center;
            padding: 50px 20px;
            background: var(--primary-color);
            color: var(--text-color);
            position: relative;
        }
        footer p {
            margin-bottom: 20px;
        }
        footer .social-icons {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin-bottom: 20px;
        }
        footer .social-icons a {
            color: var(--text-color);
            font-size: 1.8em;
            transition: color 0.3s, transform 0.3s;
        }
        footer .social-icons a:hover {
            color: var(--button-color);
            transform: translateY(-5px);
        }

        /* Scroll to Top Button */
        #scrollTopBtn {
            position: fixed;
            bottom: 30px;
            right: 30px;
            background: var(--button-color);
            color: #fff;
            padding: 15px;
            border: none;
            border-radius: 50%;
            font-size: 1.5em;
            cursor: pointer;
            display: none;
            z-index: 99;
            transition: background 0.3s, transform 0.3s;
        }
        #scrollTopBtn:hover {
            background: var(--button-hover-color);
            transform: translateY(-5px);
        }

        /* Responsive Design */
        @media (max-width: 1024px) {
            .card {
                width: calc(50% - 50px);
            }
            nav ul {
                gap: 30px;
            }
        }
        @media (max-width: 768px) {
            header h1 {
                font-size: 3.5em;
            }
            header p {
                font-size: 1.5em;
            }
            section h2 {
                font-size: 2.5em;
            }
            .card {
                width: calc(100% - 50px);
            }
            nav ul {
                flex-direction: column;
                background: rgba(13, 13, 13, 0.95);
                position: absolute;
                top: var(--nav-height);
                left: 0;
                width: 100%;
                max-height: 0;
                overflow: hidden;
                transition: max-height 0.5s;
            }
            nav ul.open {
                max-height: 300px;
            }
            nav ul li {
                text-align: center;
            }
            nav .menu-toggle {
                display: block;
            }
        }
    </style>
</head>
<body>

    <!-- Particle.js Background -->
    <div id="particles-js"></div>

    <nav>
        <div class="container">
            <a href="#" class="logo">AUSTINWRAP</a>
            <div class="menu-toggle" onclick="toggleMenu()">
                <i class="fas fa-bars"></i>
            </div>
            <ul id="nav-menu">
                <li><a href="#projects">Projects</a></li>
                <li><a href="#connect">Connect</a></li>
                <li><a href="#shop">Shop</a></li>
            </ul>
        </div>
    </nav>

    <header>
        <h1>AUSTINWRAP</h1>
        <p>Unleashing Infinite Possibilities</p>
    </header>

    <div class="container">
        <!-- Projects Section -->
        <section id="projects">
            <h2>Featured Projects</h2>
            <div class="cards">
                <!-- Bartending Game -->
                <div class="card">
                    <h3>Bartending Game</h3>
                    <p>Run the bar, manage resources, and make every drink count in this addictive game.</p>
                    <a href="https://austinwrap.github.io/Bartend/" target="_blank">Play Now</a>
                </div>
                <!-- Chicken Farm Game -->
                <div class="card">
                    <h3>Chicken Farm Game</h3>
                    <p>Grow your chicken farm empire one feather at a time.</p>
                    <a href="https://austinwrap.github.io/FrostyFarms/" target="_blank">Start Farming</a>
                </div>
                <!-- Bristol Tycoon -->
                <div class="card">
                    <h3>Bristol Tycoon</h3>
                    <p>Own the town in this Monopoly-style game, building your legacy.</p>
                    <a href="https://austinwrap.github.io/BristolTycoon/" target="_blank">Become a Tycoon</a>
                </div>
            </div>
        </section>

        <!-- Social Media Section -->
        <section id="connect">
            <h2>Connect with Me</h2>
            <div class="cards">
                <!-- YouTube -->
                <div class="card">
                    <h3>YouTube</h3>
                    <p>Tech insights, farm life adventures, and inspiring projects.</p>
                    <a href="https://www.youtube.com/@Austinwrap" target="_blank">Visit Channel</a>
                </div>
                <!-- Instagram -->
                <div class="card">
                    <h3>Instagram</h3>
                    <p>Capturing farm moments and tech highlights.</p>
                    <a href="https://www.instagram.com/austinwrap/" target="_blank">Follow Me</a>
                </div>
                <!-- TikTok -->
                <div class="card">
                    <h3>TikTok</h3>
                    <p>Quick snippets and behind-the-scenes of the hustle.</p>
                    <a href="https://www.tiktok.com/@austinwrap" target="_blank">Watch Now</a>
                </div>
                <!-- Twitch -->
                <div class="card">
                    <h3>Twitch</h3>
                    <p>Join live streams of projects in action.</p>
                    <a href="https://www.twitch.tv/austinwrap_" target="_blank">Join Live</a>
                </div>
            </div>
        </section>

        <!-- Shop Section -->
        <section id="shop">
            <h2>Shop & Support</h2>
            <div class="cards">
                <!-- Mobile Bartending -->
                <div class="card">
                    <h3>Mobile Bartending</h3>
                    <p>A web experience for the traveling bartender.</p>
                    <a href="https://austinwrap.github.io/Mobile-Bartending/" target="_blank">Visit Site</a>
                </div>
                <!-- Roundhouse Powerwash LLC -->
                <div class="card">
                    <h3>Roundhouse Powerwash LLC</h3>
                    <p>Professional power washing services.</p>
                    <a href="https://austinwrap.github.io/Powerwash/" target="_blank">Learn More</a>
                </div>
                <!-- Etsy Shop -->
                <div class="card">
                    <h3>Etsy Shop</h3>
                    <p>Farm-inspired gear and unique prints.</p>
                    <a href="https://www.etsy.com/shop/MyFavoriteAlien" target="_blank">Explore</a>
                </div>
                <!-- My Book on Amazon -->
                <div class="card">
                    <h3>My Book on Amazon</h3>
                    <p>Read my journey on building and creating.</p>
                    <a href="https://www.amazon.com/dp/1697954738" target="_blank">Buy Now</a>
                </div>
                <!-- Affirmations Journal -->
                <div class="card">
                    <h3>Affirmations Journal</h3>
                    <p>A journal for keeping your mind on growth and positivity.</p>
                    <a href="https://www.amazon.com/dp/B08XLL8P3N" target="_blank">Get it Here</a>
                </div>
                <!-- CT Draft -->
                <div class="card">
                    <h3>CT Draft</h3>
                    <p>Your go-to resource for quality draft service.</p>
                    <a href="https://www.ctdraft.com" target="_blank">Learn More</a>
                </div>
            </div>
        </section>
    </div>

    <footer>
        <p>&copy; 2024 AUSTINWRAP - Dream Big, Create Bigger</p>
        <div class="social-icons">
            <!-- Social Media Profiles -->
            <a href="https://www.facebook.com/austin.wrap.5" target="_blank"><i class="fab fa-facebook-f"></i></a>
            <a href="https://twitter.com/austin_wrap" target="_blank"><i class="fab fa-twitter"></i></a>
            <a href="https://www.linkedin.com/in/austin-wrap-123456789/" target="_blank"><i class="fab fa-linkedin-in"></i></a>
        </div>
        <p>Made with ❤️ by AUSTINWRAP</p>
    </footer>

    <!-- Scroll to Top Button -->
    <button id="scrollTopBtn" onclick="scrollToTop()"><i class="fas fa-chevron-up"></i></button>

    <!-- Particle.js Initialization -->
    <script>
        /* Particle.js Configuration */
        particlesJS('particles-js',
        {
          "particles": {
            "number": {
              "value": 80
            },
            "color": {
              "value": ["#ff6ec7", "#00eaff", "#ffffff"]
            },
            "shape": {
              "type": "circle"
            },
            "opacity": {
              "value": 0.5,
              "random": true
            },
            "size": {
              "value": 3,
              "random": true
            },
            "line_linked": {
              "enable": false
            },
            "move": {
              "speed": 1,
              "direction": "none",
              "out_mode": "out"
            }
          },
          "interactivity": {
            "detect_on": "canvas",
            "events": {
              "onhover": {
                "enable": true,
                "mode": "grab"
              },
              "onclick": {
                "enable": false
              },
              "resize": true
            },
            "modes": {
              "grab": {
                "distance": 140,
                "line_linked": {
                  "opacity": 0.5
                }
              }
            }
          },
          "retina_detect": true
        });

        /* Scroll to Top Button */
        window.onscroll = function() {scrollFunction()};

        function scrollFunction() {
            var scrollBtn = document.getElementById("scrollTopBtn");
            if (document.body.scrollTop > 500 || document.documentElement.scrollTop > 500) {
                scrollBtn.style.display = "block";
            } else {
                scrollBtn.style.display = "none";
            }
        }

        function scrollToTop() {
            window.scrollTo({top: 0, behavior: 'smooth'});
        }

        /* Mobile Navigation Toggle */
        function toggleMenu() {
            var navMenu = document.getElementById("nav-menu");
            navMenu.classList.toggle("open");
        }
    </script>
</body>
</html>
