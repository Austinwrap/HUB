<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>AUSTINWRAP - Manly Market Madness</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <!-- Enable mobile full-screen capabilities -->
  <meta name="apple-mobile-web-app-capable" content="yes">
  <meta name="mobile-web-app-capable" content="yes">
  <!-- Google Fonts & Font Awesome -->
  <link href="https://fonts.googleapis.com/css?family=Montserrat:400,700|Playfair+Display:400,700&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <style>
    /* Global Reset */
    * { margin: 0; padding: 0; box-sizing: border-box; }
    
    /* Body & Background: Deep Blue–Teal Gradient */
    body {
      font-family: 'Montserrat', sans-serif;
      background: linear-gradient(135deg, #0F2027, #203A43, #2C5364);
      background-size: 400% 400%;
      animation: gradientBG 20s ease infinite;
      overflow-x: hidden;
      color: #EEE;
      position: relative;
      padding-bottom: 150px; /* room for ledger */
    }
    @keyframes gradientBG {
      0%   { background-position: 0% 50%; }
      50%  { background-position: 100% 50%; }
      100% { background-position: 0% 50%; }
    }
    
    /* Particle Background Canvas */
    #particle-canvas {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      z-index: -1;
    }
    
    /* Top Stock Ticker - Slower Animation, Abbreviated Symbols */
    .stock-ticker {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      background: rgba(0,0,0,0.85);
      color: #00C6FF;
      padding: 10px 20px;
      font-size: 1.2em;
      white-space: nowrap;
      overflow: hidden;
      z-index: 1600;
      text-shadow: 0 0 8px #00C6FF;
    }
    .stock-ticker span {
      display: inline-block;
      padding-left: 100%;
      animation: ticker-top 40s linear infinite;
    }
    @keyframes ticker-top {
      0% { transform: translateX(0); }
      100% { transform: translateX(-100%); }
    }
    
    /* Navigation (with dropdown for Account) */
    nav {
      position: fixed;
      width: 100%;
      top: 45px; /* below ticker */
      left: 0;
      background: rgba(0, 0, 0, 0.9);
      padding: 10px 20px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      z-index: 1500;
      box-shadow: 0 2px 5px rgba(0,0,0,0.7);
    }
    nav .logo {
      font-family: 'Playfair Display', serif;
      font-size: 2em;
      font-weight: bold;
      color: #00C6FF;
      text-shadow: 0 0 10px #00C6FF;
    }
    nav ul {
      list-style: none;
      display: flex;
      gap: 15px;
    }
    nav ul li {
      position: relative;
    }
    nav ul li a {
      text-decoration: none;
      color: #EEE;
      font-weight: 600;
      transition: color 0.3s;
    }
    nav ul li a:hover { 
      color: #00C6FF;
    }
    /* Dropdown styling */
    nav ul li .dropdown {
      display: none;
      position: absolute;
      top: 100%;
      left: 0;
      background: rgba(0,0,0,0.95);
      padding: 10px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.7);
      z-index: 1700;
    }
    nav ul li:hover .dropdown {
      display: block;
    }
    nav ul li .dropdown li {
      margin: 5px 0;
    }
    nav ul li .dropdown li a {
      color: #EEE;
    }
    .hamburger {
      display: none;
      font-size: 1.5em;
      cursor: pointer;
      color: #EEE;
    }
    @media (max-width: 768px) {
      nav ul {
        display: none;
        flex-direction: column;
        position: fixed;
        top: 55px;
        right: 0;
        background: rgba(0,0,0,0.95);
        padding: 20px;
        box-shadow: -2px 2px 5px rgba(0,0,0,0.7);
      }
      nav ul.show { display: flex; }
      .hamburger { display: block; }
    }
    
    /* Hero Section */
    header {
      padding: 100px 10px 20px;
      text-align: center;
      margin-top: 80px;
    }
    header h1 {
      font-family: 'Playfair Display', serif;
      font-size: 3em;
      margin-bottom: 10px;
      color: #00C6FF;
      text-shadow: 0 0 10px #00C6FF;
      animation: pulse 3s infinite;
    }
    @keyframes pulse {
      0% { transform: scale(1); }
      50% { transform: scale(1.05); }
      100% { transform: scale(1); }
    }
    header p {
      font-size: 1.2em;
      margin-bottom: 20px;
      color: #CCC;
    }
    
    /* Sections (Projects, Social, Shop) */
    section {
      padding: 50px 20px;
      text-align: center;
    }
    section h2 {
      font-family: 'Playfair Display', serif;
      font-size: 2.5em;
      margin-bottom: 20px;
      color: #00C6FF;
      text-shadow: 0 0 8px #00C6FF;
    }
    .section-content {
      max-width: 1200px;
      margin: 0 auto;
      display: flex;
      flex-wrap: wrap;
      gap: 20px;
      justify-content: center;
    }
    
    /* Cards with Neon-Cyan Accents */
    .card {
      background: #1A1A1A;
      border-radius: 10px;
      width: 280px;
      padding: 20px;
      box-shadow: 0 8px 15px rgba(0,0,0,0.6);
      transition: transform 0.3s, box-shadow 0.3s;
      text-decoration: none;
      color: #EEE;
      position: relative;
      overflow: hidden;
      border: 1px solid transparent;
    }
    .card:hover { 
      transform: scale(1.03);
      box-shadow: 0 12px 25px rgba(0,0,0,0.8), 0 0 10px #00C6FF;
      border: 1px solid #00C6FF;
    }
    .card-icon {
      font-size: 3rem;
      margin-bottom: 10px;
      color: #00C6FF;
      text-shadow: 0 0 8px #00C6FF;
    }
    .card h3 {
      margin-bottom: 8px;
      font-size: 1.5em;
      color: #00C6FF;
    }
    .card p {
      font-size: 1em;
      color: #CCC;
      margin-bottom: 15px;
    }
    .card button {
      background: transparent;
      border: 2px solid #00C6FF;
      color: #00C6FF;
      padding: 8px 16px;
      border-radius: 5px;
      cursor: pointer;
      transition: background 0.3s, color 0.3s;
    }
    .card button:hover { 
      background: #00C6FF;
      color: #1A1A1A;
    }
    
    /* Bottom Ticker - Slower & Refined with Factual Abbreviations */
    .beer-ticker {
      position: fixed;
      bottom: 0;
      left: 0;
      width: 100%;
      background: rgba(0,0,0,0.8);
      color: #00C6FF;
      padding: 15px 20px;
      font-size: 1.2em;
      white-space: nowrap;
      overflow: hidden;
      z-index: 1500;
      text-shadow: 0 0 8px #00C6FF;
    }
    .beer-ticker span {
      display: inline-block;
      padding-left: 100%;
      animation: ticker 40s linear infinite;
    }
    @keyframes ticker {
      0%   { transform: translateX(0); }
      100% { transform: translateX(-100%); }
    }
    
    /* Bank Account Panel (Floating) with Draggable Header & Minimize Button */
    #bank-panel {
      position: fixed;
      right: 20px;
      bottom: 120px;
      background: rgba(0,0,0,0.9);
      border: 2px solid #00C6FF;
      border-radius: 10px;
      z-index: 1700;
      width: 220px;
      box-shadow: 0 0 15px #00C6FF;
    }
    /* Header for dragging and minimize control */
    #bank-header {
      cursor: move;
      background: rgba(0,0,0,0.8);
      padding: 5px 10px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      font-size: 1.1em;
      color: #00C6FF;
    }
    #minimize-bank {
      background: transparent;
      border: none;
      color: #00C6FF;
      font-size: 1.2em;
      cursor: pointer;
    }
    #bank-content {
      padding: 10px;
      text-align: center;
    }
    #bank-content p {
      font-size: 1.2em;
      margin-bottom: 10px;
    }
    #bank-content button {
      margin: 5px 0;
      width: 100%;
      background: transparent;
      border: 1px solid #00C6FF;
      color: #00C6FF;
      padding: 8px;
      border-radius: 5px;
      cursor: pointer;
      transition: background 0.3s;
    }
    #bank-content button:hover {
      background: #00C6FF;
      color: #1A1A1A;
    }
    
    /* Ledger at the Bottom */
    #ledger {
      position: fixed;
      left: 0;
      bottom: 0;
      width: 100%;
      max-height: 100px;
      overflow-y: auto;
      background: rgba(0,0,0,0.85);
      color: #00C6FF;
      padding: 10px 20px;
      font-size: 0.9em;
      z-index: 1800;
      border-top: 2px solid #00C6FF;
    }
    #ledger h4 {
      margin-bottom: 5px;
    }
    #ledger ul {
      list-style: none;
      max-height: 70px;
      overflow-y: auto;
    }
    #ledger li {
      margin-bottom: 3px;
    }
    
    /* Blackjack Modal */
    .modal {
      display: none;
      position: fixed;
      z-index: 1900;
      left: 0;
      top: 0;
      width: 100%;
      height: 100%;
      overflow: auto;
      background: rgba(0,0,0,0.8);
    }
    .modal-content {
      background: #1A1A1A;
      margin: 10% auto;
      padding: 20px;
      border: 2px solid #00C6FF;
      width: 90%;
      max-width: 400px;
      border-radius: 10px;
      color: #EEE;
      text-align: center;
      position: relative;
    }
    .close-button {
      color: #00C6FF;
      float: right;
      font-size: 1.5em;
      font-weight: bold;
      cursor: pointer;
    }
    
    /* Footer */
    footer {
      padding: 20px 10px;
      background: #0F2027;
      text-align: center;
      font-size: 0.9em;
      color: #777;
      margin-top: 40px;
    }
    
    /* Media Query to Scale Down Bank Panel on Small Screens */
    @media (max-width: 480px) {
      #bank-panel {
        width: 180px;
        right: 10px;
        bottom: 80px;
        font-size: 0.9em;
      }
      #bank-header {
        font-size: 1em;
      }
      #bank-content p {
        font-size: 1em;
      }
      #bank-content button {
        padding: 6px;
        font-size: 0.8em;
      }
    }
  </style>
</head>
<body>
  <!-- Particle Background Canvas -->
  <canvas id="particle-canvas"></canvas>
  
  <!-- Top Stock Ticker with Abbreviated, Factual Symbols -->
  <div class="stock-ticker">
    <span>
      TRK: +350 | FMPR: +400 | CHKN: +250 | RSTR: +300 | MECH: +350 | BEER: +200 | BUS: +500 | TRCK: +450 | VAC: +75 | SILO: +300 | GRAIN: +400 | TIRE: +150 | ENG: +300 | PRD: +250 | EBK: +100 | PLNT: +320 | CATT: +280 | OIL: +210 | BBQ: +270 | DSH: +330
    </span>
  </div>
  
  <!-- Navigation -->
  <nav id="navbar">
    <div class="logo">AUSTINWRAP</div>
    <div class="hamburger" id="hamburger"><i class="fas fa-bars"></i></div>
    <ul id="nav-links">
      <li><a href="#projects">Projects</a></li>
      <li><a href="#social">Social</a></li>
      <li><a href="#shop">Shop</a></li>
      <li>
        <a href="#">Account <i class="fas fa-caret-down"></i></a>
        <ul class="dropdown">
          <li><a href="#bank-panel">Bank</a></li>
          <li><a href="#ledger">Ledger</a></li>
        </ul>
      </li>
    </ul>
  </nav>
  
  <!-- Hero Section -->
  <header id="home">
    <h1>Welcome to AUSTINWRAP</h1>
    <p>Experience a dark blend of raw creativity and non‑stop action.</p>
  </header>
  
  <!-- Projects Section -->
  <section id="projects">
    <h2>Featured Projects</h2>
    <div class="section-content">
      <!-- Card 1: Bartending Game -->
      <a class="card" href="https://austinwrap.github.io/Bartend/" target="_blank">
        <div class="card-icon"><i class="fas fa-cocktail"></i></div>
        <h3>Bartending Game</h3>
        <p>Mix drinks and manage your bar in an engaging simulation.</p>
        <button>Learn More</button>
      </a>
      <!-- Card 2: Chicken Farm Game -->
      <a class="card" href="https://austinwrap.github.io/FrostyFarms/" target="_blank">
        <div class="card-icon"><i class="fas fa-drumstick-bite"></i></div>
        <h3>Chicken Farm Game</h3>
        <p>Raise your quirky flock and enjoy a farm twist.</p>
        <button>Learn More</button>
      </a>
      <!-- Card 3: Bristol Tycoon -->
      <a class="card" href="https://austinwrap.github.io/BristolTycoon/" target="_blank">
        <div class="card-icon"><i class="fas fa-building"></i></div>
        <h3>Bristol Tycoon</h3>
        <p>Build your empire with sophisticated strategy.</p>
        <button>Learn More</button>
      </a>
      <!-- Card 4: Bad Mailman -->
      <a class="card" href="https://austinwrap.github.io/bad-mailman/" target="_blank">
        <div class="card-icon"><i class="fas fa-envelope"></i></div>
        <h3>Bad Mailman</h3>
        <p>A quirky twist on the classic mail journey.</p>
        <button>Learn More</button>
      </a>
      <!-- Card 5: Feminine Stocks Simulator -->
      <a class="card" href="https://austinwrap.github.io/feminine-stocks/" target="_blank">
        <div class="card-icon"><i class="fas fa-chart-line"></i></div>
        <h3>Feminine Stocks Simulator</h3>
        <p>Dive into a satirical stock market simulation with a twist.</p>
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
        <p>Watch behind‑the‑scenes and creative explorations.</p>
        <button>Visit Channel</button>
      </a>
      <!-- Social Card 2: Instagram -->
      <a class="card" href="https://www.instagram.com/austinwrap" target="_blank">
        <div class="card-icon"><i class="fab fa-instagram"></i></div>
        <h3>Instagram</h3>
        <p>Follow for tasteful moments and creative insights.</p>
        <button>Follow Me</button>
      </a>
      <!-- Social Card 3: TikTok -->
      <a class="card" href="https://www.tiktok.com/@austinwrap" target="_blank">
        <div class="card-icon"><i class="fab fa-tiktok"></i></div>
        <h3>TikTok</h3>
        <p>Enjoy quick bursts of creative flair and fun.</p>
        <button>Watch Now</button>
      </a>
      <!-- Social Card 4: Twitch -->
      <a class="card" href="https://www.twitch.tv/austinwrap_" target="_blank">
        <div class="card-icon"><i class="fab fa-twitch"></i></div>
        <h3>Twitch</h3>
        <p>Join live sessions filled with interactive entertainment.</p>
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
        <p>Experience a full‑service bartending experience online.</p>
        <button>Visit Site</button>
      </a>
      <!-- Shop Card 2: Roundhouse Powerwash LLC -->
      <a class="card" href="https://austinwrap.github.io/Powerwash/" target="_blank">
        <div class="card-icon"><i class="fas fa-water"></i></div>
        <h3>Roundhouse Powerwash LLC</h3>
        <p>Professional power washing for a pristine space.</p>
        <button>Learn More</button>
      </a>
      <!-- Shop Card 3: Etsy Shop -->
      <a class="card" href="https://www.etsy.com/shop/MyFavoriteAlien" target="_blank">
        <div class="card-icon"><i class="fas fa-shopping-bag"></i></div>
        <h3>Etsy Shop</h3>
        <p>Discover unique merchandise with a refined twist.</p>
        <button>Explore</button>
      </a>
      <!-- Shop Card 4: My Book on Amazon -->
      <a class="card" href="https://a.co/d/3AiLY0d" target="_blank">
        <div class="card-icon"><i class="fas fa-book"></i></div>
        <h3>My Book on Amazon</h3>
        <p>Explore creative journeys through literature.</p>
        <button>Buy Now</button>
      </a>
      <!-- Shop Card 5: Affirmations Journal -->
      <a class="card" href="https://a.co/d/bF8FTHW" target="_blank">
        <div class="card-icon"><i class="fas fa-book-open"></i></div>
        <h3>Affirmations Journal</h3>
        <p>Inspire your daily routine with thoughtful reflections.</p>
        <button>Get it Here</button>
      </a>
      <!-- Shop Card 6: CT Draft -->
      <a class="card" href="http://www.ctdraft.com" target="_blank">
        <div class="card-icon"><i class="fas fa-industry"></i></div>
        <h3>CT Draft</h3>
        <p>Explore high‑quality draft services tailored to your needs.</p>
        <button>Learn More</button>
      </a>
    </div>
  </section>
  
  <!-- Bank Account Panel (Draggable & Minimizable) -->
  <div id="bank-panel">
    <div id="bank-header">
      <span>Bank Account</span>
      <button id="minimize-bank">_</button>
    </div>
    <div id="bank-content">
      <p id="account-balance">$1,000,000</p>
      <button id="play-blackjack">Play Blackjack</button>
      <button id="bet-all">All or Nothing</button>
      <button id="bet-10">Bet 10%</button>
      <button id="tip-jar">Tip Jar</button>
      <button id="trash-money">Trash Money</button>
      <button id="donate-money">Donate</button>
    </div>
  </div>
  
  <!-- Transaction Ledger -->
  <div id="ledger">
    <h4>Transaction Ledger</h4>
    <ul id="ledger-list"></ul>
  </div>
  
  <!-- Blackjack Modal -->
  <div id="blackjack-modal" class="modal">
    <div class="modal-content">
      <span class="close-button">&times;</span>
      <h2>Blackjack Game</h2>
      <p>Enter your bet:</p>
      <input type="number" id="blackjack-bet" placeholder="Bet amount">
      <button id="play-btn">Play</button>
      <div id="blackjack-result"></div>
    </div>
  </div>
  
  <!-- Bottom Ticker with Factual Abbreviations -->
  <div class="beer-ticker">
    <span>
      Did you know? TRK=350, FMPR=400, CHKN=250, RSTR=300, MECH=350, BEER=200, BUS=500, TRCK=450, VAC=75, SILO=300, GRAIN=400, TIRE=150, ENG=300, PRD=250, EBK=100, PLNT=320, CATT=280, OIL=210, BBQ=270, DSH=330
    </span>
  </div>
  
  <footer>
    <p>&copy; 2024 AUSTINWRAP. All Rights Reserved.</p>
  </footer>
  
  <script>
    /* Particle Background Effect */
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
      ctx.fillStyle = "#00C6FF";
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
    
    /* Fake Bank Account & Ledger Logic */
    let balance = 1000000;
    const balanceDisplay = document.getElementById("account-balance");
    const ledgerList = document.getElementById("ledger-list");
    function updateBalance() {
      balanceDisplay.textContent = "$" + balance.toLocaleString();
    }
    function logTransaction(message) {
      const li = document.createElement("li");
      li.textContent = message;
      ledgerList.prepend(li);
    }
    
    /* Blackjack Modal Functionality */
    const blackjackModal = document.getElementById("blackjack-modal");
    const closeButton = document.querySelector(".close-button");
    document.getElementById("play-blackjack").addEventListener("click", () => {
      blackjackModal.style.display = "block";
    });
    closeButton.addEventListener("click", () => {
      blackjackModal.style.display = "none";
      document.getElementById("blackjack-result").textContent = "";
    });
    window.addEventListener("click", (event) => {
      if (event.target == blackjackModal) {
        blackjackModal.style.display = "none";
        document.getElementById("blackjack-result").textContent = "";
      }
    });
    
    document.getElementById("play-btn").addEventListener("click", () => {
      const betInput = document.getElementById("blackjack-bet");
      let bet = parseInt(betInput.value);
      if(isNaN(bet) || bet <= 0 || bet > balance){
        document.getElementById("blackjack-result").textContent = "Invalid bet amount!";
        return;
      }
      // Simulate a quick blackjack outcome (50% chance win)
      if(Math.random() < 0.5) {
        balance += bet;
        document.getElementById("blackjack-result").textContent = "You win! +" + bet;
        logTransaction("Blackjack Win: +" + bet);
      } else {
        balance -= bet;
        document.getElementById("blackjack-result").textContent = "You lose! -" + bet;
        logTransaction("Blackjack Loss: -" + bet);
      }
      updateBalance();
      betInput.value = "";
    });
    
    /* Other Bank Actions */
    document.getElementById("bet-all").addEventListener("click", () => {
      if(balance <= 0) return;
      const bet = balance;
      if(Math.random() < 0.5) {
        balance += bet; // double
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
      if(balance <= 0) return;
      const bet = Math.floor(balance * 0.1);
      if(Math.random() < 0.5) {
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
      if(balance < tip) return;
      balance -= tip;
      logTransaction("Tip Jar Donation: -" + tip);
      updateBalance();
      alert("Thank you for the tip!");
    });
    document.getElementById("trash-money").addEventListener("click", () => {
      const loss = 50;
      if(balance < loss) return;
      balance -= loss;
      logTransaction("Trash Money: -" + loss);
      updateBalance();
      alert("You threw some money away!");
    });
    document.getElementById("donate-money").addEventListener("click", () => {
      const donation = 200;
      if(balance < donation) return;
      balance -= donation;
      logTransaction("Donation: -" + donation);
      updateBalance();
      alert("Thank you for your donation!");
    });
    
    updateBalance();
    
    /* Draggable Bank Panel */
    dragElement(document.getElementById("bank-panel"));
    function dragElement(elmnt) {
      var pos1 = 0, pos2 = 0, pos3 = 0, pos4 = 0;
      var header = document.getElementById("bank-header");
      if (header) {
        header.onmousedown = dragMouseDown;
      } else {
        elmnt.onmousedown = dragMouseDown;
      }
      function dragMouseDown(e) {
        e = e || window.event;
        e.preventDefault();
        pos3 = e.clientX;
        pos4 = e.clientY;
        document.onmouseup = closeDragElement;
        document.onmousemove = elementDrag;
      }
      function elementDrag(e) {
        e = e || window.event;
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
    
    /* Minimize/Restore Bank Panel */
    document.getElementById("minimize-bank").addEventListener("click", function() {
      var content = document.getElementById("bank-content");
      if(content.style.display === "none"){
         content.style.display = "block";
         this.textContent = "_";
      } else {
         content.style.display = "none";
         this.textContent = "+";
      }
    });
  </script>
</body>
</html>
