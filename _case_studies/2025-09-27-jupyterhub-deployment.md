---
layout: case_study
title: "Deploying JupyterHub with DockerSpawner"
date: 2025-09-27
summary: Centralized computing platform for scientists to work with PDS data in a cloud-like environment.
---

As part of my work with the Planetary Data System (PDS), I led the deployment of a scalable, containerized JupyterHub environment to support scientific computing and data analysis workflows. The goal was to provide secure access to PDS compute and storage resources via a flexible and user-friendly platform for working with Python-based tools and notebooks, while simultaneously laying the groundwork for future migration to AWS.
{: .lead}

---

## My Role
{: .pb-2}

This project demonstrates my diverse skillset as both a <strong>systems administrator and software programmer</strong>.

My responsibilities included:

- Project Planning and Tracking
    - Collaborating with the lead project scientist to define and capture requirements
    - Researching and choosing the appropriate technology stack
    - Project planning and tracking
    - Architecting integration with existing infrastructure
- Development
    - Selecting and customizing Docker images
    - Configuring authentication and user environments
    - Ensuring security and maintainability
- Deployment
- Documentation
    - Writing documentation SOPs and Knowledge Base articles
        - Standard Operating Procedures for deployment and maintenance
        - Knowledge Base articles for users
        - How-To guides
    - Planning for future cloud migration

---

## Technical Approach
{: .pb-2}

### Architecture
{: .text-secondary}

- **Base Image**: Used <samp>quay.io/jupyter/scipy-notebook</samp> from the Jupyter Docker Stacks for a rich scientific Python environment.
- **Spawner**: Configured <samp>DockerSpawner</samp> to isolate user environments.
- **Authentication**: Integrated with <abbr title="Lightweight Directory Access Protocol" class="initialism">LDAP</abbr> for secure user access.
- **Storage**: Mounted persistent volumes for user data and notebooks.
- **Networking**: Deployed behind a reverse proxy with HTTPS via Let's Encrypt.

### DevOps & Automation
{: .text-secondary}

- Created reusable Docker Compose configurations for local testing.
- Used GitHub Actions to automate image builds and updates.
- Documented deployment steps for reproducability and team onboarding.

---

## Outcome
{: .pb-2}

### Challenges
{: .text-secondary}

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

### Impact
{: .text-secondary}


- Enabled researchers to run Python notebooks without local setup.
- Reduced onboarding time for new users.
- Improved reproducibility and collaboration across teams.
- Established a foundation for future cloud migration.

---

## Reflections
{: .pb-2}

This project deepened my experience with container orchestration, secure authentication, and infrastructure-as-code. If I were to iterate on this deployment, I’d explore Kubernetes for better scalability and integrate monitoring tools like Prometheus and Grafana for observability.

---

## Related Work & Next Steps
{: .pb-2}

- Migrate the deployment to AWS using EKS and S3-backed storage.
- Expand support for R and Julia kernels.
- Implement role-based access controls and resource quotas.