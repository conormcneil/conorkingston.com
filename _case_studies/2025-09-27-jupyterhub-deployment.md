---
layout: case_study
title: "Deploying JupyterHub with DockerSpawner"
date: 2025-09-27
summary: Centralized computing platform for scientists to work with PDS data in a cloud-like environment.
---

<p class="lead">As part of my work with the Planetary Data System (PDS), I led the deployment of a scalable, containerized JupyterHub environment to support scientific computing and data analysis workflows. The goal was to provide researchers with a secure, flexible, and user-friendly platform for working with Python-based tools and notebooks, while laying the groundwork for future migration to AWS.</p>

<hr>
<h2 class="pb-2">My Role</h2>
<p>I served as the <strong>lead systems administrator and architect</strong> for this deployment. My responsibilities included:</p>
<ul>
    <li>Designing the infrastructure</li>
    <li>Selecting and customizing Docker images</li>
    <li>Configuring authentication and user environments</li>
    <li>Ensuring security and maintainability</li>
    <li>Planning for cloud migration</li>
</ul>

<hr>
<h2 class="pb-2">Technical Approach</h2>

<h3 class="text-secondary">Architecture</h3>
<ul>
    <li><strong>Base Image</strong>: Used <samp>quay.io/jupyter/scipy-notebook</samp> from the Jupyter Docker Stacks for a rich scientific Python environment.</li>
    <li><strong>Spawner</strong>: Configured <samp>DockerSpawner</samp> to isolate user environments.</li>
    <li><strong>Authentication</strong>: Integrated with <abbr title="Local Domain Access Protocol" class="initialism">LDAP</abbr> for secure user access.</li>
    <li><strong>Storage</strong>: Mounted persistent volumes for user data and notebooks.</li>
    <li><strong>Networking</strong>: Deployed behind a reverse proxy with HTTPS via Let's Encrypt.</li>
</ul>

<h3 class="text-secondary">DevOps & Automation</h3>
<ul>
    <li>Created reusable Docker Compose configurations for local testing.</li>
    <li>Used GitHub Actions to automate image builds and updates.</li>
    <li>Documented deployment steps for reproducability and team onboarding.</li>
</ul>

<hr>
<h2 class="pb-2 text">Outcome</h2>

<h3 class="text-secondary">Challenges</h3>

<table class="table">
    <thead>
        <th>Challenge</th>
        <th>Solution</th>
    </thead>
    <tr>
        <td>Ensuring compatibility with existing on-prem systems</td>
        <td>Customized Docker images and network settings</td>
    </tr>
    <tr>
        <td>Managing user environments securely</td>
        <td>Isolated containers with persistent storage</td>
    </tr>
    <tr>
        <td>Preparing for AWS migration</td>
        <td>Modular architecture with cloud-ready components</td>
    </tr>
</table>

<h3 class="text-secondary">Impact</h3>

<ul>
    <li>Enabled researchers to run Python notebooks without local setup.</li>
    <li>Reduced onboarding time for new users.</li>
    <li>Improved reproducibility and collaboration across teams.</li>
    <li>Established a foundation for future cloud migration.</li>
</ul>

<hr>
<h2 class="pb-2 text">Reflections</h2>

<p>This project deepened my experience with container orchestration, secure authentication, and infrastructure-as-code. If I were to iterate on this deployment, I’d explore Kubernetes for better scalability and integrate monitoring tools like Prometheus and Grafana for observability.</p>

<hr>
<h2 class="pb-2 text">Related Work & Next Steps</h2>

<ul>
    <li>Migrate the deployment to AWS using EKS and S3-backed storage.</li>
    <li>Expand support for R and Julia kernels.</li>
    <li>Implement role-based access controls and resource quotas.</li>
</ul>