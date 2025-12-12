#Portfolio

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfolio | Sumit Hajare</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@100..900&display=swap" rel="stylesheet">
    <style>
        /* --- General Reset & Variables --- */
        :root {
            --dark-navy: #0a192f; /* Main Background Color (Dark/Black) */
            --navy: #112240;      /* Secondary Background/Card Color */
            --light-navy: #233554;
            --lightest-slate: #ccd6f6; /* Main Body Text Color (Light) */
            --slate: #8892b0;        /* Secondary Text Color */
            --green: #64ffda;        /* Accent Color (Keep your bright teal) */
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            /* Use a modern font, like Inter */
            font-family: 'Inter', 'Poppins', sans-serif;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            background: var(--dark-navy);
            color: var(--slate);
            line-height: 1.5;
            min-height: 100vh;
            display: flex; /* Enable the two-column layout */
            overflow-x: hidden;
        }

        /* --- New Two-Column Layout Structure --- */
        .left-sidebar {
            /* Fixed sidebar on the left */
            position: fixed;
            top: 0;
            left: 0;
            width: 40%; /* Adjust as needed, e.g., 400px or 35% */
            max-width: 500px;
            min-width: 300px;
            height: 100vh;
            padding: 0 4rem;
            display: flex;
            flex-direction: column;
            justify-content: space-between; /* Space out header and footer/socials */
            z-index: 100;
        }

        .main-content {
            /* Scrollable content on the right */
            margin-left: 40%; /* Must match .left-sidebar width */
            padding: 5rem 10% 3rem 5%; /* Adjust padding for visual balance */
            width: 60%; /* Must match .left-sidebar width complement */
            min-height: 100vh;
            overflow-y: auto;
        }

        /* --- Left Sidebar Content Styling --- */
        .sidebar-header {
            padding-top: 5rem;
        }

        .sidebar-header h1 {
            font-size: 4rem;
            font-weight: 700;
            color: var(--lightest-slate);
            margin-bottom: 0.5rem;
        }

        .sidebar-header h2 {
            font-size: 1.5rem;
            font-weight: 500;
            color: var(--lightest-slate);
            margin-bottom: 1rem;
        }

        .sidebar-header p {
            font-size: 1rem;
            color: var(--slate);
            max-width: 300px;
            margin-bottom: 3rem;
        }

        /* Navigation Links in Sidebar */
        .nav-links {
            list-style: none;
            display: flex;
            flex-direction: column;
            gap: 1rem;
        }

        .nav-links a {
            color: var(--slate);
            text-decoration: none;
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            transition: color 0.3s;
            display: inline-block;
            position: relative;
            padding-left: 20px;
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
            color: var(--green);
        }

        .nav-links a:hover::before,
        .nav-links a.active::before {
            width: 25px;
            background-color: var(--green);
        }

        /* Social Links in Sidebar Footer */
        .sidebar-footer {
            padding-bottom: 3rem;
        }

        .social-links {
            display: flex;
            gap: 1rem;
        }

        .social-links a {
            font-size: 1.5rem;
            color: var(--slate);
            transition: color 0.3s, transform 0.3s;
        }

        .social-links a:hover {
            color: var(--green);
            transform: translateY(-3px);
        }
        
        /* The hero image is removed as per the reference website style */
        #home .hero-img {
            display: none;
        }

        /* --- Main Content Section Styling --- */
        section {
            padding: 3rem 0;
            min-height: auto; /* Remove fixed height for main content sections */
            margin-bottom: 5rem;
        }

        /* About Section */
        #about h2 {
            font-size: 2rem;
            color: var(--lightest-slate);
            margin-bottom: 2rem;
        }
        
        #about p {
            color: var(--slate);
            margin-bottom: 1.25rem;
        }

        .about-content h3, .about-content h4 {
            color: var(--lightest-slate);
        }
        
        .about-content .email {
            color: var(--green);
            display: block;
        }
        
        .cta-btn {
            background: var(--dark-navy); /* Match background */
            border: 1px solid var(--green); /* Thin border */
            color: var(--green);
            text-decoration: none;
            padding: 0.75rem 1.5rem;
            font-weight: 600;
        }
        
        .cta-btn:hover {
            background: rgba(100, 255, 218, 0.1);
        }

        /* About Image (often removed or highly styled in this theme) */
        #about .about-img {
            display: none;
        }

        /* General Heading Style (used for Skills, Education, Projects) */
        .section-header {
            color: var(--lightest-slate);
            margin-bottom: 1rem;
            font-size: 1.2rem;
            position: sticky;
            top: 0; /* Make section titles sticky */
            background: var(--dark-navy);
            padding: 1rem 0;
            z-index: 10;
        }
        
        .section-header span {
            color: var(--green);
            font-size: 1rem;
            font-weight: 400;
            margin-right: 0.5rem;
        }

        /* Skills Section */
        #skills h2 {
            display: none; /* Replaced by .section-header */
        }

        .skills-grid {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
        }
        
        .skill-card {
            background: var(--dark-navy); /* Match background, no distinct card */
            padding: 0.5rem 0.5rem 0.5rem 0; /* Light padding/flat appearance */
            border: none;
            text-align: left;
            transition: none;
            box-shadow: none;
            border-bottom: none;
            flex: 0 0 auto; /* Allow items to wrap */
        }
        
        .skill-icon {
            display: none; /* Hide icon for simpler list style */
        }
        
        .skill-card h3 {
            color: var(--slate);
            font-size: 0.9rem;
            font-weight: 400;
        }
        
        /* Education Section - Timeline-style, simple listing */
        #education h2, #education .subtitle {
            display: none; /* Replaced by .section-header */
        }
        
        .education-grid {
            grid-template-columns: 1fr; /* Single column */
            gap: 1rem;
        }
        
        .education-card {
            background: var(--navy); /* Use secondary background color for cards */
            padding: 1.5rem;
            border: none;
            box-shadow: 0 10px 30px -15px rgba(2, 12, 27, 0.7); /* Subtle dark shadow */
            transition: background 0.3s;
            border-radius: 4px;
        }

        .education-card:hover {
            background: var(--light-navy);
            transform: translateY(0); /* Remove unnecessary hover transform */
            box-shadow: 0 10px 30px -15px rgba(2, 12, 27, 0.7);
        }

        .education-card img {
            display: none; /* Remove images for a cleaner look */
        }
        
        .education-card h3 {
            color: var(--lightest-slate);
            font-size: 1.2rem;
            margin-bottom: 0.25rem;
        }
        
        .education-card h4 {
            color: var(--green);
            font-size: 0.9rem;
            margin-bottom: 0.75rem;
        }
        
        .education-card p {
            color: var(--slate);
            font-size: 0.9rem;
        }
        
        /* Projects Section - Card style adjusted for dark theme */
        #work h2 {
            display: none; /* Replaced by .section-header */
        }

        .projects-grid {
            grid-template-columns: 1fr; /* Single column layout for projects */
            gap: 2.5rem;
        }
        
        .project-card {
            background: var(--navy); /* Secondary background color */
            border: none;
            box-shadow: 0 10px 30px -15px rgba(2, 12, 27, 0.7);
            border-radius: 4px;
            display: flex; /* Adjust to place image/content horizontally */
            overflow: visible;
        }

        .project-card:nth-child(even) {
            flex-direction: row-reverse; /* Alternate image/text position */
        }

        .project-card:hover {
            transform: translateY(0);
            box-shadow: 0 10px 30px -15px rgba(2, 12, 27, 0.7);
        }

        .project-card img {
            width: 50%;
            height: auto;
            object-fit: cover;
            opacity: 0.8;
            mix-blend-mode: multiply; /* Optional: adds a nice dark/tinted effect */
            transition: opacity 0.3s;
            border-radius: 4px 0 0 4px;
        }

        .project-card:nth-child(even) img {
            border-radius: 0 4px 4px 0;
        }
        
        .project-card:hover img {
            opacity: 1;
        }

        .project-info {
            width: 50%;
            padding: 2rem;
        }
        
        .project-info h3 {
            color: var(--lightest-slate);
            font-size: 1.2rem;
            margin-bottom: 0.5rem;
        }

        .project-info p {
            color: var(--slate);
            font-size: 0.95rem;
            margin-bottom: 1rem;
        }

        .project-links a {
            padding: 0.5rem 1rem;
            border: 1px solid var(--green);
            color: var(--green);
            font-size: 0.9rem;
        }
        
        .project-links a:hover {
            background: rgba(100, 255, 218, 0.1);
        }
        
        /* Contact Section */
        #contact {
            padding: 3rem 0;
            flex-direction: column;
            text-align: center;
            justify-content: flex-start;
            min-height: auto;
        }
        
        .contact-img {
            display: none; /* Remove image */
        }
        
        .contact-form {
            max-width: 500px;
            margin-top: 2rem;
        }

        .contact-form h2 {
            font-size: 2.5rem;
            color: var(--lightest-slate);
            margin-bottom: 0.5rem;
        }
        
        .contact-form p {
             margin-bottom: 2rem;
        }

        .form-group input,
        .form-group textarea {
            background: var(--navy);
            border: 1px solid var(--light-navy);
            color: var(--lightest-slate);
            padding: 0.75rem;
        }

        .submit-btn {
            background: var(--green);
            color: var(--dark-navy);
        }

        .submit-btn:hover {
            background: #52d4b8;
        }

        /* Footer */
        footer {
            background: var(--dark-navy); /* Dark background */
            padding: 1rem 0;
            text-align: center;
            border-top: none;
        }

        .footer-content {
            display: none; /* Only keep the bottom copyright/designer line */
        }
        
        .footer-bottom {
            padding: 0;
            border-top: none;
            font-size: 0.8rem;
        }
        
        .footer-bottom a {
            color: var(--green);
        }
        
        /* --- Responsive Design for Mobile/Small Screens --- */
        @media (max-width: 1080px) {
            .left-sidebar {
                position: relative; /* Make sidebar scrollable */
                width: 100%;
                max-width: 100%;
                height: auto;
                padding: 3rem 5%;
                justify-content: flex-start;
            }

            .main-content {
                margin-left: 0;
                width: 100%;
                padding: 3rem 5%;
            }

            .sidebar-header h1 {
                font-size: 3rem;
            }
            
            .sidebar-header p {
                max-width: 100%;
            }

            .nav-links {
                flex-direction: row; /* Horizontal navigation links for mobile */
                gap: 1.5rem;
                overflow-x: auto;
                padding-bottom: 1rem;
                border-bottom: 1px solid var(--light-navy);
            }
            
            .nav-links a {
                padding-left: 0;
            }
            
            .nav-links a::before {
                display: none; /* Remove the link indicator line */
            }

            .sidebar-footer {
                padding-top: 2rem;
                padding-bottom: 0;
            }
            
            .project-card {
                flex-direction: column; /* Stack image and content vertically */
            }

            .project-card:nth-child(even) {
                flex-direction: column;
            }

            .project-card img,
            .project-info {
                width: 100%;
                border-radius: 4px;
            }
            
            .project-card:nth-child(even) img {
                border-radius: 4px 4px 0 0;
            }
        }
        
        /* Mobile: Further adjustments for very small screens */
        @media (max-width: 768px) {
            .sidebar-header h1 {
                font-size: 2.5rem;
            }
            
            .sidebar-header h2 {
                font-size: 1.2rem;
            }
            
            .skills-grid {
                column-count: 2; /* 2 columns for skills in very small screens */
                display: block;
            }
            
            .skill-card {
                width: 50%;
                display: inline-block;
            }
        }
        
        /* Ensure all sections fade in correctly on the right side */
        .main-content section > * {
            opacity: 0;
            transform: translateY(10px);
            transition: opacity 0.6s ease-out, transform 0.6s ease-out;
        }
        
        /* Add a class to visible elements */
        .main-content section > .is-visible {
            opacity: 1;
            transform: translateY(0);
        }
        
        /* Remove original scroll-reveal styles that target cards/elements directly */
        .skill-card, .education-card, .project-card {
            opacity: 1 !important;
            transform: translateY(0) !important;
            transition: none !important;
        }

    </style>
</head>
<body>
    <div class="left-sidebar">
        <header class="sidebar-header">
            <h1>Sumit Hajare</h1>
            <h2>Embedded Systems & IoT Developer</h2>
            <p>I'm an IoT and Embedded Systems enthusiast with hands-on experience in developing automation solutions using ESP32, Arduino, and Raspberry Pi.</p>
            
            <ul class="nav-links">
                <li><a href="#about" class="active">About</a></li>
                <li><a href="#skills">Skills</a></li>
                <li><a href="#education">Education</a></li>
                <li><a href="#work">Projects</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </header>

        <footer class="sidebar-footer">
             <div class="social-links">
                <a href="https://linkedin.com/in/sumithajare3b562132b" target="_blank" aria-label="LinkedIn"><i class="fab fa-linkedin"></i></a>
                <a href="https://github.com/sumithajare11" target="_blank" aria-label="GitHub"><i class="fab fa-github"></i></a>
                <a href="mailto:sumithajare2003@gmail.com" aria-label="Email"><i class="fas fa-envelope"></i></a>
                <a href="tel:+917057353171" aria-label="Phone"><i class="fas fa-phone"></i></a>
            </div>
             <div class="footer-bottom">
                <p>Designed with ❤️ by <a href="https://linkedin.com/in/sumithajare3b562132b">Sumit Hajare</a></p>
            </div>
        </footer>
    </div>
    
    <main class="main-content">
        <section id="home" style="padding: 0; margin-bottom: 2rem;"></section>

        <section id="about">
            <h2 class="section-header"><span class="number">01.</span> About Me</h2>
            <div class="about-content">
                <p>Hello! I'm Sumit, and I'm deeply passionate about **Embedded Systems & IoT Development**. My journey began with a strong foundation in Electronics & Telecommunication Engineering from Shivaji University.</p>
                
                <p>I specialize in engineering real-time automation and monitoring solutions using **ESP32, Arduino, and Raspberry Pi**. My focus is on robust sensor interfacing, implementing efficient communication protocols like I2C, SPI, and UART, and designing systems that connect physical devices to the digital world.</p>
                
                <p>Over the years, I've delivered projects ranging from advanced railway safety systems to smart home automation, achieving tangible results like a 95% anomaly detection accuracy and reducing energy consumption by 30% through intelligent scheduling. I'm proficient in **C, Python, and Embedded C**, and I leverage cloud platforms like **MQTT, ThingSpeak, and Blynk** for seamless data logging and control.</p>
                
                <p>I am currently seeking opportunities where I can apply my expertise in microcontrollers (AVR, ARM) and my enthusiasm for new technologies to build impactful, scalable IoT solutions. Let's build something smart together!</p>
                
                <p class="email">Email: <a href="mailto:sumithajare2003@gmail.com">sumithajare2003@gmail.com</a></p>
                <a href="#" class="cta-btn">View Full Resume</a>
            </div>
        </section>

        <section id="skills">
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

        <section id="education">
            <h2 class="section-header"><span class="number">03.</span> My Education</h2>
            <div class="education-grid">
                <div class="education-card">
                    <h3>B.Tech in Electronics & Telecommunication Engineering</h3>
                    <h4>Shivaji University, Kolhapur | Aug 2021 – May 2025 (Expected)</h4>
                    <p>Relevant Coursework: Microcontrollers, Digital Signal Processing, IoT Systems, Communication Networks.</p>
                    <p>CGPA: 7.0</p>
                </div>
                <div class="education-card">
                    <h3>Higher Secondary Certificate (HSC) in Science</h3>
                    <h4>Maharashtra State Board | Jul 2019 – Feb 2021</h4>
                    <p>Focus on Physics, Chemistry, and Mathematics.</p>
                    <p>Percentage: 84%</p>
                </div>
            </div>
        </section>

        <section id="work">
            <h2 class="section-header"><span class="number">04.</span> Featured Projects</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <img src="https://images.unsplash.com/photo-1474487548417-781cb71495f3?w=600&h=400&fit=crop" alt="Railway Accident Prevention System">
                    <div class="project-info">
                        <h3>Railway Accident Prevention System</h3>
                        <p>Engineered a real-time railway safety system using multiple sensors (vibration, obstacle) and microcontrollers to detect track anomalies. Integrated **GPS and GSM modules** for instant location tracking and automated alert generation, achieving **95% accuracy** in anomaly detection.</p>
                        <div class="project-links">
                            <a href="#">Code</a>
                            <a href="#">Visit</a>
                        </div>
                    </div>
                </div>
                
                <div class="project-card">
                    <img src="https://images.unsplash.com/photo-1558002038-1055907df827?w=600&h=400&fit=crop" alt="Automated Home Monitoring System">
                    <div class="project-info">
                        <h3>Automated Home Monitoring System</h3>
                        <p>Developed a smart home automation system with temperature, humidity, and motion sensors for remote monitoring via the cloud. Created a mobile application interface for real-time control, resulting in a **30% reduction** in energy consumption through intelligent scheduling.</p>
                        <div class="project-links">
                            <a href="#">Code</a>
                        </div>
                    </div>
                </div>
                
                <div class="project-card">
                    <img src="https://images.unsplash.com/photo-1558346490-a72e53ae2d4f?w=600&h=400&fit=crop" alt="IoT Cloud Monitoring">
                    <div class="project-info">
                        <h3>Industrial IoT Cloud Monitoring</h3>
                        <p>Implemented a cloud-based data logging and visualization dashboard for predictive maintenance analytics. Leveraged the **MQTT protocol** for efficient data transmission from industrial sensors and **ThingSpeak** for real-time data visualization and alerts.</p>
                        <div class="project-links">
                            <a href="#">Code</a>
                            <a href="#">Visit</a>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section id="contact">
            <h2 class="section-header"><span class="number">05.</span> Get In Touch</h2>
            <p>I'm currently looking for new opportunities in the IoT and Embedded Systems space. Whether you have a project idea, a job offer, or just want to connect, feel free to reach out! My inbox is always open.</p>

            <div class="contact-form">
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

        <footer>
             <div class="footer-bottom" style="text-align: left; margin-top: 5rem;">
                <p>Inspired by the popular B4B/Brittany Chiang portfolio design.</p>
            </div>
        </footer>
    </main>

    <script>
        // --- Typing Animation (Retained) ---
        const words = ['IoT', 'Embedded Systems', 'Automation', 'Real-Time Monitoring'];
        let wordIndex = 0;
        let charIndex = 0;
        let isDeleting = false;
        const typingSpeed = 150;
        const deletingSpeed = 100;
        const delayBetweenWords = 2000;

        function type() {
            const typedElement = document.getElementById('typed');
            if (!typedElement) return; // Prevent error if element is missing

            const currentWord = words[wordIndex];

            if (isDeleting) {
                typedElement.textContent = currentWord.substring(0, charIndex - 1);
                charIndex--;
            } else {
                typedElement.textContent = currentWord.substring(0, charIndex + 1);
                charIndex++;
            }

            if (!isDeleting && charIndex === currentWord.length) {
                setTimeout(() => {
                    isDeleting = true;
                }, delayBetweenWords);
            } else if (isDeleting && charIndex === 0) {
                isDeleting = false;
                wordIndex = (wordIndex + 1) % words.length;
            }

            const speed = isDeleting ? deletingSpeed : typingSpeed;
            setTimeout(type, speed);
        }
        
        // Start typing animation (Note: The "typing" element is now within the ABOUT section text block, not the hero)
        // type(); // Keeping this commented out as the Hero section where it was originally placed is now styled differently.

        // --- Smooth Scroll & Active Nav ---
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
            root: document.querySelector('.main-content'),
            threshold: 0.1, // Trigger when 10% of the section is visible
            rootMargin: '0px 0px -50% 0px'
        };
        
        const navObserver = new IntersectionObserver(updateActiveLink, navObserverOptions);
        sections.forEach(section => {
             // Only observe sections with actual content
            if (section.id !== 'home') {
                navObserver.observe(section);
            }
        });
        
        // Form submission (Retained)
        document.querySelector('form').addEventListener('submit', function(e) {
            e.preventDefault();
            alert('Thank you for your message! I will get back to you soon.');
            this.reset();
        });

        // --- Scroll Reveal Animation (Modified for the new layout) ---
        const revealObserverOptions = {
            root: document.querySelector('.main-content'), // Observe scrolling in the main content area
            threshold: 0.1,
            rootMargin: '0px 0px -100px 0px'
        };

        const revealObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    // Apply reveal effect to ALL immediate children of the section
                    Array.from(entry.target.children).forEach((el, index) => {
                        // Exclude the section header/title as it's sticky/already visible
                        if (!el.classList.contains('section-header')) {
                             setTimeout(() => {
                                el.classList.add('is-visible');
                            }, index * 100); // Stagger the reveal slightly
                        }
                    });
                    // Stop observing after it has been revealed
                    revealObserver.unobserve(entry.target); 
                }
            });
        }, revealObserverOptions);

        // Observe all main content sections for reveal
        document.querySelectorAll('.main-content section').forEach(el => {
            if (el.id !== 'home') {
                revealObserver.observe(el);
            }
        });

    </script>
</body>
</html>
