# Portfolio


<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfolio | Sumit Hajare</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&display=swap');

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            text-decoration: none;
            border: none;
            outline: none;
            scroll-behavior: smooth;
            font-family: 'Poppins', sans-serif;
        }

        :root {
            --bg-color: #081b29;
            --second-bg-color: #112e42;
            --text-color: #ededed;
            --main-color: #00abf0;
        }

        html {
            font-size: 62.5%;
            overflow-x: hidden;
        }

        body {
            background: var(--bg-color);
            color: var(--text-color);
        }

        .header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            padding: 2rem 9%;
            background: transparent;
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 100;
            transition: .3s;
        }

        .header.sticky {
            background: var(--bg-color);
        }

        .logo {
            font-size: 2.5rem;
            color: var(--text-color);
            font-weight: 600;
        }

        .navbar a {
            font-size: 1.7rem;
            color: var(--text-color);
            font-weight: 500;
            margin-left: 3.5rem;
            transition: .3s;
        }

        .navbar a:hover,
        .navbar a.active {
            color: var(--main-color);
        }

        #menu-icon {
            font-size: 3.6rem;
            color: var(--text-color);
            cursor: pointer;
            display: none;
        }

        section {
            min-height: 100vh;
            padding: 10rem 9% 2rem;
        }

        .home {
            display: flex;
            align-items: center;
            padding: 0 9%;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 800"><rect fill="%23081b29"/></svg>');
        }

        .home-content {
            max-width: 60rem;
        }

        .home-content h1 {
            font-size: 5.6rem;
            font-weight: 700;
            line-height: 1.3;
        }

        .home-content .text-animate {
            position: relative;
            width: 32.8rem;
        }

        .home-content .text-animate h3 {
            font-size: 3.2rem;
            font-weight: 700;
            color: transparent;
            -webkit-text-stroke: .7px var(--main-color);
        }

        .home-content p {
            font-size: 1.6rem;
            margin: 2rem 0 4rem;
        }

        .btn-box {
            position: relative;
            display: flex;
            justify-content: space-between;
            width: 34.5rem;
            height: 5rem;
        }

        .btn-box .btn {
            position: relative;
            display: inline-flex;
            justify-content: center;
            align-items: center;
            width: 15rem;
            height: 100%;
            background: var(--main-color);
            border: .2rem solid var(--main-color);
            border-radius: .8rem;
            font-size: 1.8rem;
            font-weight: 600;
            letter-spacing: .1rem;
            color: var(--bg-color);
            z-index: 1;
            overflow: hidden;
            transition: .5s;
        }

        .btn-box .btn:hover {
            color: var(--main-color);
        }

        .btn-box .btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 0;
            height: 100%;
            background: var(--bg-color);
            z-index: -1;
            transition: .5s;
        }

        .btn-box .btn:hover::before {
            width: 100%;
        }

        .home-sci {
            position: absolute;
            bottom: 4rem;
            width: 170px;
            display: flex;
            justify-content: space-between;
        }

        .home-sci a {
            position: relative;
            display: inline-flex;
            justify-content: center;
            align-items: center;
            width: 40px;
            height: 40px;
            background: transparent;
            border: .2rem solid var(--main-color);
            border-radius: 50%;
            font-size: 20px;
            color: var(--main-color);
            z-index: 1;
            overflow: hidden;
            transition: .5s;
        }

        .home-sci a:hover {
            color: var(--bg-color);
        }

        .home-sci a::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 0;
            height: 100%;
            background: var(--main-color);
            z-index: -1;
            transition: .5s;
        }

        .home-sci a:hover::before {
            width: 100%;
        }

        .home-imgHover {
            position: absolute;
            top: 0;
            right: 0;
            width: 45%;
            height: 100%;
            background: transparent;
            transition: 3s;
        }

        .home-imgHover:hover {
            background: var(--bg-color);
            opacity: .8;
        }

        .about {
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            gap: 2rem;
            background: var(--second-bg-color);
            padding-bottom: 6rem;
        }

        .heading {
            font-size: 5rem;
            margin-bottom: 3rem;
            text-align: center;
        }

        span {
            color: var(--main-color);
        }

        .about-img {
            position: relative;
            width: 25rem;
            height: 25rem;
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .about-img img {
            width: 90%;
            border-radius: 50%;
            border: .2rem solid var(--main-color);
        }

        .about-img .circle-spin {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%) rotate(0);
            width: 100%;
            height: 100%;
            border-radius: 50%;
            border-top: .2rem solid var(--second-bg-color);
            border-bottom: .2rem solid var(--second-bg-color);
            border-left: .2rem solid var(--main-color);
            border-right: .2rem solid var(--main-color);
        }

        .about-content {
            text-align: center;
        }

        .about-content h3 {
            font-size: 2.6rem;
        }

        .about-content p {
            font-size: 1.6rem;
            margin: 2rem 0 3rem;
        }

        .btn-box.btns {
            display: inline-block;
            width: 15rem;
        }

        .btn-box.btns a::before {
            background: var(--second-bg-color);
        }

        .education {
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            min-height: auto;
            padding-bottom: 5rem;
        }

        .education .education-row {
            display: flex;
            flex-wrap: wrap;
            gap: 5rem;
        }

        .education-row .education-column {
            flex: 1 1 40rem;
        }

        .education-column .title {
            font-size: 2.5rem;
            margin: 0 0 1.5rem 2rem;
        }

        .education-column .education-box {
            border-left: .2rem solid var(--main-color);
        }

        .education-box .education-content {
            position: relative;
            padding-left: 2rem;
        }

        .education-box .education-content::before {
            content: '';
            position: absolute;
            top: 0;
            left: -1.1rem;
            width: 2rem;
            height: 2rem;
            background: var(--main-color);
            border-radius: 50%;
        }

        .education-content .content {
            position: relative;
            padding: 1.5rem;
            border: .2rem solid var(--main-color);
            border-radius: .6rem;
            margin-bottom: 2rem;
            overflow: hidden;
        }

        .education-content .content::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 0;
            height: 100%;
            background: var(--second-bg-color);
            z-index: -1;
            transition: .5s;
        }

        .education-content .content:hover::before {
            width: 100%;
        }

        .education-content .content .year {
            font-size: 1.5rem;
            color: var(--main-color);
            padding-bottom: .5rem;
        }

        .education-content .content .year i {
            padding-right: .5rem;
        }

        .education-content .content h3 {
            font-size: 2rem;
        }

        .education-content .content p {
            font-size: 1.6rem;
            padding-top: .5rem;
        }

        .skills {
            min-height: auto;
            padding-bottom: 7rem;
            background: var(--second-bg-color);
        }

        .skills .skills-row {
            display: flex;
            flex-wrap: wrap;
            gap: 5rem;
        }

        .skills-row .skills-column {
            flex: 1 1 40rem;
        }

        .skills-column .title {
            font-size: 2.5rem;
            margin: 0 0 1.5rem;
        }

        .skills-box .skills-content {
            position: relative;
            border: .2rem solid var(--main-color);
            border-radius: .6rem;
            padding: .5rem 1.5rem;
            z-index: 1;
            overflow: hidden;
        }

        .skills-box .skills-content::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 0;
            height: 100%;
            background: var(--bg-color);
            z-index: -1;
            transition: .5s;
        }

        .skills-box .skills-content:hover::before {
            width: 100%;
        }

        .skills-content .progress {
            padding: 1rem 0;
        }

        .skills-content .progress h3 {
            font-size: 1.7rem;
            display: flex;
            justify-content: space-between;
        }

        .skills-content .progress h3 span {
            color: var(--text-color);
        }

        .skills-content .progress .bar {
            height: 2.5rem;
            border-radius: .6rem;
            border: .2rem solid var(--main-color);
            padding: .5rem;
            margin: 1rem 0;
        }

        .skills-content .progress .bar span {
            display: block;
            height: 100%;
            border-radius: .3rem;
            background: var(--main-color);
        }

        .skills-column:nth-child(1) .skills-content .progress:nth-child(1) .bar span {
            width: 90%;
        }

        .skills-column:nth-child(1) .skills-content .progress:nth-child(2) .bar span {
            width: 85%;
        }

        .skills-column:nth-child(1) .skills-content .progress:nth-child(3) .bar span {
            width: 80%;
        }

        .skills-column:nth-child(1) .skills-content .progress:nth-child(4) .bar span {
            width: 75%;
        }

        .skills-column:nth-child(2) .skills-content .progress:nth-child(1) .bar span {
            width: 85%;
        }

        .skills-column:nth-child(2) .skills-content .progress:nth-child(2) .bar span {
            width: 80%;
        }

        .skills-column:nth-child(2) .skills-content .progress:nth-child(3) .bar span {
            width: 85%;
        }

        .skills-column:nth-child(2) .skills-content .progress:nth-child(4) .bar span {
            width: 75%;
        }

        .contact {
            min-height: auto;
            padding-bottom: 7rem;
        }

        .contact form {
            max-width: 70rem;
            margin: 0 auto;
            text-align: center;
        }

        .contact form .input-box {
            position: relative;
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
        }

        .contact form .input-box .input-field {
            position: relative;
            width: 49%;
            margin: .8rem 0;
        }

        .contact form .input-box .input-field input,
        .contact form .textarea-field textarea {
            width: 100%;
            height: 100%;
            padding: 1.5rem;
            font-size: 1.6rem;
            color: var(--text-color);
            background: transparent;
            border-radius: .6rem;
            border: .2rem solid var(--main-color);
        }

        .contact form .input-box .input-field input::placeholder,
        .contact form .textarea-field textarea::placeholder {
            color: var(--text-color);
        }

        .contact form .textarea-field {
            position: relative;
            margin: .8rem 0 2.7rem;
            display: flex;
        }

        .contact form .textarea-field textarea {
            resize: none;
        }

        .contact form .btn-box.btns .btn {
            cursor: pointer;
        }

        .footer {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            padding: 2rem 9%;
            background: var(--second-bg-color);
        }

        .footer-text p {
            font-size: 1.6rem;
        }

        .footer-iconTop a {
            position: relative;
            display: inline-flex;
            justify-content: center;
            align-items: center;
            padding: .8rem;
            background: var(--main-color);
            border: .2rem solid var(--main-color);
            border-radius: .6rem;
            z-index: 1;
            overflow: hidden;
        }

        .footer-iconTop a::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 0;
            height: 100%;
            background: var(--second-bg-color);
            z-index: -1;
            transition: .5s;
        }

        .footer-iconTop a:hover::before {
            width: 100%;
        }

        .footer-iconTop a i {
            font-size: 2.4rem;
            color: var(--bg-color);
            transition: .5s;
        }

        .footer-iconTop a:hover i {
            color: var(--main-color);
        }

        @media (max-width: 1200px) {
            html {
                font-size: 55%;
            }
        }

        @media (max-width: 991px) {
            .header {
                padding: 2rem 4%;
            }

            section {
                padding: 10rem 4% 2rem;
            }

            .home {
                padding: 0 4%;
            }

            .footer {
                padding: 2rem 4%;
            }
        }

        @media (max-width: 768px) {
            .header {
                background: var(--bg-color);
            }

            #menu-icon {
                display: block;
            }

            .navbar {
                position: absolute;
                top: 100%;
                left: -100%;
                width: 100%;
                padding: 1rem 4%;
                background: var(--bg-color);
                box-shadow: 0 .5rem 1rem rgba(0, 0, 0, .2);
                transition: .25s ease;
                transition-delay: .25s;
            }

            .navbar.active {
                left: 0;
                transition-delay: 0s;
            }

            .navbar a {
                display: block;
                font-size: 2rem;
                margin: 3rem 0;
            }

            .home-imgHover {
                pointer-events: none;
                background: var(--bg-color);
                opacity: .6;
            }
        }

        @media (max-width: 520px) {
            html {
                font-size: 50%;
            }

            .home-content h1 {
                display: flex;
                flex-direction: column;
            }

            .home-sci {
                width: 160px;
            }

            .home-sci a {
                width: 38px;
                height: 38px;
            }
        }

        @media (max-width: 462px) {
            .home-content h1 {
                font-size: 5.2rem;
            }

            .education {
                padding: 10rem 4% 5rem 5%;
            }

            .contact form .input-box .input-field {
                width: 100%;
            }

            .footer {
                flex-direction: column-reverse;
            }

            .footer p {
                margin-top: 2rem;
                text-align: center;
            }
        }

        @media (max-width: 371px) {
            .home {
                justify-content: center;
            }

            .home-content {
                display: flex;
                align-items: center;
                flex-direction: column;
                text-align: center;
            }

            .home-content h1 {
                font-size: 5rem;
            }
        }

        @keyframes homeBgText {
            0%,
            10%,
            100% {
                background-position: -33rem 0;
            }

            65%,
            85% {
                background-position: 0 0;
            }
        }

        @keyframes homeCursorText {
            0%,
            10%,
            100% {
                width: 0;
            }

            65%,
            78%,
            85% {
                width: 100%;
                opacity: 1;
            }

            75%,
            81% {
                opacity: 0;
            }
        }

        @keyframes aboutSpinner {
            100% {
                transform: translate(-50%, -50%) rotate(360deg);
            }
        }

        .about-img .circle-spin {
            animation: aboutSpinner 8s linear infinite;
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header class="header">
        <a href="#" class="logo">Sumit Hajare</a>
        <div class="bx bx-menu" id="menu-icon"><i class="fas fa-bars"></i></div>
        <nav class="navbar">
            <a href="#home" class="active">Home</a>
            <a href="#about">About</a>
            <a href="#skills">Skills</a>
            <a href="#education">Education</a>
            <a href="#work">Projects</a>
            <a href="#contact">Contact</a>
        </nav>
    </header>

    <!-- Home Section -->
    <section class="home" id="home">
        <div class="home-content">
            <h1>Hi There, I'm <span>Sumit Hajare</span></h1>
            <div class="text-animate">
                <h3>Embedded Systems & IoT Developer</h3>
            </div>
            <p>I'm an Electronics & Telecommunication Engineering student passionate about IoT and embedded systems. With hands-on experience in developing real-time monitoring solutions using Arduino, ESP32, and Raspberry Pi.</p>
            <div class="btn-box">
                <a href="#about" class="btn">About Me</a>
                <a href="https://www.linkedin.com/in/sumithajare3b562132b" class="btn" target="_blank">Resume</a>
            </div>
        </div>

        <div class="home-sci">
            <a href="https://github.com/sumithajare11" target="_blank"><i class="fab fa-github"></i></a>
            <a href="https://www.linkedin.com/in/sumithajare3b562132b" target="_blank"><i class="fab fa-linkedin"></i></a>
            <a href="mailto:sumithajare2003@gmail.com"><i class="fas fa-envelope"></i></a>
        </div>

        <div class="home-imgHover"></div>
    </section>

    <!-- About Section -->
    <section class="about" id="about">
        <h2 class="heading">About <span>Me</span></h2>
        <div class="about-img">
            <img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='200' height='200'%3E%3Crect fill='%2300abf0' width='200' height='200'/%3E%3Ctext x='50%25' y='50%25' font-size='80' text-anchor='middle' dy='.3em' fill='white'%3ESH%3C/text%3E%3C/svg%3E" alt="Profile">
            <span class="circle-spin"></span>
        </div>
        <div class="about-content">
            <h3>I'm <span>Sumit</span></h3>
            <p>Embedded Systems & IoT Developer</p>
            <p>I'm an AI/ML enthusiast exploring the power of IoT and embedded systems, with hands-on experience using ESP32, Arduino, and Raspberry Pi platforms. I also work with sensor interfacing, MQTT protocols, and cloud connectivity to build real-time monitoring solutions.</p>
            <p>Alongside embedded development, I have a strong foundation in circuit design, signal processing, and digital electronics. I've worked on various automation systems including railway safety solutions and smart home monitoring.</p>
            <p>I'm constantly improving my skills through real-world projects while applying knowledge from coursework in Electronics & Telecommunication Engineering, with expertise in AVR and ARM microcontroller architectures.</p>
            <p><strong>Email:</strong> sumithajare2003@gmail.com</p>
            <p><strong>Location:</strong> Kolhapur, Maharashtra, India</p>
            <div class="btn-box btns">
                <a href="https://www.linkedin.com/in/sumithajare3b562132b" target="_blank" class="btn">LinkedIn Profile</a>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section class="skills" id="skills">
        <h2 class="heading">My <span>Skills</span></h2>
        <div class="skills-row">
            <div class="skills-column">
                <h3 class="title">Programming Skills</h3>
                <div class="skills-box">
                    <div class="skills-content">
                        <div class="progress">
                            <h3>C Language <span>90%</span></h3>
                            <div class="bar"><span></span></div>
                        </div>
                        <div class="progress">
                            <h3>Python <span>85%</span></h3>
                            <div class="bar"><span></span></div>
                        </div>
                        <div class="progress">
                            <h3>Embedded C <span>80%</span></h3>
                            <div class="bar"><span></span></div>
                        </div>
                        <div class="progress">
                            <h3>MATLAB <span>75%</span></h3>
                            <div class="bar"><span></span></div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="skills-column">
                <h3 class="title">Technical Skills</h3>
                <div class="skills-box">
                    <div class="skills-content">
                        <div class="progress">
                            <h3>Arduino & ESP32 <span>85%</span></h3>
                            <div class="bar"><span></span></div>
                        </div>
                        <div class="progress">
                            <h3>IoT & Cloud <span>80%</span></h3>
                            <div class="bar"><span></span></div>
                        </div>
                        <div class="progress">
                            <h3>Circuit Design <span>85%</span></h3>
                            <div class="bar"><span></span></div>
                        </div>
                        <div class="progress">
                            <h3>Sensor Interfacing <span>75%</span></h3>
                            <div class="bar"><span></span></div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Education Section -->
    <section class="education" id="education">
        <h2 class="heading">My <span>Education</span></h2>
        <div class="education-row">
            <div class="education-column">
                <h3 class="title">Education</h3>
                <div class="education-box">
                    <div class="education-content">
                        <div class="content">
                            <div class="year"><i class="fas fa-calendar"></i> Aug 2021 - May 2025</div>
                            <h3>Bachelor of Technology - Shivaji University, Kolhapur</h3>
                            <p>Electronics & Telecommunication Engineering | CGPA: 7.0</p>
                        </div>
                    </div>
                    <div class="education-content">
                        <div class="content">
                            <div class="year"><i class="fas fa-calendar"></i> Jul 2019 - Feb 2021</div>
                            <h3>Higher Secondary Certificate - Maharashtra State Board</h3>
                            <p>Science Stream | Percentage: 84%</p>
                        </div>
                    </div>
                </div>
            </div>

            <div class="education-column">
                <h3 class="title">Experience</h3>
                <div class="education-box">
                    <div class="education-content">
                        <div class="content">
                            <div class="year"><i class="fas fa-calendar"></i> Jun 2024</div>
                            <h3>IoT Intern - AVR Tech (INDIA)</h3>
                            <p>Developed IoT-based automation solutions using ESP32 and Arduino platforms for real-time monitoring and cloud connectivity.</p>
                        </div>
                    </div>
                    <div class="education-content">
                        <div class="content">
                            <div class="year"><i class="fas fa-calendar"></i> Sep 2023 - Nov 2023</div>
                            <h3>Embedded Developer - EduSkills Foundation</h3>
                            <p>Built embedded applications using C for microcontroller-based systems with focus on RTOS and hardware-software integration.</p>
                        </div>
                    </div>
                    <div class="education-content">
                        <div class="content">
                            <div class="year"><i class="fas fa-calendar"></i> Sep 2023 - Nov 2023</div>
                            <h3>Embedded System Intern - Acmegrade</h3>
                            <p>Comprehensive training in embedded system design covering AVR and ARM architectures with peripheral interfacing.</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section class="education" id="work" style="background: var(--second-bg-color);">
        <h2 class="heading">My <span>Projects</span></h2>
        <div class="education-row">
            <div class="education-column">
                <div class="education-box">
                    <div class="education-content">
                        <div class="content">
                            <div class="year"><i class="fas fa-calendar"></i> 2025</div>
                            <h3>Railway Accident Prevention System</h3>
                            <p>Engineered real-time railway safety system using multiple sensors and microcontrollers to detect track anomalies. Integrated GPS and GSM modules for instant location tracking with 95% accuracy.</p>
                            <p><strong>Tech:</strong> IoT, Embedded Systems, Cloud Monitoring, GPS/GSM</p>
                        </div>
                    </div>
                </div>
            </div>
            <div class="education-column">
                <div class="education-box">
                    <div class="education-content">
                        <div class="content">
                            <div class="year"><i class="fas fa-calendar"></i> 2023</div>
                            <h3>Automated Home Monitoring System</h3>
                            <p>Developed smart home automation system with temperature, humidity, and motion sensors. Created mobile app for real-time control reducing energy consumption by 30%.</p>
                            <p><strong>Tech:</strong> Arduino, IoT, Mobile App Integration, Wi-Fi</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
