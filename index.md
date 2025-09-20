---
layout: default
title: Home
---

<header class="bg-dark text-white text-center py-5">
  <h1>Conor Kingston</h1>
  <p class="lead">Systems Administrator & Software Programmer</p>
</header>

<main class="container my-5">
  <section>
    <h2 class="mb-4">Project Case Studies</h2>
    <ul class="list-group">
      <li class="list-group-item">
        <strong>IT Security Policy Overhaul</strong><br>
        Improved compliance and reduced incidents.
      </li>
      <li class="list-group-item">
        <strong>AD Certificate Services Deployment</strong><br>
        Enabled secure internal PKI.
      </li>
      <li class="list-group-item">
        <strong>JupyterHub Deployment</strong><br>
        Centralized scientific computing platform.
      </li>
      <li class="list-group-item">
        <strong>Network Expansion</strong><br>
        Boosted throughput and redundancy.
      </li>
    </ul>
  </section>

  <section class="mt-5">
    <h2 class="mb-4">Blog</h2>
    <div class="card mb-3">
      <div class="card-body">
        <h5 class="card-title">Automating Certificate Management with PowerShell</h5>
        <h6 class="card-subtitle mb-2 text-muted">September 2025</h6>
        <p class="card-text">A walkthrough of how I automated certificate renewal and deployment using PowerShell scripts and Group Policy.</p>
      </div>
    </div>
    <div class="card mb-3">
      <div class="card-body">
        <h5 class="card-title">Deploying JupyterHub for Scientific Research</h5>
        <h6 class="card-subtitle mb-2 text-muted">August 2025</h6>
        <p class="card-text">Lessons learned from building a secure, scalable JupyterHub environment for planetary scientists at PSI.</p>
      </div>
    </div>
    <div class="card mb-3">
      <div class="card-body">
        <h5 class="card-title">Network Expansion: Planning for Redundancy</h5>
        <h6 class="card-subtitle mb-2 text-muted">July 2025</h6>
        <p class="card-text">How I redesigned PSI's network to improve throughput and eliminate single points of failure.</p>
      </div>
    </div>
  </section>

  <section class="mt-5">
    <h2 class="mb-4">Contact Me</h2>
    <form action="https://formspree.io/f/mwpngnrj" method="POST">
      <div class="mb-3">
        <label for="name" class="form-label">Name</label>
        <input type="text" class="form-control" id="name" name="name" placeholder="Your name">
      </div>
      <div class="mb-3">
        <label for="email" class="form-label">Email</label>
        <input type="email" class="form-control" id="email" name="email" placeholder="you@example.com">
      </div>
      <div class="mb-3">
        <label for="message" class="form-label">Message</label>
        <textarea class="form-control" id="message" name="message" rows="4" placeholder="Your message"></textarea>
      </div>
      <button type="submit" class="btn btn-success">Send Message</button>
    </form>
  </section>

  <section class="mt-5 text-center">
    <a href="assets/Conor_Kingston_Resume.pdf" class="btn btn-primary">Download Resume</a>
  </section>
</main>

<footer class="bg-light text-center py-3">
  <small>&copy; 2025 Conor Kingston</small>
</footer>