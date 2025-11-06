<!doctype html>
<html lang="en">
 <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Dhanusri - Cyber Networking Portfolio</title>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&amp;display=swap" rel="stylesheet">
  <script src="/_sdk/element_sdk.js"></script>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      box-sizing: border-box;
      font-family: 'Inter', sans-serif;
      overflow-x: hidden;
      scroll-behavior: smooth;
      background: linear-gradient(135deg, #0a0a2e 0%, #16213e 25%, #1a1a3a 50%, #0f0f23 75%, #000011 100%);
    }

    html, body {
      height: 100%;
    }

    #starfield {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: -2;
    }

    #network-lines {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: -1;
      opacity: 0.3;
    }

    .hero-section {
      min-height: 100%;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
      padding: 2rem;
      position: relative;
      background: radial-gradient(ellipse at center, rgba(138, 43, 226, 0.1) 0%, transparent 70%);
    }

    .hero-content h1 {
      font-size: 3.5rem;
      font-weight: 700;
      background: linear-gradient(135deg, #4169e1, #da70d6, #ff69b4, #dda0dd);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      margin-bottom: 1rem;
      animation: heroGlow 3s ease-in-out infinite alternate;
      text-shadow: 0 0 30px rgba(138, 43, 226, 0.5);
    }

    @keyframes heroGlow {
      from {
        filter: drop-shadow(0 0 15px rgba(65, 105, 225, 0.6));
      }
      to {
        filter: drop-shadow(0 0 25px rgba(218, 112, 214, 0.8));
      }
    }

    .hero-content h2 {
      font-size: 1.6rem;
      font-weight: 400;
      color: #87ceeb;
      margin-bottom: 2.5rem;
      text-shadow: 0 0 10px rgba(135, 206, 235, 0.5);
    }

    .hero-buttons {
      display: flex;
      gap: 2rem;
      flex-wrap: wrap;
      justify-content: center;
    }

    .btn {
      padding: 1.2rem 2.5rem;
      font-size: 1.1rem;
      font-weight: 600;
      border: none;
      border-radius: 50px;
      cursor: pointer;
      transition: all 0.4s ease;
      text-decoration: none;
      display: inline-block;
      position: relative;
      overflow: hidden;
    }

    .btn::before {
      content: '';
      position: absolute;
      top: 0;
      left: -100%;
      width: 100%;
      height: 100%;
      background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
      transition: left 0.5s;
    }

    .btn:hover::before {
      left: 100%;
    }

    .btn-primary {
      background: linear-gradient(135deg, #ff69b4, #da70d6, #dda0dd);
      color: white;
      box-shadow: 0 0 25px rgba(255, 105, 180, 0.4);
      border: 2px solid transparent;
    }

    .btn-primary:hover {
      box-shadow: 0 0 35px rgba(255, 105, 180, 0.7), 0 0 50px rgba(218, 112, 214, 0.5);
      transform: translateY(-5px) scale(1.05);
      border-color: #ff1493;
    }

    .btn-secondary {
      background: rgba(65, 105, 225, 0.1);
      color: #4169e1;
      border: 2px solid #4169e1;
      box-shadow: 0 0 20px rgba(65, 105, 225, 0.3);
    }

    .btn-secondary:hover {
      background: rgba(65, 105, 225, 0.2);
      box-shadow: 0 0 30px rgba(65, 105, 225, 0.6);
      transform: translateY(-5px) scale(1.05);
      border-color: #87ceeb;
    }

    .about-section {
      min-height: 100%;
      background: linear-gradient(135deg, #1a1a2e 0%, #16213e 50%, #0f0f23 100%);
      padding: 4rem 2rem;
      display: flex;
      align-items: center;
      justify-content: center;
      position: relative;
    }

    .about-section::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
      background: linear-gradient(45deg, rgba(255, 105, 180, 0.1) 0%, rgba(138, 43, 226, 0.1) 100%);
      border-top: 3px solid #ff69b4;
      border-bottom: 3px solid #8a2be2;
    }

    .about-container {
      max-width: 1200px;
      display: grid;
      grid-template-columns: 1fr 2fr;
      gap: 4rem;
      align-items: center;
      z-index: 1;
      position: relative;
    }

    .about-image {
      width: 100%;
      max-width: 320px;
      height: 320px;
      border-radius: 25px;
      background: linear-gradient(135deg, #2a2a4e, #1a1a3e);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 7rem;
      filter: grayscale(100%) contrast(1.2);
      border: 4px solid #da70d6;
      box-shadow: 0 0 40px rgba(218, 112, 214, 0.4);
      transition: all 0.3s ease;
    }

    .about-image:hover {
      transform: scale(1.05);
      box-shadow: 0 0 50px rgba(218, 112, 214, 0.6);
    }

    .about-content h2 {
      font-size: 2.8rem;
      color: #ffffff;
      margin-bottom: 2rem;
      filter: grayscale(100%);
      font-weight: 700;
    }

    .about-content p {
      font-size: 1.2rem;
      line-height: 1.9;
      color: #e0e0e0;
      filter: grayscale(100%);
    }

    .skills-section {
      min-height: 100%;
      padding: 4rem 2rem;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }

    .skills-container {
      max-width: 1200px;
      width: 100%;
      background: rgba(20, 20, 50, 0.8);
      backdrop-filter: blur(15px);
      border-radius: 25px;
      padding: 3.5rem;
      border: 2px solid rgba(65, 105, 225, 0.3);
      box-shadow: 0 0 40px rgba(138, 43, 226, 0.2);
    }

    .skills-container h2 {
      font-size: 2.8rem;
      color: #87ceeb;
      text-align: center;
      margin-bottom: 2.5rem;
      font-weight: 700;
    }

    .skills-grid {
      display: flex;
      flex-wrap: wrap;
      gap: 1.5rem;
      justify-content: center;
    }

    .skill-tag {
      padding: 1rem 2rem;
      border-radius: 50px;
      font-weight: 600;
      font-size: 1rem;
      transition: all 0.4s ease;
      cursor: default;
      border: 2px solid transparent;
    }

    .skill-tag:nth-child(1) { 
      background: linear-gradient(135deg, #4169e1, #6495ed); 
      color: white; 
      box-shadow: 0 0 15px rgba(65, 105, 225, 0.4);
    }
    .skill-tag:nth-child(2) { 
      background: linear-gradient(135deg, #ff69b4, #ff1493); 
      color: white; 
      box-shadow: 0 0 15px rgba(255, 105, 180, 0.4);
    }
    .skill-tag:nth-child(3) { 
      background: linear-gradient(135deg, #da70d6, #dda0dd); 
      color: white; 
      box-shadow: 0 0 15px rgba(218, 112, 214, 0.4);
    }
    .skill-tag:nth-child(4) { 
      background: linear-gradient(135deg, #8a2be2, #9370db); 
      color: white; 
      box-shadow: 0 0 15px rgba(138, 43, 226, 0.4);
    }
    .skill-tag:nth-child(5) { 
      background: linear-gradient(135deg, #4169e1, #87ceeb); 
      color: white; 
      box-shadow: 0 0 15px rgba(65, 105, 225, 0.4);
    }
    .skill-tag:nth-child(6) { 
      background: linear-gradient(135deg, #ff69b4, #da70d6); 
      color: white; 
      box-shadow: 0 0 15px rgba(255, 105, 180, 0.4);
    }
    .skill-tag:nth-child(7) { 
      background: linear-gradient(135deg, #dda0dd, #d8bfd8); 
      color: white; 
      box-shadow: 0 0 15px rgba(221, 160, 221, 0.4);
    }

    .skill-tag:hover {
      transform: translateY(-8px) scale(1.1);
      box-shadow: 0 0 30px rgba(255, 20, 147, 0.7);
      border-color: #ff1493;
    }

    .projects-section {
      min-height: 100%;
      padding: 4rem 2rem;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }

    .projects-container {
      max-width: 1200px;
      width: 100%;
    }

    .projects-container h2 {
      font-size: 2.8rem;
      color: #da70d6;
      text-align: center;
      margin-bottom: 3.5rem;
      font-weight: 700;
    }

    .projects-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
      gap: 2.5rem;
    }

    .project-card {
      background: rgba(20, 20, 50, 0.9);
      backdrop-filter: blur(15px);
      border-radius: 20px;
      padding: 2.5rem;
      border: 2px solid transparent;
      transition: all 0.4s ease;
      cursor: pointer;
      position: relative;
      overflow: hidden;
    }

    .project-card::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
      background: linear-gradient(135deg, rgba(255, 105, 180, 0.1), rgba(138, 43, 226, 0.1));
      opacity: 0;
      transition: opacity 0.3s ease;
    }

    .project-card:hover::before {
      opacity: 1;
    }

    .project-card:hover {
      border-color: #ff1493;
      box-shadow: 0 0 40px rgba(255, 20, 147, 0.6);
      transform: translateY(-15px) scale(1.02);
    }

    .project-card h3 {
      font-size: 1.6rem;
      color: #87ceeb;
      margin-bottom: 1.2rem;
      font-weight: 600;
      z-index: 1;
      position: relative;
    }

    .project-card p {
      color: #e0e0e0;
      line-height: 1.7;
      margin-bottom: 2rem;
      z-index: 1;
      position: relative;
    }

    .project-card .btn {
      padding: 0.8rem 1.8rem;
      font-size: 0.95rem;
      z-index: 1;
      position: relative;
    }

    .contact-section {
      min-height: 100%;
      padding: 4rem 2rem;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }

    .contact-container {
      max-width: 900px;
      width: 100%;
      text-align: center;
    }

    .contact-container h2 {
      font-size: 2.8rem;
      color: #87ceeb;
      margin-bottom: 2.5rem;
      font-weight: 700;
      text-shadow: 0 0 20px rgba(135, 206, 235, 0.5);
    }

    .contact-cards {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 2.5rem;
      margin-top: 2.5rem;
    }

    .contact-card {
      background: rgba(20, 20, 50, 0.8);
      backdrop-filter: blur(15px);
      padding: 2.5rem;
      border-radius: 20px;
      border: 2px solid rgba(135, 206, 235, 0.3);
      transition: all 0.4s ease;
      position: relative;
      overflow: hidden;
    }

    .contact-card::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
      background: linear-gradient(135deg, rgba(65, 105, 225, 0.1), rgba(255, 105, 180, 0.1));
      opacity: 0;
      transition: opacity 0.3s ease;
    }

    .contact-card:hover::before {
      opacity: 1;
    }

    .contact-card:hover {
      border-color: #87ceeb;
      box-shadow: 0 0 35px rgba(135, 206, 235, 0.6);
      transform: translateY(-10px) scale(1.05);
    }

    .contact-card h3 {
      color: #da70d6;
      font-size: 1.4rem;
      margin-bottom: 0.8rem;
      font-weight: 600;
      z-index: 1;
      position: relative;
    }

    .contact-card p {
      color: #ffffff;
      font-size: 1rem;
      z-index: 1;
      position: relative;
    }

    footer {
      background: linear-gradient(135deg, rgba(10, 10, 30, 0.95), rgba(20, 20, 50, 0.95));
      padding: 2.5rem;
      text-align: center;
      color: #87ceeb;
      font-size: 1rem;
      border-top: 2px solid rgba(218, 112, 214, 0.3);
      backdrop-filter: blur(10px);
    }

    @media (max-width: 768px) {
      .hero-content h1 {
        font-size: 2.5rem;
      }

      .hero-content h2 {
        font-size: 1.3rem;
      }

      .about-container {
        grid-template-columns: 1fr;
        text-align: center;
        gap: 2rem;
      }

      .about-image {
        margin: 0 auto;
        max-width: 250px;
        height: 250px;
        font-size: 5rem;
      }

      .hero-buttons {
        flex-direction: column;
        width: 100%;
        gap: 1rem;
      }

      .btn {
        width: 100%;
        padding: 1rem 2rem;
      }

      .skills-container, .projects-container, .contact-container {
        padding: 2rem;
      }
    }
  </style>
  <style>@view-transition { navigation: auto; }</style>
  <script src="/_sdk/data_sdk.js" type="text/javascript"></script>
  <script src="https://cdn.tailwindcss.com" type="text/javascript"></script>
 </head>
 <body>
  <canvas id="starfield"></canvas>
  <canvas id="network-lines"></canvas>
  <section class="hero-section" id="home">
   <div class="hero-content">
    <h1 id="hero-headline">Building Secure Networks &amp; Exploring Cyber Defense.</h1>
    <h2 id="hero-subheadline">Dhanusri — Cyber Networking Enthusiast &amp; Security Learner.</h2>
    <div class="hero-buttons"><a href="#projects" class="btn btn-primary">✨ View Projects ⭐</a> <a href="#contact" class="btn btn-secondary">💫 Contact Me 🌟</a>
    </div>
   </div>
  </section>
  <section class="about-section" id="about">
   <div class="about-container">
    <div class="about-image">
     👤
    </div>
    <div class="about-content">
     <h2 id="about-title">About Me</h2>
     <p id="about-bio">I'm a passionate Cyber Networking student with a deep fascination for network security, ethical hacking, and digital forensics. My journey in cybersecurity is driven by an insatiable curiosity and the desire to build secure, resilient networks that protect against evolving cyber threats. I thrive on analyzing network traffic, implementing robust security protocols, and exploring the intricate world of penetration testing and vulnerability assessment. Every challenge is an opportunity to strengthen digital defenses.</p>
    </div>
   </div>
  </section>
  <section class="skills-section" id="skills">
   <div class="skills-container">
    <h2 id="skills-title">Technical Expertise</h2>
    <div class="skills-grid">
     <div class="skill-tag">
      TCP/IP
     </div>
     <div class="skill-tag">
      Subnetting
     </div>
     <div class="skill-tag">
      Wireshark
     </div>
     <div class="skill-tag">
      IDS/IPS
     </div>
     <div class="skill-tag">
      Linux
     </div>
     <div class="skill-tag">
      Python Scripting
     </div>
     <div class="skill-tag">
      Network Security Tools
     </div>
    </div>
   </div>
  </section>
  <section class="projects-section" id="projects">
   <div class="projects-container">
    <h2 id="projects-title">Featured Projects</h2>
    <div class="projects-grid">
     <div class="project-card">
      <h3>VLAN Segmentation Lab</h3>
      <p>Designed and implemented a comprehensive multi-VLAN network topology to enhance security through strategic network segmentation and advanced access control mechanisms.</p><a href="#" class="btn btn-primary">View Details</a>
     </div>
     <div class="project-card">
      <h3>Wireshark Packet Analysis</h3>
      <p>Conducted deep packet inspection and forensic analysis to identify security vulnerabilities, analyze network traffic patterns, and develop threat detection methodologies.</p><a href="#" class="btn btn-primary">GitHub</a>
     </div>
     <div class="project-card">
      <h3>Python Network Scanner</h3>
      <p>Developed an intelligent automated network scanning tool using Python to discover active hosts, identify open ports, and perform comprehensive security auditing.</p><a href="#" class="btn btn-primary">View Details</a>
     </div>
    </div>
   </div>
  </section>
  <section class="contact-section" id="contact">
   <div class="contact-container">
    <h2 id="contact-title">Get In Touch</h2>
    <div class="contact-cards">
     <div class="contact-card">
      <h3>📧 Email</h3>
      <p>dhanusri@cybernetwork.com</p>
     </div>
     <div class="contact-card">
      <h3>💼 LinkedIn</h3>
      <p>linkedin.com/in/dhanusri-cyber</p>
     </div>
     <div class="contact-card">
      <h3>🔗 GitHub</h3>
      <p>github.com/dhanusri-security</p>
     </div>
    </div>
   </div>
  </section>
  <footer>
   <p id="footer-text">© 2025 Dhanusri • Cyber Networking Portfolio</p>
  </footer>
  <script>
    const defaultConfig = {
      hero_headline: "Building Secure Networks & Exploring Cyber Defense.",
      hero_subheadline: "Dhanusri — Cyber Networking Enthusiast & Security Learner.",
      about_title: "About Me",
      about_bio: "I'm a passionate Cyber Networking student with a deep fascination for network security, ethical hacking, and digital forensics. My journey in cybersecurity is driven by an insatiable curiosity and the desire to build secure, resilient networks that protect against evolving cyber threats. I thrive on analyzing network traffic, implementing robust security protocols, and exploring the intricate world of penetration testing and vulnerability assessment. Every challenge is an opportunity to strengthen digital defenses.",
      skills_title: "Technical Expertise",
      projects_title: "Featured Projects",
      contact_title: "Get In Touch",
      footer_text: "© 2025 Dhanusri • Cyber Networking Portfolio",
      background_color: "#0a0a2e",
      surface_color: "#16213e",
      text_color: "#ffffff",
      primary_accent: "#4169e1",
      secondary_accent: "#ff69b4",
      font_family: "Inter",
      font_size: 16
    };

    async function onConfigChange(config) {
      const baseSize = config.font_size || defaultConfig.font_size;
      const customFont = config.font_family || defaultConfig.font_family;
      const baseFontStack = 'sans-serif';

      document.getElementById('hero-headline').textContent = config.hero_headline || defaultConfig.hero_headline;
      document.getElementById('hero-subheadline').textContent = config.hero_subheadline || defaultConfig.hero_subheadline;
      document.getElementById('about-title').textContent = config.about_title || defaultConfig.about_title;
      document.getElementById('about-bio').textContent = config.about_bio || defaultConfig.about_bio;
      document.getElementById('skills-title').textContent = config.skills_title || defaultConfig.skills_title;
      document.getElementById('projects-title').textContent = config.projects_title || defaultConfig.projects_title;
      document.getElementById('contact-title').textContent = config.contact_title || defaultConfig.contact_title;
      document.getElementById('footer-text').textContent = config.footer_text || defaultConfig.footer_text;

      document.body.style.fontSize = `${baseSize}px`;
      document.body.style.fontFamily = `${customFont}, ${baseFontStack}`;

      const h1Elements = document.querySelectorAll('h1');
      h1Elements.forEach(el => {
        el.style.fontSize = `${baseSize * 2.2}px`;
        el.style.fontFamily = `${customFont}, ${baseFontStack}`;
      });

      const h2Elements = document.querySelectorAll('h2');
      h2Elements.forEach(el => {
        el.style.fontSize = `${baseSize * 1.75}px`;
        el.style.fontFamily = `${customFont}, ${baseFontStack}`;
      });

      const h3Elements = document.querySelectorAll('h3');
      h3Elements.forEach(el => {
        el.style.fontSize = `${baseSize * 1.4}px`;
        el.style.fontFamily = `${customFont}, ${baseFontStack}`;
      });

      const pElements = document.querySelectorAll('p');
      pElements.forEach(el => {
        el.style.fontSize = `${baseSize}px`;
        el.style.fontFamily = `${customFont}, ${baseFontStack}`;
      });

      const buttons = document.querySelectorAll('.btn');
      buttons.forEach(el => {
        el.style.fontSize = `${baseSize * 0.95}px`;
        el.style.fontFamily = `${customFont}, ${baseFontStack}`;
      });
    }

    function mapToCapabilities(config) {
      return {
        recolorables: [
          {
            get: () => config.background_color || defaultConfig.background_color,
            set: (value) => {
              config.background_color = value;
              window.elementSdk.setConfig({ background_color: value });
            }
          },
          {
            get: () => config.surface_color || defaultConfig.surface_color,
            set: (value) => {
              config.surface_color = value;
              window.elementSdk.setConfig({ surface_color: value });
            }
          },
          {
            get: () => config.text_color || defaultConfig.text_color,
            set: (value) => {
              config.text_color = value;
              window.elementSdk.setConfig({ text_color: value });
            }
          },
          {
            get: () => config.primary_accent || defaultConfig.primary_accent,
            set: (value) => {
              config.primary_accent = value;
              window.elementSdk.setConfig({ primary_accent: value });
            }
          },
          {
            get: () => config.secondary_accent || defaultConfig.secondary_accent,
            set: (value) => {
              config.secondary_accent = value;
              window.elementSdk.setConfig({ secondary_accent: value });
            }
          }
        ],
        borderables: [],
        fontEditable: {
          get: () => config.font_family || defaultConfig.font_family,
          set: (value) => {
            config.font_family = value;
            window.elementSdk.setConfig({ font_family: value });
          }
        },
        fontSizeable: {
          get: () => config.font_size || defaultConfig.font_size,
          set: (value) => {
            config.font_size = value;
            window.elementSdk.setConfig({ font_size: value });
          }
        }
      };
    }

    function mapToEditPanelValues(config) {
      return new Map([
        ["hero_headline", config.hero_headline || defaultConfig.hero_headline],
        ["hero_subheadline", config.hero_subheadline || defaultConfig.hero_subheadline],
        ["about_title", config.about_title || defaultConfig.about_title],
        ["about_bio", config.about_bio || defaultConfig.about_bio],
        ["skills_title", config.skills_title || defaultConfig.skills_title],
        ["projects_title", config.projects_title || defaultConfig.projects_title],
        ["contact_title", config.contact_title || defaultConfig.contact_title],
        ["footer_text", config.footer_text || defaultConfig.footer_text]
      ]);
    }

    if (window.elementSdk) {
      window.elementSdk.init({
        defaultConfig,
        onConfigChange,
        mapToCapabilities,
        mapToEditPanelValues
      });
    }

    // Starfield Animation
    const canvas = document.getElementById('starfield');
    const ctx = canvas.getContext('2d');
    let stars = [];
    let mouseX = 0;
    let mouseY = 0;

    // Network Lines Animation
    const networkCanvas = document.getElementById('network-lines');
    const networkCtx = networkCanvas.getContext('2d');
    let nodes = [];

    function resizeCanvas() {
      canvas.width = window.innerWidth;
      canvas.height = document.documentElement.scrollHeight;
      networkCanvas.width = window.innerWidth;
      networkCanvas.height = document.documentElement.scrollHeight;
    }

    function createStars() {
      stars = [];
      const numStars = 150;
      for (let i = 0; i < numStars; i++) {
        stars.push({
          x: Math.random() * canvas.width,
          y: Math.random() * canvas.height,
          radius: Math.random() * 3 + 1,
          vx: (Math.random() - 0.5) * 0.3,
          vy: (Math.random() - 0.5) * 0.3,
          color: ['#4169e1', '#87ceeb', '#da70d6', '#ff69b4', '#dda0dd'][Math.floor(Math.random() * 5)],
          twinkle: Math.random() * Math.PI * 2
        });
      }
    }

    function createNodes() {
      nodes = [];
      const numNodes = 20;
      for (let i = 0; i < numNodes; i++) {
        nodes.push({
          x: Math.random() * networkCanvas.width,
          y: Math.random() * networkCanvas.height,
          vx: (Math.random() - 0.5) * 0.5,
          vy: (Math.random() - 0.5) * 0.5
        });
      }
    }

    function drawStars() {
      ctx.fillStyle = 'rgba(10, 10, 46, 0.05)';
      ctx.fillRect(0, 0, canvas.width, canvas.height);

      stars.forEach(star => {
        const dx = mouseX - star.x;
        const dy = mouseY - star.y;
        const distance = Math.sqrt(dx * dx + dy * dy);

        if (distance < 200) {
          star.x -= dx * 0.008;
          star.y -= dy * 0.008;
        }

        star.x += star.vx;
        star.y += star.vy;
        star.twinkle += 0.02;

        if (star.x < 0 || star.x > canvas.width) star.vx *= -1;
        if (star.y < 0 || star.y > canvas.height) star.vy *= -1;

        const twinkleAlpha = (Math.sin(star.twinkle) + 1) * 0.5;
        
        ctx.beginPath();
        ctx.arc(star.x, star.y, star.radius, 0, Math.PI * 2);
        ctx.fillStyle = star.color;
        ctx.shadowBlur = 15;
        ctx.shadowColor = star.color;
        ctx.globalAlpha = 0.7 + twinkleAlpha * 0.3;
        ctx.fill();
        ctx.globalAlpha = 1;
      });

      requestAnimationFrame(drawStars);
    }

    function drawNetworkLines() {
      networkCtx.clearRect(0, 0, networkCanvas.width, networkCanvas.height);

      nodes.forEach(node => {
        node.x += node.vx;
        node.y += node.vy;

        if (node.x < 0 || node.x > networkCanvas.width) node.vx *= -1;
        if (node.y < 0 || node.y > networkCanvas.height) node.vy *= -1;
      });

      for (let i = 0; i < nodes.length; i++) {
        for (let j = i + 1; j < nodes.length; j++) {
          const dx = nodes[i].x - nodes[j].x;
          const dy = nodes[i].y - nodes[j].y;
          const distance = Math.sqrt(dx * dx + dy * dy);

          if (distance < 200) {
            networkCtx.beginPath();
            networkCtx.moveTo(nodes[i].x, nodes[i].y);
            networkCtx.lineTo(nodes[j].x, nodes[j].y);
            networkCtx.strokeStyle = `rgba(65, 105, 225, ${0.3 - distance / 600})`;
            networkCtx.lineWidth = 1;
            networkCtx.stroke();
          }
        }
      }

      requestAnimationFrame(drawNetworkLines);
    }

    window.addEventListener('resize', () => {
      resizeCanvas();
      createStars();
      createNodes();
    });

    document.addEventListener('mousemove', (e) => {
      mouseX = e.clientX;
      mouseY = e.clientY + window.scrollY;
    });

    resizeCanvas();
    createStars();
    createNodes();
    drawStars();
    drawNetworkLines();
  </script>
 <script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9991890391d84013',t:'MTc2MjIzMjI5NS4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
