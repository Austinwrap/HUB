<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>AUSTINWRAP – Revised Edition</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <!-- Google Fonts & Font Awesome -->
  <link href="https://fonts.googleapis.com/css?family=Montserrat:400,700&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <style>
    /* Global Reset */
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body {
      font-family: 'Montserrat', sans-serif;
      /* Grey–Blue Gradient Background */
      background: linear-gradient(135deg, #5D6D7E, #34495E);
      background-size: 400% 400%;
      animation: gradientBG 15s ease infinite;
      overflow-x: hidden;
      color: #eee;
    }
    @keyframes gradientBG {
      0%   { background-position: 0% 50%; }
      50%  { background-position: 100% 50%; }
      100% { background-position: 0% 50%; }
    }
    
    /* Navigation */
    nav {
      position: fixed;
      width: 100%;
      top: 0;
      left: 0;
      background: rgba(0, 0, 0, 0.8);
      padding: 10px 20px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      z-index: 1000;
      box-shadow: 0 2px 5px rgba(0,0,0,0.5);
    }
    nav .logo {
      font-size: 2em;
      font-weight: bold;
      color: #81D4FA;
    }
    nav ul {
      list-style: none;
      display: flex;
      gap: 15px;
    }
    nav ul li a {
      text-decoration: none;
      color: #eee;
      font-weight: 600;
      transition: color 0.3s;
    }
    nav ul li a:hover { color: #81D4FA; }
    .hamburger {
      display: none;
      font-size: 1.5em;
      cursor: pointer;
      color: #eee;
    }
    @media (max-width: 768px) {
      nav ul {
        display: none;
        flex-direction: column;
        position: fixed;
        top: 60px;
        right: 0;
        background: rgba(0,0,0,0.9);
        padding: 20px;
        box-shadow: -2px 2px 5px rgba(0,0,0,0.5);
      }
      nav ul.show { display: flex; }
      .hamburger { display: block; }
    }
    
    /* Hero Section */
    header {
      padding: 20px 10px;
      text-align: center;
      margin-top: 60px; /* Allow room for the fixed nav */
    }
    header h1 {
      font-size: 2.8em;
      margin-bottom: 10px;
      color: #81D4FA;
      text-shadow: 1px 1px 3px rgba(0,0,0,0.7);
    }
    header p {
      font-size: 1.2em;
      margin-bottom: 20px;
      color: #ccc;
    }
    
    /* Sections */
    section {
      padding: 50px 20px;
      text-align: center;
    }
    section h2 {
      font-size: 2.5em;
      margin-bottom: 20px;
      color: #81D4FA;
    }
    .section-content {
      max-width: 1200px;
      margin: 0 auto;
      display: flex;
      flex-wrap: wrap;
      gap: 20px;
      justify-content: center;
    }
    
    /* Cards (Icon Based, with Direct External Links) */
    .card {
      background: #333;
      border-radius: 20px;
      width: 280px;
      padding: 15px;
      box-shadow: 0 8px 12px rgba(0,0,0,0.5);
      transition: transform 0.3s;
      text-decoration: none;
      color: inherit;
    }
    .card:hover { transform: scale(1.04); }
    .card-icon {
      font-size: 3rem;
      margin-bottom: 10px;
      color: #81D4FA;
    }
    .card h3 {
      margin-bottom: 8px;
      font-size: 1.3em;
      color: #81D4FA;
    }
    .card p {
      font-size: 0.95em;
      color: #ccc;
      margin-bottom: 10px;
    }
    .card button {
      background: #81D4FA;
      color: #fff;
      border: none;
      padding: 8px 16px;
      border-radius: 20px;
      cursor: pointer;
      transition: background 0.3s;
    }
    .card button:hover { background: #6EC1E4; }
    
    /* Beer Facts Ticker */
    .beer-ticker {
      position: fixed;
      bottom: 0;
      left: 0;
      width: 100%;
      background: #81D4FA;
      color: #fff;
      padding: 8px 15px;
      font-size: 1em;
      white-space: nowrap;
      overflow: hidden;
      z-index: 1500;
    }
    .beer-ticker span {
      display: inline-block;
      padding-left: 100%;
      animation: ticker 20s linear infinite;
    }
    @keyframes ticker {
      0%   { transform: translateX(0); }
      100% { transform: translateX(-100%); }
    }
    
    /* Footer */
    footer {
      padding: 20px 10px;
      background: #222;
      text-align: center;
      font-size: 0.9em;
      color: #777;
    }
  </style>
</head>
<body>
  <!-- Navigation -->
  <nav id="navbar">
    <div class="logo">AUSTINWRAP</div>
    <div class="hamburger" id="hamburger"><i class="fas fa-bars"></i></div>
    <ul id="nav-links">
      <li><a href="#projects">Projects</a></li>
      <li><a href="#social">Social</a></li>
      <li><a href="#shop">Shop</a></li>
    </ul>
  </nav>
  
  <!-- Hero Section -->
  <header id="home">
    <h1>Welcome to AUSTINWRAP</h1>
    <p>Experience sleek design, explosive interactivity, and pure creative innovation!</p>
  </header>
  
  <!-- Projects Section -->
  <section id="projects">
    <h2>Featured Projects</h2>
    <div class="section-content">
      <!-- Card 1: Bartending Game -->
      <a class="card" href="https://austinwrap.github.io/Bartend/" target="_blank">
        <div class="card-icon"><i class="fas fa-cocktail"></i></div>
        <h3>Bartending Game</h3>
        <p>Mix drinks, manage your bar, and dive into wild simulations.</p>
        <button>Learn More</button>
      </a>
      <!-- Card 2: Chicken Farm Game -->
      <a class="card" href="https://austinwrap.github.io/FrostyFarms/" target="_blank">
        <div class="card-icon"><i class="fas fa-drumstick-bite"></i></div>
        <h3>Chicken Farm Game</h3>
        <p>Raise your quirky flock and harvest the fun!</p>
        <button>Learn More</button>
      </a>
      <!-- Card 3: Bristol Tycoon -->
      <a class="card" href="https://austinwrap.github.io/BristolTycoon/" target="_blank">
        <div class="card-icon"><i class="fas fa-building"></i></div>
        <h3>Bristol Tycoon</h3>
        <p>Build your empire and rule the town in outrageous style.</p>
        <button>Learn More</button>
      </a>
    </div>
  </section>
  
  <!-- Social Section -->
  <section id="social">
    <h2>Connect with Me</h2>
    <div class="section-content">
      <!-- Social Card 1: YouTube -->
      <a class="card" href="https://www.youtube.com/@austinwrap" target="_blank">
        <div class="card-icon"><i class="fab fa-youtube"></i></div>
        <h3>YouTube</h3>
        <p>Watch creative projects and behind-the-scenes content.</p>
        <button>Visit Channel</button>
      </a>
      <!-- Social Card 2: Instagram -->
      <a class="card" href="https://www.instagram.com/austinwrap" target="_blank">
        <div class="card-icon"><i class="fab fa-instagram"></i></div>
        <h3>Instagram</h3>
        <p>Follow for vibrant, off-the-wall moments.</p>
        <button>Follow Me</button>
      </a>
      <!-- Social Card 3: TikTok -->
      <a class="card" href="https://www.tiktok.com/@austinwrap" target="_blank">
        <div class="card-icon"><i class="fab fa-tiktok"></i></div>
        <h3>TikTok</h3>
        <p>Short bursts of creative energy and fun!</p>
        <button>Watch Now</button>
      </a>
      <!-- Social Card 4: Twitch -->
      <a class="card" href="https://www.twitch.tv/austinwrap_" target="_blank">
        <div class="card-icon"><i class="fab fa-twitch"></i></div>
        <h3>Twitch</h3>
        <p>Join live sessions full of interactive surprises.</p>
        <button>Join Live</button>
      </a>
    </div>
  </section>
  
  <!-- Shop Section -->
  <section id="shop">
    <h2>Shop &amp; Support</h2>
    <div class="section-content">
      <!-- Shop Card 1: Mobile Bartending -->
      <a class="card" href="https://austinwrap.github.io/Mobile-Bartending/" target="_blank">
        <div class="card-icon"><i class="fas fa-mobile-alt"></i></div>
        <h3>Mobile Bartending</h3>
        <p>Experience a full-service bartending web extravaganza.</p>
        <button>Visit Site</button>
      </a>
      <!-- Shop Card 2: Roundhouse Powerwash LLC -->
      <a class="card" href="https://austinwrap.github.io/Powerwash/" target="_blank">
        <div class="card-icon"><i class="fas fa-water"></i></div>
        <h3>Roundhouse Powerwash LLC</h3>
        <p>Keep your space spotless with pro power washing.</p>
        <button>Learn More</button>
      </a>
      <!-- Shop Card 3: Etsy Shop -->
      <a class="card" href="https://www.etsy.com/shop/MyFavoriteAlien" target="_blank">
        <div class="card-icon"><i class="fas fa-shopping-bag"></i></div>
        <h3>Etsy Shop</h3>
        <p>Find unique, creative merch that celebrates our journey.</p>
        <button>Explore</button>
      </a>
      <!-- Shop Card 4: My Book on Amazon -->
      <a class="card" href="https://a.co/d/3AiLY0d" target="_blank">
        <div class="card-icon"><i class="fas fa-book"></i></div>
        <h3>My Book on Amazon</h3>
        <p>Dive into my creative adventures and learn from the chaos.</p>
        <button>Buy Now</button>
      </a>
      <!-- Shop Card 5: Affirmations Journal -->
      <a class="card" href="https://a.co/d/bF8FTHW" target="_blank">
        <div class="card-icon"><i class="fas fa-book-open"></i></div>
        <h3>Affirmations Journal</h3>
        <p>Fuel your daily creativity with affirmations and positive vibes.</p>
        <button>Get it Here</button>
      </a>
      <!-- Shop Card 6: CT Draft -->
      <a class="card" href="http://www.ctdraft.com" target="_blank">
        <div class="card-icon"><i class="fas fa-industry"></i></div>
        <h3>CT Draft</h3>
        <p>Explore our high-quality draft services that bring order to creative chaos.</p>
        <button>Learn More</button>
      </a>
    </div>
  </section>
  
  <!-- Beer Facts Ticker -->
  <div class="beer-ticker">
    <span id="beer-facts">
      Did you know? The oldest beer recipe dates back to 1800 BC. | Beer was once a safe alternative to water. | The Czech Republic leads in per capita beer consumption. | Cheers to fun beer facts!
    </span>
  </div>
  
  <script>
    // Toggle Hamburger Menu on Mobile
    document.getElementById('hamburger').addEventListener('click', function() {
      document.getElementById('nav-links').classList.toggle('show');
    });
  </script>
  
  <footer>
    <p>&copy; 2024 AUSTINWRAP. All Rights Reserved.</p>
  </footer>
</body>
</html>
