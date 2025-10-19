<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Pen-Test Report — Brady Reid</title>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&display=swap" rel="stylesheet">
  <style>
    :root{
      --bg:#0b1220; --panel:#0f1a2b; --muted:#9fb0c8; --accent:#00a3ff; --glass: rgba(255,255,255,0.03);
      --text:#e6eef6; --success:#3ddc84; --danger:#ff6b6b;
    }
    *{box-sizing:border-box}
    body{margin:0;font-family:Inter,system-ui,-apple-system,"Segoe UI",Roboto,Arial;background:linear-gradient(180deg,#051021 0%,var(--bg) 100%);color:var(--text);-webkit-font-smoothing:antialiased;padding:28px}
    .wrap{max-width:1100px;margin:0 auto}
    .banner{width:100%;height:220px;border-radius:10px;overflow:hidden;box-shadow:0 10px 30px rgba(0,0,0,0.6)}
    .banner img{width:100%;height:100%;object-fit:cover;display:block}
    header{display:flex;gap:18px;align-items:center;margin-top:18px}
    .avatar{width:84px;height:84px;border-radius:10px;background:linear-gradient(180deg,#081023,#0f1a2b);display:flex;align-items:center;justify-content:center;font-weight:700;font-size:28px;color:var(--accent);box-shadow:0 6px 18px rgba(0,0,0,0.5)}
    h1{margin:0;font-size:26px}
    .subtitle{color:var(--muted);margin-top:6px;font-size:14px}
    .meta{color:var(--muted);font-size:13px;margin-top:6px}
    .grid{display:grid;grid-template-columns:1fr 320px;gap:20px;margin-top:20px}
    .card{background:linear-gradient(180deg,var(--panel), rgba(255,255,255,0.02));padding:18px;border-radius:10px;box-shadow:0 8px 30px rgba(2,6,23,0.6)}
    .card h2{margin:0 0 10px 0;font-size:18px}
    p{color:var(--muted);line-height:1.5;margin:0 0 12px 0}
    table{width:100%;border-collapse:collapse;margin-top:10px}
    th,td{padding:8px 6px;border-bottom:1px dashed rgba(255,255,255,0.03);text-align:left;color:var(--muted);font-size:14px}
    th{color:var(--text);font-weight:600}
    .badges{display:flex;flex-wrap:wrap;gap:8px}
    .badge{background:var(--glass);padding:6px 10px;border-radius:999px;font-size:13px;color:var(--text);border:1px solid rgba(255,255,255,0.02)}
    .section{margin-top:16px}
    .muted{color:var(--muted)}
    .kbox{background:#071529;padding:12px;border-radius:8px;color:#cfeeff;font-family:ui-monospace,SFMono-Regular,Menlo,Monaco, "Roboto Mono",monospace;font-size:13px}
    .warn{display:inline-block;background:linear-gradient(90deg,var(--danger),#ff9f9f);color:white;padding:6px 8px;border-radius:8px;font-weight:600;font-size:13px;margin-bottom:10px}
    .screens{display:grid;grid-template-columns:repeat(2,1fr);gap:10px;margin-top:12px}
    .screens img{width:100%;height:170px;object-fit:cover;border-radius:8px;border:1px solid rgba(255,255,255,0.03)}
    .right .panel-item{margin-bottom:12px}
    .small{font-size:13px;color:var(--muted)}
    .cta{display:flex;gap:8px;flex-wrap:wrap;margin-top:12px}
    .btn{background:transparent;border:1px solid rgba(255,255,255,0.06);padding:8px 10px;border-radius:8px;color:var(--text);text-decoration:none;font-size:13px}
    footer{margin-top:20px;color:var(--muted);font-size:13px;text-align:center}
    @media (max-width:980px){
      .grid{grid-template-columns:1fr}
      .screens{grid-template-columns:1fr}
      header{flex-direction:row}
    }
  </style>
</head>
<body>
  <div class="wrap">
    <!-- banner: replace src with your uploaded banner raw link -->
    <div class="banner">
      <img src="https://github.com/Brady0Reid/Banner.jpg/raw/main/Banner.jpg" alt="Banner">
    </div>

    <header>
      <div class="avatar">BR</div>
      <div>
        <h1>Pen-Test Report — ITT-340</h1>
        <div class="subtitle">Educational penetration testing engagement — sandbox environment</div>
        <div class="meta">Author: <strong>Brady Reid</strong> · Updated: <strong>Nov 3, 2024 (v2.0)</strong></div>
      </div>
    </header>

    <div class="grid">
      <!-- main content -->
      <main class="card">
        <h2>Description</h2>
        <p class="muted">This project demonstrates a penetration testing engagement performed within a controlled laboratory. It covers the full testing lifecycle: passive OSINT, automated reconnaissance, network scanning (Nmap), vulnerability assessment (OpenVAS), exploitation demonstrations (Metasploit, lab-only), and payload testing in an isolated sandbox.</p>

        <div class="section">
          <h2>Disclaimer</h2>
          <p class="warn">LAB ONLY — All actions were performed in isolated virtual machines under explicit educational permission. This report is for learning, documentation, and remediation planning. Do NOT apply techniques from this report to systems you do not own or have permission to test.</p>
        </div>

        <div class="section">
          <h2>Environments</h2>
          <ul class="muted">
            <li><strong>Attacker:</strong> Kali Linux (VM)</li>
            <li><strong>Targets:</strong> Ubuntu server (lab), Windows XP / Server 2003 (lab), optional Windows 10 (documentation)</li>
            <li><strong>Network:</strong> Isolated host-only VM network (no internet-facing actions)</li>
          </ul>
        </div>

        <div class="section">
          <h2>Languages & Utilities</h2>
          <div class="badges">
            <span class="badge">Kali Linux</span>
            <span class="badge">Nmap</span>
            <span class="badge">OpenVAS</span>
            <span class="badge">Metasploit</span>
            <span class="badge">MSFVenom (lab-only)</span>
            <span class="badge">SpiderFoot</span>
            <span class="badge">DNSenum</span>
            <span class="badge">Metagoofil</span>
            <span class="badge">Wireshark</span>
          </div>
        </div>

        <div class="section">
          <h2>Executive Summary</h2>
          <p class="muted">A controlled assessment found several textbook vulnerabilities attributable to outdated services, weak encryption, and misconfiguration. Demonstrated exploits confirmed potential for privilege escalation and data access in the lab. Recommended mitigations: timely patching, removing/segregating EOL systems, hardening SSH/TLS configuration, and implementing least-privilege access controls.</p>
        </div>

        <div class="section">
          <h2>Version Log</h2>
          <table>
            <thead>
              <tr><th>Version</th><th>Date</th><th>Author</th><th>Summary</th></tr>
            </thead>
            <tbody>
              <tr><td>1.0</td><td>10/04/2024</td><td>Brady Reid</td><td>Initial OSINT & Recon</td></tr>
              <tr><td>1.2</td><td>10/05/2024</td><td>Brady Reid</td><td>Added automated recon modules</td></tr>
              <tr><td>1.3</td><td>10/12/2024</td><td>Brady Reid</td><td>Nmap scanning results</td></tr>
              <tr><td>1.4</td><td>10/20/2024</td><td>Brady Reid</td><td>OpenVAS vulnerability reports</td></tr>
              <tr><td>1.5</td><td>10/29/2024</td><td>Brady Reid</td><td>Metasploit exploitation demos</td></tr>
              <tr><td>2.0</td><td>11/03/2024</td><td>Brady Reid</td><td>Custom payload summary (redacted)</td></tr>
            </tbody>
          </table>
        </div>

        <div class="section">
          <h2>Findings & Recommendations</h2>

          <h3 class="small">1) Passive OSINT</h3>
          <p class="muted">Publicly available metadata and subdomains were discovered. <strong>Recommendation:</strong> audit public documents, apply DMARC/DKIM, and limit exposed metadata.</p>

          <h3 class="small">2) Automated Recon</h3>
          <p class="muted">Aggregated domain and username data from public sources. <strong>Recommendation:</strong> remove legacy pages and enforce a data-retention policy for public artifacts.</p>

          <h3 class="small">3) Network Scanning (Nmap)</h3>
          <p class="muted">Open ports and outdated service versions were discovered on lab hosts. <strong>Recommendation:</strong> patch/upgrade services, restrict management ports with firewall rules and VPN-only access.</p>

          <h3 class="small">4) Vulnerability Assessment (OpenVAS)</h3>
          <p class="muted">Weak ciphers, EOL OS, and cleartext services were flagged. <strong>Recommendation:</strong> enforce modern TLS, disable obsolete protocols, and replace EOL systems.</p>

          <h3 class="small">5) Exploitation (Lab-only)</h3>
          <p class="muted">Exploits were executed in a sandbox to validate impact. Command-level details and payload generation are intentionally omitted here — they exist in the secure lab log. <strong>Recommendation:</strong> implement endpoint monitoring, EDR, and re-scan after remediation.</p>
        </div>

        <div class="section">
          <h2>Sanitized Lab Notes (high-level)</h2>
          <ul class="muted">
            <li>Initial compromise via vulnerable webapp module (lab-only demonstration).</li>
            <li>Privilege escalation confirmed on legacy Windows VM using known vulnerability (documented in secure lab notes).</li>
            <li>Samba misconfiguration allowed access to shared data on one host (mitigate by ACLs and SMB security policies).</li>
            <li>Persistence techniques were tested and blocked by the sandbox environment — ensure endpoint hardening to detect similar attempts.</li>
          </ul>
        </div>

        <div class="section">
          <h2>Evidence (replace with your screenshots)</h2>
          <div class="screens">
            <img src="screenshot-1.png" alt="OSINT screenshot (replace)">
            <img src="screenshot-2.png" alt="Nmap results (replace)">
            <img src="screenshot-3.png" alt="OpenVAS report (replace)">
            <img src="screenshot-4.png" alt="Metasploit session (replace)">
          </div>
          <p class="small">Tip: upload screenshots into the repository and use exact filenames above or adjust paths accordingly.</p>
        </div>

        <div class="section">
          <h2>Conclusion & Next Steps</h2>
          <p class="muted">The lab engagement highlighted classic weaknesses: outdated software, misconfigurations, and insufficient encryption. Prioritize remediations with a phased plan: (1) patch & replace EOL systems, (2) harden network perimeter & access controls, (3) enable centralized logging and detection, (4) re-assess with follow-up scans and a penetration test validation.</p>
        </div>
      </main>

      <!-- right column -->
      <aside class="card right">
        <div class="panel-item">
          <h3>Quick Links</h3>
          <div class="cta">
            <a class="btn" href="https://github.com/Brady0Reid/Pen-Test-Report" target="_blank">Repository</a>
            <a class="btn" href="mailto:bradycreid@protonmail.com">Contact</a>
            <a class="btn" href="https://www.linkedin.com/in/brady-reidin" target="_blank">LinkedIn</a>
          </div>
        </div>

        <div class="panel-item">
          <h3>Project Facts</h3>
          <table>
            <tr><th>Scope</th><td>Lab VMs only</td></tr>
            <tr><th>Duration</th><td>Oct 2024 — Nov 2024</td></tr>
            <tr><th>Author</th><td>Brady Reid</td></tr>
            <tr><th>Report</th><td>v2.0</td></tr>
          </table>
        </div>

        <div class="panel-item">
          <h3>Recommendations (at-a-glance)</h3>
          <ul class="muted">
            <li>Patch & upgrade EOL systems</li>
            <li>Harden TLS/SSH configs</li>
            <li>Restrict remote access</li>
            <li>Endpoint detection & monitoring</li>
            <li>Re-scan & validate</li>
          </ul>
        </div>

        <div class="panel-item">
          <h3>Notes</h3>
          <p class="small">Sensitive technical details and exploit commands are kept in a secure, instructor-approved lab notebook. Only sanitized evidence is published here for portfolio and educational purposes.</p>
        </div>
      </aside>
    </div>

    <footer>
      <div class="small">© Brady Reid — Penetration testing performed in an isolated lab environment for educational purposes only.</div>
    </footer>
  </div>
</body>
</html>
