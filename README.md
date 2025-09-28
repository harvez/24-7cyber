# 24-7cyber
first web site build 
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Cybersecurity 101</title>
  <style>
  body {
    background-color: #0d0d0d;
    color: #00ff41;
    font-family: 'Courier New', Courier, monospace;
  }
  .card, .btn, .chip {
    background-color: #1a1a1a !important;
    border: 1px solid #00ff41 !important;
    color: #00ff41 !important;
  }
  .btn.primary {
    background-color: #00ff41 !important;
    color: #0d0d0d !important;
  }
  h2, h3, h4, strong {
    color: #00ff41;
    text-shadow: 0 0 5px rgba(0,255,65,0.5);
  }
  .muted { color: #00b32d !important; }

  /* Mini Terminal Styles */
  .terminal {
    background-color: #0a0a0a;
    border: 1px solid #00ff41;
    border-radius: 5px;
    padding: 10px;
    font-family: 'Courier New', Courier, monospace;
    font-size: 0.9em;
    box-shadow: 0 0 15px rgba(0,255,65,0.15);
  }
  .terminal-header {
    background-color: #1a1a1a;
    padding: 5px;
    margin: -10px -10px 10px -10px;
    border-bottom: 1px solid #00ff41;
    color: #00b32d;
    text-align: center;
  }
  .terminal-body {
    white-space: pre-wrap;
    word-break: break-all;
  }
  .terminal-cursor {
    display: inline-block;
    background-color: #00ff41;
    width: 10px;
    height: 1.2em;
    animation: blink 1s step-end infinite;
  }
  @keyframes blink { from, to { background-color: transparent } 50% { background-color: #00ff41; } }

  /* Live Attack Map Styles */
  .attack-map-container {
    position: fixed;
    top: 1rem;
    right: 1rem;
    width: 250px;
    height: 180px;
    background-color: #0a0a0a;
    border: 1px solid #00ff41;
    border-radius: 5px;
    box-shadow: 0 0 15px rgba(0,255,65,0.15);
    z-index: 1000;
    overflow: hidden;
  }
  .attack-map-header {
    background-color: #1a1a1a;
    padding: 3px 5px;
    border-bottom: 1px solid #00ff41;
    color: #00b32d;
    text-align: center;
    font-size: 0.8em;
  }
  #attack-map {
    position: relative;
    width: 100%;
    height: calc(100% - 25px);
  }
  .attack-dot {
    position: absolute;
    left: 0; /* Set initial horizontal position in CSS */
    width: 4px;
    height: 4px;
    background-color: #ff4141;
    border-radius: 50%;
    opacity: 1;
    box-shadow: 0 0 8px #ff4141;
    transition: transform 1.5s ease-out, opacity 1.5s ease-out;
  }
  /* @keyframes fadeOut { to { opacity: 0; } } // No longer needed */

  </style>
</head>
<body>

<header>
  <h1>Cybersecurity 101</h1>
  <div class="top-actions" role="toolbar" aria-label="Actions">
    <a href="threats.html" class="btn">Threats</a>
    <a href="best-practices.html" class="btn">Best Practices</a>
    <a href="tools.html" class="btn">Tools</a>
  </div>
</header>

<main>
  <div class="card section" aria-labelledby="terminal-emu" style="margin-top:0;">
    <div class="terminal">
      <div class="terminal-header">/dev/console</div>
      <div class="terminal-body">
        <span id="terminal-text"></span><span class="terminal-cursor"></span>
      </div>
    </div>
  </div>

  <!-- Live Attack Map -->
  <div class="attack-map-container" aria-hidden="true">
    <div class="attack-map-header">LIVE CYBER ATTACKS</div>
    <div id="attack-map"></div>
  </div>


  <section aria-labelledby="start">
    <div class="card hero" id="start">
      <div style="flex:1">
        <h2>Welcome to Cybersecurity 101</h2>
        <p>Learn the essentials: common threats, protective measures, useful tools, hands-on tutorials, and trusted resources — all on one page.</p>
        <nav class="topnav" aria-label="Quick topics">
          <a href="#threats" class="chip" style="text-decoration: none;">Threats</a>
          <a href="#best" class="chip" style="text-decoration: none;">Best Practices</a>
          <a href="#tools" class="chip" style="text-decoration: none;">Tools</a>
          <a href="#tutorials" class="chip" style="text-decoration: none;">Tutorials</a>
          <div class="chip">Quiz</div>
        </nav>
      </div>
      <div style="width:220px;text-align:right">
        <img src="data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='160' height='120' viewBox='0 0 24 24'><path fill='%2300ff41' d='M12 1L3 5v6c0 5.55 3.84 10.74 9 12c5.16-1.26 9-6.45 9-12V5l-9-4zm0 10.99h7c-.53 4.12-3.28 7.79-7 8.94V12H5V6.3l7-3.11v8.8z'/></svg>"
             alt="Cybersecurity Shield" style="border-radius:10px;box-shadow:0 6px 18px rgba(0,255,65,0.1)" />
        <p class="small" style="margin-top:8px">Start with basics, practice often.</p>
      </div>
    </div>

    <div class="card section" aria-labelledby="what-is">
      <h3 id="what-is">What is cybersecurity?</h3>
      <p class="muted">Cybersecurity is protection of systems, networks, and data from digital attacks. It spans prevention, detection, response, and recovery. Here are the pillars and a quick primer.</p>

      <div class="grid-2" style="margin-top:12px">
        <div>
          <h4 style="margin:0 0 6px 0">Core goals</h4>
          <ul class="small">
            <li>Confidentiality — keep data private</li>
            <li>Integrity — ensure data is accurate and unaltered</li>
            <li>Availability — systems and data are accessible when needed</li>
            <li>Authentication & Authorization — verify identity and permissions</li>
          </ul>
        </div>
        <div>
          <h4 style="margin:0 0 6px 0">Who needs it?</h4>
          <p class="small">Everyone: individuals protecting personal accounts, organizations defending assets, and developers building secure software.</p>
        </div>
      </div>
    </div>

    <div class="card section" aria-labelledby="threats">
      <h3 id="threats">Common threats</h3>
      <p class="muted">A closer look at the tactics used by attackers.</p>
      <div class="card" style="margin-top:1rem; border-color: #00b32d;">
        <h4>Phishing</h4>
        <p class="small">Phishing attacks use deceptive emails, messages, or websites to trick individuals into revealing sensitive information like passwords, credit card numbers, or personal data. They often create a sense of urgency or fear.</p>
        <ul class="small"><li><strong>Spear Phishing:</strong> A targeted attack on a specific person or organization.</li><li><strong>Whaling:</strong> Spear phishing aimed at high-profile executives.</li><li><strong>Smishing/Vishing:</strong> Phishing conducted via SMS text messages or voice calls.</li></ul>
      </div>
      <div class="card" style="margin-top:1rem; border-color: #00b32d;">
        <h4>Malware (Malicious Software)</h4>
        <p class="small">Malware is any software intentionally designed to cause damage to a computer, server, client, or computer network. It's a broad category that includes many different types of threats.</p>
        <ul class="small"><li><strong>Ransomware:</strong> Encrypts a victim's files and demands a ransom payment for the decryption key.</li><li><strong>Trojans:</strong> Disguise themselves as legitimate software to trick users into installing them, creating a backdoor for attackers.</li><li><strong>Spyware:</strong> Secretly gathers information about a person or organization and sends it to another entity.</li><li><strong>Adware:</strong> Automatically delivers advertisements, often in a manner that is unexpected and intrusive.</li></ul>
      </div>
      <div class="card" style="margin-top:1rem; border-color: #00b32d;">
        <h4>Account Takeover (ATO)</h4>
        <p class="small">This occurs when an attacker gains unauthorized access to a user's account. This is often achieved through automated attacks that exploit poor password hygiene.</p>
        <ul class="small"><li><strong>Credential Stuffing:</strong> Using lists of leaked usernames and passwords from one data breach to try and log in to other services.</li><li><strong>Password Spraying:</strong> Trying a single, common password (like "Password123!") against many different accounts.</li></ul>
      </div>
      <div class="card" style="margin-top:1rem; border-color: #00b32d;">
        <h4>Software Vulnerabilities</h4>
        <p class="small">Flaws, bugs, or weaknesses in software code or system configurations that can be exploited by an attacker to perform unauthorized actions.</p>
        <ul class="small"><li><strong>Unpatched Systems:</strong> Failing to apply security patches leaves systems open to known, publicly documented vulnerabilities.</li><li><strong>Zero-Day Exploit:</strong> An attack that targets a previously unknown vulnerability, meaning there is no patch available for it yet.</li><li><strong>Misconfigurations:</strong> Incorrectly configured security settings, such as leaving a database open to the internet without a password.</li></ul>
      </div>
    </div>

    <div class="card section" aria-labelledby="best">
      <h3 id="best">Best practices — practical steps</h3>
      <p class="muted">Practical steps to secure your digital life.</p>
      <div class="card" style="margin-top:1rem; border-color: #00b32d;">
        <h4>Account Security</h4>
        <p class="small">Your accounts are the keys to your digital kingdom. Protecting them is the single most important step you can take.</p>
        <ul class="small"><li><strong>Use a Password Manager:</strong> Humans are bad at creating and remembering strong, unique passwords for every site. A password manager solves this by generating and storing them for you. This is the #1 defense against credential stuffing.</li><li><strong>Enable Multi-Factor Authentication (MFA):</strong> MFA adds a crucial second layer of security. Even if an attacker steals your password, they can't log in without your second factor (e.g., a code from your phone app, a text message, or a physical security key).</li><li><strong>Review Recovery Options:</strong> Ensure your account recovery email and phone number are up-to-date and secure. If an attacker compromises your email, they can use it to reset passwords for your other accounts.</li></ul>
      </div>
      <div class="card" style="margin-top:1rem; border-color: #00b32d;">
        <h4>Device & Network Security</h4>
        <p class="small">The devices you use and the networks you connect to are potential entry points for attackers.</p>
        <ul class="small"><li><strong>Keep Software Updated:</strong> This is non-negotiable. Software updates contain critical security patches that fix vulnerabilities discovered by researchers. Running outdated software is like leaving your front door unlocked. Enable automatic updates whenever possible.</li><li><strong>Use Reputable Endpoint Protection:</strong> Modern antivirus/anti-malware software does more than just scan for viruses. It provides real-time protection against ransomware, malicious websites, and other threats.</li><li><strong>Be Wary of Public Wi-Fi:</strong> Unsecured public Wi-Fi networks are a hunting ground for attackers who can perform Man-in-the-Middle (MitM) attacks. Avoid logging into sensitive accounts (banking, email) on public Wi-Fi. If you must, use a trusted VPN.</li></ul>
      </div>
      <div class="card" style="margin-top:1rem; border-color: #00b32d;">
        <h4>Data Hygiene & Awareness</h4>
        <p class="small">Treat your personal data like cash. Be mindful of where it is, who has it, and how it's protected.</p>
        <ul class="small"><li><strong>Back Up Your Data:</strong> Ransomware can destroy your files in an instant. Regular backups are your safety net. Follow the 3-2-1 rule: <strong>3</strong> copies of your data, on <strong>2</strong> different media types, with <strong>1</strong> copy off-site (e.g., in the cloud or a physical drive at another location).</li><li><strong>Use Encryption:</strong> Encrypt the hard drive on your computer (e.g., BitLocker for Windows, FileVault for macOS) and your smartphone. This ensures that if your device is stolen, the data on it is unreadable.</li><li><strong>Recognize Phishing:</strong> Learn to spot the signs of a phishing attempt: a sense of urgency, poor grammar, suspicious links (hover before you click!), and requests for personal information. When in doubt, don't click.</li></ul>
      </div>
    </div>

    <div class="card section" aria-labelledby="tools">
      <h3 id="tools">Useful tools & categories</h3>
      <p class="muted">A look at software and services for defense and analysis.</p>
      <div class="card" style="margin-top:1rem; border-color: #00b32d;">
        <h4>Tools for Individuals</h4>
        <p class="small">Essential software for personal security.</p>
        <ul class="small"><li><strong>Password Managers:</strong> The cornerstone of account security. They generate, store, and fill strong, unique passwords.<ul><li>Examples: Bitwarden (open-source, excellent free tier), 1Password (great family features), KeePass (offline, open-source).</li></ul></li><li><strong>Authenticator Apps (MFA):</strong> Used for generating time-based one-time passcodes (TOTP) for multi-factor authentication.<ul><li>Examples: Authy, Google Authenticator, Microsoft Authenticator. For higher security, consider hardware keys like YubiKey.</li></ul></li><li><strong>Virtual Private Networks (VPNs):</strong> Encrypt your internet traffic, protecting you on public Wi-Fi and enhancing privacy.<ul><li>Look for providers with no-log policies that have undergone third-party audits.</li></ul></li></ul>
      </div>
      <div class="card" style="margin-top:1rem; border-color: #00b32d;">
        <h4>Tools for Professionals</h4>
        <p class="small">Software used by security analysts, engineers, and penetration testers.</p>
        <ul class="small"><li><strong>Vulnerability Scanners:</strong> Scan networks and applications for known security weaknesses.<ul><li>Examples: Nmap (network mapping), OpenVAS (full-featured scanner), Nessus (popular commercial scanner).</li></ul></li><li><strong>Endpoint & SIEM:</strong> Tools for monitoring and responding to threats on devices (endpoints) and aggregating logs (SIEM).<ul><li>Examples: OSQuery (endpoint visibility), Wazuh (open-source SIEM/XDR), Splunk (enterprise SIEM leader).</li></ul></li><li><strong>Dynamic & Static Analysis (DAST/SAST):</strong> Tools for finding vulnerabilities in code, either while it's running (DAST) or by analyzing the source (SAST).<ul><li>Examples: OWASP ZAP (DAST), SonarQube (SAST), Snyk (developer-focused security).</li></ul></li></ul>
      </div>
      <div class="card" style="margin-top:1rem; border-color: #00b32d;">
        <h4>Open Source & Community Projects</h4>
        <p class="small">Valuable resources developed and maintained by the security community.</p>
        <ul class="small"><li><strong>DevOps Bash Tools:</strong> A collection of useful Bash scripts and tools for DevOps, sysadmins, and developers. A great resource for automation and system management tasks.<ul><li><a href="https://github.com/harvez/DevOps-Bash-tools" target="_blank" rel="noopener noreferrer" style="color: #00ff41;">View on GitHub</a></li></ul></li><li><strong>OWASP (Open Web Application Security Project):</strong> An organization providing free articles, methodologies, documentation, tools, and technologies in the field of web application security. Their "Top 10" list is an industry standard.</li></ul>
      </div>
    </div>

    <div class="card section" aria-labelledby="tutorials">
      <h3 id="tutorials">Hands-on tutorials & learning path</h3>
      <ol class="small">
        <li>Start with fundamentals: networking basics (TCP/IP, DNS), OS concepts.</li>
        <li>Learn about common attacks: practice identifying phishing and suspicious behavior.</li>
        <li>Practice in safe environments: use virtual labs (VMs) for hands-on learning.</li>
        <li>Build projects: create a simple port scanner or a password checker.</li>
      </ol>
    </div>

<script>
document.addEventListener('DOMContentLoaded', function() {
  const terminalTextElement = document.getElementById('terminal-text');
  if (terminalTextElement) {
    const lines = [
      '> Running security audit...',
      '> Checking for open ports... [OK]',
      '> Analyzing firewall rules... [OK]',
      '> Scanning for known vulnerabilities... [DETECTED]',
      '> Threat Level: HIGH. Action required.'
    ];
    const textToType = lines.join('\n');
    let i = 0;
    function typeWriter() {
      if (i < textToType.length) {
        terminalTextElement.innerHTML += textToType.charAt(i);
        i++;
        setTimeout(typeWriter, Math.random() * 50 + 20);
      }
    }
    typeWriter();
  }

  // Live attack map simulation
  const attackMap = document.getElementById('attack-map');
  if (attackMap) {
    setInterval(() => {
      const dot = document.createElement('div');
      dot.className = 'attack-dot';

      const mapWidth = attackMap.clientWidth;
      const mapHeight = attackMap.clientHeight;

      // Start on the left edge at a random vertical position
      const startTop = Math.random() * mapHeight;
      dot.style.top = `${startTop}px`;

      attackMap.appendChild(dot);

      // After appending, set the destination to trigger the transition
      const endX = Math.random() * mapWidth;
      const endTop = Math.random() * mapHeight;

      // Use a small timeout to ensure the browser renders the dot before the transition starts
      setTimeout(() => {
        dot.style.opacity = '0';
        // Translate from its starting position (left: 0) to the destination
        dot.style.transform = `translate(${endX}px, ${endTop - startTop}px)`;
      }, 10);

      setTimeout(() => {
        dot.remove();
      }, 1500); // Remove dot after animation
    }, 500); // Create a new attack every 500ms
  }
});
</script>
</body>
</html>
