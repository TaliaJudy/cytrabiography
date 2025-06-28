<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>✨ Cytra's Legendary Site ✨</title>
  <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@500;700&display=swap" rel="stylesheet" />
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    body {
      font-family: 'Orbitron', sans-serif;
      background: radial-gradient(circle, #000 0%, #0a0a0a 100%);
      color: #0ff;
      overflow-x: hidden;
    }
    canvas#stars {
      position: fixed;
      top: 0;
      left: 0;
      z-index: -1;
      width: 100%;
      height: 100%;
      pointer-events: none;
    }
    header {
      text-align: center;
      padding: 4rem 1rem 2rem;
      animation: fadeIn 2s ease;
    }
    header h1 {
      font-size: 3rem;
      background: linear-gradient(90deg, #0ff, #f0f, #0ff);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      animation: glow 3s infinite alternate;
    }
    @keyframes glow {
      from { text-shadow: 0 0 10px #0ff; }
      to { text-shadow: 0 0 20px #f0f, 0 0 40px #0ff; }
    }
    nav {
      position: sticky;
      top: 0;
      background: #000;
      display: flex;
      justify-content: center;
      gap: 2rem;
      padding: 1rem;
      z-index: 999;
    }
    nav a {
      color: #0ff;
      text-decoration: none;
      font-weight: bold;
      transition: 0.3s;
    }
    nav a:hover {
      color: #f0f;
    }
    section {
      max-width: 900px;
      margin: 2rem auto;
      padding: 2rem;
      background: rgba(0,0,0,0.6);
      border-radius: 1rem;
      box-shadow: 0 0 20px #0ff;
    }
    .btn {
      display: inline-block;
      margin-top: 1rem;
      padding: 0.75rem 1.5rem;
      background: linear-gradient(45deg, #0ff, #0fc);
      color: #000;
      border: none;
      border-radius: 40px;
      text-decoration: none;
      font-weight: bold;
      transition: 0.3s;
    }
    .btn:hover {
      transform: scale(1.1);
      box-shadow: 0 0 20px #0ff;
    }
    input, textarea {
      width: 100%;
      padding: 0.5rem;
      margin-bottom: 1rem;
      border: none;
      border-radius: 10px;
      font-family: inherit;
    }
    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }
    .typewriter {
      overflow: hidden;
      white-space: nowrap;
      border-right: 2px solid #0ff;
      animation: typing 4s steps(30) 1s 1 normal both, blink 1s step-end infinite;
    }
    @keyframes typing {
      from { width: 0 }
      to { width: 100% }
    }
    @keyframes blink {
      50% { border-color: transparent }
    }
    .theme-toggle {
      position: fixed;
      top: 1rem;
      right: 1rem;
      background: #0ff;
      color: #000;
      border: none;
      border-radius: 50px;
      padding: 0.5rem 1rem;
      font-weight: bold;
      cursor: pointer;
      z-index: 1000;
    }
  </style>
</head>
<body>
  <canvas id="stars"></canvas>
  <button class="theme-toggle" onclick="toggleTheme()">🌓 Toggle Theme</button>

  <header>
    <h1 class="typewriter">Welcome to Cytra's Legendary Space 👾</h1>
  </header>

  <nav>
    <a href="#about">About</a>
    <a href="#projects">Projects</a>
    <a href="#skills">Skills</a>
    <a href="#socials">Socials</a>
    <a href="#contact">Contact</a>
  </nav>

  <section id="about">
    <h2>👋 About Me</h2>
    <p>I'm <strong>Jack "Cytra" Waikwa</strong>, 16 y/o from Kenya 🇰🇪. Learning the magic of HTML & CSS while building my online empire 💻🌍.</p>
  </section>

  <section id="projects">
    <h2>🚀 Projects</h2>
    <ul>
      <li>📸 <a class="btn" href="https://taliajudy.github.io/cytra/">My Gallery</a></li>
      <li>🌍 <a class="btn" href="https://socialmedia-m7z4.onrender.com/">Social Media Link Hub</a></li>
    </ul>
  </section>

  <section id="skills">
    <h2>💡 Skills</h2>
    <p>✔️ HTML5<br>✔️ CSS3 Animations<br>✔️ Responsive Design<br>✔️ Building Vibes 😎</p>
  </section>

  <section id="socials">
    <h2>📱 Social Media</h2>
    <a class="btn" href="https://t.me/Cytrak9_bot">🤖 Telegram Bot</a>
    <a class="btn" href="https://ig-ban.vercel.app/">🚫 IG Ban Tool</a>
  </section>

  <section id="contact">
    <h2>📩 Leave a Message</h2>
    <form action="https://formsubmit.co/YOUR_EMAIL@example.com" method="POST">
      <input type="text" name="name" placeholder="Your name" required>
      <input type="email" name="email" placeholder="Your email" required>
      <textarea name="message" placeholder="Your message" rows="4" required></textarea>
      <button class="btn" type="submit">Send</button>
    </form>
  </section>

  <audio autoplay loop>
    <source src="https://www.dropbox.com/scl/fi/4v6g8ozclqmrylrag7v6f/SHOKA.m4a?rlkey=at5e8r4v548zdkaywzxwtlraa&st=z9edt1py&raw=1" type="audio/mpeg">
  </audio>

  <script>
    const canvas = document.getElementById('stars');
    const ctx = canvas.getContext('2d');
    let stars = Array.from({ length: 100 }, () => ({
      x: Math.random() * window.innerWidth,
      y: Math.random() * window.innerHeight,
      radius: Math.random() * 1.5,
      speed: 0.2 + Math.random()
    }));

    function resizeCanvas() {
      canvas.width = window.innerWidth;
      canvas.height = window.innerHeight;
    }

    function animateStars() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);
      ctx.fillStyle = 'white';
      stars.forEach(star => {
        star.y += star.speed;
        if (star.y > canvas.height) star.y = 0;
        ctx.beginPath();
        ctx.arc(star.x, star.y, star.radius, 0, Math.PI * 2);
        ctx.fill();
      });
      requestAnimationFrame(animateStars);
    }

    window.addEventListener('resize', resizeCanvas);
    resizeCanvas();
    animateStars();

    function toggleTheme() {
      const body = document.body;
      if (body.style.background.includes("radial")) {
        body.style.background = "#f9f9f9";
        body.style.color = "#111";
      } else {
        body.style.background = "radial-gradient(circle, #000 0%, #0a0a0a 100%)";
        body.style.color = "#0ff";
      }
    }
  </script>
</body>
</html>
4rem 1rem 2rem
