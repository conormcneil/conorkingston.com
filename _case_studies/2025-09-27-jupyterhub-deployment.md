---
layout: case_study
title: "Deploying JupyterHub with DockerSpawner"
date: 2025-09-27
summary: Centralized computing platform for scientists to work with PDS data in a cloud-like environment.
---

As part of my work with the Planetary Data System (PDS), I led the deployment of a scalable, containerized JupyterHub environment to support scientific computing and data analysis workflows. The goal was to provide secure access to PDS compute and storage resources via a flexible and user-friendly platform for working with Python-based tools and notebooks, while simultaneously laying the groundwork for future migration to AWS.
{: .lead}

---

## Role & Responsibilities
{: .pb-2}

This project showcases my multifaceted skill set as a <strong>systems administrator and software programmer</strong>, with a focus on infrastructure design, automation, and secure deployment practices.

### Project Planning & Architecture
{: .text-secondary}

- Partnered with the lead project scientist to gather and refine technical requirements.
- Conducted comparative analysis of containerized solutions, ultimately selecting **[JupyterHub](https://jupyter.org/hub) with [DockerSpawner](https://github.com/jupyterhub/dockerspawner)** to balance usability, scalability, and maintainablity.
- Designed a deployment architecture that integrates with existing on-prem infrastructure, including:
    - **SSL termination via a proxy VM running Apache httpd**, supporting multiple subdomains under a shared external IP.
    - **Secure, direct access to archive data stored on an on-prem NAS**, using **NFS mounts** combined with **[UnionFS](https://unionfs.filesystems.org/) overlays** to provide seamless, read-only access to hundreds of terabytes of archive datasets while preserving container isolation and performance.


### Infrastructure & Deployment
{: .text-secondary}

- Built and deployed a **production-grade JupyterHub environment** using Docker containers, designed for long-term maintainability and scalability.
- Architected the system with **future cloud migration in mind**, ensuring compatibility with AWS-hosted services and container orchestration platforms.
- Imlpemented **secure authentication** using Google OAuth 2.0 and user environment isolation.
- **Automated deployment workflows** and configuration management to ensure reproducibility and reduce operational overhead.

### Security & Maintainability
{: .text-secondary}

- Applied best practices for container hardening and network segmentation.
- Developed and enforced **Standard Operating Procedures (SOPs)** for deployment, updates, and incident response.
- Created a suite of **Knowledge Base articles and How-To guides** to support end users and streamline onboarding.

### Cloud Migration Planning
{: .text-secondary}

- Evaluated cloud-native alternatives and designed a migration strategy to transition to AWS with minimal disruption.
- Ensured compatibiility with existing data pipelines and authentication systems.

---

## Technical Approach
{: .pb-2}

### Architecture
{: .text-secondary}

- **Hyper-V Virtual Machine** host with Docker Engine, Docker Compose, and a Jupyter server.
- **Logical Volume Management** technology simplifies scaling the amount of storage available to the VM and enables daily checkpoints to ensure system and user data are recoverable.
- Mounted **persistent volumes** for user data and notebooks.
- Utilized **DockerSpawner** to easily spawn separate containers for every user, increasing security and easing future integration with orchestration services.
- Integrated with **Google OAuth 2.0** for secure user access with existing credentials for any user explicitly included in a custom allow list.
- Deployed in a segmented VLAN behind a reverse proxy with **HTTPS** provided by Let's Encrypt.

### DevOps & Automation
{: .text-secondary}

- Used Ansible to define roles and playbooks to **automate VM provisioning**.
- Created reusable Docker Compose configurations for consistent, **platform-independent container deployment**.

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