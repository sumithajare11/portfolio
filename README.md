<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfolio | Sumit Hajare</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* --- General Reset & Variables (Light Theme) --- */
        :root {
            --light-white: #ffffff;    /* Main Background Color (White) */
            --light-gray: #f0f0f0;     /* Secondary Background/Card Color (Very Light Gray) */
            --dark-navy: #172a45;      /* Primary Text Color (Dark) */
            --slate: #5e6f88;          /* Secondary Text Color (Medium Gray) */
            --green: #007bff;          /* Accent Color (Changed to a blue for better contrast on white) */
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            background: var(--light-white); /* White Background */
            color: var(--dark-navy);
            line-height: 1.6;
            min-height: 100vh;
            display: block; 
            overflow-x: hidden;
            padding: 0 5%;
        }

        /* --- New Layout Structure (Desktop: Two Columns) --- */
        .page-container {
            display: flex;
            gap: 2rem;
            max-width: 1600px;
            margin: 0 auto;
        }

        .left-sidebar {
            /* Fixed sidebar for desktop */
            position: sticky; 
            top: 0;
            width: 40%;
            max-width: 400px;
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: space-between; 
            padding-top: 5rem;
            padding-bottom: 3rem;
        }

        .main-content {
            /* Scrollable content on the right */
            width: 60%;
            padding: 5rem 0 3rem 0;
        }

        /* --- Left Sidebar Content Styling --- */
        .sidebar-header {
            padding: 0;
        }

        .sidebar-header h1 {
            font-size: 4rem;
            font-weight: 700;
            color: var(--dark-navy); /* Dark text on white */
            margin-bottom: 0.5rem;
        }

        .sidebar-header h2 {
            font-size: 1.5rem;
            font-weight: 500;
            color: var(--dark-navy);
            margin-bottom: 1rem;
        }

        .sidebar-header p {
            font-size: 1rem;
            color: var(--slate);
            max-width: 400px;
            margin-bottom: 4rem;
        }
        
        /* Navigation Links in Sidebar */
        .nav-links {
            list-style: none;
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
            margin-bottom: auto;
        }

        .nav-links li {
            width: fit-content;
        }

        .nav-links a {
            color: var(--slate);
            text-decoration: none;
            font-size: 0.95rem;
            font-weight: 600;
            letter-spacing: 0.1em;
            text-transform: uppercase;
            transition: color 0.3s;
            display: inline-block;
            position: relative;
            padding-left: 25px;
        }

        .nav-links a::before {
            content: '';
            position: absolute;
            left: 0;
            top: 50%;
            transform: translateY(-50%);
            width: 15px;
            height: 1px;
            background-color: var(--slate);
            transition: all 0.3s;
        }

        .nav-links a:hover,
        .nav-links a.active {
            color: var(--dark-navy); /* Text color changes to dark on hover/active */
        }

        .nav-links a:hover::before,
        .nav-links a.active::before {
            width: 25px;
            background-color: var(--green); /* Line indicator uses accent color */
        }
        
        /* Social Links in Sidebar Footer */
        .sidebar-footer {
            padding-top: 5rem;
        }

        .social-links {
            display: flex;
            gap: 1.25rem;
            padding-top: 1rem;
        }

        .social-links a {
            font-size: 1.25rem;
            color: var(--slate);
            transition: color 0.3s, transform 0.3s;
        }

        .social-links a:hover {
            color: var(--green);
            transform: translateY(-3px);
        }
        
        /* --- Main Content Section Styling --- */
        section {
            padding: 2rem 0;
            margin-bottom: 4rem;
        }
        
        /* Section Header Title Style (H2) */
        .section-header {
            color: var(--dark-navy);
            margin-bottom: 2rem;
            font-size: 1.7rem;
            font-weight: 700;
            letter-spacing: -0.01em;
        }
        
        .section-header .number {
            color: var(--green);
            font-size: 1rem;
            font-weight: 400;
            margin-right: 0.5rem;
        }

        /* About Section */
        #about p {
            color: var(--slate);
            margin-bottom: 1.25rem;
        }

        #about a {
            color: var(--green);
            text-decoration: none;
        }
        
        /* Skills Section - Flat list style */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
            gap: 0.5rem 0;
        }
        
        .skill-card {
            background: none; 
            padding: 0;
            border: none;
            text-align: left;
        }
        
        .skill-card h3 {
            color: var(--slate);
            font-size: 0.9rem;
            font-weight: 400;
            padding-left: 15px;
            position: relative;
        }

        .skill-card h3::before {
            content: '▹';
            position: absolute;
            left: 0;
            color: var(--green);
        }
        
        /* Education Section - Minimal card style */
        .education-card {
            background: none;
            padding: 0;
            border: none;
            box-shadow: none;
            transition: none;
            margin-bottom: 2rem;
            cursor: default;
        }
        
        .education-card h3 {
            color: var(--dark-navy);
            font-size: 1.1rem;
            margin-bottom: 0.25rem;
        }
        
        .education-card h4 {
            color: var(--green);
            font-size: 0.85rem;
            font-weight: 400;
            margin-bottom: 0.75rem;
        }
        
        .education-card p {
            color: var(--slate);
            font-size: 0.9rem;
        }

        /* Projects Section - Text-only hoverable cards */
        .project-card {
            background: none; 
            border: none;
            box-shadow: none;
            border-radius: 4px;
            padding: 2rem 1.75rem;
            transition: background 0.3s;
            overflow: hidden;
            margin-bottom: 1.5rem;
        }

        .project-card:hover {
            background: var(--light-gray); /* Subtle light gray highlight on hover */
            transform: translateY(0);
            box-shadow: none;
        }
        
        .project-info {
            width: 100%;
            padding: 0;
        }
        
        .project-info h3 {
            color: var(--dark-navy);
            font-size: 1.3rem;
            margin-bottom: 0.5rem;
        }

        .project-info p {
            color: var(--slate);
            font-size: 1rem;
            margin-bottom: 0.75rem;
        }

        /* Contact Section */
        #contact {
            padding: 2rem 0;
            text-align: center;
        }
        
        .contact-form {
            max-width: 500px;
            margin: 2rem auto;
            text-align: left;
        }
        
        .form-group input,
        .form-group textarea {
            background: var(--light-gray); /* Light gray background for input fields */
            border: 1px solid #ccc;
            color: var(--dark-navy);
            padding: 0.75rem;
            border-radius: 4px;
        }

        .submit-btn {
            padding: 0.75rem 1.5rem;
            background: var(--green);
            color: var(--light-white); /* White text on blue button */
            border-radius: 4px;
        }

        .submit-btn:hover {
            background: #0056b3;
        }

        /* Footer */
        .page-footer {
            background: none;
            padding: 3rem 0;
        }
        
        .footer-bottom {
            font-size: 0.8rem;
            text-align: center;
            color: var(--slate);
        }
        
        /* --- Responsive Design for Mobile/Small Screens --- */
        @media (max-width: 1080px) {
            .page-container {
                flex-direction: column;
                gap: 0;
            }

            .left-sidebar {
                position: relative;
                width: 100%;
                max-width: 100%;
                height: auto;
                padding-top: 3rem;
                padding-bottom: 1rem;
            }

            .main-content {
                width: 100%;
                padding: 1rem 0 3rem 0;
            }
            
            .sidebar-footer {
                display: none;
            }

            .nav-links {
                display: none;
            }
        }
        
        /* Add basic scroll-reveal */
        .reveal-element {
            opacity: 0;
            transform: translateY(10px);
            transition: opacity 0.6s ease-out, transform 0.6s ease-out;
        }
        
        .is-visible {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>
    <div class="page-container">
        <div class="left-sidebar">
            <header class="sidebar-header">
                <h1>Sumit Hajare</h1>
                <h2>Embedded Systems & IoT Developer</h2>
                <p>I'm an IoT and Embedded Systems enthusiast with hands-on experience in developing automation solutions using ESP32, Arduino, and Raspberry Pi.</p>
                
                <nav>
                    <ul class="nav-links">
                        <li><a href="#about" class="active">ABOUT</a></li>
                        <li><a href="#skills">SKILLS</a></li>
                        <li><a href="#education">EDUCATION</a></li>
                        <li><a href="#work">PROJECTS</a></li>
                        <li><a href="#contact">CONTACT</a></li>
                    </ul>
                </nav>
            </header>

            <footer class="sidebar-footer">
                 <div class="social-links">
                    <a href="https://linkedin.com/in/sumithajare3b562132b" target="_blank" aria-label="LinkedIn"><i class="fab fa-linkedin"></i></a>
                    <a href="https://github.com/sumithajare11" target="_blank" aria-label="GitHub"><i class="fab fa-github"></i></a>
                    <a href="mailto:sumithajare2003@gmail.com" aria-label="Email"><i class="fas fa-envelope"></i></a>
                    <a href="tel:+917057353171" aria-label="Phone"><i class="fas fa-phone"></i></a>
                </div>
            </footer>
        </div>
        
        <main class="main-content">
            <section id="about" class="reveal-element">
                <h2 class="section-header"><span class="number">01.</span> About Me</h2>
                <div class="about-content">
                    <p>Hello! I'm Sumit, and I'm deeply passionate about **Embedded Systems & IoT Development**. My journey began with a strong foundation in Electronics & Telecommunication Engineering from Shivaji University.</p>
                    
                    <p>I specialize in engineering real-time automation and monitoring solutions using ESP32, Arduino, and Raspberry Pi. My focus is on robust sensor interfacing, implementing efficient communication protocols like I2C, SPI, and UART, and designing systems that connect physical devices to the digital world.</p>
                    
                    <p>Over the years, I've delivered projects ranging from advanced railway safety systems to smart home automation, achieving tangible results like a 95% anomaly detection accuracy and reducing energy consumption by 30% through intelligent scheduling. I'm proficient in C, Python, and Embedded C, and I leverage cloud platforms like MQTT, ThingSpeak, and Blynk for seamless data logging and control.</p>
                    
                    <p>I am currently seeking opportunities where I can apply my expertise in microcontrollers (AVR, ARM) and my enthusiasm for new technologies to build impactful, scalable IoT solutions. Let's build something smart together!</p>
                    
                    <p>Contact me: <a href="mailto:sumithajare2003@gmail.com">sumithajare2003@gmail.com</a></p>
                    <a href="#" class="cta-btn" style="display: none;">View Full Resume</a>
                </div>
            </section>

            <section id="skills" class="reveal-element">
                <h2 class="section-header"><span class="number">02.</span> Skills & Technologies</h2>
                <div class="skills-grid">
                    <div class="skill-card"><h3>C</h3></div>
                    <div class="skill-card"><h3>Embedded C</h3></div>
                    <div class="skill-card"><h3>Python</h3></div>
                    <div class="skill-card"><h3>MATLAB</h3></div>
                    
                    <div class="skill-card"><h3>Arduino</h3></div>
                    <div class="skill-card"><h3>ESP32</h3></div>
                    <div class="skill-card"><h3>Raspberry Pi</h3></div>
                    <div class="skill-card"><h3>AVR / ARM Architectures</h3></div>

                    <div class="skill-card"><h3>MQTT</h3></div>
                    <div class="skill-card"><h3>ThingSpeak</h3></div>
                    <div class="skill-card"><h3>Blynk</h3></div>
                    <div class="skill-card"><h3>I2C, SPI, UART, PWM</h3></div>
                    
                    <div class="skill-card"><h3>Git</h3></div>
                    <div class="skill-card"><h3>GitHub</h3></div>
                </div>
            </section>

            <section id="education" class="reveal-element">
                <h2 class="section-header"><span class="number">03.</span> Education</h2>
                <div class="education-grid">
                    <div class="education-card">
                        <header>
                            <h3>B.Tech in Electronics & Telecommunication Engineering</h3>
                            <h4>Shivaji University, Kolhapur | Aug 2021 – May 2025 (Expected)</h4>
                        </header>
                        <ul>
                            <li><p>Relevant Coursework: Microcontrollers, Digital Signal Processing, IoT Systems, Communication Networks.</p></li>
                            <li><p>Academic Achievement: CGPA: 7.0</p></li>
                        </ul>
                    </div>
                    <div class="education-card">
                         <header>
                            <h3>Higher Secondary Certificate (HSC) in Science</h3>
                            <h4>Maharashtra State Board | Jul 2019 – Feb 2021</h4>
                        </header>
                         <ul>
                            <li><p>Focus on Physics, Chemistry, and Mathematics.</p></li>
                            <li><p>Academic Achievement: Percentage: 84%</p></li>
                        </ul>
                    </div>
                </div>
            </section>

            <section id="work" class="reveal-element">
                <h2 class="section-header"><span class="number">04.</span> Featured Projects</h2>
                <div class="projects-grid">
                    <a href="#" target="_blank" class="project-card">
                        <div class="project-info">
                            <h3>Railway Accident Prevention System</h3>
                            <p>Engineered a real-time railway safety system using multiple sensors and microcontrollers. Integrated GPS and GSM modules for instant location tracking and automated alert generation, achieving **95% accuracy** in anomaly detection. <span style="color: var(--green); font-size: 0.9rem;">(Microcontrollers, GPS/GSM, Embedded C)</span></p>
                        </div>
                    </a>
                    
                    <a href="#" target="_blank" class="project-card">
                        <div class="project-info">
                            <h3>Automated Home Monitoring System</h3>
                            <p>Developed a smart home automation system with temperature, humidity, and motion sensors for remote monitoring via the cloud. Created a mobile application interface for real-time control, resulting in a **30% reduction** in energy consumption. <span style="color: var(--green); font-size: 0.9rem;">(ESP32, MQTT, Blynk, Sensor Interfacing)</span></p>
                        </div>
                    </a>
                    
                    <a href="#" target="_blank" class="project-card">
                        <div class="project-info">
                            <h3>Industrial IoT Cloud Monitoring</h3>
                            <p>Implemented a cloud-based data logging and visualization dashboard for predictive maintenance analytics. Leveraged the **MQTT protocol** for efficient data transmission and **ThingSpeak** for real-time data visualization. <span style="color: var(--green); font-size: 0.9rem;">(Python, MQTT, ThingSpeak, Data Analytics)</span></p>
                        </div>
                    </a>
                </div>
            </section>

            <section id="contact" class="reveal-element">
                <h2 class="section-header"><span class="number">05.</span> Get In Touch</h2>
                <div class="contact-form">
                    <p style="text-align: center; max-width: 450px; margin: 0 auto 2rem;">I'm currently looking for new opportunities in the IoT and Embedded Systems space. Whether you have a project idea, a job offer, or just want to connect, feel free to reach out! My inbox is always open.</p>

                    <form>
                        <div class="form-group">
                            <input type="text" placeholder="Name" required>
                        </div>
                        <div class="form-group">
                            <input type="email" placeholder="Email" required>
                        </div>
                        <div class="form-group">
                            <input type="tel" placeholder="Phone (Optional)">
                        </div>
                        <div class="form-group">
                            <textarea placeholder="Message" required></textarea>
                        </div>
                        <button type="submit" class="submit-btn">Say Hello!</button>
                    </form>
                </div>
            </section>

            <footer class="page-footer">
                 <div class="footer-bottom">
                    <p>Designed with ❤️ by <a href="https://linkedin.com/in/sumithajare3b562132b">Sumit Hajare</a></p>
                    <p style="font-size: 0.75rem; margin-top: 0.5rem;">Inspired by the popular B4B/Brittany Chiang portfolio design.</p>
                </div>
            </footer>
        </main>
    </div>

    <script>
        // --- Navigation Activation & Scroll Logic ---
        const navLinks = document.querySelectorAll('.nav-links a');
        const sections = document.querySelectorAll('.main-content section');

        // Function to update the active link
        function updateActiveLink(entries) {
            entries.forEach(entry => {
                const id = entry.target.id;
                const activeLink = document.querySelector(`.nav-links a[href="#${id}"]`);

                if (entry.isIntersecting && activeLink) {
                    navLinks.forEach(link => link.classList.remove('active'));
                    activeLink.classList.add('active');
                }
            });
        }
        
        // Initialize IntersectionObserver for active link highlighting
        const navObserverOptions = {
            root: null,
            threshold: 0.2,
            rootMargin: '0px 0px -50% 0px'
        };
        
        const navObserver = new IntersectionObserver(updateActiveLink, navObserverOptions);
        sections.forEach(section => {
            navObserver.observe(section);
        });

        // --- Scroll Reveal Animation ---
        const revealObserverOptions = {
            root: null,
            threshold: 0.1,
        };

        const revealObserver = new IntersectionObserver((entries, observer) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('is-visible');
                    observer.unobserve(entry.target);
                }
            });
        }, revealObserverOptions);

        document.querySelectorAll('.reveal-element').forEach(el => {
            revealObserver.observe(el);
        });

        // --- Form submission (Retained) ---
        document.querySelector('form').addEventListener('submit', function(e) {
            e.preventDefault();
            alert('Thank you for your message! I will get back to you soon.');
            this.reset();
        });
    </script>
</body>
</html>
