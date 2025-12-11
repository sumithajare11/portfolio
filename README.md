# portfolio

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Sumit Hajare - Portfolio</title>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Poppins', sans-serif; }
    body { background: #0e0e0e; color: #fff; line-height: 1.6; }
    header { padding: 40px 10%; display: flex; justify-content: space-between; align-items: center; }
    header h1 { font-size: 28px; font-weight: 700; }
    nav a { margin-left: 25px; text-decoration: none; color: #fff; font-weight: 500; }

    .hero { padding: 90px 10%; text-align: left; }
    .hero h2 { font-size: 48px; font-weight: 700; }
    .hero h3 { font-size: 24px; margin-top: 10px; color: #00e1ff; }
    .hero p { margin-top: 20px; width: 60%; }
    .btn { display: inline-block; margin-top: 25px; padding: 12px 25px; background: #00e1ff; color: #000; font-weight: 600; text-decoration: none; border-radius: 6px; }

    .section { padding: 80px 10%; }
    .section h2 { font-size: 36px; font-weight: 700; margin-bottom: 30px; border-left: 5px solid #00e1ff; padding-left: 15px; }

    .skills-grid, .projects-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 25px; }
    .card { background: #1a1a1a; padding: 25px; border-radius: 10px; border: 1px solid #333; transition: 0.3s; }
    .card:hover { transform: translateY(-5px); border-color: #00e1ff; }
    .card h3 { margin-bottom: 10px; color: #00e1ff; }

    footer { text-align: center; padding: 40px; background: #111; margin-top: 50px; }

    /* Responsive */
    @media (max-width: 768px) {
      .hero h2 { font-size: 36px; }
      .hero p { width: 100%; }
    }
  </style>
</head>
<body>

<header>
  <h1>Sumit Hajare</h1>
  <nav>
    <a href="#skills">Skills</a>
    <a href="#projects">Projects</a>
    <a href="#contact">Contact</a>
  </nav>
</header>

<section class="hero">
  <h2>Hello, I'm Sumit 👋</h2>
  <h3>IoT & Embedded Systems Developer</h3>
  <p>Passionate B.Tech (E&TC) graduate with hands-on experience in IoT development, embedded systems, cloud-based automation, and application integration. Strong problem-solving mindset with the ability to convert business needs into efficient technical solutions.</p>
  <a class="btn" href="#projects">View My Work</a>
</section>

<section class="section" id="skills">
  <h2>Skills</h2>
  <div class="skills-grid">
    <div class="card"><h3>Programming</h3><p>C, Python, Embedded C, Java (Basic)</p></div>
    <div class="card"><h3>IoT Platforms</h3><p>MQTT, Blynk, ThingSpeak</p></div>
    <div class="card"><h3>Microcontrollers</h3><p>Arduino, ESP32, ESP8266, Raspberry Pi</p></div>
    <div class="card"><h3>Tools</h3><p>Git, VS Code, MATLAB</p></div>
  </div>
</section>

<section class="section" id="projects">
  <h2>Projects</h2>
  <div class="projects-grid">
    <div class="card">
      <h3>Railway Accident Prevention System</h3>
      <p>IoT-based railway safety system with sensor fusion, GPS/GSM modules, and cloud monitoring achieving 95% anomaly detection accuracy.</p>
    </div>
    <div class="card">
      <h3>Smart Drip Automation System</h3>
      <p>Automated irrigation solution using soil-moisture control, ESP32 cloud integration, and wireless mobile monitoring.</p>
    </div>
    <div class="card">
      <h3>Automated Home Monitoring System</h3>
      <p>Smart home system with real-time appliance control and remote security monitoring using IoT and mobile integration.</p>
    </div>
  </div>
</section>

<section class="section" id="contact">
  <h2>Contact</h2>
  <p>Email: <strong>sumithajare2003@gmail.com</strong></p>
  <p>GitHub: <strong>github.com/sumithajare11</strong></p>
  <p>LinkedIn: <strong>linkedin.com/in/sumit-hajare-3b562132b</strong></p>
</section>

<footer>
  <p>© 2025 Sumit Hajare | Portfolio Website</p>
</footer>

</body>
</html>
