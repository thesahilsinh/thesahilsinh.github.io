---
layout: tab
title: Projects
icon: fas fa-diagram-project
order: 4
---

# My Projects

Here are some of the tools, experiments, and projects I’ve built during my learning journey — mostly focused on **Malware Analysis**, **Digital Forensics**, **AI**, and **Cybersecurity tools**.

I enjoy building practical things that help me learn and solve real problems.

<style>
.project-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 1.5rem;
  margin-top: 2rem;
}
.project-card {
  background: #1f1f1f;
  padding: 1.4rem;
  border-radius: 12px;
  color: #ddd;
  text-decoration: none;
  box-shadow: 0 4px 12px rgba(0,0,0,0.3);
  transition: all 0.3s ease;
  display: block;
  border: 1px solid #2a2a2a;
}
.project-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 8px 20px rgba(0,240,255,0.15);
  border-color: #00f0ff;
}
.project-icon {
  font-size: 2.2rem;
  margin-bottom: 0.8rem;
}
.project-card h3 {
  margin: 0.3rem 0 0.6rem;
  color: #fff;
  font-size: 1.25rem;
}
.project-card p {
  font-size: 0.95rem;
  color: #aaa;
  line-height: 1.5;
}
</style>

<div class="project-grid">

  <a href="https://github.com/thesahilsinh/AI-Learning/tree/main/Anth/Intro2MCP" class="project-card" target="_blank">
    <div class="project-icon">🤖</div>
    <h3>MCP CLI Chatbot</h3>
    <p>Command-line chatbot using Anthropic’s Model Context Protocol (MCP) with FastMCP SDK. Supports custom tools, resources, and reusable prompts.</p>
  </a>

  <a href="https://github.com/thesahilsinh/qr-gen" class="project-card" target="_blank">
    <div class="project-icon">🔲</div>
    <h3>QR.GEN — Real-time QR Studio</h3>
    <p>Beautiful live QR code generator with advanced styling, logo overlay, scannability analysis, and real-time preview. Built with Flask and modern UI.</p>
  </a>

  <a href="#https://github.com/thesahilsinh/PMA" class="project-card">
    <div class="project-icon">🛡️</div>
    <h3>Practical Malware Analysis Labs</h3>
    <p>Detailed notes, screenshots, and solutions for every lab from the book "Practical Malware Analysis" by Sikorski & Honig.</p>
  </a>

</div>

<br>

<p style="color:#666; font-size:0.9rem;">
  More projects coming soon as I progress through malware analysis, reverse engineering, and AI security.
</p>
