<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>AUSTINWRAP - Gambling Galore</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <meta name="apple-mobile-web-app-capable" content="yes">
  <meta name="mobile-web-app-capable" content="yes">
  <link href="https://fonts.googleapis.com/css?family=Montserrat:400,700|Playfair+Display:400,700&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body {
      font-family: 'Montserrat', sans-serif;
      background: linear-gradient(135deg, #2E2E2E, #4A4A4A, #00A1D6);
      background-size: 400% 400%;
      animation: gradientBG 15s ease infinite;
      overflow-x: hidden;
      color: #E0E0E0;
      position: relative;
      padding-bottom: 200px;
    }
    @keyframes gradientBG {
      0% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
      100% { background-position: 0% 50%; }
    }
    #particle-canvas {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      z-index: -1;
    }
    .stock-ticker {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      background: rgba(0,0,0,0.9);
      color: #00A1D6;
      padding: 15px 20px;
      font-size: 1.3em;
      white-space: nowrap;
      overflow: hidden;
      z-index: 1600;
      text-shadow: 0 0 10px #00A1D6;
    }
    .stock-ticker span {
      display: inline-block;
      padding-left: 100%;
      animation: ticker-top 60s linear infinite;
    }
    @keyframes ticker-top {
      0% { transform: translateX(0); }
      100% { transform: translateX(-100%); }
    }
    nav {
      position: fixed;
      width: 100%;
      top: 50px;
      left: 0;
      background: rgba(0,0,0,0.95);
      padding: 15px 20px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      z-index: 1500;
      box-shadow: 0 3px 10px rgba(0,0,0,0.8);
    }
    nav .logo {
      font-family: 'Playfair Display', serif;
      font-size: 2.2em;
      font-weight: bold;
      color: #00A1D6;
      text-shadow: 0 0 12px #00A1D6;
    }
    nav ul {
      list-style: none;
      display: flex;
      gap: 20px;
    }
    nav ul li { position: relative; }
    nav ul li a {
      text-decoration: none;
      color: #E0E0E0;
      font-weight: 600;
      transition: color 0.3s;
    }
    nav ul li a:hover { color: #00A1D6; }
    nav ul li .dropdown {
      display: none;
      position: absolute;
      top: 100%;
      left: 0;
      background: rgba(0,0,0,0.95);
      padding: 10px;
      box-shadow: 0 3px 10px rgba(0,0,0,0.8);
      z-index: 1700;
    }
    nav ul li:hover .dropdown { display: block; }
    nav ul li .dropdown li { margin: 8px 0; }
    .hamburger {
      display: none;
      font-size: 1.8em;
      cursor: pointer;
      color: #E0E0E0;
    }
    @media (max-width: 768px) {
      nav ul {
        display: none;
        flex-direction: column;
        position: fixed;
        top: 65px;
        right: 0;
        background: rgba(0,0,0,0.95);
        padding: 20px;
        box-shadow: -3px 3px 10px rgba(0,0,0,0.8);
      }
      nav ul.show { display: flex; }
      .hamburger { display: block; }
    }
    header {
      padding: 120px 10px 20px;
      text-align: center;
      margin-top: 80px;
    }
    header h1 {
      font-family: 'Playfair Display', serif;
      font-size: 3.5em;
      margin-bottom: 15px;
      color: #00A1D6;
      text-shadow: 0 0 15px #00A1D6;
      animation: pulse 3s infinite;
    }
    @keyframes pulse {
      0% { transform: scale(1); }
      50% { transform: scale(1.05); }
      100% { transform: scale(1); }
    }
    header p {
      font-size: 1.4em;
      margin-bottom: 20px;
      color: #B0B0B0;
    }
    section {
      padding: 60px 20px;
      text-align: center;
    }
    section h2 {
      font-family: 'Playfair Display', serif;
      font-size: 3em;
      margin-bottom: 25px;
      color: #00A1D6;
      text-shadow: 0 0 12px #00A1D6;
    }
    .section-content {
      max-width: 1200px;
      margin: 0 auto;
      display: flex;
      flex-wrap: wrap;
      gap: 25px;
      justify-content: center;
    }
    .card {
      background: #2E2E2E;
      border-radius: 12px;
      width: 300px;
      padding: 25px;
      box-shadow: 0 10px 20px rgba(0,0,0,0.7);
      transition: transform 0.3s, box-shadow 0.3s;
      text-decoration: none;
      color: #E0E0E0;
      position: relative;
      overflow: hidden;
      border: 1px solid #00A1D6;
    }
    .card:hover {
      transform: scale(1.05);
      box-shadow: 0 15px 30px rgba(0,0,0,0.9), 0 0 15px #00A1D6;
    }
    .card-icon {
      font-size: 3.5rem;
      margin-bottom: 15px;
      color: #00A1D6;
      text-shadow: 0 0 10px #00A1D6;
    }
    .card h3 {
      margin-bottom: 10px;
      font-size: 1.8em;
      color: #00A1D6;
    }
    .card p {
      font-size: 1.1em;
      color: #B0B0B0;
      margin-bottom: 20px;
    }
    .card button {
      background: transparent;
      border: 2px solid #00A1D6;
      color: #00A1D6;
      padding: 10px 20px;
      border-radius: 6px;
      cursor: pointer;
      transition: background 0.3s, color 0.3s;
    }
    .card button:hover {
      background: #00A1D6;
      color: #2E2E2E;
    }
    .beer-ticker {
      position: fixed;
      bottom: 140px;
      left: 0;
      width: 100%;
      background: rgba(0,0,0,0.9);
      color: #00A1D6;
      padding: 15px 20px;
      font-size: 1.3em;
      white-space: nowrap;
      overflow: hidden;
      z-index: 1500;
      text-shadow: 0 0 10px #00A1D6;
    }
    .beer-ticker span {
      display: inline-block;
      padding-left: 100%;
      animation: ticker 40s linear infinite;
    }
    @keyframes ticker {
      0% { transform: translateX(0); }
      100% { transform: translateX(-100%); }
    }
    #bank-panel {
      position: fixed;
      right: 15px;
      bottom: 200px;
      background: rgba(0,0,0,0.95);
      border: 2px solid #00A1D6;
      border-radius: 12px;
      z-index: 1700;
      width: 200px;
      box-shadow: 0 0 20px #00A1D6;
    }
    #bank-header {
      cursor: move;
      background: rgba(0,0,0,0.9);
      padding: 8px 15px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      font-size: 1.2em;
      color: #00A1D6;
    }
    #minimize-bank {
      background: transparent;
      border: none;
      color: #00A1D6;
      font-size: 1.4em;
      cursor: pointer;
    }
    #bank-content {
      padding: 15px;
      text-align: center;
    }
    #bank-content p {
      font-size: 1.3em;
      margin-bottom: 15px;
    }
    #bank-content button {
      margin: 8px 0;
      width: 100%;
      background: transparent;
      border: 1px solid #00A1D6;
      color: #00A1D6;
      padding: 10px;
      border-radius: 6px;
      cursor: pointer;
      transition: background 0.3s;
    }
    #bank-content button:hover {
      background: #00A1D6;
      color: #2E2E2E;
    }
    #slot-panel {
      position: fixed;
      left: 15px;
      bottom: 200px;
      background: rgba(0,0,0,0.95);
      border: 2px solid #00A1D6;
      border-radius: 12px;
      z-index: 1700;
      width: 200px;
      box-shadow: 0 0 20px #00A1D6;
    }
    #slot-header {
      cursor: move;
      background: rgba(0,0,0,0.9);
      padding: 8px 15px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      font-size: 1.2em;
      color: #00A1D6;
    }
    #minimize-slot {
      background: transparent;
      border: none;
      color: #00A1D6;
      font-size: 1.4em;
      cursor: pointer;
    }
    #slot-content {
      padding: 15px;
      text-align: center;
    }
    #slot-content input {
      width: 100%;
      margin-bottom: 10px;
      padding: 8px;
    }
    #slot-content button {
      margin: 8px 0;
      width: 100%;
      background: transparent;
      border: 1px solid #00A1D6;
      color: #00A1D6;
      padding: 10px;
      border-radius: 6px;
      cursor: pointer;
      transition: background 0.3s;
    }
    #slot-content button:hover {
      background: #00A1D6;
      color: #2E2E2E;
    }
    #slot-result {
      font-size: 1.8em;
      margin-top: 15px;
    }
    #ledger {
      position: fixed;
      left: 0;
      bottom: 0;
      width: 100%;
      max-height: 140px;
      overflow-y: auto;
      background: rgba(0,0,0,0.9);
      color: #00A1D6;
      padding: 15px 25px;
      font-size: 1.1em;
      z-index: 1800;
      border-top: 3px solid #00A1D6;
    }
    #ledger h4 { margin-bottom: 10px; font-size: 1.5em; }
    #ledger ul {
      list-style: none;
      max-height: 100px;
      overflow-y: auto;
    }
    #ledger li { margin-bottom: 5px; }
    .modal {
      display: none;
      position: fixed;
      z-index: 1900;
      left: 0;
      top: 0;
      width: 100%;
      height: 100%;
      overflow: auto;
      background: rgba(0,0,0,0.85);
    }
    .modal-content {
      background: #2E2E2E;
      margin: 10% auto;
      padding: 25px;
      border: 3px solid #00A1D6;
      width: 90%;
      max-width: 450px;
      border-radius: 12px;
      color: #E0E0E0;
      text-align: center;
      position: relative;
      box-shadow: 0 0 20px #00A1D6;
    }
    .close-button {
      color: #00A1D6;
      float: right;
      font-size: 1.8em;
      font-weight: bold;
      cursor: pointer;
    }
    .game-container {
      margin: 25px 0;
    }
    .game-container button { margin: 8px; }
    #rocket-multiplier {
      font-size: 2.5em;
      color: #00A1D6;
    }
    @media (max-width: 480px) {
      #bank-panel, #slot-panel { width: 180px; }
      #bank-panel { bottom: 160px; right: 10px; }
      #slot-panel { bottom: 160px; left: 10px; }
      #bank-header, #slot-header { font-size: 1em; }
      #bank-content p, #slot-content input, #slot-content button { font-size: 0.9em; padding: 8px; }
      .modal-content { max-width: 350px; }
      #slot-result { font-size: 1.4em; }
    }
  </style>
</head>
<body>
  <canvas id="particle-canvas"></canvas>
  <div class="stock-ticker">
    <span>
      Algeria | Angola | Benin | Botswana | Burkina Faso | Burundi | Cape Verde | Cameroon | Central African Republic | Chad | Comoros | Democratic Republic of the Congo | Djibouti | Egypt | Equatorial Guinea | Eritrea | Eswatini | Ethiopia | Gabon | Gambia | Ghana | Guinea | Guinea-Bissau | Ivory Coast | Kenya | Lesotho | Liberia | Libya | Madagascar | Malawi | Mali | Mauritania | Mauritius | Morocco | Mozambique | Namibia | Niger | Nigeria | Republic of the Congo | Rwanda | São Tomé and Príncipe | Senegal | Seychelles | Sierra Leone | Somalia | South Africa | South Sudan | Sudan | Tanzania | Togo | Tunisia | Uganda | Zambia | Zimbabwe | Afghanistan | Armenia | Azerbaijan | Bahrain | Bangladesh | Bhutan | Brunei | Cambodia | China | Cyprus | Georgia | India | Indonesia | Iran | Iraq | Israel | Japan | Jordan | Kazakhstan | Kuwait | Kyrgyzstan | Laos | Lebanon | Malaysia | Maldives | Mongolia | Myanmar | Nepal | North Korea | Oman | Pakistan | Palestine | Philippines | Qatar | Saudi Arabia | Singapore | South Korea | Sri Lanka | Syria | Taiwan | Tajikistan | Thailand | Timor-Leste | Turkey | Turkmenistan | United Arab Emirates | Uzbekistan | Vietnam | Yemen | Albania | Andorra | Austria | Belarus | Belgium | Bosnia and Herzegovina | Bulgaria | Croatia | Cyprus | Czech Republic | Denmark | Estonia | Finland | France | Germany | Greece | Hungary | Iceland | Ireland | Italy | Kazakhstan | Kosovo | Latvia | Liechtenstein | Lithuania | Luxembourg | Malta | Moldova | Monaco | Montenegro | Netherlands | North Macedonia | Norway | Poland | Portugal | Romania | Russia | San Marino | Serbia | Slovakia | Slovenia | Spain | Sweden | Switzerland | Ukraine | United Kingdom | Vatican City | Antigua and Barbuda | Bahamas | Barbados | Belize | Canada | Costa Rica | Cuba | Dominica | Dominican Republic | El Salvador | Grenada | Guatemala | Haiti | Honduras | Jamaica | Mexico | Nicaragua | Panama | Saint Kitts and Nevis | Saint Lucia | Saint Vincent and the Grenadines | Trinidad and Tobago | United States | Argentina | Bolivia | Brazil | Chile | Colombia | Ecuador | Guyana | Paraguay | Peru | Suriname | Uruguay | Venezuela | Australia | Fiji | Kiribati | Marshall Islands | Micronesia | Nauru | New Zealand | Palau | Papua New Guinea | Samoa | Solomon Islands | Tonga | Tuvalu | Vanuatu
    </span>
  </div>
  <nav id="navbar">
    <div class="logo">AUSTINWRAP</div>
    <div class="hamburger" id="hamburger"><i class="fas fa-bars"></i></div>
    <ul id="nav-links">
      <li><a href="#projects">Projects</a></li>
      <li><a href="#social">Social</a></li>
      <li><a href="#shop">Shop</a></li>
      <li><a href="#casino">Casino</a></li>
      <li>
        <a href="#">Account <i class="fas fa-caret-down"></i></a>
        <ul class="dropdown">
          <li><a href="#" id="bank-link">Bank</a></li>
          <li><a href="#" id="ledger-link">Ledger</a></li>
        </ul>
      </li>
    </ul>
  </nav>
  <header id="home">
    <h1>Welcome to AUSTINWRAP</h1>
    <p>Experience a sleek blend of raw creativity and high-stakes action.</p>
  </header>
  <section id="projects">
    <h2>Featured Projects</h2>
    <div class="section-content">
      <a class="card" href="https://austinwrap.github.io/Bartend/" target="_blank">
        <div class="card-icon"><i class="fas fa-cocktail"></i></div>
        <h3>Bartending Game</h3>
        <p>Mix drinks and manage your bar in an engaging simulation.</p>
        <button>Learn More</button>
      </a>
      <a class="card" href="https://austinwrap.github.io/FrostyFarms/" target="_blank">
        <div class="card-icon"><i class="fas fa-drumstick-bite"></i></div>
        <h3>Chicken Farm Game</h3>
        <p>Raise your quirky flock and enjoy a farm twist.</p>
        <button>Learn More</button>
      </a>
      <a class="card" href="https://austinwrap.github.io/BristolTycoon/" target="_blank">
        <div class="card-icon"><i class="fas fa-building"></i></div>
        <h3>Bristol Tycoon</h3>
        <p>Build your empire with sophisticated strategy.</p>
        <button>Learn More</button>
      </a>
      <a class="card" href="https://austinwrap.github.io/bad-mailman/" target="_blank">
        <div class="card-icon"><i class="fas fa-envelope"></i></div>
        <h3>Bad Mailman</h3>
        <p>A quirky twist on the classic mail journey.</p>
        <button>Learn More</button>
      </a>
      <a class="card" href="https://austinwrap.github.io/feminine-stocks/" target="_blank">
        <div class="card-icon"><i class="fas fa-chart-line"></i></div>
        <h3>Feminine Stocks Simulator</h3>
        <p>Dive into a satirical stock market simulation with a twist.</p>
        <button>Learn More</button>
      </a>
    </div>
  </section>
  <section id="social">
    <h2>Connect with Me</h2>
    <div class="section-content">
      <a class="card" href="https://www.youtube.com/@austinwrap" target="_blank">
        <div class="card-icon"><i class="fab fa-youtube"></i></div>
        <h3>YouTube</h3>
        <p>Watch behind-the-scenes and creative explorations.</p>
        <button>Visit Channel</button>
      </a>
      <a class="card" href="https://www.instagram.com/austinwrap" target="_blank">
        <div class="card-icon"><i class="fab fa-instagram"></i></div>
        <h3>Instagram</h3>
        <p>Follow for tasteful moments and creative insights.</p>
        <button>Follow Me</button>
      </a>
      <a class="card" href="https://www.tiktok.com/@austinwrap" target="_blank">
        <div class="card-icon"><i class="fab fa-tiktok"></i></div>
        <h3>TikTok</h3>
        <p>Enjoy quick bursts of creative flair and fun.</p>
        <button>Watch Now</button>
      </a>
      <a class="card" href="https://www.twitch.tv/austinwrap_" target="_blank">
        <div class="card-icon"><i class="fab fa-twitch"></i></div>
        <h3>Twitch</h3>
        <p>Join live sessions filled with interactive entertainment.</p>
        <button>Join Live</button>
      </a>
    </div>
  </section>
  <section id="shop">
    <h2>Shop & Support</h2>
    <div class="section-content">
      <a class="card" href="https://austinwrap.github.io/Mobile-Bartending/" target="_blank">
        <div class="card-icon"><i class="fas fa-mobile-alt"></i></div>
        <h3>Mobile Bartending</h3>
        <p>Experience a full-service bartending experience online.</p>
        <button>Visit Site</button>
      </a>
      <a class="card" href="https://austinwrap.github.io/Powerwash/" target="_blank">
        <div class="card-icon"><i class="fas fa-water"></i></div>
        <h3>Roundhouse Powerwash LLC</h3>
        <p>Professional power washing for a pristine space.</p>
        <button>Learn More</button>
      </a>
      <a class="card" href="https://www.etsy.com/shop/MyFavoriteAlien" target="_blank">
        <div class="card-icon"><i class="fas fa-shopping-bag"></i></div>
        <h3>Etsy Shop</h3>
        <p>Discover unique merchandise with a refined twist.</p>
        <button>Explore</button>
      </a>
      <a class="card" href="https://a.co/d/3AiLY0d" target="_blank">
        <div class="card-icon"><i class="fas fa-book"></i></div>
        <h3>My Book on Amazon</h3>
        <p>Explore creative journeys through literature.</p>
        <button>Buy Now</button>
      </a>
      <a class="card" href="https://a.co/d/bF8FTHW" target="_blank">
        <div class="card-icon"><i class="fas fa-book-open"></i></div>
        <h3>Affirmations Journal</h3>
        <p>Inspire your daily routine with thoughtful reflections.</p>
        <button>Get it Here</button>
      </a>
      <a class="card" href="http://www.ctdraft.com" target="_blank">
        <div class="card-icon"><i class="fas fa-industry"></i></div>
        <h3>CT Draft</h3>
        <p>Explore high-quality draft services tailored to your needs.</p>
        <button>Learn More</button>
      </a>
    </div>
  </section>
  <section id="casino">
    <h2>Casino Games</h2>
    <div class="section-content">
      <div class="card">
        <div class="card-icon"><i class="fas fa-cards"></i></div>
        <h3>Blackjack</h3>
        <p>Play against the dealer and test your luck!</p>
        <button id="play-blackjack">Play Now</button>
      </div>
      <div class="card">
        <div class="card-icon"><i class="fas fa-slot-machine"></i></div>
        <h3>Slot Machine</h3>
        <p>Spin the reels for big wins with cool vibes!</p>
        <button id="play-slots">Play Now</button>
      </div>
      <div class="card">
        <div class="card-icon"><i class="fas fa-rocket"></i></div>
        <h3>Rocket Game</h3>
        <p>Cash out before the rocket crashes!</p>
        <button id="play-rocket">Play Now</button>
      </div>
    </div>
  </section>
  <div id="bank-panel">
    <div id="bank-header">
      <span>Bank Account</span>
      <button id="minimize-bank">_</button>
    </div>
    <div id="bank-content">
      <p id="account-balance">$1,000,000</p>
      <button id="bet-all">All or Nothing</button>
      <button id="bet-10">Bet 10%</button>
      <button id="tip-jar">Tip Jar</button>
      <button id="trash-money">Trash Money</button>
      <button id="donate-money">Donate</button>
    </div>
  </div>
  <div id="slot-panel">
    <div id="slot-header">
      <span>Mini Slots</span>
      <button id="minimize-slot">_</button>
    </div>
    <div id="slot-content">
      <input type="number" id="slot-bet" placeholder="Bet amount" value="100">
      <button id="spin-slots">Spin Slots</button>
      <div id="slot-result"></div>
    </div>
  </div>
  <div id="ledger">
    <h4>Transaction Ledger</h4>
    <ul id="ledger-list"></ul>
  </div>
  <div id="blackjack-modal" class="modal">
    <div class="modal-content">
      <span class="close-button">×</span>
      <h2>Blackjack</h2>
      <div class="game-container">
        <input type="number" id="blackjack-bet" placeholder="Bet amount">
        <button id="blackjack-start">Start</button>
        <div id="blackjack-game">
          <p>Player: <span id="player-hand"></span></p>
          <p>Dealer: <span id="dealer-hand"></span></p>
          <button id="hit">Hit</button>
          <button id="stand">Stand</button>
          <button id="double-down">Double Down</button>
          <button id="split" disabled>Split</button>
        </div>
        <div id="blackjack-result"></div>
      </div>
    </div>
  </div>
  <div id="slots-modal" class="modal">
    <div class="modal-content">
      <span class="close-button">×</span>
      <h2>Slot Machine</h2>
      <div class="game-container">
        <input type="number" id="slots-bet" placeholder="Bet ($1-$500)" min="1" max="500">
        <button id="slots-spin">Spin</button>
        <div id="slots-reels"></div>
        <div id="slots-result"></div>
      </div>
    </div>
  </div>
  <div id="rocket-modal" class="modal">
    <div class="modal-content">
      <span class="close-button">×</span>
      <h2>Rocket Game</h2>
      <div class="game-container">
        <input type="number" id="rocket-bet" placeholder="Bet amount">
        <button id="rocket-start">Launch</button>
        <div id="rocket-multiplier">1.00x</div>
        <button id="rocket-cashout" disabled>Cash Out</button>
        <div id="rocket-result"></div>
      </div>
    </div>
  </div>
  <div id="bank-modal" class="modal">
    <div class="modal-content">
      <span class="close-button">×</span>
      <h2>Bank Account</h2>
      <p>Current Balance: <span id="modal-balance">$1,000,000</span></p>
    </div>
  </div>
  <div id="ledger-modal" class="modal">
    <div class="modal-content">
      <span class="close-button">×</span>
      <h2>Transaction Ledger</h2>
      <ul id="modal-ledger-list" style="max-height: 300px; overflow-y: auto;"></ul>
    </div>
  </div>
  <footer>
    <p>© 2024 AUSTINWRAP. All Rights Reserved.</p>
  </footer>
  <script>
    const canvas = document.getElementById("particle-canvas");
    const ctx = canvas.getContext("2d");
    let particles = [];
    const particleCount = 100;
    function resizeCanvas() {
      canvas.width = window.innerWidth;
      canvas.height = window.innerHeight;
    }
    window.addEventListener("resize", resizeCanvas);
    resizeCanvas();
    function Particle() {
      this.x = Math.random() * canvas.width;
      this.y = Math.random() * canvas.height;
      this.radius = Math.random() * 2 + 1;
      this.vx = (Math.random() - 0.5) * 0.5;
      this.vy = (Math.random() - 0.5) * 0.5;
    }
    Particle.prototype.update = function() {
      this.x += this.vx;
      this.y += this.vy;
      if (this.x < 0 || this.x > canvas.width) this.vx = -this.vx;
      if (this.y < 0 || this.y > canvas.height) this.vy = -this.vy;
    }
    Particle.prototype.draw = function() {
      ctx.beginPath();
      ctx.arc(this.x, this.y, this.radius, 0, Math.PI * 2, false);
      ctx.fillStyle = "#00A1D6";
      ctx.fill();
    }
    function initParticles() {
      particles = [];
      for (let i = 0; i < particleCount; i++) {
        particles.push(new Particle());
      }
    }
    function animateParticles() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);
      particles.forEach(p => {
        p.update();
        p.draw();
      });
      requestAnimationFrame(animateParticles);
    }
    initParticles();
    animateParticles();

    let balance = 1000000;
    let transactions = [];
    const balanceDisplay = document.getElementById("account-balance");
    const modalBalance = document.getElementById("modal-balance");
    const ledgerList = document.getElementById("ledger-list");
    const modalLedgerList = document.getElementById("modal-ledger-list");
    function updateBalance() {
      balanceDisplay.textContent = "$" + balance.toLocaleString();
      modalBalance.textContent = "$" + balance.toLocaleString();
    }
    function logTransaction(message) {
      transactions.unshift(message);
      const li = document.createElement("li");
      li.textContent = message;
      ledgerList.prepend(li);
      const modalLi = document.createElement("li");
      modalLi.textContent = message;
      modalLedgerList.prepend(modalLi);
    }
    window.addEventListener("load", () => {
      transactions = [];
      ledgerList.innerHTML = "";
      modalLedgerList.innerHTML = "";
      updateBalance();
    });

    document.getElementById("hamburger").addEventListener("click", () => {
      document.getElementById("nav-links").classList.toggle("show");
    });

    document.getElementById("bank-link").addEventListener("click", () => {
      document.getElementById("bank-modal").style.display = "block";
    });
    document.getElementById("ledger-link").addEventListener("click", () => {
      document.getElementById("ledger-modal").style.display = "block";
    });

    // Bank Actions
    document.getElementById("bet-all").addEventListener("click", () => {
      if (balance <= 0) return;
      const bet = balance;
      if (Math.random() < 0.5) {
        balance += bet;
        logTransaction("All or Nothing Win: +" + bet);
        alert("Jackpot! You doubled your money!");
      } else {
        balance = 0;
        logTransaction("All or Nothing Loss: Lost it all!");
        alert("Ouch! You lost everything!");
      }
      updateBalance();
    });
    document.getElementById("bet-10").addEventListener("click", () => {
      if (balance <= 0) return;
      const bet = Math.floor(balance * 0.1);
      if (Math.random() < 0.5) {
        balance += bet;
        logTransaction("Bet 10% Win: +" + bet);
      } else {
        balance -= bet;
        logTransaction("Bet 10% Loss: -" + bet);
      }
      updateBalance();
    });
    document.getElementById("tip-jar").addEventListener("click", () => {
      const tip = 100;
      if (balance < tip) return;
      balance -= tip;
      logTransaction("Tip Jar Donation: -" + tip);
      updateBalance();
      alert("Thank you for the tip!");
    });
    document.getElementById("trash-money").addEventListener("click", () => {
      const loss = 50;
      if (balance < loss) return;
      balance -= loss;
      logTransaction("Trash Money: -" + loss);
      updateBalance();
      alert("You threw some money away!");
    });
    document.getElementById("donate-money").addEventListener("click", () => {
      const donation = 200;
      if (balance < donation) return;
      balance -= donation;
      logTransaction("Donation: -" + donation);
      updateBalance();
      alert("Thank you for your donation!");
    });
    updateBalance();

    // Blackjack Logic
    const blackjackModal = document.getElementById("blackjack-modal");
    let playerCards = [], dealerCards = [], bet = 0, canSplit = false;
    function getRandomCard() {
      const ranks = ["A", "2", "3", "4", "5", "6", "7", "8", "9", "10", "J", "Q", "K"];
      const suits = ["♠", "♥", "♦", "♣"];
      let rank = ranks[Math.floor(Math.random() * ranks.length)];
      let suit = suits[Math.floor(Math.random() * suits.length)];
      let value = (rank === "A") ? 11 : (["J", "Q", "K"].includes(rank) ? 10 : parseInt(rank));
      return { label: rank + suit, value: value };
    }
    function calculateTotal(cards) {
      let total = cards.reduce((sum, card) => sum + card.value, 0);
      let aceCount = cards.filter(card => card.label[0] === "A").length;
      while (total > 21 && aceCount > 0) {
        total -= 10;
        aceCount--;
      }
      return total;
    }
    document.getElementById("play-blackjack").addEventListener("click", () => {
      blackjackModal.style.display = "block";
      document.getElementById("blackjack-game").style.display = "none";
      document.getElementById("blackjack-result").innerHTML = "";
    });
    document.getElementById("blackjack-start").addEventListener("click", () => {
      bet = parseInt(document.getElementById("blackjack-bet").value);
      if (isNaN(bet) || bet <= 0 || bet > balance) {
        document.getElementById("blackjack-result").innerHTML = "Invalid bet!";
        return;
      }
      balance -= bet;
      updateBalance();
      playerCards = [getRandomCard(), getRandomCard()];
      dealerCards = [getRandomCard(), getRandomCard()];
      document.getElementById("player-hand").textContent = playerCards.map(c => c.label).join(", ");
      document.getElementById("dealer-hand").textContent = dealerCards[0].label + ", ?";
      document.getElementById("blackjack-game").style.display = "block";
      canSplit = playerCards[0].value === playerCards[1].value;
      document.getElementById("split").disabled = !canSplit;
    });
    document.getElementById("hit").addEventListener("click", () => {
      playerCards.push(getRandomCard());
      let total = calculateTotal(playerCards);
      document.getElementById("player-hand").textContent = playerCards.map(c => c.label).join(", ");
      if (total > 21) {
        endBlackjack("loss");
      }
    });
    document.getElementById("stand").addEventListener("click", () => {
      dealerTurn();
    });
    document.getElementById("double-down").addEventListener("click", () => {
      if (balance < bet) return;
      balance -= bet;
      bet *= 2;
      updateBalance();
      playerCards.push(getRandomCard());
      document.getElementById("player-hand").textContent = playerCards.map(c => c.label).join(", ");
      if (calculateTotal(playerCards) > 21) {
        endBlackjack("loss");
      } else {
        dealerTurn();
      }
    });
    document.getElementById("split").addEventListener("click", () => {
      if (!canSplit || balance < bet) return;
      balance -= bet;
      updateBalance();
      alert("Split not fully implemented yet! Playing one hand for now.");
      dealerTurn();
    });
    function dealerTurn() {
      while (calculateTotal(dealerCards) < 17) {
        dealerCards.push(getRandomCard());
      }
      document.getElementById("dealer-hand").textContent = dealerCards.map(c => c.label).join(", ");
      endBlackjack();
    }
    function endBlackjack(outcome = null) {
      let playerTotal = calculateTotal(playerCards);
      let dealerTotal = calculateTotal(dealerCards);
      let result = "";
      if (outcome === "loss" || playerTotal > 21) {
        result = "You bust! Lost: -" + bet;
        logTransaction("Blackjack Loss: -" + bet);
      } else if (dealerTotal > 21 || playerTotal > dealerTotal) {
        let payout = (playerCards.length === 2 && playerTotal === 21) ? bet * 2.5 : bet * 2;
        balance += payout;
        result = "You win! +" + payout;
        logTransaction("Blackjack Win: +" + payout);
      } else if (playerTotal === dealerTotal) {
        balance += bet;
        result = "Push. Bet returned.";
        logTransaction("Blackjack Push");
      } else {
        result = "Dealer wins! Lost: -" + bet;
        logTransaction("Blackjack Loss: -" + bet);
      }
      document.getElementById("blackjack-result").innerHTML = result;
      document.getElementById("blackjack-game").style.display = "none";
      updateBalance();
    }

    // Slot Machine Logic
    const slotsModal = document.getElementById("slots-modal");
    const slotSymbols = [
      { emoji: "🍺", payout: 3, prob: 0.35 },
      { emoji: "🥃", payout: 5, prob: 0.25 },
      { emoji: "💨", payout: 10, prob: 0.20 },
      { emoji: "🔫", payout: 20, prob: 0.10 },
      { emoji: "💎", payout: 50, prob: 0.07 },
      { emoji: "🍉", payout: 15, prob: 0.03 }
    ];
    document.getElementById("play-slots").addEventListener("click", () => {
      slotsModal.style.display = "block";
      document.getElementById("slots-result").innerHTML = "";
    });
    document.getElementById("slots-spin").addEventListener("click", () => {
      let bet = parseInt(document.getElementById("slots-bet").value);
      if (isNaN(bet) || bet < 1 || bet > 500 || bet > balance) {
        document.getElementById("slots-result").innerHTML = "Invalid bet! ($1-$500)";
        return;
      }
      balance -= bet;
      updateBalance();
      let spinDuration = 1500, spinInterval = 50, elapsed = 0;
      const reels = document.getElementById("slots-reels");
      const interval = setInterval(() => {
        let r1 = slotSymbols[Math.floor(Math.random() * slotSymbols.length)].emoji;
        let r2 = slotSymbols[Math.floor(Math.random() * slotSymbols.length)].emoji;
        let r3 = slotSymbols[Math.floor(Math.random() * slotSymbols.length)].emoji;
        reels.innerHTML = `${r1} | ${r2} | ${r3}`;
        elapsed += spinInterval;
        if (elapsed >= spinDuration) {
          clearInterval(interval);
          let result = spinSlots(bet);
          reels.innerHTML = `${result.reels[0]} | ${result.reels[1]} | ${result.reels[2]}`;
          document.getElementById("slots-result").innerHTML = result.message;
          balance += result.payout;
          updateBalance();
          logTransaction(result.log);
        }
      }, spinInterval);
    });
    function spinSlots(bet) {
      let reels = [];
      for (let i = 0; i < 3; i++) {
        let rand = Math.random();
        let cumulativeProb = 0;
        for (let symbol of slotSymbols) {
          cumulativeProb += symbol.prob;
          if (rand <= cumulativeProb) {
            reels.push(symbol.emoji);
            break;
          }
        }
      }
      let payout = 0, message = "", log = "";
      if (reels[0] === reels[1] && reels[1] === reels[2]) {
        payout = bet * slotSymbols.find(s => s.emoji === reels[0]).payout;
        message = `Jackpot! +$${payout}`;
        log = `Slots Jackpot: +${payout}`;
      } else if (reels[0] === reels[1] || reels[1] === reels[2] || reels[0] === reels[2]) {
        payout = bet * (reels.includes("💎") ? 2 : 1.5);
        message = `Two match! +$${payout}`;
        log = `Slots Win: +${payout}`;
      } else if (reels.includes("💎")) {
        payout = bet * 1.5;
        message = `Diamond bonus! +$${payout}`;
        log = `Slots Bonus: +${payout}`;
      } else {
        message = `Lost: -$${bet}`;
        log = `Slots Loss: -${bet}`;
        payout = 0;
      }
      return { reels, payout, message, log };
    }

    // Rocket Game Logic
    const rocketModal = document.getElementById("rocket-modal");
    let rocketBet = 0, multiplier = 1, crashed = false, intervalId;
    document.getElementById("play-rocket").addEventListener("click", () => {
      rocketModal.style.display = "block";
      document.getElementById("rocket-result").innerHTML = "";
      document.getElementById("rocket-cashout").disabled = true;
    });
    document.getElementById("rocket-start").addEventListener("click", () => {
      rocketBet = parseInt(document.getElementById("rocket-bet").value);
      if (isNaN(rocketBet) || rocketBet <= 0 || rocketBet > balance) {
        document.getElementById("rocket-result").innerHTML = "Invalid bet!";
        return;
      }
      balance -= rocketBet;
      updateBalance();
      multiplier = 1;
      crashed = false;
      document.getElementById("rocket-multiplier").textContent = "1.00x";
      document.getElementById("rocket-start").disabled = true;
      document.getElementById("rocket-cashout").disabled = false;
      intervalId = setInterval(() => {
        if (crashed) return;
        multiplier += 0.05;
        document.getElementById("rocket-multiplier").textContent = multiplier.toFixed(2) + "x";
        if (Math.random() < crashProbability(multiplier)) {
          crashed = true;
          clearInterval(intervalId);
          document.getElementById("rocket-result").innerHTML = `Crashed at ${multiplier.toFixed(2)}x! Lost: -$${rocketBet}`;
          logTransaction(`Rocket Loss: -${rocketBet}`);
          document.getElementById("rocket-start").disabled = false;
          document.getElementById("rocket-cashout").disabled = true;
        }
      }, 100);
    });
    document.getElementById("rocket-cashout").addEventListener("click", () => {
      if (!crashed) {
        clearInterval(intervalId);
        let payout = Math.floor(rocketBet * multiplier);
        balance += payout;
        document.getElementById("rocket-result").innerHTML = `Cashed out at ${multiplier.toFixed(2)}x! +$${payout}`;
        logTransaction(`Rocket Win: +${payout}`);
        updateBalance();
        document.getElementById("rocket-start").disabled = false;
        document.getElementById("rocket-cashout").disabled = true;
      }
    });
    function crashProbability(multiplier) {
      if (multiplier < 2) return 0.05;
      if (multiplier < 5) return 0.1;
      if (multiplier < 10) return 0.2;
      if (multiplier < 20) return 0.3;
      if (multiplier < 100) return 0.5;
      return 0.7;
    }

    // Mini Slots Logic
    document.getElementById("spin-slots").addEventListener("click", () => {
      let bet = parseInt(document.getElementById("slot-bet").value);
      if (isNaN(bet) || bet <= 0 || bet > balance) {
        document.getElementById("slot-result").textContent = "Invalid bet!";
        return;
      }
      balance -= bet;
      updateBalance();
      let spinDuration = 1500, spinInterval = 50, elapsed = 0;
      const resultDiv = document.getElementById("slot-result");
      const interval = setInterval(() => {
        let r1 = slotSymbols[Math.floor(Math.random() * slotSymbols.length)].emoji;
        let r2 = slotSymbols[Math.floor(Math.random() * slotSymbols.length)].emoji;
        let r3 = slotSymbols[Math.floor(Math.random() * slotSymbols.length)].emoji;
        resultDiv.textContent = `${r1} | ${r2} | ${r3}`;
        elapsed += spinInterval;
        if (elapsed >= spinDuration) {
          clearInterval(interval);
          let result = spinSlots(bet);
          resultDiv.textContent = `${result.reels.join(" | ")} - ${result.message}`;
          balance += result.payout;
          updateBalance();
          logTransaction(result.log);
        }
      }, spinInterval);
    });

    // Modal Close
    document.querySelectorAll(".close-button").forEach(btn => {
      btn.addEventListener("click", () => {
        btn.closest(".modal").style.display = "none";
      });
    });
    window.addEventListener("click", (event) => {
      if (event.target.classList.contains("modal")) {
        event.target.style.display = "none";
      }
    });

    // Draggable Panels
    dragElement(document.getElementById("bank-panel"));
    dragElement(document.getElementById("slot-panel"));
    function dragElement(elmnt) {
      let pos1 = 0, pos2 = 0, pos3 = 0, pos4 = 0;
      let header = elmnt.querySelector("[id$='header']");
      if (header) header.onmousedown = dragMouseDown;
      function dragMouseDown(e) {
        e.preventDefault();
        pos3 = e.clientX;
        pos4 = e.clientY;
        document.onmouseup = closeDragElement;
        document.onmousemove = elementDrag;
      }
      function elementDrag(e) {
        e.preventDefault();
        pos1 = pos3 - e.clientX;
        pos2 = pos4 - e.clientY;
        pos3 = e.clientX;
        pos4 = e.clientY;
        elmnt.style.top = (elmnt.offsetTop - pos2) + "px";
        elmnt.style.left = (elmnt.offsetLeft - pos1) + "px";
      }
      function closeDragElement() {
        document.onmouseup = null;
        document.onmousemove = null;
      }
    }

    // Minimize Panels
    document.getElementById("minimize-bank").addEventListener("click", function() {
      let content = document.getElementById("bank-content");
      content.style.display = content.style.display === "none" ? "block" : "none";
      this.textContent = content.style.display === "none" ? "+" : "_";
    });
    document.getElementById("minimize-slot").addEventListener("click", function() {
      let content = document.getElementById("slot-content");
      content.style.display = content.style.display === "none" ? "block" : "none";
      this.textContent = content.style.display === "none" ? "+" : "_";
    });
  </script>
</body>
</html>
