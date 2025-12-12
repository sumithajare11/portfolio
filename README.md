<!DOCTYPE html
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfolio | Sumit Hajare</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            background: #ffffff;
            color: #0d0b0b;
            overflow-x: hidden;
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(255, 255, 255, 0.95);
            padding: 1rem 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 1000;
            backdrop-filter: blur(10px);
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 700;
            color: #0d0b0b;
            text-decoration: none;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            color: #0d0b0b;
            text-decoration: none;
            font-size: 0.95rem;
            transition: color 0.3s;
        }

        .nav-links a:hover {
            color: #545d8f;
        }

        /* Hero Section */
        #home {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 0 10%;
            gap: 4rem;
        }

        .hero-content h1 {
            font-size: 1.2rem;
            color: #545d8f;
            margin-bottom: 1rem;
        }

        .hero-content h2 {
            font-size: 4rem;
            color: #545d8f;
            margin-bottom: 1rem;
        }

        .hero-content .typing {
            font-size: 1.5rem;
            color: #ba7641;
            margin-bottom: 2rem;
        }

        .cta-btn {
            display: inline-block;
            padding: 1rem 2rem;
            background: transparent;
            border: 2px solid #545d8f;
            color: #545d8f;
            text-decoration: none;
            border-radius: 5px;
            transition: all 0.3s;
        }

        .cta-btn:hover {
            background: rgba(100, 255, 218, 0.1);
        }

        .hero-img {
            width: 500px;
            height: 500px;
            border-radius: 50%;
            overflow: hidden;
            border: 5px solid #0d0b0b;
        }

        .hero-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        /* About Section */
        #about {
            min-height: 100vh;
            padding: 5rem 10%;
            display: flex;
            align-items: center;
            gap: 4rem;
        }

        .about-img {
            width: 400px;
            height: 400px;
            border-radius: 10px;
            overflow: hidden;
            border: 3px solid #64ffda;
        }

        .about-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .about-content h2 {
            font-size: 2.5rem;
            color: #0d0b0b;
            margin-bottom: 1rem;
        }

        .about-content h3 {
            font-size: 1.8rem;
            color: #545d8f;
            margin-bottom: 1rem;
        }

        .about-content h4 {
            font-size: 1.3rem;
            color: #0d0b0b;
            margin-bottom: 1rem;
        }

        .about-content p {
            line-height: 1.8;
            margin-bottom: 1rem;
            color: #555555;
        }

        .about-content .email {
            color: #545d8f;
            margin: 1rem 0;
        }

        /* Skills Section */
        #skills {
            min-height: 100vh;
            padding: 5rem 10%;
            background: #f8f9fa;
        }

        #skills h2 {
            font-size: 2.5rem;
            color: #0d0b0b;
            text-align: center;
            margin-bottom: 3rem;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .skill-card {
            background: #ffffff;
            padding: 2rem;
            border-radius: 10px;
            text-align: center;
            transition: transform 0.3s, box-shadow 0.3s;
            border: 1px solid #e0e0e0;
        }

        .skill-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 30px rgba(100, 255, 218, 0.3);
        }

        .skill-icon {
            font-size: 3rem;
            color: #545d8f;
            margin-bottom: 1rem;
        }

        .skill-card h3 {
            color: #0d0b0b;
            font-size: 1rem;
        }

        /* Education Section */
        #education {
            min-height: 100vh;
            padding: 5rem 10%;
            background: #ffffff;
        }

        #education h2 {
            font-size: 2.5rem;
            color: #0d0b0b;
            text-align: center;
            margin-bottom: 1rem;
        }

        #education .subtitle {
            text-align: center;
            color: #545d8f;
            margin-bottom: 3rem;
        }

        .education-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
            gap: 3rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .education-card {
            background: #ffffff;
            padding: 2rem;
            border-radius: 10px;
            border: 1px solid #e0e0e0;
            transition: transform 0.3s;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
        }

        .education-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 30px rgba(100, 255, 218, 0.3);
        }

        .education-card img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            border-radius: 10px;
            margin-bottom: 1rem;
        }

        .education-card h3 {
            color: ##0d0b0b;
            font-size: 1.3rem;
            margin-bottom: 0.5rem;
        }

        .education-card h4 {
            color: #545d8f;
            font-size: 1rem;
            margin-bottom: 1rem;
        }

        .education-card p {
            color: #555555;
        }

        /* Projects Section */
        #work {
            min-height: 100vh;
            padding: 5rem 10%;
            background: #f8f9fa;
        }

        #work h2 {
            font-size: 2.5rem;
            color: #0d0b0b;
            text-align: center;
            margin-bottom: 3rem;
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
            max-width: 1400px;
            margin: 0 auto;
        }

        .project-card {
            background: #ffffff;
            border-radius: 10px;
            overflow: hidden;
            border: 1px solid #e0e0e0;
            transition: transform 0.3s;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 30px rgba(100, 255, 218, 0.3);
        }

        .project-card img {
            width: 100%;
            height: 250px;
            object-fit: cover;
        }

        .project-info {
            padding: 2rem;
        }

        .project-info h3 {
            color: #0d0b0b;
            font-size: 1.5rem;
            margin-bottom: 1rem;
        }

        .project-info p {
            line-height: 1.6;
            margin-bottom: 1.5rem;
            color: #555555;
        }

        .project-links {
            display: flex;
            gap: 1rem;
        }

        .project-links a {
            padding: 0.5rem 1.5rem;
            background: transparent;
            border: 2px solid #545d8f;
            color: #64ffda;
            text-decoration: none;
            border-radius: 5px;
            transition: all 0.3s;
        }

        .project-links a:hover {
            background: rgba(100, 255, 218, 0.1);
        }

        /* Contact Section */
        #contact {
            min-height: 100vh;
            padding: 5rem 10%;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 4rem;
            background: #ffffff;
        }

        .contact-img {
            width: 500px;
        }

        .contact-img img {
            width: 100%;
            height: auto;
        }

        .contact-form {
            flex: 1;
            max-width: 600px;
        }

        .contact-form h2 {
            font-size: 2.5rem;
            color: #0d0b0b;
            margin-bottom: 2rem;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 1rem;
            background: #f8f9fa;
            border: 1px solid #e0e0e0;
            color: #0d0b0b;
            border-radius: 5px;
            font-family: inherit;
        }

        .form-group textarea {
            resize: vertical;
            min-height: 150px;
        }

        .submit-btn {
            padding: 1rem 2rem;
            background: #545d8f;
            color: #ffffff;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s;
        }

        .submit-btn:hover {
            background: #52d4b8;
        }

        /* Footer */
        footer {
            background: #f8f9fa;
            padding: 3rem 10%;
            border-top: 1px solid #e0e0e0;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 3rem;
            margin-bottom: 2rem;
        }

        .footer-section h3 {
            color: #0d0b0b;
            margin-bottom: 1rem;
        }

        .footer-section p {
            line-height: 1.8;
            color: #555555;
        }

        .footer-section a {
            color: #555555;
            text-decoration: none;
            display: block;
            margin-bottom: 0.5rem;
            transition: color 0.3s;
        }

        .footer-section a:hover {
            color: #545d8f;
        }

        .social-links {
            display: flex;
            gap: 1rem;
            margin-top: 1rem;
        }

        .social-links a {
            width: 40px;
            height: 40px;
            background: #ffffff;
            border: 1px solid #e0e0e0;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #545d8f;
            transition: all 0.3s;
        }

        .social-links a:hover {
            background: #545d8f;
            color: #ffffff;
        }

        .footer-bottom {
            text-align: center;
            padding-top: 2rem;
            border-top: 1px solid #e0e0e0;
            color: #555555;
        }

        .footer-bottom a {
            color: #545d8f;
            text-decoration: none;
        }

        /* Responsive */
        @media (max-width: 768px) {
            #home {
                flex-direction: column-reverse;
                padding-top: 8rem;
            }

            .hero-content h2 {
                font-size: 2.5rem;
            }

            .hero-img {
                width: 300px;
                height: 300px;
            }

            #about {
                flex-direction: column;
            }

            .about-img {
                width: 100%;
                max-width: 400px;
            }

            #contact {
                flex-direction: column;
            }

            .contact-img {
                width: 100%;
                max-width: 400px;
            }

            .nav-links {
                display: none;
            }

            .projects-grid,
            .education-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav>
        <a href="#Home" class="logo">Sumit Hajare</a>
        <ul class="nav-links">
            <li><a href="#Home">Home</a></li>
            <li><a href="#About">About</a></li>
            <li><a href="#Skills">Skills</a></li>
            <li><a href="#Education">Education</a></li>
            <li><a href="#Work">Projects</a></li>
            <li><a href="#Contact">Contact</a></li>
        </ul>
    </nav>

    <!-- Hero Section -->
    <section id="home">
     <h1>Hi There, I'm Sumit Hajare</h1>
        <div class="hero-content">
            <h2>Sumit Hajare</h2>
            <p class="typing">I Am Into <span id="typed"></span></p>
            <a href="#about" class="cta-btn">About Me</a>
        </div>
        <div class="hero-img">
            <img src="https://media.licdn.com/dms/image/v2/D4D22AQFjupgqPXdqQg/feedshare-shrink_2048_1536/feedshare-shrink_2048_1536/0/1692686262219?e=2147483647&v=beta&t=Eep7g_xoZT49NtdpI6eatJeBVadETR2Zd0zkBn6GWpM" alt="Sumit Hajare">
        </div>
    </section>

    <!-- About Section -->
    <section id="about">
        <div class="about-img">
            <img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?w=400&h=400&fit=crop" alt="Sumit Hajare">
        </div>
        <div class="about-content">
            <h2>About Me</h2>
            <h3>I'm Sumit</h3>
            <h4>Embedded Systems & IoT Developer</h4>
            <p>I'm an IoT and Embedded Systems enthusiast with hands-on experience in developing automation solutions using ESP32, Arduino, and Raspberry Pi. I specialize in real-time monitoring systems, sensor interfacing, and cloud-based data logging.</p>
            <p>With a strong foundation in Electronics & Telecommunication Engineering, I've worked on projects ranging from railway safety systems to smart home automation. I'm proficient in C, Python, and Embedded C, with expertise in MQTT, ThingSpeak, and various IoT platforms.</p>
            <p>I'm constantly exploring new technologies in embedded systems, working with microcontroller architectures (AVR, ARM), and implementing efficient communication protocols (I2C, SPI, UART, PWM).</p>
            <p class="email">email : sumithajare2003@gmail.com</p>
            <a href="#" class="cta-btn">Resume</a>
        </div>
    </section>

    <!-- Skills Section -->
    <section id="skills">
        <h2>Skills & Abilities</h2>
        <div class="skills-grid">
            <div class="skill-card">
                <div class="skill-icon">
                    <i class="fas fa-code"></i>
                </div>
                <h3>C</h3>
            </div>
            <div class="skill-card">
                <div class="skill-icon">
                    <i class="fab fa-python"></i>
                </div>
                <h3>Python</h3>
            </div>
            <div class="skill-card">
                <div class="skill-icon">
                    <i class="fas fa-microchip"></i>
                </div>
                <h3>Embedded C</h3>
            </div>
            <div class="skill-card">
                <div class="skill-icon">
                    <i class="fas fa-microchip"></i>
                </div>
                <h3>Arduino</h3>
            </div>
            <div class="skill-card">
                <div class="skill-icon">
                    <i class="fas fa-wifi"></i>
                </div>
                <h3>ESP32</h3>
            </div>
            <div class="skill-card">
                <div class="skill-icon">
                    <i class="fab fa-raspberry-pi"></i>
                </div>
                <h3>Raspberry Pi</h3>
            </div>
            <div class="skill-card">
                <div class="skill-icon">
                    <i class="fas fa-cloud"></i>
                </div>
                <h3>MQTT</h3>
            </div>
            <div class="skill-card">
                <div class="skill-icon">
                    <i class="fas fa-database"></i>
                </div>
                <h3>ThingSpeak</h3>
            </div>
            <div class="skill-card">
                <div class="skill-icon">
                    <i class="fas fa-mobile-alt"></i>
                </div>
                <h3>Blynk</h3>
            </div>
            <div class="skill-card">
                <div class="skill-icon">
                    <i class="fab fa-git-alt"></i>
                </div>
                <h3>Git</h3>
            </div>
            <div class="skill-card">
                <div class="skill-icon">
                    <i class="fas fa-chart-line"></i>
                </div>
                <h3>MATLAB</h3>
            </div>
            <div class="skill-card">
                <div class="skill-icon">
                    <i class="fab fa-github"></i>
                </div>
                <h3>Github</h3>
            </div>
        </div>
    </section>

    <!-- Education Section -->
    <section id="education">
        <h2>My Education</h2>
        <p class="subtitle">Education is not the learning of facts, but the training of the mind to think.</p>
        <div class="education-grid">
            <div class="education-card">
                <img src="https://media.getmyuni.com/azure/college-images-test/shivaji-university-suk-kolhapur/3876586d0ba040b5a33bb7b65d86b9c4.jpeg" alt="Shivaji University">
                <h3>Shivaji University, Kolhapur</h3>
                <h4>Aug 2021 – May 2025 | B.Tech in Electronics & Telecommunication Engineering</h4>
                <p>CGPA: 7.0</p>
            </div>
            <div class="education-card">                <img src="https://hscinspire.mahahsscboard.in/mahalogo.png" alt="School">
                <h3>Maharashtra State Board</h3>
                <h4>Jul 2019 – Feb 2021 | Completed Higher Secondary Certificate (HSC) in Science</h4>
                <p>Percentage: 84%</p>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="work">
        <h2>Projects Made</h2>
        <div class="projects-grid">
            <div class="project-card">
                <img src="https://images.unsplash.com/photo-1474487548417-781cb71495f3?w=600&h=400&fit=crop" alt="Railway Accident Prevention System">
                <div class="project-info">
                    <h3>Railway Accident Prevention System</h3>
                    <p>Engineered real-time railway safety system using multiple sensors and microcontrollers to detect track anomalies. Integrated GPS and GSM modules for instant location tracking and automated alert generation. Achieved 95% accuracy in anomaly detection.</p>
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
                    <p>Developed smart home automation system with temperature, humidity, and motion sensors for remote monitoring. Created mobile application interface for real-time control. Reduced energy consumption by 30% through intelligent scheduling.</p>
                    <div class="project-links">
                        <a href="#">Code</a>
                    </div>
                </div>
            </div>
            <div class="project-card">
                <img src="https://images.unsplash.com/photo-1558346490-a72e53ae2d4f?w=600&h=400&fit=crop" alt="IoT Cloud Monitoring">
                <div class="project-info">
                    <h3>IoT Cloud Monitoring Dashboard</h3>
                    <p>Implemented cloud-based data logging and visualization dashboard for predictive maintenance analytics. Integrated MQTT protocol for efficient data transmission and ThingSpeak for real-time monitoring.</p>
                    <div class="project-links">
                        <a href="#">Code</a>
                        <a href="#">Visit</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact">
        <div class="contact-img">
            
        </div>
        <div class="contact-form">
            <h2>Get in Touch</h2>
            <form>
                <div class="form-group">
                    <input type="text" placeholder="Name" required>
                </div>
                <div class="form-group">
                    <input type="email" placeholder="Email" required>
                </div>
                <div class="form-group">
                    <input type="tel" placeholder="Phone">
                </div>
                <div class="form-group">
                    <textarea placeholder="Message" required></textarea>
                </div>
                <button type="submit" class="submit-btn">Submit</button>
            </form>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <div class="footer-section">
                <h3>Sumit's Portfolio</h3>
                <p>Thank you for visiting my personal portfolio website. Connect with me over socials.</p>
                <p>Keep Rising 🚀. Connect with me over live chat!</p>
                <div class="social-links">
                    <a href="https://linkedin.com/in/sumithajare3b562132b" target="_blank"><i class="fab fa-linkedin"></i></a>
                    <a href="https://github.com/sumithajare11" target="_blank"><i class="fab fa-github"></i></a>
                    <a href="mailto:sumithajare2003@gmail.com"><i class="fas fa-envelope"></i></a>
                    <a href="tel:+917057353171"><i class="fas fa-phone"></i></a>
                </div>
            </div>
            <div class="footer-section">
                <h3>Quick Links</h3>
                <a href="#Home">Home</a>
                <a href="#About">About</a>
                <a href="#Skills">Skills</a>
                <a href="#Education">Education</a>
                <a href="#Work">Work</a>
            </div>
            <div class="footer-section">
                <h3>Contact Info</h3>
                <p><i class="fas fa-phone"></i> +91-7057353171</p>
                <p><i class="fas fa-envelope"></i> sumithajare2003@gmail.com</p>
                <p><i class="fas fa-map-marker-alt"></i> Kolhapur, Maharashtra, India</p>
            </div>
        </div>
        <div class="footer-bottom">
            <p>Designed with ❤️ by <a href="https://linkedin.com/in/sumithajare3b562132b">Sumit Hajare</a></p>
        </div>
    </footer>

    <script>
        // Typing Animation
        const words = ['IoT', 'Embedded Systems', 'Automation', 'Real-Time Monitoring'];
        let wordIndex = 0;
        let charIndex = 0;
        let isDeleting = false;
        const typingSpeed = 150;
        const deletingSpeed = 100;
        const delayBetweenWords = 2000;

        function type() {
            const currentWord = words[wordIndex];
            const typedElement = document.getElementById('typed');

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

        // Start typing animation
        type();

        // Smooth scroll with offset for fixed nav
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    window.scrollTo({
                        top: target.offsetTop - 80,
                        behavior: 'smooth'
                    });
                }
            });
        });

        // Form submission
        document.querySelector('form').addEventListener('submit', function(e) {
            e.preventDefault();
            alert('Thank you for your message! I will get back to you soon.');
            this.reset();
        });

        // Scroll reveal animation
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -100px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        document.querySelectorAll('.skill-card, .education-card, .project-card').forEach(el => {
            el.style.opacity = '0';
            el.style.transform = 'translateY(30px)';
            el.style.transition = 'all 0.6s ease-out';
            observer.observe(el);
        });
    </script>
</body>
</html>
