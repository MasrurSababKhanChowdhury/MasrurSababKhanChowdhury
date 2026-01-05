<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Masrur Sabab | Aspiring Engineer</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;800&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg-color: #050505;
            --text-main: #ffffff;
            --text-muted: #a0a0a0;
            --card-bg: rgba(255, 255, 255, 0.03);
            --border: rgba(255, 255, 255, 0.1);
            --spotlight-size: 600px;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Inter', sans-serif;
            background-color: var(--bg-color);
            color: var(--text-main);
            line-height: 1.6;
            min-height: 100vh;
            overflow-x: hidden;
            position: relative;
        }

        /* Spotlight Effect Background */
        #spotlight {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            background: radial-gradient(
                circle at var(--x) var(--y), 
                rgba(255, 255, 255, 0.08) 0%, 
                transparent var(--spotlight-size)
            );
            z-index: 0;
        }

        /* Container */
        .container {
            position: relative;
            z-index: 1;
            max-width: 900px;
            margin: 0 auto;
            padding: 4rem 1.5rem;
        }

        /* Header / Nav */
        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 8rem;
            border-bottom: 1px solid var(--border);
            padding-bottom: 1.5rem;
        }

        .logo {
            font-weight: 800;
            font-size: 1.2rem;
            letter-spacing: -1px;
            text-transform: uppercase;
        }

        .socials a {
            color: var(--text-muted);
            text-decoration: none;
            margin-left: 1.5rem;
            font-size: 0.9rem;
            transition: color 0.3s;
        }

        .socials a:hover {
            color: var(--text-main);
        }

        /* Hero Section */
        .hero h1 {
            font-size: clamp(2.5rem, 8vw, 5rem);
            font-weight: 800;
            line-height: 1;
            letter-spacing: -2px;
            margin-bottom: 1.5rem;
            background: linear-gradient(to bottom right, #fff, #666);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .hero h2 {
            font-size: 1.25rem;
            font-weight: 300;
            color: var(--text-muted);
            margin-bottom: 3rem;
            border-left: 2px solid var(--text-main);
            padding-left: 1rem;
        }

        /* Bio Section */
        .bio-section {
            background: var(--card-bg);
            border: 1px solid var(--border);
            padding: 3rem;
            border-radius: 24px;
            backdrop-filter: blur(10px);
            margin-bottom: 3rem;
            transition: border-color 0.3s;
        }

        .bio-section:hover {
            border-color: rgba(255,255,255,0.2);
        }

        .bio-text {
            font-size: 1.15rem;
            color: #d1d1d1;
            margin-bottom: 2rem;
        }

        .highlight {
            color: #fff;
            font-weight: 600;
            background: rgba(255,255,255,0.1);
            padding: 0 4px;
            border-radius: 4px;
        }

        /* Stats / Focus Grid */
        .grid-focus {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 1.5rem;
            margin-bottom: 3rem;
        }

        .grid-card {
            background: var(--card-bg);
            border: 1px solid var(--border);
            padding: 2rem;
            border-radius: 16px;
        }

        .grid-label {
            font-size: 0.75rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            color: var(--text-muted);
            margin-bottom: 0.5rem;
        }

        .grid-value {
            font-size: 1.5rem;
            font-weight: 600;
        }

        /* Skills Section */
        .skills-section h3 {
            margin-bottom: 1.5rem;
            font-size: 1rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            color: var(--text-muted);
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(80px, 1fr));
            gap: 1.5rem;
        }

        .skill-icon-wrapper {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 10px;
            padding: 1.5rem;
            background: var(--card-bg);
            border: 1px solid var(--border);
            border-radius: 12px;
            transition: transform 0.3s, background 0.3s;
            cursor: default;
        }

        .skill-icon-wrapper:hover {
            transform: translateY(-5px);
            background: rgba(255,255,255,0.05);
        }

        .skill-icon-wrapper img {
            width: 40px;
            height: 40px;
            /* Monochrome filter */
            filter: grayscale(100%) brightness(200%);
        }

        .skill-name {
            font-size: 0.7rem;
            font-weight: 500;
            color: var(--text-muted);
        }

        /* Footer */
        footer {
            margin-top: 6rem;
            text-align: center;
            font-size: 0.8rem;
            color: #444;
            padding-bottom: 2rem;
        }

        /* Animations */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .animate-in {
            animation: fadeIn 0.8s ease-out forwards;
            opacity: 0;
        }
        
        .delay-1 { animation-delay: 0.1s; }
        .delay-2 { animation-delay: 0.2s; }
        .delay-3 { animation-delay: 0.3s; }

        @media (max-width: 768px) {
            .hero h1 { font-size: 2.5rem; }
            .grid-focus { grid-template-columns: 1fr; }
            .bio-section { padding: 1.5rem; }
        }
    </style>
</head>
<body>

    <!-- Spotlight Background Effect -->
    <div id="spotlight"></div>

    <div class="container">
        
        <header class="animate-in">
            <div class="logo">Masrur Sabab</div>
            <div class="socials">
                <a href="https://linkedin.com/in/masrursababkhanchowdhury">LinkedIn</a>
                <a href="https://github.com/MasrurSababKhanChowdhury">GitHub</a>
                <a href="mailto:masrursababkhanchowdhury@gmail.com">Email</a>
            </div>
        </header>

        <main>
            <!-- Hero -->
            <section class="hero">
                <h1 class="animate-in delay-1">Building the future<br>one line at a time.</h1>
                <h2 class="animate-in delay-2">Aspiring Engineer & Technology Enthusiast</h2>
            </section>

            <!-- Biography -->
            <section class="bio-section animate-in delay-2">
                <div class="bio-text">
                    A technology enthusiast driven by the logic of networks and the creativity of code. I am currently interning at Summit Communication Limited, where I focus on <span class="highlight">Network Visualization</span>—translating complex data flows into clear, actionable insights.
                    <br><br>
                    My journey spans from building scalable web systems to exploring the architecture of Deep Learning. I am fascinated by the power of Transformers, LLMs, and the elegance of modern software engineering. 
                    <br><br>
                    Personally, I am a lifelong learner, constantly seeking the "great future" where innovation meets practicality. I believe in using technology not just to solve problems, but to improve lives and industries.
                </div>
            </section>

            <!-- Focus Grid -->
            <section class="grid-focus animate-in delay-3">
                <div class="grid-card">
                    <div class="grid-label">Current Work</div>
                    <div class="grid-value">Network Visualization<br><span style="font-size:1rem; color:#666; font-weight:400;">Summit Comm. Ltd.</span></div>
                </div>
                <div class="grid-card">
                    <div class="grid-label">Interests</div>
                    <div class="grid-value">AI & Full Stack<br><span style="font-size:1rem; color:#666; font-weight:400;">Transformers • Web Systems</span></div>
                </div>
            </section>

            <!-- Technical Stack -->
            <section class="skills-section animate-in delay-3">
                <h3>Technical Arsenal</h3>
                <div class="skills-grid">
                    
                    <!-- Core -->
                    <div class="skill-icon-wrapper">
                        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" alt="Python">
                        <span class="skill-name">Python</span>
                    </div>
                    <div class="skill-icon-wrapper">
                        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/c/c-original.svg" alt="C">
                        <span class="skill-name">C</span>
                    </div>
                    <div class="skill-icon-wrapper">
                        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/cplusplus/cplusplus-original.svg" alt="C++">
                        <span class="skill-name">C++</span>
                    </div>
                    <div class="skill-icon-wrapper">
                        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original.svg" alt="Java">
                        <span class="skill-name">Java</span>
                    </div>

                    <!-- Web & Frameworks -->
                    <div class="skill-icon-wrapper">
                        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/django/django-plain.svg" alt="Django">
                        <span class="skill-name">Django</span>
                    </div>
                    <div class="skill-icon-wrapper">
                        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" alt="JavaScript">
                        <span class="skill-name">JavaScript</span>
                    </div>
                    <div class="skill-icon-wrapper">
                        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" alt="HTML">
                        <span class="skill-name">HTML5</span>
                    </div>
                    <div class="skill-icon-wrapper">
                        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg" alt="CSS">
                        <span class="skill-name">CSS3</span>
                    </div>

                    <!-- DB & OS -->
                    <div class="skill-icon-wrapper">
                        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mariadb/mariadb-original.svg" alt="MariaDB">
                        <span class="skill-name">MariaDB</span>
                    </div>
                    <div class="skill-icon-wrapper">
                        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg" alt="MySQL">
                        <span class="skill-name">MySQL</span>
                    </div>
                    <div class="skill-icon-wrapper">
                        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linux/linux-original.svg" alt="Linux">
                        <span class="skill-name">Linux</span>
                    </div>
                    <div class="skill-icon-wrapper">
                        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg" alt="Git">
                        <span class="skill-name">Git</span>
                    </div>

                    <!-- AI -->
                    <div class="skill-icon-wrapper">
                        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/tensorflow/tensorflow-original.svg" alt="TensorFlow">
                        <span class="skill-name">TensorFlow</span>
                    </div>
                    <div class="skill-icon-wrapper">
                        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/pytorch/pytorch-original.svg" alt="PyTorch">
                        <span class="skill-name">PyTorch</span>
                    </div>
                </div>
            </section>

        </main>

        <footer>
            <p>&copy; 2024 Masrur Sabab. Building towards the future.</p>
        </footer>

    </div>

    <script>
        // Spotlight Effect Logic
        const spotlight = document.getElementById('spotlight');
        
        document.addEventListener('mousemove', (e) => {
            const x = e.clientX;
            const y = e.clientY;
            
            spotlight.style.setProperty('--x', `${x}px`);
            spotlight.style.setProperty('--y', `${y}px`);
        });

        // Optional: Click interaction for skills
        const skills = document.querySelectorAll('.skill-icon-wrapper');
        skills.forEach(skill => {
            skill.addEventListener('click', () => {
                // Reset all
                skills.forEach(s => s.style.borderColor = 'rgba(255,255,255,0.1)');
                // Highlight clicked
                skill.style.borderColor = '#fff';
            });
        });
    </script>
</body>
</html>
