<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>GitHub README Preview — Jackson Tuyikunde</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }

    body {
      font-family: -apple-system, BlinkMacSystemFont, 'Inter', 'Segoe UI', Helvetica, Arial, sans-serif;
      background: #0d1117;
      color: #e6edf3;
      line-height: 1.6;
      -webkit-font-smoothing: antialiased;
    }

    /* GitHub header bar */
    .gh-header {
      background: #161b22;
      border-bottom: 1px solid #30363d;
      padding: 16px 32px;
      display: flex;
      align-items: center;
      gap: 12px;
      position: sticky;
      top: 0;
      z-index: 100;
    }
    .gh-header svg { color: #e6edf3; }
    .gh-header .repo-name {
      color: #e6edf3;
      font-size: 20px;
      font-weight: 600;
    }
    .gh-header .repo-label {
      color: #8b949e;
      font-size: 14px;
      border: 1px solid #30363d;
      border-radius: 6px;
      padding: 2px 8px;
      font-weight: 500;
    }
    .gh-header .badge-public {
      border: 1px solid #30363d;
      border-radius: 999px;
      padding: 2px 10px;
      font-size: 12px;
      color: #8b949e;
      font-weight: 500;
    }

    /* Tabs */
    .gh-tabs {
      background: #0d1117;
      border-bottom: 1px solid #30363d;
      padding: 0 32px;
      display: flex;
      gap: 0;
      overflow-x: auto;
    }
    .gh-tab {
      padding: 10px 16px;
      font-size: 14px;
      color: #e6edf3;
      text-decoration: none;
      border-bottom: 2px solid #f78166;
      font-weight: 600;
      display: flex;
      align-items: center;
      gap: 6px;
      white-space: nowrap;
    }
    .gh-tab-inactive {
      color: #8b949e;
      border-bottom: 2px solid transparent;
      font-weight: 400;
    }
    .gh-tab:hover { color: #e6edf3; }
    .gh-tab-count {
      background: #30363d;
      border-radius: 999px;
      padding: 0 7px;
      font-size: 12px;
      font-weight: 500;
      min-width: 20px;
      text-align: center;
    }

    /* Main content area */
    .gh-main {
      max-width: 1012px;
      margin: 0 auto;
      padding: 32px;
    }

    /* GitHub markdown styles */
    .markdown-body {
      background: #0d1117;
      color: #e6edf3;
      font-size: 16px;
      line-height: 1.6;
    }
    .markdown-body h1 {
      font-size: 2em;
      font-weight: 600;
      padding-bottom: 0.3em;
      border-bottom: 1px solid #30363d;
      margin: 24px 0 16px;
      text-align: center;
    }
    .markdown-body h1:first-child {
      margin-top: 0;
      border-bottom: none;
      padding-bottom: 0;
      font-size: 2.25em;
    }
    .markdown-body h2 {
      font-size: 1.5em;
      font-weight: 600;
      padding-bottom: 0.3em;
      border-bottom: 1px solid #30363d;
      margin: 32px 0 16px;
    }
    .markdown-body h3 {
      font-size: 1.25em;
      font-weight: 600;
      margin: 24px 0 16px;
      text-align: center;
      font-weight: 400;
      color: #8b949e;
    }
    .markdown-body h3 strong { color: #e6edf3; }
    .markdown-body h4 {
      font-size: 1em;
      font-weight: 600;
      margin: 24px 0 8px;
    }
    .markdown-body p {
      margin: 0 0 16px;
      text-align: center;
      color: #8b949e;
    }
    .markdown-body a {
      color: #58a6ff;
      text-decoration: none;
    }
    .markdown-body a:hover { text-decoration: underline; }
    .markdown-body img {
      max-width: 100%;
      height: auto;
      box-sizing: content-box;
    }
    .markdown-body ul {
      list-style: none;
      padding-left: 0;
      margin: 0 0 16px;
    }
    .markdown-body ul li {
      padding: 4px 0;
      position: relative;
      padding-left: 24px;
    }
    .markdown-body ul li::before {
      content: '•';
      position: absolute;
      left: 8px;
      color: #8b949e;
    }
    .markdown-body code {
      background: rgba(110, 118, 129, 0.2);
      border-radius: 6px;
      padding: 0.2em 0.4em;
      font-size: 85%;
      font-family: 'JetBrains Mono', 'SFMono-Regular', Consolas, monospace;
    }
    .markdown-body pre {
      background: #161b22;
      border: 1px solid #30363d;
      border-radius: 12px;
      padding: 16px;
      overflow-x: auto;
      margin: 0 0 16px;
    }
    .markdown-body pre code {
      background: none;
      padding: 0;
      font-size: 14px;
      line-height: 1.5;
    }
    .markdown-body blockquote {
      border-left: 4px solid #3b82f6;
      padding: 0 16px;
      margin: 0 0 16px;
      color: #8b949e;
    }
    .markdown-body hr {
      border: none;
      border-top: 1px solid #30363d;
      margin: 32px 0;
      height: 0;
    }
    .markdown-body table {
      border-collapse: collapse;
      width: 100%;
      margin: 0 0 16px;
      display: block;
      overflow-x: auto;
    }
    .markdown-body th, .markdown-body td {
      border: 1px solid #30363d;
      padding: 12px 16px;
      text-align: left;
    }
    .markdown-body th {
      background: #161b22;
      font-weight: 600;
    }
    .markdown-body tr:nth-child(even) { background: rgba(110, 118, 129, 0.04); }

    .markdown-body [align="center"] { text-align: center; }
    .markdown-body [align="left"] { text-align: left; }

    /* Status badge row */
    .status-row {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
      flex-wrap: wrap;
      margin-bottom: 16px;
    }

    /* Preview label */
    .preview-label {
      position: fixed;
      bottom: 20px;
      right: 20px;
      background: #238636;
      color: white;
      padding: 8px 16px;
      border-radius: 8px;
      font-size: 13px;
      font-weight: 600;
      z-index: 200;
      box-shadow: 0 4px 12px rgba(0,0,0,0.4);
      display: flex;
      align-items: center;
      gap: 6px;
    }

    /* Responsive */
    @media (max-width: 768px) {
      .gh-main { padding: 16px; }
      .gh-header { padding: 12px 16px; }
      .gh-tabs { padding: 0 16px; }
      .markdown-body h1:first-child { font-size: 1.75em; }
      .markdown-body h2 { font-size: 1.25em; }
    }
  </style>
</head>
<body>

  <!-- GitHub Header -->
  <div class="gh-header">
    <svg height="32" viewBox="0 0 16 16" width="32"><path d="M8 0c4.42 0 8 3.58 8 8a8.013 8.013 0 0 1-5.45 7.59c-.4.08-.55-.17-.55-.38 0-.27.01-1.13.01-2.2 0-.75-.25-1.23-.54-1.48 1.78-.2 3.65-.88 3.65-3.95 0-.88-.31-1.59-.82-2.15.08-.2.36-1.02-.08-2.12 0 0-.67-.22-2.2.82-.64-.18-1.32-.27-2-.27-.68 0-1.36.09-2 .27-1.53-1.03-2.2-.82-2.2-.82-.44 1.1-.16 1.92-.08 2.12-.51.56-.82 1.28-.82 2.15 0 3.06 1.86 3.75 3.64 3.95-.23.2-.44.55-.51 1.07-.46.21-1.61.55-2.33-.66-.15-.24-.6-.83-1.23-.82-.67.01-.27.38.01.53.34.19.73.9.82 1.13.16.45.68 1.31 2.69.94 0 .67.01 1.3.01 1.49 0 .21-.15.45-.55.38A7.995 7.995 0 0 1 0 8c0-4.42 3.58-8 8-8Z" fill="currentColor"></path></svg>
    <span class="repo-name">Jackson-tj74</span>
    <span class="repo-label">/</span>
    <span class="repo-name">Jackson-tj74</span>
    <span class="badge-public">Public</span>
  </div>

  <!-- Tabs -->
  <div class="gh-tabs">
    <a class="gh-tab" href="#">
      <svg height="16" viewBox="0 0 16 16" width="16"><path d="M0 1.75A.75.75 0 0 1 .75 1h4.253c1.227 0 2.317.59 3 1.501A3.743 3.743 0 0 1 11.006 1h4.245a.75.75 0 0 1 .75.75v10.5a.75.75 0 0 1-.75.75h-4.507a2.25 2.25 0 0 0-1.591.659l-.622.621a.75.75 0 0 1-1.06 0l-.622-.621A2.25 2.25 0 0 0 5.258 13H.75a.75.75 0 0 1-.75-.75Zm7.251 10.324.004-9.823a2.247 2.247 0 0 0-1.494-2.118A2.25 2.25 0 0 0 5.003 2.5H1.5v9.375c0 .138.112.25.25.25h2.5a3.75 3.75 0 0 1 2.46.907l.041.042Zm1.5-9.823.004 9.823.041-.042a3.75 3.75 0 0 1 2.46-.907h2.5a.25.25 0 0 0 .25-.25V2.5h-3.504a2.25 2.25 0 0 0-2.25 2.25v.001Z" fill="currentColor"></path></svg>
      README.md
    </a>
    <a class="gh-tab gh-tab-inactive" href="#">
      <svg height="16" viewBox="0 0 16 16" width="16"><path d="M8 .25a.75.75 0 0 1 .673.418l1.882 3.815 4.21.612a.75.75 0 0 1 .416 1.279l-3.046 2.97.719 4.192a.751.751 0 0 1-1.088.791L8 12.347l-3.766 1.98a.75.75 0 0 1-1.088-.79l.72-4.194L.818 6.374a.75.75 0 0 1 .416-1.28l4.21-.611L7.327.668A.75.75 0 0 1 8 .25Z" fill="currentColor"></path></svg>
      Star
      <span class="gh-tab-count">0</span>
    </a>
  </div>

  <!-- README Content -->
  <div class="gh-main">
    <div class="markdown-body">

      <!-- HEADER -->
      <h1>Hi 👋, I'm Jackson Tuyikunde</h1>

      <h3>
        <strong>Full Stack Developer</strong> From Rwanda 🇷🇼
      </h3>

      <p>Building modern web apps with React, Node.js & MongoDB</p>

      <br/>

      <p>
        <img src="https://readme-typing-svg.herokuapp.com?font=Inter&weight=500&size=22&duration=3000&pause=1000&color=F5F5F5&center=true&vCenter=true&width=600&lines=Full+Stack+Developer;React+%7C+Node.js+%7C+MongoDB;UI%2FUX+Enthusiast;Always+Learning+New+Technologies" alt="Typing SVG" />
      </p>

      <div class="status-row">
        <img src="https://img.shields.io/badge/🟢_Open_to_Work-4ADE80?style=flat-square" alt="Open to Work" />
        <img src="https://img.shields.io/badge/📍_Rwanda-FF6B6B?style=flat-square" alt="Location" />
        <img src="https://img.shields.io/badge/🎓_Alight_Coding_School-58A6FF?style=flat-square" alt="Education" />
        <img src="https://komarev.com/ghpvc/?username=Jackson-tj74&color=58A6FF&style=flat-square&label=VIEWS" alt="Views" />
      </div>

      <p>
        <a href="https://github.com/Jackson-tj74"><img src="https://img.shields.io/badge/GitHub-Jackson--tj74-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" /></a>
        <a href="https://tjdevsphere.netlify.app"><img src="https://img.shields.io/badge/Portfolio-TJ_Dev_Sphere-4C1D95?style=for-the-badge&logo=vercel&logoColor=white" alt="Portfolio" /></a>
        <a href="mailto:tuyikundejackson74@gmail.com"><img src="https://img.shields.io/badge/Email-Me-DC2626?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" /></a>
      </p>

      <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=80&section=footer" width="100%" alt="wave"/>

      <hr/>

      <!-- ABOUT ME -->
      <h2>🚀 About Me</h2>

      <pre><code>Full Stack Developer based in Rwanda 🇷🇼
┌──────────────────────────────────────────────────────────────┐
│ 🔭 Currently building IngendoSmart (MERN stack)            │
│ 💻 React.js · TypeScript · Tailwind CSS · Node.js · MongoDB│
│ 🎨 UI/UX Design enthusiast (Figma)                         │
│ 🎓 Full-Stack Certified — Alight Coding School             │
│ 🗣️ Kinyarwanda (Native) · English (IELTS)                  │
│ ⚡ Exploring Next.js & Open Source                          │
└──────────────────────────────────────────────────────────────┘</code></pre>

      <hr/>

      <!-- TECH STACK -->
      <h2>🛠️ Tech Stack</h2>

      <h4>Frontend</h4>
      <p>
        <img src="https://skillicons.dev/icons?i=html,css,js,react,typescript,tailwind,nextjs" alt="Frontend" />
      </p>

      <h4>Backend & Database</h4>
      <p>
        <img src="https://skillicons.dev/icons?i=nodejs,express,mongodb" alt="Backend" />
      </p>

      <h4>Tools & Platforms</h4>
      <p>
        <img src="https://skillicons.dev/icons?i=git,github,figma,vscode,vercel,netlify" alt="Tools" />
      </p>

      <br/>

      <p>
        <img src="https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black" alt="React" />
        <img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript" />
        <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black" alt="JS" />
        <img src="https://img.shields.io/badge/Tailwind-06B6D4?style=flat-square&logo=tailwindcss&logoColor=black" alt="Tailwind" />
        <img src="https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=node.js&logoColor=white" alt="Node" />
        <img src="https://img.shields.io/badge/Express-000000?style=flat-square&logo=express&logoColor=white" alt="Express" />
        <img src="https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white" alt="MongoDB" />
        <img src="https://img.shields.io/badge/Figma-F24E1E?style=flat-square&logo=figma&logoColor=white" alt="Figma" />
        <img src="https://img.shields.io/badge/React_Native-61DAFB?style=flat-square&logo=react&logoColor=black" alt="RN" />
        <img src="https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white" alt="Git" />
        <img src="https://img.shields.io/badge/VS_Code-007ACC?style=flat-square&logo=visualstudiocode&logoColor=white" alt="VS Code" />
        <img src="https://img.shields.io/badge/Vercel-000000?style=flat-square&logo=vercel&logoColor=white" alt="Vercel" />
        <img src="https://img.shields.io/badge/Netlify-00C7B7?style=flat-square&logo=netlify&logoColor=white" alt="Netlify" />
      </p>

      <hr/>

      <!-- GITHUB STATS -->
      <h2>📊 GitHub Stats</h2>

      <p>
        <img height="170" src="https://github-readme-stats.vercel.app/api?username=Jackson-tj74&show_icons=true&theme=tokyonight&hide_border=true" alt="Stats" />
        &nbsp;&nbsp;
        <img height="170" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Jackson-tj74&layout=compact&theme=tokyonight&hide_border=true" alt="Langs" />
      </p>

      <p>
        <img src="https://github-readme-streak-stats.herokuapp.com?user=Jackson-tj74&theme=tokyonight&hide_border=true" alt="Streak" />
      </p>

      <p>
        <img src="https://github-profile-trophy.vercel.app/?username=Jackson-tj74&theme=darkhub&no-bg=true&no-frame=true&column=7" width="100%" alt="Trophies" />
      </p>

      <hr/>

      <!-- PROJECTS -->
      <h2>🌟 Featured Projects</h2>

      <table>
        <thead>
          <tr>
            <th>Project</th>
            <th>Description</th>
            <th>Tech</th>
            <th>Link</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td><strong>🔥 IngendoSmart</strong><br/><em>Currently Working On</em></td>
            <td>Smart management system built with the MERN stack</td>
            <td>
              <img src="https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black" alt="React" />
              <img src="https://img.shields.io/badge/Node-339933?style=flat-square&logo=node.js&logoColor=white" alt="Node" />
              <img src="https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white" alt="MongoDB" />
            </td>
            <td><a href="https://github.com/Jackson-tj74/IngendoSmart">⭐ Source Code</a></td>
          </tr>
          <tr>
            <td><strong>🌍 TJ Dev Sphere</strong><br/><em>Portfolio Site</em></td>
            <td>Personal portfolio showcasing projects and skills</td>
            <td>
              <img src="https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black" alt="React" />
              <img src="https://img.shields.io/badge/Tailwind-06B6D4?style=flat-square&logo=tailwindcss&logoColor=black" alt="Tailwind" />
              <img src="https://img.shields.io/badge/Netlify-00C7B7?style=flat-square&logo=netlify&logoColor=white" alt="Netlify" />
            </td>
            <td><a href="https://tjdevsphere.netlify.app">🌐 Live Demo</a></td>
          </tr>
          <tr>
            <td><strong>🤝 Community Services</strong><br/><em>Open to Collaboration</em></td>
            <td>Community platform for service coordination</td>
            <td>
              <img src="https://img.shields.io/badge/HTML-CSS-E34F26?style=flat-square&logo=html5&logoColor=white" alt="HTML" />
              <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black" alt="JS" />
              <img src="https://img.shields.io/badge/Netlify-00C7B7?style=flat-square&logo=netlify&logoColor=white" alt="Netlify" />
            </td>
            <td><a href="https://community-services-nyabiheke-cohort4.netlify.app/">🌐 Live Demo</a></td>
          </tr>
        </tbody>
      </table>

      <p>
        <a href="https://github.com/Jackson-tj74?tab=repositories"><img src="https://img.shields.io/badge/📁_Browse_All_Repositories-333333?style=for-the-badge&logo=github&logoColor=white" alt="All Repos" /></a>
      </p>

      <hr/>

      <!-- CERTIFICATES -->
      <h2>🏅 Certificates & Awards</h2>

      <table>
        <thead>
          <tr>
            <th></th>
            <th>Certificate</th>
            <th>Institution</th>
            <th>Type</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>🎓</td>
            <td><strong>High School Diploma</strong></td>
            <td>MCE, Rwanda</td>
            <td>Academic</td>
          </tr>
          <tr>
            <td>💻</td>
            <td><strong>Full-Stack Development</strong></td>
            <td>Alight Coding School</td>
            <td>Professional</td>
          </tr>
          <tr>
            <td>🌍</td>
            <td><strong>Duolingo International</strong></td>
            <td>Duolingo Platform</td>
            <td>International</td>
          </tr>
          <tr>
            <td>📝</td>
            <td><strong>IELTS Academic</strong></td>
            <td>Certified English Communications</td>
            <td>International</td>
          </tr>
          <tr>
            <td>💡</td>
            <td><strong>Entrepreneurship Challenge</strong></td>
            <td>Innovation Program</td>
            <td>Innovator Award</td>
          </tr>
        </tbody>
      </table>

      <hr/>

      <!-- LANGUAGES -->
      <h2>🗣️ Languages</h2>

      <table>
        <tbody>
          <tr>
            <td>🇷🇼 <strong>Kinyarwanda</strong></td>
            <td><img src="https://img.shields.io/badge/Native-4ADE80?style=flat-square" alt="Native" /></td>
          </tr>
          <tr>
            <td>🇬🇧 <strong>English</strong></td>
            <td><img src="https://img.shields.io/badge/Fluent_(IELTS)-58A6FF?style=flat-square" alt="Fluent" /></td>
          </tr>
        </tbody>
      </table>

      <hr/>

      <!-- ASK ME ABOUT -->
      <h2>💬 Ask Me About</h2>

      <p>
        <code>react</code> <code>typescript</code> <code>tailwind</code> <code>javascript</code> <code>node.js</code> <code>mongodb</code> <code>express</code> <code>figma</code> <code>rest-apis</code> <code>git</code> <code>vercel</code> <code>netlify</code>
      </p>

      <br/>

      <p>
        <img src="https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black" alt="React" />
        <img src="https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white" alt="TS" />
        <img src="https://img.shields.io/badge/Tailwind-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=black" alt="Tailwind" />
        <img src="https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=node.js&logoColor=white" alt="Node" />
        <img src="https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white" alt="MongoDB" />
        <img src="https://img.shields.io/badge/Figma-F24E1E?style=for-the-badge&logo=figma&logoColor=white" alt="Figma" />
        <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" />
        <img src="https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white" alt="Vercel" />
        <img src="https://img.shields.io/badge/Netlify-00C7B7?style=for-the-badge&logo=netlify&logoColor=white" alt="Netlify" />
      </p>

      <hr/>

      <!-- CONNECT -->
      <h2>🌐 Connect With Me</h2>

      <p>
        <a href="mailto:tuyikundejackson74@gmail.com"><img src="https://img.shields.io/badge/Email-Me-DC2626?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" /></a>
        <a href="https://github.com/Jackson-tj74"><img src="https://img.shields.io/badge/GitHub-@Jackson--tj74-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" /></a>
        <a href="https://tjdevsphere.netlify.app"><img src="https://img.shields.io/badge/Portfolio-TJ_Dev_Sphere-4C1D95?style=for-the-badge&logo=vercel&logoColor=white" alt="Portfolio" /></a>
        <a href="https://community-services-nyabiheke-cohort4.netlify.app/"><img src="https://img.shields.io/badge/Collaborate-Community_Services-059669?style=for-the-badge&logo=handshake&logoColor=white" alt="Collaborate" /></a>
      </p>

      <hr/>

      <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=80&section=header" width="100%" alt="wave"/>

      <p>
        <img src="https://img.shields.io/badge/Made_with_%E2%9D%A4_in_Rwanda_%F0%9F%87%B7%F0%9F%87%BC-2025-58A6FF?style=flat-square" alt="Made with love" />
      </p>

      <p>
        <strong>⭐ Thanks for visiting! Consider starring my repos ⭐</strong>
      </p>

    </div>
  </div>

  <!-- Preview Label -->
  <div class="preview-label">
    <svg width="14" height="14" viewBox="0 0 16 16" fill="none"><path d="M8 1a7 7 0 100 14A7 7 0 008 1zM0 8a8 8 0 1116 0A8 8 0 010 8zm6.5-2.5a.5.5 0 00-1 0v4a.5.5 0 00.75.433l2.5-1.5a.5.5 0 00-.5-.866L6.5 8.766V5.5z" fill="white"/></svg>
    GitHub Preview — How it looks on GitHub
  </div>

</body>
</html>
