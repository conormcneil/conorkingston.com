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
    - **SSL termination via a proxy VM running Apache httpd**, supporting multiple subdomains under a shared external IPF
    - **Secure, direct access to archive data stored on an on-prem NAS**, using **NFS mounts** combined with **[Unionfs](https://unionfs.filesystems.org/) overlays** to provide seamless, read-only access to hundreds of terabytes of archive datasets while preserving container isolation and performance.


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

## Challenges
{: .pb-2}

### Mounting archive data
{: .text-secondary}

**Challenge**: Disorganized archive data split across multiple directories, including overlapping and superseded datasets.

**Solution**: Researched and implemented a Unionfs overlay to present a unified, read-only mount with authoritative data.

**Outcome**: Delivered a clean, reliable user experience while gaining valuable expertise in filesystem overlays and legacy data integration.

The most unexpected challenge in this deployment was the complexity of the archive data storage layout. I initially assumed the data would be organized under a single, unified directory structure. Instead, I discovered that the archive was fragmented across multiple locations: PDS3 data, PDS4 data, and the Catalina Sky Survey (CSS) data, which was so large it warranted its own top-level directory.

My original plan was to mount each of these datasets separately and expose them to users as distinct volumes. However, this approach quickly broke down when I encountered theh OSIRIS-REx mission data. It was split across two diretories, each containing a mix of unique and overlapping datasets. Crucially, one of the directories included updated versions of certain datasets that superseded older versions found in the other. Users needed to access the most current and authoritative data, but the disorganized structure made it difficult to expose a clean, reliable view.

This situation required a solution that could abstract away the underlying complexity and present a clean, logical view of the data. After researching filesystem overlay techniques, I identified **Unionfs** as a viable approach. I studied its behavior, tested various configurations, and ultimately implemented a setup that merged the relevant directories while prioritizing the correct versions of the data. This allowed me to expose a unified, read-only mount to users that masked the disorganization and ensured consistent access to authoritative datasets.

Solving this technical challenge taught be a great deal about **filesystem overlays**, particularly how they can be used to abstract and simplify access to fragmented or inconsistent data sources. It even works with network storage, which makes it incredibly adaptable. I'm glad to have this knowledge in my toolbelt- it's a powerful technique I'll be able to apply to future filesystem challenges, especially in environments where legacy data structures and modern workflows intersect.

---

## Impact
{: .pb-2}

- Enabled researchers to run Python notebooks securely alongside PDS archive data using PDS-provided resources without any local setup.
- Established a pathway that supports future migration of the archive data and the JupyterHub environment to the cloud.

<!-- --- -->

<!-- ## Reflections -->
<!-- {: .pb-2} -->
