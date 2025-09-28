---
layout: case_study
title: "Migrating Backshop Assets to PSI Infrastructure"
date: 2025-09-20
---

## Overview
This project involved migrating legacy Backshop assets from external storage into PSI's internal infrastructure. The goal was to improve data accessibility, security, and long-term maintainability.

## Context & Background
Backshop assets were previously stored on external systems with limited access and inconsistent backup strategies. PSI's infrastructure offered better integration with existing workflows and more robust data protection.

## Problem Statement
The challenge was to migrate large volumes of data without disrupting ongoing operations, while ensuring compatibility with PSI's storage architecture and security policies.

## Approach & Thought Process
I began by auditing the existing Backshop data: volume, formats, access patterns, and dependencies. I evaluated PSI's storage options and designed a migration plan that minimized downtime and preserved data integrity.

## Implementation
- Used rsync with checksum verification for data transfer
- Scheduled migration during low-usage windows
- Created access control policies in Active Directory
- Documented the new asset structure for internal teams

## Challenges & Solutions
- Some legacy files had inconsistent naming and permissions; I wrote scripts to normalize them before migration.
- Network bottlenecks were mitigated by staging data transfers and using parallel streams.

## Outcome & Impact
The migration was completed with zero data loss and minimal disruption. PSI teams now have faster, more secure access to Backshop assets, and backups are integrated into our standard procedures.

## Reflection
This project reinforced the importance of thorough pre-migration audits and stakeholder communication. Next time, I’d automate more of the validation steps to speed up the process.

## Related Work or Follow-Up
This migration laid the groundwork for future consolidation of legacy systems. It also informed our approach to the upcoming network expansion project.
