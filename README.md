<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>AUSTINWRAP</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <!-- Updated Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Rock+Salt&family=Roboto:wght@400;700&display=swap" rel="stylesheet">
    <style>
        /* Reset */
        *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

        /* Color Variables */
        :root {
            --background-color: #121212;  /* Dark background */
            --primary-color: #00E5FF;     /* Bright cyan */
            --secondary-color: #FF4081;   /* Bright pink */
            --accent-color: #FFC107;      /* Amber */
            --text-color: #FFFFFF;        /* White */
        }

        /* Body Styling */
        body {
            font-family: 'Roboto', sans-serif;
            background-color: var(--background-color);
            color: var(--text-color);
            line-height: 1.6;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            overflow-x: hidden;
        }

        /* Container */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
            flex: 1;
        }

        /* Header */
        header {
            text-align: center;
            padding: 40px 20px;
            background-color: var(--background-color);
        }
        header h1 {
            font-size: 4em;
            font-family: 'Rock Salt', cursive;
            color: var(--primary-color);
            text-shadow: 2px 2px 8px rgba(0,229,255,0.7);
        }
        header p {
            font-size: 1.2em;
            margin-top: 10px;
            color: var(--accent-color);
        }
        header::after {
            content: '';
            display: block;
            width: 150px;
            height: 3px;
            background: var(--secondary-color);
            margin: 20px auto 0;
        }

        /* Navigation */
        nav {
            background-color: var(--background-color);
            padding: 10px 0;
            display: flex;
            justify-content: center;
            gap: 30px;
            position: sticky;
            top: 0;
            z-index: 1000;
            border-bottom: 1px solid var(--secondary-color);
        }
        nav a {
            font-size: 1.1em;
            color: var(--text-color);
            text-decoration: none;
            padding: 5px 10px;
            position: relative;
            transition: color 0.3s;
        }
        nav a::after {
            content: '';
            position: absolute;
            left: 50%;
            bottom: -5px;
            transform: translateX(-50%);
            width: 0%;
            height: 2px;
            background: var(--secondary-color);
            transition: width 0.3s;
        }
        nav a:hover {
            color: var(--secondary-color);
        }
        nav a:hover::after {
            width: 100%;
        }

        /* Section Headings */
        section {
            padding: 40px 20px;
        }
        section h2 {
            font-size: 2.5em;
            text-align: center;
            margin-bottom: 30px;
            color: var(--primary-color);
            font-family: 'Rock Salt', cursive;
            text-shadow: 2px 2px 8px rgba(0,229,255,0.7);
        }

        /* Cards */
        .cards {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 30px;
        }
        .card {
            background-color: var(--secondary-color);
            border-radius: 10px;
            padding: 20px;
            width: 100%;
            max-width: 280px;
            color: var(--text-color);
            position: relative;
            overflow: hidden;
            transition: transform 0.3s;
        }
        .card:hover {
            transform: translateY(-5px);
        }
        .card h3 {
            font-size: 1.8em;
            margin-bottom: 15px;
            font-family: 'Rock Salt', cursive;
            color: var(--accent-color);
        }
        .card p {
            font-size: 1em;
            margin-bottom: 20px;
        }
        .card a {
            display: inline-block;
            text-decoration: none;
            background-color: var(--primary-color);
            color: var(--background-color);
            padding: 12px 25px;
            border-radius: 5px;
            font-weight: bold;
            transition: background-color 0.3s, transform 0.3s;
        }
        .card a:hover {
            background-color: var(--accent-color);
            transform: translateY(-3px);
        }

        /* Footer */
        footer {
            text-align: center;
            padding: 20px 0;
            background-color: var(--background-color);
            color: var(--text-color);
            border-top: 1px solid var(--secondary-color);
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            header h1 { font-size: 3em; }
            section h2 { font-size: 2em; }
            .cards {
                flex-direction: column;
                align-items: center;
            }
            nav {
                flex-wrap: wrap;
            }
        }
    </style>
</head>
<body>

<header>
    <h1>AUSTINWRAP</h1>
    <p> </p>
</header>

<nav>
    <a href="#projects">Projects</a>
    <a href="#social">Connect</a>
    <a href="#ecommerce">Shop</a>
</nav>

<div class="container">
    <!-- Projects Section -->
    <section id="projects">
        <h2>Featured Projects</h2>
        <div class="cards">
            <div class="card">
                <h3>Bartending Game</h3>
                <p>Run the bar, manage your resources, and make every drink count in this addictive game.</p>
                <a href="https://austinwrap.github.io/Bartend/" target="_blank">Check it Out</a>
            </div>
            <div class="card">
                <h3>Chicken Farm Game</h3>
                <p>From feed to eggs, grow your chicken farm empire one feather at a time.</p>
                <a href="https://austinwrap.github.io/FrostyFarms/" target="_blank">Get Started</a>
            </div>
            <div class="card">
                <h3>Bristol Tycoon</h3>
                <p>Own the town in this Monopoly-style game, where every choice builds your legacy.</p>
                <a href="https://austinwrap.github.io/BristolTycoon/" target="_blank">Play Now</a>
            </div>
        </div>
    </section>

    <!-- Social Media Section -->
    <section id="social">
        <h2>Connect with Me</h2>
        <div class="cards">
            <div class="card">
                <h3>YouTube</h3>
                <p>Videos on tech, farm life, and projects that make a difference.</p>
                <a href="https://www.youtube.com/@Austinwrap" target="_blank">Visit Channel</a>
            </div>
            <div class="card">
                <h3>Instagram</h3>
                <p>Farm moments and tech highlights — a blend of life’s best.</p>
                <a href="https://www.instagram.com/austinwrap/" target="_blank">Follow Me</a>
            </div>
            <div class="card">
                <h3>TikTok</h3>
                <p>Quick insights and fun snippets from the hustle.</p>
                <a href="https://www.tiktok.com/@austinwrap" target="_blank">Watch Now</a>
            </div>
            <div class="card">
                <h3>Twitch</h3>
                <p>Live streams from projects in action.</p>
                <a href="https://www.twitch.tv/austinwrap_" target="_blank">Join Live</a>
            </div>
        </div>
    </section>

    <!-- E-Commerce Section -->
    <section id="ecommerce">
        <h2>Shop & Support</h2>
        <div class="cards">
            <div class="card">
                <h3>Mobile Bartending</h3>
                <p>A complete web experience for the traveling bartender. Made for Raeanne’s service.</p>
                <a href="https://austinwrap.github.io/Mobile-Bartending/" target="_blank">Visit Site</a>
            </div>
            <div class="card">
                <h3>Etsy Shop</h3>
                <p>Farm-inspired gear, tech merch, and unique prints.</p>
                <a href="https://www.etsy.com/shop/MyFavoriteAlien" target="_blank">Explore</a>
            </div>
            <div class="card">
                <h3>My Book on Amazon</h3>
                <p>Read my journey and thoughts on building and creating.</p>
                <a href="https://a.co/d/3AiLY0d" target="_blank">Buy Now</a>
            </div>
            <div class="card">
                <h3>Affirmations Journal</h3>
                <p>A journal for keeping your mind on growth and positivity.</p>
                <a href="https://a.co/d/bF8FTHW" target="_blank">Get it Here</a>
            </div>
            <div class="card">
                <h3>CT Draft</h3>
                <p>Your go-to resource for quality draft service.</p>
                <a href="http://www.ctdraft.com" target="_blank">Learn More</a>
            </div>
        </div>
    </section>
</div>

<footer>
    &copy; 2024 AUSTINWRAP
</footer>

</body>
</html>
