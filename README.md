<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>M. Sangeetha | Full Stack Developer</title>

  <!-- Google Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">

  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Poppins', sans-serif;
    }

    body {
      background: radial-gradient(ellipse at bottom, #0a0f1f, #000);
      color: #e0f7ff;
      overflow-x: hidden;
      position: relative;
    }

    /* Floating particles background */
    .particles {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      overflow: hidden;
      z-index: -1;
    }

    .particles span {
      position: absolute;
      display: block;
      width: 20px;
      height: 20px;
      background: rgba(0, 255, 255, 0.3);
      border-radius: 50%;
      bottom: -150px;
      animation: rise 10s infinite ease-in;
    }

    @keyframes rise {
      0% { transform: translateY(0) scale(0.5); opacity: 0; }
      50% { opacity: 1; }
      100% { transform: translateY(-110vh) scale(1); opacity: 0; }
    }

    header {
      position: fixed;
      top: 0;
      width: 100%;
      background: rgba(10, 25, 47, 0.7);
      backdrop-filter: blur(10px);
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 1rem 3rem;
      z-index: 1000;
      border-bottom: 1px solid rgba(0, 255, 255, 0.2);
    }

    header h1 {
      font-size: 1.5rem;
      color: cyan;
      letter-spacing: 1px;
    }

    nav a {
      color: #e0f7ff;
      margin: 0 15px;
      text-decoration: none;
      font-weight: 500;
      transition: color 0.3s ease;
    }

    nav a:hover { color: cyan; }

    section {
      min-height: 100vh;
      padding: 100px 10%;
    }

    /* HERO SECTION */
    .hero {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
    }

    /* Circular Profile Image (Professional Look) */
    .profile-img {
      width: 190px;
      height: 190px;
      border-radius: 50%;
      border: 3px solid cyan;
      box-shadow: 0 0 25px rgba(0, 255, 255, 0.5),
                  0 0 50px rgba(0, 255, 255, 0.3);
      object-fit: cover;
      transition: all 0.4s ease;
      margin-bottom: 25px;
    }

    .profile-img:hover {
      transform: scale(1.07);
      box-shadow: 0 0 40px cyan, 0 0 70px rgba(0, 255, 255, 0.5);
    }

    .hero h2 {
      font-size: 2.8rem;
      color: cyan;
    }

    .hero h3 {
      font-size: 1.5rem;
      margin-top: 0.5rem;
    }

    .hero p {
      margin-top: 1rem;
      font-size: 1.1rem;
      max-width: 700px;
    }

    .hero button {
      background: cyan;
      border: none;
      padding: 12px 24px;
      color: #000;
      border-radius: 30px;
      margin-top: 1.5rem;
      font-weight: 600;
      cursor: pointer;
      transition: 0.3s ease;
    }

    .hero button:hover {
      transform: translateY(-3px);
      box-shadow: 0 0 20px cyan;
    }

    /* About Section */
    .about {
      background: rgba(255, 255, 255, 0.05);
      border-radius: 20px;
      backdrop-filter: blur(10px);
      padding: 3rem;
      box-shadow: 0 0 20px rgba(0, 255, 255, 0.1);
    }

    .about h2 {
      color: cyan;
      font-size: 2rem;
      margin-bottom: 1rem;
    }

    .about p {
      font-size: 1.19rem;
      line-height: 1.9;
    }

    /* Skills */
    .skills {
      text-align: center;
      margin-top: 4rem;
    }

    .skills h2 {
      color: cyan;
      font-size: 3.9rem;
      margin-bottom: 2rem;
    }

    .skills-list {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 1rem;
      margin-top: 1.5rem;
    }

    .skill {
      background: rgba(255, 255, 255, 0.1);
      padding: 10px 25px;
      border-radius: 25px;
      color: #fff;
      border: 1px solid rgba(0, 255, 255, 0.3);
      transition: 0.3s ease;
    }

    .skill:hover {
      background: cyan;
      color: #000;
      box-shadow: 0 0 10px cyan;
    }

    /* Education */
    .education { text-align: center; margin-top: 4rem; }

    .education h2 {
      color: cyan;
      font-size: 2.2rem;
      margin-bottom: 1rem;
    }

    .edu-card {
      background: rgba(255, 255, 255, 0.05);
      backdrop-filter: blur(10px);
      margin: 1rem auto;
      max-width: 700px;
      padding: 1.5rem;
      border-radius: 15px;
      box-shadow: 0 0 20px rgba(0, 255, 255, 0.1);
      font-size: 1.2rem;
    }

    /* Projects */
    .projects { text-align: center; }

    .projects h2 {
      color: cyan;
      font-size: 2.2rem;
      margin-bottom: 1rem;
    }

    .project-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 2rem;
    }

    .project-card {
      background: rgba(255, 255, 255, 0.05);
      backdrop-filter: blur(10px);
      border-radius: 20px;
      overflow: hidden;
      box-shadow: 0 0 20px rgba(0, 255, 255, 0.1);
      transition: transform 0.3s ease;
    }

    .project-card:hover { transform: translateY(-5px); }

    .project-card img {
      width: 100%;
      height: 200px;
      object-fit: cover;
    }

    .project-card h3 {
      margin: 1rem;
      color: cyan;
      font-size: 1.3rem;
    }

    .project-card p {
      margin: 0 1rem 1.5rem;
      font-size: 1.05rem;
      line-height: 1.6;
    }

    /* Contact */
    .contact { text-align: center; }

    .contact h2 {
      color: cyan;
      font-size: 2.2rem;
      margin-bottom: 1rem;
    }

    .contact form {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 1rem;
      max-width: 500px;
      margin: 0 auto;
    }

    .contact input, .contact textarea {
      width: 100%;
      padding: 12px;
      border: none;
      border-radius: 10px;
      background: rgba(255, 255, 255, 0.05);
      color: #e0f7ff;
      backdrop-filter: blur(10px);
      outline: none;
    }

    .contact button {
      background: cyan;
      border: none;
      color: #000;
      padding: 10px 25px;
      border-radius: 30px;
      font-weight: 600;
      cursor: pointer;
      transition: box-shadow 0.3s ease;
    }

    .contact button:hover { box-shadow: 0 0 15px cyan; }

    footer {
      text-align: center;
      padding: 1rem;
      font-size: 0.9rem;
      color: #999;
      border-top: 1px solid rgba(0, 255, 255, 0.1);
    }
  </style>
</head>

<body>
  <div class="particles">
    <span></span><span></span><span></span><span></span><span></span>
    <span></span><span></span><span></span><span></span><span></span>
  </div>

  <header>
    <h1>M. Sangeetha</h1>
    <nav>
      <a href="#hero">Home</a>
      <a href="#about">About</a>
      <a href="#skills">Skills</a>
      <a href="#education">Education</a>
      <a href="#projects">Projects</a>
      <a href="#contact">Contact</a>
    </nav>
  </header>

  <section class="hero" id="hero">
    <img src="https://i.postimg.cc/c1QgWYmT/IMG-20241106-212304.jpg" alt="M. Sangeetha Profile Photo" class="profile-img">
    <h2>Hi, I’m M. Sangeetha</h2>
    <h3>Full Stack Developer</h3>
    <p>Building intelligent, modern, and user-focused web applications with creativity and precision.</p>
    <button onclick="window.location.href='resume.pdf'">Download Resume</button>
  </section>

  <section class="about" id="about">
    <h2>About Me</h2>
    <p>
      I’m <b>M. Sangeetha</b> from Hyderabad — a dedicated Full Stack Developer passionate about blending design with functionality.  
      I develop responsive, efficient web applications using Python, Django, React, and MySQL.  
      My goal is to build products that are secure, scalable, and futuristic, aligning technology with user experience.  
      I’m always learning, improving, and pushing creative boundaries in development and cyber security.<br>I’m a passionate Python Full Stack Developer skilled in building responsive web applications using modern technologies like HTML, CSS, JavaScript, React, Django, and MySQL. I enjoy turning ideas into functional, user-friendly digital solutions.

I have hands-on experience developing both front-end interfaces and back-end systems, ensuring seamless integration between client and server sides. I’m always eager to learn new technologies and improve my coding and problem-solving skills.

Currently, I’m looking for an opportunity where I can contribute my technical skills, grow as a developer, and be part of an innovative team.
    </p>
  </section>

  <section class="skills" id="skills">
    <h2>My Skills</h2>
    <div class="skills-list">
      <span class="skill">HTML5</span>
      <span class="skill">CSS3</span>
      <span class="skill">JavaScript</span>
      <span class="skill">Python</span>
      <span class="skill">Django</span>
      <span class="skill">React</span>
      <span class="skill">MySQL</span>
      <span class="skill">Git & GitHub</span>
      
      
      
    </div>
  </section>

  <section class="education" id="education">
    <h2>Education</h2>
    <div class="edu-card">
      <b>B.Tech – Computer Science (Cyber Security)</b><br>
      Malla Reddy Engineering College, Hyderabad<br>
      CGPA: 7.9 (2021–2025)
    </div>
    <div class="edu-card">
      <b>Intermediate – MPC</b><br>
      Srimathi Kottam Manikyamma Junior College, Gadwal<br>
      Percentage: 75%
    </div>
    <div class="edu-card">
      <b>SSC</b><br>
      ZP High School, Uppair<br>
      GPA: 9.0
    </div>
  </section>

  <section class="projects" id="projects">
    <h2>My Projects</h2>
    <div class="project-grid">
      <div class="project-card">
        <img src="https://ars.els-cdn.com/content/image/1-s2.0-S277267112400024X-gr5.jpg" alt="Traffic Sign Detection">
        <h3>Robust Traffic Sign Detection</h3>
        <p>Used deep learning (CNNs) to detect and classify traffic signs under any weather.<br>
          <b>Tech Used:</b> Python, TensorFlow, OpenCV, CNN
        </p>
      </div>

      <div class="project-card">
        <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTlaYpV1VFN2ce6he9gXjFjOn32feH-tAQkhQ&s" alt="Health Monitoring">
        <h3>Health Monitoring on Social Media</h3>
        <p>Analyzes health discussions across social media to detect public health trends.<br>
          <b>Tech Used:</b> HTML, CSS, JavaScript, JSP, JDBC, MySQL
        </p>
      </div>

      <div class="project-card">
        <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcS3Vl9mhD67GPMmz3t4vJaMiqLsayg6cwthxg&s" alt="Portfolio">
        <h3>Personal Portfolio Website</h3>
        <p>Designed a professional and futuristic online portfolio featuring smooth animations and responsive layout.<br>
          <b>Tech Used:</b> HTML, CSS, JavaScript
        </p>
      </div>
    </div>
  </section>

  <section class="contact" id="contact">
    <h2>Contact Me</h2>
    <form>
      <input type="text" placeholder="Your Name" required />
      <input type="email" placeholder="Your Email" required />
      <textarea rows="4" placeholder="Your Message"></textarea>
      <button type="submit">Send Message</button>
    </form>
    <p style="margin-top: 1rem;">📧 <b>Email:</b> sangeethamanyambavi@gmail.com</p>
    <p>💼 <a href="https://www.linkedin.com/in/sangeetha-manyambavi-4a29b329a" target="_blank" style="color: cyan;">LinkedIn</a> | 
       🐙 <a href="https://github.com/manyambavisangeetha" target="_blank" style="color: cyan;">GitHub</a></p>
  </section>

  <footer>
    © 2025 M. Sangeetha | Designed with 💙 and futuristic vision.
  </footer>
</body>
</html>
