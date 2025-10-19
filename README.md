<!-- Chosen Palette: GitHub Dark (Deep Slate/Charcoal background, Vibrant Blue accent, Neutral Grays) -->
<!-- Application Structure Plan: The SPA is designed as a single-page, scrollable portfolio with a fixed sidebar navigation for desktop and a hamburger menu for mobile. The information architecture prioritizes quantifiable impact by placing "Vulnerability Triage" and "Live PoCs" before certifications and history. This non-linear structure immediately showcases hands-on skills to a recruiter. The "Operational Resilience" section is a key differentiator, designed to frame the non-traditional background as a unique strength in crisis management, directly translating it to security incident response. The user flow is designed for quick scanning by a technical hiring manager. -->
<!-- Visualization & Content Choices: Report Info: Skillset -> Goal: Organize/Inform -> Viz/Presentation: Two Chart.js visualizations (Doughnut for skill balance, Radar for domain proficiency) and tagged skill lists -> Interaction: Charts are static but visually engaging -> Justification: Charts provide a quick, digestible overview of technical breadth, which is more scannable than a long list. | Report Info: Career History -> Goal: Organize/Change -> Viz/Presentation: The "Operational Resilience" section uses a structured HTML grid with icons to explain the value of the non-traditional background. -> Justification: This is more direct than a chronological timeline and focuses on transferable skills. | Report Info: PoCs/Certs -> Goal: Compare/Inform -> Viz/Presentation: Interactive HTML cards with hover effects -> Interaction: Click to verify external links -> Justification: Card layout allows for clear segmentation and encourages engagement with verifiable proof. Library/Method: Chart.js (Canvas), Tailwind CSS, Vanilla JS. -->
<!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MD Azmol Haque Rony | Threat Hunter & Resilience Specialist</title>
    <meta name="description" content="Professional portfolio for MD Azmol Haque Rony, a Cybersecurity Practitioner specializing in threat hunting, vulnerability triage, and operational resilience.">
    <meta name="keywords" content="Cybersecurity, Threat Hunter, Bug Bounty, Vulnerability Assessment, Incident Response, Python, Linux, SIEM">
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <script src="https://unpkg.com/lucide@latest"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700;800&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #0d1117;
            color: #c9d1d9;
        }
        .card {
            background-color: #161b22;
            border: 1px solid #30363d;
            transition: transform 0.3s ease, box-shadow 0.3s ease, border-color 0.3s ease;
        }
        .card:hover {
            transform: translateY(-5px);
            border-color: #58a6ff;
            box-shadow: 0 10px 30px rgba(88, 166, 255, 0.15);
        }
        .skill-tag {
            background-color: #21262d;
            border: 1px solid #30363d;
        }
        .nav-link.active {
            color: #58a6ff;
            font-weight: 700;
        }
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 400px;
            margin-left: auto;
            margin-right: auto;
            height: 300px;
            max-height: 400px;
        }
        @media (min-width: 768px) {
            .chart-container {
                height: 350px;
            }
        }
    </style>
</head>
<body class="antialiased">

    <div class="lg:flex">
        <!-- Sidebar Navigation (Desktop) -->
        <header class="hidden lg:flex lg:w-1/4 lg:flex-col lg:fixed lg:inset-y-0 lg:border-r lg:border-gray-800 bg-[#0d1117] p-8">
            <div class="flex flex-col gap-y-5 overflow-y-auto">
                <div class="text-center">
                    <h1 class="text-2xl font-bold text-white">MD Azmol Haque Rony</h1>
                    <p class="text-md text-[#58a6ff]">Threat Hunter & Operational Resilience Specialist</p>
                </div>
                <nav class="flex flex-1 flex-col mt-8">
                    <ul role="list" class="flex flex-1 flex-col gap-y-7 text-center">
                        <li>
                            <ul role="list" class="-mx-2 space-y-2">
                                <li><a href="#impact" class="nav-link text-gray-400 hover:text-white group flex gap-x-3 rounded-md p-2 text-sm leading-6 font-semibold">Impact</a></li>
                                <li><a href="#projects" class="nav-link text-gray-400 hover:text-white group flex gap-x-3 rounded-md p-2 text-sm leading-6 font-semibold">PoC Portfolio</a></li>
                                <li><a href="#skills" class="nav-link text-gray-400 hover:text-white group flex gap-x-3 rounded-md p-2 text-sm leading-6 font-semibold">Skills</a></li>
                                <li><a href="#certs" class="nav-link text-gray-400 hover:text-white group flex gap-x-3 rounded-md p-2 text-sm leading-6 font-semibold">Certifications</a></li>
                                <li><a href="#contact" class="nav-link text-gray-400 hover:text-white group flex gap-x-3 rounded-md p-2 text-sm leading-6 font-semibold">Contact</a></li>
                            </ul>
                        </li>
                    </ul>
                </nav>
                 <div class="mt-auto text-center">
                    <div class="flex justify-center space-x-4 mb-4">
                         <a href="https://www.linkedin.com/in/md-azmol-haque-rony" target="_blank" class="text-gray-400 hover:text-white"><i data-lucide="linkedin"></i></a>
                         <a href="https://github.com/azmolhaque" target="_blank" class="text-gray-400 hover:text-white"><i data-lucide="github"></i></a>
                    </div>
                    <p class="text-xs text-gray-500">&copy; 2025 MD Azmol Haque Rony</p>
                </div>
            </div>
        </header>

        <!-- Mobile Header -->
        <div class="lg:hidden sticky top-0 z-40 flex items-center gap-x-6 bg-[#0d1117] px-4 py-4 shadow-sm sm:px-6">
            <button type="button" id="mobile-menu-button" class="-m-2.5 p-2.5 text-gray-400">
                <i data-lucide="menu"></i>
            </button>
            <div class="flex-1 text-sm font-semibold leading-6 text-white">MD Azmol Haque Rony</div>
        </div>
        
        <!-- Mobile Sidebar -->
        <div id="mobile-menu" class="hidden fixed inset-0 z-50">
            <div id="mobile-menu-overlay" class="fixed inset-0 bg-gray-900/80"></div>
            <div id="mobile-menu-content" class="fixed inset-y-0 left-0 z-50 w-full overflow-y-auto bg-[#0d1117] px-6 py-6 sm:max-w-sm sm:ring-1 sm:ring-white/10 -translate-x-full transition-transform duration-300 ease-in-out">
                 <div class="flex items-center justify-between">
                    <a href="#" class="text-lg font-bold text-[#58a6ff]">Portfolio</a>
                    <button type="button" id="mobile-close-button" class="-m-2.5 rounded-md p-2.5 text-gray-400">
                        <i data-lucide="x"></i>
                    </button>
                </div>
                <div class="mt-6 flow-root">
                    <div class="-my-6 divide-y divide-gray-500/25">
                        <div class="space-y-2 py-6">
                            <a href="#impact" class="mobile-nav-link -mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-white hover:bg-gray-800">Impact</a>
                            <a href="#projects" class="mobile-nav-link -mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-white hover:bg-gray-800">PoC Portfolio</a>
                            <a href="#skills" class="mobile-nav-link -mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-white hover:bg-gray-800">Skills</a>
                            <a href="#certs" class="mobile-nav-link -mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-white hover:bg-gray-800">Certifications</a>
                            <a href="#contact" class="mobile-nav-link -mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-white hover:bg-gray-800">Contact</a>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <main class="py-10 lg:pl-72">
            <div class="px-4 sm:px-6 lg:px-8">

                <!-- Professional Summary -->
                <section id="summary" class="mb-16">
                     <h2 class="text-3xl font-bold text-white mb-4">MD AZMOL HAQUE RONY</h2>
                     <p class="text-lg text-gray-300 leading-relaxed">
                        A highly disciplined Security Practitioner with <strong>3+ years of equivalent Security Operations experience</strong>, primarily gained through intensive global bug bounty work and technical projects. I blend proven technical hunting skills with a decade of high-stakes <strong>Crisis Management</strong> (Médecins Sans Frontières / MSF), delivering precision and unwavering integrity during incident response.
                    </p>
                </section>
                
                <!-- Quantified Impact Section -->
                <section id="impact" class="mb-16">
                    <h2 class="text-2xl font-bold text-white mb-6 border-l-4 border-[#58a6ff] pl-4">Quantified Technical Impact (Vulnerability Triage)</h2>
                    <p class="mb-8 text-gray-400">This section demonstrates hands-on expertise in identifying, triaging, and documenting critical security flaws—a core function of a threat hunter or vulnerability analyst.</p>
                    <div class="grid md:grid-cols-3 gap-6">
                        <div class="card p-6 rounded-lg">
                            <h3 class="font-bold text-[#58a6ff] text-lg mb-2">Threat Hunting Record</h3>
                            <p>Identified and disclosed <strong>5+ High-to-Exceptional Severity</strong> flaws to major firms, including **Google VRP, BMW, and Monzo**.</p>
                        </div>
                        <div class="card p-6 rounded-lg">
                            <h3 class="font-bold text-[#58a6ff] text-lg mb-2">Key Flaw Types</h3>
                            <p>Expert in **API Misconfiguration, XSS, and complex Business Logic Flaws**.</p>
                        </div>
                        <div class="card p-6 rounded-lg">
                            <h3 class="font-bold text-[#58a6ff] text-lg mb-2">Deliverables</h3>
                            <p>Proven ability to conduct detailed **Root Cause Analysis (RCA)** and submit triage-ready reports.</p>
                        </div>
                    </div>
                </section>

                <!-- PoC Projects Section -->
                <section id="projects" class="mb-16">
                    <h2 class="text-2xl font-bold text-white mb-6 border-l-4 border-[#58a6ff] pl-4">Verified Proof of Concept (PoC) Projects</h2>
                    <p class="mb-8 text-gray-400">These projects are live demonstrations of my ability to identify, quantify, and report real-world risk, focusing on API Misconfiguration and financial impact.</p>
                     <div class="space-y-8">
                        <div class="card p-6 rounded-lg">
                            <h3 class="font-bold text-xl text-white mb-2">Synology Maps API Key Exposure</h3>
                            <p class="text-gray-400 mb-4"><strong>Risk Type:</strong> Financial/Data Leakage (Quota Exhaustion)</p>
                            <a href="https://azmolhaque.github.io/synology_poc/" target="_blank" class="font-semibold text-[#58a6ff] hover:underline">View PoC Demo <i data-lucide="arrow-right" class="inline w-4 h-4"></i></a>
                        </div>
                        <div class="card p-6 rounded-lg">
                            <h3 class="font-bold text-xl text-white mb-2">Wing.com Geocoding API Key Leak</h3>
                            <p class="text-gray-400 mb-4"><strong>Risk Type:</strong> Unauthorized Access (Cloud Billing Impact)</p>
                            <a href="https://azmolhaque.github.io/wing-com-unrestricted-maps-api-key-poc/" target="_blank" class="font-semibold text-[#58a6ff] hover:underline">View PoC Demo <i data-lucide="arrow-right" class="inline w-4 h-4"></i></a>
                        </div>
                    </div>
                </section>
                
                <!-- Skills Section with Charts -->
                <section id="skills" class="mb-16">
                    <h2 class="text-2xl font-bold text-white mb-8 border-l-4 border-[#58a6ff] pl-4">Core Technical Arsenal</h2>
                    <p class="mb-8 text-gray-400">A visual breakdown of technical focus areas and domain proficiency, demonstrating a balanced skill set for a junior analyst role.</p>
                    <div class="grid md:grid-cols-2 gap-12 items-center">
                        <div class="chart-container">
                             <canvas id="skillBalanceChart"></canvas>
                        </div>
                        <div class="chart-container">
                            <canvas id="domainProficiencyChart"></canvas>
                        </div>
                    </div>
                     <div class="mt-8 grid grid-cols-2 md:grid-cols-4 gap-4 text-center">
                        <div><p class="skill-tag rounded-md p-2 text-sm">Python</p></div>
                        <div><p class="skill-tag rounded-md p-2 text-sm">Linux & Bash</p></div>
                        <div><p class="skill-tag rounded-md p-2 text-sm">SQL</p></div>
                        <div><p class="skill-tag rounded-md p-2 text-sm">SIEM Tools</p></div>
                        <div><p class="skill-tag rounded-md p-2 text-sm">Nmap</p></div>
                        <div><p class="skill-tag rounded-md p-2 text-sm">Burp Suite</p></div>
                        <div><p class="skill-tag rounded-md p-2 text-sm">NIST CSF</p></div>
                        <div><p class="skill-tag rounded-md p-2 text-sm">Incident Response</p></div>
                    </div>
                </section>

                <!-- Certifications Section -->
                <section id="certs" class="mb-16">
                    <h2 class="text-2xl font-bold text-white mb-6 border-l-4 border-[#58a6ff] pl-4">Certifications & Verifications</h2>
                    <p class="mb-8 text-gray-400">All training and certifications are up-to-date and verifiable, demonstrating hands-on proficiency in core cybersecurity domains.</p>
                    <div class="grid md:grid-cols-3 gap-6">
                        <div class="card p-6 rounded-lg">
                            <h3 class="font-bold text-lg text-white mb-2">Google Cybersecurity Professional Certificate</h3>
                            <p class="text-sm text-gray-400 mb-4">Python, Linux/SQL, Detection & Response, SIEM</p>
                            <a href="https://coursera.org/verify/professional-cert/9EMHGS2G0UAM" target="_blank" class="font-semibold text-[#58a6ff] hover:underline text-sm">Verify Credential</a>
                        </div>
                         <div class="card p-6 rounded-lg">
                            <h3 class="font-bold text-lg text-white mb-2">Advent of Cyber 2024 (THM)</h3>
                            <p class="text-sm text-gray-400 mb-4">Forensics, Web Exploitation, Defensive Strategies</p>
                            <a href="https://tryhackme-certificates.s3-eu-west-1.amazonaws.com/THM-BB6YTOI6RT.pdf" target="_blank" class="font-semibold text-[#58a6ff] hover:underline text-sm">View Certificate (PDF)</a>
                        </div>
                         <div class="card p-6 rounded-lg">
                            <h3 class="font-bold text-lg text-white mb-2">Mastercard Cybersecurity Job Simulation</h3>
                            <p class="text-sm text-gray-400 mb-4">Phishing Defense, Security Awareness</p>
                            <a href="https://forage-uploads-prod.s3.amazonaws.com/completion-certificates/mastercard/vcKAB5yYAgvemepGQ_Mastercard_JMsHG793ksfGqPq9v_1715191717515_completion_certificate.pdf" target="_blank" class="font-semibold text-[#58a6ff] hover:underline text-sm">View Certificate (PDF)</a>
                        </div>
                    </div>
                </section>
                
                <!-- Operational Resilience -->
                <section id="resilience" class="mb-16">
                    <h2 class="text-2xl font-bold text-white mb-6 border-l-4 border-[#58a6ff] pl-4">Operational Resilience: The Crisis Management Advantage</h2>
                    <p class="mb-8 text-gray-400">My background as a Security Advisor and Humanitarian Professional (MSF) provides highly valuable, non-technical capabilities that define operational resilience in a security context.</p>
                    <div class="grid md:grid-cols-3 gap-8">
                        <div>
                            <i data-lucide="shield-alert" class="w-8 h-8 text-[#58a6ff] mb-4"></i>
                            <h3 class="font-bold text-lg text-white mb-2">Pressure Management & Decision Making</h3>
                            <p class="text-sm">Managed high-stress situations in Emergency Rooms and ICUs. This translates directly to rapid, calm assessment, disciplined decision-making, and accurate execution of containment protocols during an active security incident.</p>
                        </div>
                        <div>
                            <i data-lucide="lock" class="w-8 h-8 text-[#58a6ff] mb-4"></i>
                            <h3 class="font-bold text-lg text-white mb-2">Unwavering Confidentiality & Compliance</h3>
                            <p class="text-sm">Responsible for sensitive patient health information (PHI) and operational intelligence. Guaranteed strict adherence to policy, demonstrating an intrinsic understanding of data integrity and discretion required for compliance roles.</p>
                        </div>
                        <div>
                            <i data-lucide="users" class="w-8 h-8 text-[#58a6ff] mb-4"></i>
                            <h3 class="font-bold text-lg text-white mb-2">Cross-Functional Policy Adherence</h3>
                            <p class="text-sm">As an MSF Security Advisor, I translated complex security protocols into actionable communication for non-technical, international teams, ensuring high accountability and policy acceptance across organizational boundaries.</p>
                        </div>
                    </div>
                </section>

                 <!-- Contact Section -->
                <section id="contact" class="mb-16">
                     <h2 class="text-2xl font-bold text-white mb-6 border-l-4 border-[#58a6ff] pl-4">Contact & Documentation</h2>
                     <p class="mb-8 text-gray-400">I am actively seeking new opportunities. Please feel free to reach out via email, phone, or connect on LinkedIn. You can also download my full professional resume for your records.</p>
                     <div class="card p-6 rounded-lg">
                        <ul class="space-y-4">
                            <li class="flex items-center"><i data-lucide="at-sign" class="w-5 h-5 mr-3 text-[#58a6ff]"></i> <a href="mailto:azmolhaque95@gmail.com" class="hover:underline">azmolhaque95@gmail.com</a></li>
                            <li class="flex items-center"><i data-lucide="phone" class="w-5 h-5 mr-3 text-[#58a6ff]"></i> <span>+8801717534550</span></li>
                            <li class="flex items-center"><i data-lucide="file-text" class="w-5 h-5 mr-3 text-[#58a6ff]"></i> <a href="Cybersecurity Resume.pdf" target="_blank" class="hover:underline">Download Professional Resume (PDF)</a></li>
                        </ul>
                     </div>
                </section>


            </div>
        </main>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            lucide.createIcons();

            // Mobile menu logic
            const mobileMenu = document.getElementById('mobile-menu');
            const mobileMenuButton = document.getElementById('mobile-menu-button');
            const mobileCloseButton = document.getElementById('mobile-close-button');
            const mobileMenuOverlay = document.getElementById('mobile-menu-overlay');
            const mobileMenuContent = document.getElementById('mobile-menu-content');
            
            const openMenu = () => {
                mobileMenu.classList.remove('hidden');
                setTimeout(() => {
                    mobileMenuContent.classList.remove('-translate-x-full');
                }, 20);
            };

            const closeMenu = () => {
                mobileMenuContent.classList.add('-translate-x-full');
                setTimeout(() => {
                    mobileMenu.classList.add('hidden');
                }, 300);
            };

            mobileMenuButton.addEventListener('click', openMenu);
            mobileCloseButton.addEventListener('click', closeMenu);
            mobileMenuOverlay.addEventListener('click', closeMenu);
            document.querySelectorAll('.mobile-nav-link').forEach(link => {
                link.addEventListener('click', closeMenu);
            });

            // Scrollspy for desktop nav
            const sections = document.querySelectorAll('section[id]');
            const navLinks = document.querySelectorAll('.nav-link');

            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        navLinks.forEach(link => {
                            link.classList.toggle('active', link.getAttribute('href').substring(1) === entry.target.id);
                        });
                    }
                });
            }, { rootMargin: "-50% 0px -50% 0px" });

            sections.forEach(section => observer.observe(section));
            
            // Chart.js visualizations
            const skillBalanceCtx = document.getElementById('skillBalanceChart');
            if(skillBalanceCtx) {
                new Chart(skillBalanceCtx, {
                    type: 'doughnut',
                    data: {
                        labels: ['Offensive Security', 'Defensive & GRC', 'Automation & Scripting'],
                        datasets: [{
                            label: 'Skill Balance',
                            data: [45, 30, 25],
                            backgroundColor: ['#f87171', '#60a5fa', '#34d399'],
                             borderColor: '#161b22',
                            borderWidth: 4
                        }]
                    },
                    options: {
                        responsive: true,
                        maintainAspectRatio: false,
                        plugins: {
                            legend: {
                                position: 'top',
                                labels: {
                                    color: '#c9d1d9'
                                }
                            },
                            title: {
                                display: true,
                                text: 'Skill Area Balance',
                                color: '#ffffff',
                                font: { size: 16 }
                            }
                        }
                    }
                });
            }

            const domainProficiencyCtx = document.getElementById('domainProficiencyChart');
            if(domainProficiencyCtx) {
                 new Chart(domainProficiencyCtx, {
                    type: 'radar',
                    data: {
                        labels: ['Web App Pentesting', 'Network Security', 'Incident Response', 'GRC/Compliance', 'Python Scripting', 'Cloud Security'],
                        datasets: [{
                            label: 'Domain Proficiency',
                            data: [85, 70, 75, 65, 80, 60],
                            fill: true,
                            backgroundColor: 'rgba(88, 166, 255, 0.2)',
                            borderColor: '#58a6ff',
                            pointBackgroundColor: '#58a6ff',
                            pointBorderColor: '#fff',
                            pointHoverBackgroundColor: '#fff',
                            pointHoverBorderColor: '#58a6ff'
                        }]
                    },
                    options: {
                        responsive: true,
                        maintainAspectRatio: false,
                         plugins: {
                            legend: {
                                display: false
                            },
                             title: {
                                display: true,
                                text: 'Proficiency Across Domains',
                                color: '#ffffff',
                                font: { size: 16 }
                            }
                        },
                        scales: {
                            r: {
                                angleLines: { color: '#30363d' },
                                grid: { color: '#30363d' },
                                pointLabels: { color: '#c9d1d9', font: {size: 10}},
                                ticks: {
                                    color: '#c9d1d9',
                                    backdropColor: 'rgba(0,0,0,0)',
                                    stepSize: 20
                                }
                            }
                        }
                    }
                });
            }
        });
    </script>
</body>
</html>

