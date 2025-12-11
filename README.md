# portfolio

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Sumit Hajare - Portfolio</title>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
  <style>
    /* Reset */
    * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Poppins', sans-serif; }

    body { background-color: #ffffff; color: #111; } /* Same as Manya's white background */
    a { text-decoration: none; color: inherit; }

    /* Header */
    header { display: flex; justify-content: space-between; align-items: center; padding: 30px 10%; position: sticky; top: 0; background: #fff; z-index: 1000; box-shadow: 0 2px 5px rgba(0,0,0,0.05); }
    header h1 { font-weight: 700; font-size: 28px; }
    nav a { margin-left: 25px; font-weight: 500; transition: 0.3s; }
    nav a:hover { color: #00bcd4; }

    /* Hero Section */
    .hero { display: flex; flex-direction: column; justify-content: center; padding: 100px 10%; text-align: left; }
    .hero h2 { font-size: 48px; font-weight: 700; color: #111; }
    .hero h3 { font-size: 24px; color: #00bcd4; margin-top: 10px; }
    .hero p { margin-top: 20px; font-size: 18px; line-height: 1.6; max-width: 650px; }
    .btn { display: inline-block; margin-top: 30px; padding: 12px 25px; background: #00bcd4; color: #fff; font-weight: 600; border-radius: 6px; transition: 0.3s; }
    .btn:hover { background: #0097a7; }

    /* Section Titles */
    .section { padding: 80px 10%; }
    .section h2 { font-size: 36px; font-weight: 700; margin-bottom: 30px; border-left: 5px solid #00bcd4; padding-left: 15px; }

    /* Skills & Projects Grid */
    .skills-grid, .projects-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 25px; }
    .card { background: #f5f5f5; padding: 25px; border-radius: 10px; transition: 0.3s; border: 1px solid #e0e0e0; }
    .card:hover { transform: translateY(-5px); box-shadow: 0 5px 15px rgba(0,0,0,0.1); }
    .card h3 { margin-bottom: 10px; color: #00bcd4; }
    .card p { color: #111; }

    /* Footer */
    footer { text-align: center; padding: 40px 10%; background: #f8f8f8; margin-top: 50px; font-size: 14px; color: #555; }

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
