<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MD Azmol Haque Rony | Security Practitioner</title>
    <meta name="description" content="Professional portfolio for MD Azmol Haque Rony, a Security Practitioner specializing in threat hunting, vulnerability management, and operational resilience.">
    
    <!-- Load necessary external libraries -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <script src="https://unpkg.com/lucide@latest"></script>
    
    <!-- Inter Font -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700;800&display=swap" rel="stylesheet">
    
    <!-- Custom Styles for Dark Theme and Card Effects -->
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #0d1117; /* GitHub Dark Background */
            color: #c9d1d9; /* Light Gray Text */
        }
        .card {
            background-color: #161b22; /* Slightly Lighter Dark Gray */
            border: 1px solid #30363d;
            transition: transform 0.3s ease, box-shadow 0.3s ease, border-color 0.3s ease;
        }
        .card:hover {
            transform: translateY(-3px);
            border-color: #58a6ff; /* Accent Blue */
            box-shadow: 0 8px 25px rgba(88, 166, 255, 0.1);
        }
        .nav-link.active {
            color: #58a6ff;
            font-weight: 700;
        }
        /* Chart container enforces fixed height for Chart.js responsiveness */
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 450px;
            margin-left: auto;
            margin-right: auto;
            height: 300px; /* Base height for mobile/tablet */
            max-height: 400px;
        }
        @media (min-width: 768px) {
            .chart-container {
                height: 350px; /* Slightly taller on desktop */
            }
        }
    </style>
</head>
<body class="antialiased">

    <div class="lg:flex">
        <!-- Sidebar Navigation (Desktop - Fixed) -->
        <header class="hidden lg:flex lg:w-1/4 lg:flex-col lg:fixed lg:inset-y-0 lg:border-r lg:border-gray-800 bg-[#0d1117] p-8">
            <div class="flex flex-col gap-y-5 overflow-y-auto">
                <div class="text-center">
                    <h1 class="text-2xl font-bold text-white">RONY</h1>
                    <p class="text-md text-[#58a6ff]">SECURITY PRACTITIONER</p>
                </div>
                <nav class="flex flex-1 flex-col mt-8" aria-label="Desktop Navigation">
                    <ul role="list" class="flex flex-1 flex-col gap-y-4 text-center">
                        <li><a href="#impact" class="nav-link text-gray-400 hover:text-white group flex gap-x-3 rounded-md p-2 text-sm leading-6 font-semibold">Impact & Triage</a></li>
                        <li><a href="#skills" class="nav-link text-gray-400 hover:text-white group flex gap-x-3 rounded-md p-2 text-sm leading-6 font-semibold">Tech Stack</a></li>
                        <li><a href="#resilience" class="nav-link text-gray-400 hover:text-white group flex gap-x-3 rounded-md p-2 text-sm leading-6 font-semibold">Resilience</a></li>
                        <li><a href="#certs" class="nav-link text-gray-400 hover:text-white group flex gap-x-3 rounded-md p-2 text-sm leading-6 font-semibold">Certs</a></li>
                        <li><a href="#contact" class="nav-link text-gray-400 hover:text-white group flex gap-x-3 rounded-md p-2 text-sm leading-6 font-semibold">Contact</a></li>
                    </ul>
                </nav>
                 <div class="mt-auto text-center">
                    <div class="flex justify-center space-x-4 mb-4">
                         <a href="https://www.linkedin.com/in/md-azmol-haque-rony" target="_blank" aria-label="LinkedIn Profile" class="text-gray-400 hover:text-white"><i data-lucide="linkedin"></i></a>
                         <a href="https://github.com/azmolhaque" target="_blank" aria-label="GitHub Profile" class="text-gray-400 hover:text-white"><i data-lucide="github"></i></a>
                    </div>
                </div>
            </div>
        </header>

        <!-- Mobile Header -->
        <div class="lg:hidden sticky top-0 z-40 flex items-center gap-x-6 bg-[#0d1117] px-4 py-4 shadow-sm sm:px-6 border-b border-gray-800">
            <button type="button" id="mobile-menu-button" class="-m-2.5 p-2.5 text-gray-400" aria-expanded="false" aria-controls="mobile-menu-content" aria-label="Open main menu">
                <i data-lucide="menu"></i>
            </button>
            <div class="flex-1 text-sm font-semibold leading-6 text-white">MD AZMOL HAQUE RONY</div>
        </div>
        
        <!-- Mobile Sidebar (Off-canvas) -->
        <div id="mobile-menu" class="hidden fixed inset-0 z-50">
            <div id="mobile-menu-overlay" class="fixed inset-0 bg-gray-900/80" aria-hidden="true"></div>
            <div id="mobile-menu-content" class="fixed inset-y-0 left-0 z-50 w-full overflow-y-auto bg-[#0d1117] px-6 py-6 sm:max-w-sm sm:ring-1 sm:ring-white/10 -translate-x-full transition-transform duration-300 ease-in-out">
                 <div class="flex items-center justify-between">
                    <a href="#" class="text-lg font-bold text-[#58a6ff]">Navigation</a>
                    <button type="button" id="mobile-close-button" class="-m-2.5 rounded-md p-2.5 text-gray-400" aria-label="Close menu">
                        <i data-lucide="x"></i>
                    </button>
                </div>
                <nav class="mt-6 flow-root" aria-label="Mobile Navigation">
                    <div class="-my-6 divide-y divide-gray-500/25">
                        <div class="space-y-2 py-6">
                            <a href="#impact" class="mobile-nav-link -mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-white hover:bg-gray-800">Impact & Triage</a>
                            <a href="#skills" class="mobile-nav-link -mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-white hover:bg-gray-800">Tech Stack</a>
                            <a href="#resilience" class="mobile-nav-link -mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-white hover:bg-gray-800">Resilience</a>
                            <a href="#certs" class="mobile-nav-link -mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-white hover:bg-gray-800">Certs</a>
                            <a href="#contact" class="mobile-nav-link -mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-white hover:bg-gray-800">Contact</a>
                        </div>
                    </div>
                </nav>
            </div>
        </div>

        <main class="py-10 lg:pl-72 w-full">
            <div class="px-4 sm:px-6 lg:px-8">

                <!-- Professional Summary -->
                <section id="summary" class="mb-16">
                     <h2 class="text-3xl font-bold text-white mb-4">MD AZMOL HAQUE RONY</h2>
                     <p class="text-lg text-[#58a6ff] mb-4">Threat Hunting & Vulnerability Management | Operational Resilience Specialist</p>
                     <p class="text-gray-300 leading-relaxed">
                        A highly disciplined security practitioner with **3+ years of hands-on experience** in identifying, analyzing, and reporting critical vulnerabilities (Google VRP, BMW, Monzo). My technical proficiency is reinforced by a decade of high-stakes **crisis and confidentiality management** (MSF), delivering a unique blend of technical defense, precise incident response, and unwavering integrity.
                    </p>
                    <div class="mt-6 border-t border-gray-800 pt-4">
                        <a href="#impact" class="font-semibold text-[#58a6ff] hover:underline flex items-center">
                            View Quantified Vulnerability Impact <i data-lucide="arrow-right" class="inline w-4 h-4 ml-2"></i>
                        </a>
                    </div>
                </section>
                
                <!-- Quantified Impact Section -->
                <section id="impact" class="mb-16">
                    <h2 class="text-2xl font-bold text-white mb-6 border-l-4 border-[#58a6ff] pl-4">Quantified Impact: Vulnerability Discovery & Triage</h2>
                    <p class="mb-8 text-gray-400">This section demonstrates practical expertise in threat hunting, incident triage, and producing engineering-ready reports—core skills for a proactive security analyst.</p>
                    <div class="space-y-8">
                        <!-- Experience Card -->
                        <div class="card p-6 rounded-lg border-l-4 border-red-500">
                            <h3 class="font-bold text-xl text-white mb-3">Security Practitioner Experience (2022-Present)</h3>
                            <ul class="list-disc list-inside space-y-2 text-gray-300 ml-4">
                                <li>**Threat Hunting:** Proactively identified and disclosed **5+ High-to-Exceptional Severity** vulnerabilities to global firms (Google VRP, Flipkart, Monzo, BMW).</li>
                                <li>**Incident Triage:** Conducted detailed **Root Cause Analysis (RCA)** and produced high-fidelity, triage-ready reports for vendor engineering teams, significantly accelerating patch deployment.</li>
                                <li>**Scope Proficiency:** Proven hands-on experience in API Misconfiguration, Cross-Site Scripting (XSS), and complex Business Logic Flaws.</li>
                            </ul>
                        </div>
                        
                        <!-- PoC Projects -->
                        <div class="grid md:grid-cols-2 gap-6">
                            <div class="card p-6 rounded-lg">
                                <h4 class="font-bold text-lg text-white mb-2">PoC: Synology Maps API Key Exposure</h4>
                                <p class="text-gray-400 mb-4 text-sm">**Risk Quantified:** Demonstrated unrestricted Places API abuse, proving potential for **financial quota exhaustion** and PII/metadata leakage. Identified a critical failure in client-side access control.</p>
                                <a href="https://azmolhaque.github.io/synology_poc/" target="_blank" class="font-semibold text-yellow-500 hover:underline flex items-center">
                                    View Live PoC <i data-lucide="external-link" class="inline w-4 h-4 ml-2"></i>
                                </a>
                            </div>
                            <div class="card p-6 rounded-lg">
                                <h4 class="font-bold text-lg text-white mb-2">PoC: Wing.com Geocoding API Key Leak</h4>
                                <p class="text-gray-400 mb-4 text-sm">**Risk Quantified:** Verified unauthorized usage of a Geocoding API key, illustrating a direct financial impact through unauthorized consumption of paid cloud services and data processing.</p>
                                <a href="https://azmolhaque.github.io/wing-com-unrestricted-maps-api-key-poc/" target="_blank" class="font-semibold text-yellow-500 hover:underline flex items-center">
                                    View Live PoC <i data-lucide="external-link" class="inline w-4 h-4 ml-2"></i>
                                </a>
                            </div>
                        </div>
                    </div>
                </section>

                <!-- Skills Section with Charts -->
                <section id="skills" class="mb-16">
                    <h2 class="text-2xl font-bold text-white mb-8 border-l-4 border-[#58a6ff] pl-4">Core Technical Stack & Fundamentals</h2>
                    <p class="mb-8 text-gray-400">A visual breakdown of technical focus areas, demonstrating a balanced skill set necessary for modern security operations and analysis.</p>
                    
                    <div class="grid md:grid-cols-2 gap-12 mb-12">
                        <div class="chart-container card p-4 rounded-lg">
                            <h3 class="text-white text-center font-bold text-lg mb-2">Skill Area Balance</h3>
                            <canvas id="skillBalanceChart" aria-label="Doughnut chart showing skill balance"></canvas>
                        </div>
                        <div class="chart-container card p-4 rounded-lg">
                            <h3 class="text-white text-center font-bold text-lg mb-2">Proficiency Across Domains</h3>
                            <canvas id="domainProficiencyChart" aria-label="Radar chart showing domain proficiency"></canvas>
                        </div>
                    </div>

                    <div class="grid md:grid-cols-3 gap-6">
                        <div class="card p-4 rounded-lg">
                            <h3 class="font-bold text-lg text-[#58a6ff] mb-2 flex items-center"><i data-lucide="activity" class="w-5 h-5 mr-2"></i> SOC & Analysis</h3>
                            <p class="text-sm text-gray-400">SIEM Tools (Conceptual), Detection & Response (D&R), IDS, Vulnerability Assessment, Burp Suite, Nmap, Wireshark.</p>
                        </div>
                         <div class="card p-4 rounded-lg">
                            <h3 class="font-bold text-lg text-[#58a6ff] mb-2 flex items-center"><i data-lucide="code" class="w-5 h-5 mr-2"></i> Automation & OS</h3>
                            <p class="text-sm text-gray-400">Python (Security Scripting), SQL (Data Query & Logging), Linux / Bash Scripting, Cloud Security (GCP/AWS Theory).</p>
                        </div>
                        <div class="card p-4 rounded-lg">
                            <h3 class="font-bold text-lg text-[#58a6ff] mb-2 flex items-center"><i data-lucide="shield-check" class="w-5 h-5 mr-2"></i> Frameworks & Policy</h3>
                            <p class="text-sm text-gray-400">NIST CSF (Identify, Detect, Respond), Security Awareness Training, Confidentiality & Integrity Principles.</p>
                        </div>
                    </div>
                </section>

                <!-- Operational Resilience Section -->
                <section id="resilience" class="mb-16">
                    <h2 class="text-2xl font-bold text-white mb-6 border-l-4 border-[#58a6ff] pl-4">Operational Resilience: The Crisis Management Advantage</h2>
                    <p class="mb-8 text-gray-400">My decade of experience in Crisis Management (MSF) provides unique, non-technical capabilities essential for effective security operations and incident handling.</p>
                    <div class="space-y-6">
                        <div class="card p-6 rounded-lg border-l-4 border-yellow-500">
                            <h3 class="font-bold text-xl text-white mb-2 flex items-center"><i data-lucide="zap" class="w-5 h-5 mr-2 text-yellow-500"></i> Pressure Management & Decision Making</h3>
                            <p class="text-gray-300">Managed high-stress situations in Emergency Rooms and ICUs. This translates directly to **rapid, calm assessment, disciplined decision-making**, and accurate execution of containment protocols during an active security incident.</p>
                        </div>
                        <div class="card p-6 rounded-lg border-l-4 border-green-500">
                            <h3 class="font-bold text-xl text-white mb-2 flex items-center"><i data-lucide="lock" class="w-5 h-5 mr-2 text-green-500"></i> Unwavering Confidentiality & Compliance</h3>
                            <p class="text-gray-300">Responsible for sensitive **patient health information (PHI)** and operational intelligence. Guaranteed strict adherence to policy, demonstrating an intrinsic understanding of data integrity and discretion required for compliance roles.</p>
                        </div>
                        <div class="card p-6 rounded-lg border-l-4 border-blue-500">
                            <h3 class="font-bold text-xl text-white mb-2 flex items-center"><i data-lucide="users" class="w-5 h-5 mr-2 text-blue-500"></i> Cross-Functional Policy Adherence</h3>
                            <p class="text-gray-300">As an MSF Security Advisor, I translated complex security protocols into actionable communication for non-technical, international teams, ensuring high **accountability and policy acceptance** across organizational boundaries.</p>
                        </div>
                    </div>
                </section>

                <!-- Certifications Section -->
                <section id="certs" class="mb-16">
                    <h2 class="text-2xl font-bold text-white mb-6 border-l-4 border-[#58a6ff] pl-4">Verifiable Certifications & Technical Proof</h2>
                    <p class="mb-8 text-gray-400">Formal training and practical challenge completion that validates core security knowledge and hands-on skills.</p>
                    <div class="grid md:grid-cols-3 gap-6">
                        <div class="card p-6 rounded-lg">
                            <h3 class="font-bold text-lg text-white mb-2">Google Cybersecurity Professional Cert.</h3>
                            <p class="text-sm text-gray-400 mb-3">8-course mastery of Python Automation, Detection & Response, Linux, and SIEM/IDS fundamentals. | Completion: Jan 2025</p>
                            <a href="https://coursera.org/verify/professional-cert/9EMHGS2G0UAM" target="_blank" class="font-semibold text-[#58a6ff] hover:underline text-sm">Verify Credentials</a>
                        </div>
                         <div class="card p-6 rounded-lg">
                            <h3 class="font-bold text-lg text-white mb-2">Advent of Cyber 2024 Completion (THM)</h3>
                            <p class="text-sm text-gray-400 mb-3">Completed 24 practical, hands-on challenges in forensics, web exploitation, and defensive strategies. | Completion: Dec 2024</p>
                            <a href="https://tryhackme-certificates.s3-eu-west-1.amazonaws.com/THM-BB6YTOI6RT.pdf" target="_blank" class="font-semibold text-[#58a6ff] hover:underline text-sm">View Certificate</a>
                        </div>
                         <div class="card p-6 rounded-lg">
                            <h3 class="font-bold text-lg text-white mb-2">Mastercard Cybersecurity Job Simulation</h3>
                            <p class="text-sm text-gray-400 mb-3">Practical experience in phishing defense design and interpreting security awareness results. | Completion: May 2024</p>
                            <a href="https://forage-uploads-prod.s3.amazonaws.com/completion-certificates/mastercard/vcKAB5yYAgvemepGQ_Mastercard_JMsHG793ksfGqPq9v_1715191717515_completion_certificate.pdf" target="_blank" class="font-semibold text-[#58a6ff] hover:underline text-sm">View Certificate</a>
                        </div>
                    </div>
                </section>

                 <!-- Contact Section -->
                <section id="contact" class="mb-16">
                     <h2 class="text-2xl font-bold text-white mb-6 border-l-4 border-[#58a6ff] pl-4">Contact & Resume</h2>
                     <p class="mb-6 text-gray-400">My full resume provides the complete professional timeline and detailed project descriptions.</p>
                     <div class="grid md:grid-cols-2 gap-6">
                        <div class="card p-6 rounded-lg">
                           <h3 class="font-bold text-xl text-white mb-3">Contact Information</h3>
                           <ul class="space-y-3 text-gray-300">
                               <li class="flex items-center"><i data-lucide="at-sign" class="w-5 h-5 mr-3 text-[#58a6ff]"></i> <a href="mailto:azmolhaque95@gmail.com" class="hover:underline">azmolhaque95@gmail.com</a></li>
                               <li class="flex items-center"><i data-lucide="phone" class="w-5 h-5 mr-3 text-[#58a6ff]"></i> <span>+8801717534550</span></li>
                               <li class="flex items-center"><i data-lucide="map-pin" class="w-5 h-5 mr-3 text-[#58a6ff]"></i> <span>Bogura, Bangladesh</span></li>
                           </ul>
                        </div>
                        <div class="card p-6 rounded-lg flex flex-col justify-center items-center">
                            <h3 class="font-bold text-xl text-white mb-4">Final Step: View the Full Resume</h3>
                            <!-- Note: The file 'Cybersecurity Resume.pdf' must be available in the same directory for this link to work -->
                            <a href="Cybersecurity Resume.pdf" target="_blank" class="inline-flex items-center justify-center bg-[#58a6ff] text-white font-bold py-3 px-6 rounded-lg hover:bg-blue-600 transition duration-300 shadow-lg" aria-label="Download full resume as PDF">
                                <i data-lucide="download" class="w-5 h-5 mr-2"></i> Download Full Resume (PDF)
                            </a>
                        </div>
                     </div>
                </section>

                <footer class="text-center text-xs text-gray-500 pt-8 mt-16 border-t border-gray-800">
                    <p>&copy; 2025 MD Azmol Haque Rony. All rights reserved.</p>
                    <p class="mt-1">GitHub: Cyber-Safety</p>
                </footer>

            </div>
        </main>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            // Initialize Lucide icons
            lucide.createIcons();

            // --- Mobile Menu Logic ---
            const mobileMenu = document.getElementById('mobile-menu');
            const mobileMenuButton = document.getElementById('mobile-menu-button');
            const mobileCloseButton = document.getElementById('mobile-close-button');
            const mobileMenuOverlay = document.getElementById('mobile-menu-overlay');
            const mobileMenuContent = document.getElementById('mobile-menu-content');
            
            const openMenu = () => {
                mobileMenu.classList.remove('hidden');
                mobileMenuButton.setAttribute('aria-expanded', 'true');
                // Use requestAnimationFrame for immediate translation trigger after display change
                requestAnimationFrame(() => {
                    mobileMenuContent.classList.remove('-translate-x-full');
                });
            };

            const closeMenu = () => {
                mobileMenuContent.classList.add('-translate-x-full');
                mobileMenuButton.setAttribute('aria-expanded', 'false');
                // Hide after the transition is visually complete (300ms defined in CSS)
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

            // --- Intersection Observer for Active Desktop Nav Links ---
            const sections = document.querySelectorAll('section[id]');
            const navLinks = document.querySelectorAll('.nav-link');

            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        navLinks.forEach(link => {
                            const sectionId = entry.target.id;
                            const linkHash = link.getAttribute('href').substring(1);
                            link.classList.toggle('active', linkHash === sectionId);
                        });
                    }
                });
            }, { rootMargin: "-30% 0px -70% 0px" }); // Adjusted root margin for better link switching

            sections.forEach(section => observer.observe(section));
            
            // --- Chart.js Initialization ---
            
            // 1. Skill Area Balance (Doughnut Chart)
            const skillBalanceCtx = document.getElementById('skillBalanceChart');
            if(skillBalanceCtx) {
                new Chart(skillBalanceCtx, {
                    type: 'doughnut',
                    data: {
                        labels: ['Offensive Security', 'Defensive & GRC', 'Automation & Scripting'],
                        datasets: [{
                            label: 'Skill Balance (%)',
                            data: [45, 30, 25],
                            backgroundColor: ['#ef4444', '#3b82f6', '#10b981'], // Red, Blue, Green
                            borderColor: '#161b22', // Card background color for clean separation
                            borderWidth: 4
                        }]
                    },
                    options: {
                        responsive: true,
                        maintainAspectRatio: false,
                        plugins: {
                            legend: {
                                position: 'bottom',
                                labels: {
                                    color: '#c9d1d9',
                                    padding: 15
                                }
                            },
                            // Title moved out of Chart.js to h3 element for cleaner structure
                        }
                    }
                });
            }

            // 2. Domain Proficiency (Radar Chart)
            const domainProficiencyCtx = document.getElementById('domainProficiencyChart');
            if(domainProficiencyCtx) {
                 new Chart(domainProficiencyCtx, {
                    type: 'radar',
                    data: {
                        labels: ['Web App Pentesting', 'Network Security', 'Incident Response', 'GRC/Compliance', 'Python Scripting', 'Cloud Security'],
                        datasets: [{
                            label: 'Proficiency Score',
                            data: [85, 70, 75, 65, 80, 60],
                            fill: true,
                            backgroundColor: 'rgba(88, 166, 255, 0.2)', // Light blue fill
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
                        },
                        scales: {
                            r: {
                                angleLines: { color: '#30363d' },
                                grid: { color: '#30363d' },
                                pointLabels: { color: '#c9d1d9', font: {size: 10}},
                                ticks: {
                                    color: '#c9d1d9',
                                    backdropColor: '#161b22',
                                    stepSize: 20,
                                    // Ensure ticks stop at 100
                                    max: 100,
                                    beginAtZero: true
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
