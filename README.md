<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>AUSTINWRAP</title>
    <meta name="viewport" content="width=device-width, initial-scale=0.3, maximum-scale=0.3, user-scalable=no">
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
            padding: 10px;
            position: relative;
            z-index: 1;
        }

        /* Header */
        header {
            text-align: center;
            padding: 50px 20px 30px;
            color: #fff;
            position: relative;
        }
        header h1 {
            font-size: 4em;
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
            justify-content: center;
            align-items: center;
        }
        nav .logo {
            font-family: 'Orbitron', sans-serif;
            font-size: 1.8em;
            color: var(--text-color);
            text-decoration: none;
        }

        /* Sections */
        section {
            padding: 50px 0;
            position: relative;
        }
        section h2 {
            font-size: 2.5em;
            color: var(--highlight-color);
            text-align: center;
            margin-bottom: 40px;
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
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
        }
        .card {
            background: var(--card-background);
            border-radius: 15px;
            padding: 20px;
            color: var(--text-color);
            box-shadow: 0 15px 30px rgba(0,0,0,0.3);
            position: relative;
            overflow: hidden;
            transition: transform 0.5s, box-shadow 0.5s;
            cursor: pointer;
            text-decoration: none;
            display: flex;
            flex-direction: column;
        }
        .card:hover {
            transform: translateY(-10px);
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
            font-size: 1.5em;
            margin-bottom: 10px;
            font-family: 'Orbitron', sans-serif;
        }
        .card p {
            font-size: 1em;
            margin-bottom: 20px;
            line-height: 1.6;
        }
        .card button {
            display: block;
            width: 100%;
            text-decoration: none;
            color: #fff;
            background: var(--button-color);
            padding: 10px 0;
            border-radius: 50px;
            font-weight: bold;
            font-size: 1em;
            transition: background 0.3s, transform 0.3s;
            border: none;
            cursor: pointer;
            margin-top: auto;
        }
        .card button:hover {
            background: var(--button-hover-color);
            transform: translateY(-5px);
        }

        /* Footer */
        footer {
            text-align: center;
            padding: 30px 20px;
            background: var(--primary-color);
            color: var(--text-color);
            position: relative;
        }
        footer p {
            margin-bottom: 20px;
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

        /* Adjustments for Mobile to Shrink Content */
        @media (max-width: 480px) {
            body {
                transform: scale(0.5);
                transform-origin: top left;
                width: 200%;
                overflow: hidden;
            }
            nav {
                height: calc(var(--nav-height) * 0.5);
            }
            header {
                padding: 25px 10px 15px;
            }
            header h1 {
                font-size: 2em;
            }
            section {
                padding: 25px 0;
            }
            section h2 {
                font-size: 1.25em;
                margin-bottom: 20px;
            }
            .card {
                padding: 10px;
            }
            .card h3 {
                font-size: 0.75em;
                margin-bottom: 5px;
            }
            .card p {
                font-size: 0.5em;
                margin-bottom: 10px;
            }
            .card button {
                padding: 5px 0;
                font-size: 0.5em;
            }
            footer {
                padding: 15px 10px;
            }
            footer p {
                font-size: 0.75em;
            }
            #scrollTopBtn {
                width: 30px;
                height: 30px;
                font-size: 1em;
                padding: 5px;
                bottom: 15px;
                right: 15px;
            }
        }
    </style>
</head>
<body>

    <!-- Particle.js Background -->
    <div id="particles-js"></div>

    <!-- Navigation Bar -->
    <nav>
        <div class="container">
            <a href="#" class="logo">AUSTINWRAP</a>
        </div>
    </nav>

    <!-- Header Section -->
    <header>
        <h1>AUSTINWRAP</h1>
    </header>

    <div class="container">
        <!-- Projects Section -->
        <section id="projects">
            <h2>Featured Projects</h2>
            <div class="cards">
                <!-- Bartending Game -->
                <a href="https://austinwrap.github.io/Bartend/" target="_blank" class="card">
                    <h3>Bartending Game</h3>
                    <p>Run the bar, manage resources, and make every drink count in this addictive game.</p>
                    <button>Check it Out</button>
                </a>
                <!-- Chicken Farm Game -->
                <a href="https://austinwrap.github.io/FrostyFarms/" target="_blank" class="card">
                    <h3>Chicken Farm Game</h3>
                    <p>From feed to eggs, grow your chicken farm empire one feather at a time.</p>
                    <button>Get Started</button>
                </a>
                <!-- Bristol Tycoon -->
                <a href="https://austinwrap.github.io/BristolTycoon/" target="_blank" class="card">
                    <h3>Bristol Tycoon</h3>
                    <p>Own the town in this Monopoly-style game, where every choice builds your legacy.</p>
                    <button>Play Now</button>
                </a>
            </div>
        </section>

        <!-- Social Media Section -->
        <section id="social">
            <h2>Connect with Me</h2>
            <div class="cards">
                <!-- YouTube -->
                <a href="https://www.youtube.com/@Austinwrap" target="_blank" class="card">
                    <h3>YouTube</h3>
                    <p>Videos on tech, farm life, and projects that make a difference.</p>
                    <button>Visit Channel</button>
                </a>
                <!-- Instagram -->
                <a href="https://www.instagram.com/austinwrap/" target="_blank" class="card">
                    <h3>Instagram</h3>
                    <p>Farm moments and tech highlights—a blend of life's best.</p>
                    <button>Follow Me</button>
                </a>
                <!-- TikTok -->
                <a href="https://www.tiktok.com/@austinwrap" target="_blank" class="card">
                    <h3>TikTok</h3>
                    <p>Quick insights and fun snippets from the hustle.</p>
                    <button>Watch Now</button>
                </a>
                <!-- Twitch -->
                <a href="https://www.twitch.tv/austinwrap_" target="_blank" class="card">
                    <h3>Twitch</h3>
                    <p>Live streams showcasing projects in action.</p>
                    <button>Join Live</button>
                </a>
            </div>
        </section>

        <!-- E-Commerce Section -->
        <section id="ecommerce">
            <h2>Shop & Support</h2>
            <div class="cards">
                <!-- Mobile Bartending -->
                <a href="https://austinwrap.github.io/Mobile-Bartending/" target="_blank" class="card">
                    <h3>Mobile Bartending</h3>
                    <p>A complete web experience for the traveling bartender. Made for Raeanne's service.</p>
                    <button>Visit Site</button>
                </a>
                <!-- Roundhouse Powerwash LLC -->
                <a href="https://austinwrap.github.io/Powerwash/" target="_blank" class="card">
                    <h3>Roundhouse Powerwash LLC</h3>
                    <p>Your trusted partner for professional power washing services.</p>
                    <button>Learn More</button>
                </a>
                <!-- Etsy Shop -->
                <a href="https://www.etsy.com/shop/MyFavoriteAlien" target="_blank" class="card">
                    <h3>Etsy Shop</h3>
                    <p>Farm-inspired gear, tech merch, and unique prints.</p>
                    <button>Explore</button>
                </a>
                <!-- My Book on Amazon -->
                <a href="https://a.co/d/3AiLY0d" target="_blank" class="card">
                    <h3>My Book on Amazon</h3>
                    <p>Read my journey and thoughts on building and creating.</p>
                    <button>Buy Now</button>
                </a>
                <!-- Affirmations Journal -->
                <a href="https://a.co/d/bF8FTHW" target="_blank" class="card">
                    <h3>Affirmations Journal</h3>
                    <p>A journal for keeping your mind on growth and positivity.</p>
                    <button>Get it Here</button>
                </a>
                <!-- CT Draft -->
                <a href="http://www.ctdraft.com" target="_blank" class="card">
                    <h3>CT Draft</h3>
                    <p>Your go-to resource for quality draft service.</p>
                    <button>Learn More</button>
                </a>
            </div>
        </section>
    </div>

    <footer>
        <p>&copy; 2024 AUSTINWRAP</p>
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
    </script>
</body>
</html>

