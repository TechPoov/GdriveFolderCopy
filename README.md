GDrive-FolderCopy V1.0 Overview
===============================

GDrive-FolderCopy is a reliable TechPoov utility that duplicates entire Google Drive folder structures---files, subfolders, and nested levels---into a destination folder without breaking hierarchy or creating messy duplicates. It intelligently recreates the folder tree, avoids re-copying items with identical names, and continues smoothly even when the source is very large.

There is no installation required, no scripting expertise needed, and no special admin privileges involved. Simply configure your copy jobs in the Profile sheet, click Start Copy, and the tool handles everything automatically.

The copy process uses a checkpoint-and-resume engine that safely works within Google Apps Script's time limits. Even multi-GB folders with thousands of items are completed reliably over multiple controlled runs. Each job records its progress, updates status, and logs completion or errors with timestamps. Email notifications keep you informed without checking manually.

Whether you're reorganizing your Drive, preparing backups, creating sandbox environments, or duplicating department structures for new teams, GDrive-FolderCopy delivers a clean, predictable, auditable copy every time.

Google Drive Folder Copy Manager (GDFCM) &nbsp; 

[Download Link](https://github.com/TechPoov/02_Gdrive-FolderCopy/releases/tag/V1.0)
&nbsp; <br>
![GitHub all releases](https://img.shields.io/github/downloads/TechPoov/02_Gdrive-FolderCopy/total.svg)

* * * * *

Features
========

-   Multi-Profile Copy Engine\
    Runs multiple folder-copy jobs in a single spreadsheet, each fully independent.

-   Recursive Folder Copying\
    Rebuilds the entire folder structure---root, subfolders, nested trees---preserving hierarchy exactly.

-   Duplicate-Safe File Transfer\
    Files are copied only when a file with the same name does not already exist in the destination.

-   Automatic Folder Reuse\
    If a matching folder name already exists in the destination, it is reused instead of recreated, preventing clutter.

-   Checkpoint & Resume Execution\
    Large copy operations automatically pause and resume using time-based triggers, ensuring completion even for massive folders.

-   Browser-Independent Processing\
    Copying continues safely in the background---even if the browser is closed, the network drops, or the computer shuts down.

-   Live Status Tracking\
    The Profiles sheet updates status as "Running", "Completed", or "Error", along with timestamps.

-   Error-Isolated Job Handling\
    One failed row does not impact the rest of the queue; jobs continue cleanly.

-   Per-Job Email Notifications\
    Receive an automatic email summarizing completion, counts, or errors, including execution ID for auditing.

-   Detailed Log Sheet\
    Each job writes a timestamped log entry containing:\
    Start time, end time, folder/file counts, execution ID, and error details (if any).

-   No Installation or Admin Rights Needed\
    Runs entirely inside Google Drive + Google Sheets using Apps Script.

-   Lightweight, Predictable, and Admin-Friendly\
    Perfect for Drive reorganizations, team onboarding, cloning templates, backups, and controlled test environments.

* * * * *

Who Needs This Tool & How They Use It
=====================================

1\. Users Who Need Clean, Safe Backups
--------------------------------------

Some users simply want a dependable duplicate of an important folder---personal archives, annual work documents, or data that must be preserved exactly.

Use Cases:

-   Creating a full backup before reorganizing a Drive or deleting content.

-   Taking a year-end snapshot (e.g., "2024 Work") for long-term storage.

-   Making a safeguard copy before cleaning or restructuring folders.

-   Protecting shared folders from unwanted modifications or deletions.

* * * * *

2\. Template Builders & Structure Designers
-------------------------------------------

For users who repeatedly create standardized folder layouts---projects, courses, onboarding materials, or client packages---this tool acts as a template replication engine.

Use Cases:

-   Cloning a master "Project Template" for every new assignment.

-   Preparing course or training material for each new batch.

-   Creating consistent onboarding folders for new employees or volunteers.

-   Generating uniform client workspaces with identical subfolder structure.

* * * * *

3\. Operations Teams Requiring Repeatable Environments
------------------------------------------------------

Operations teams need consistent, error-free folder structures for scheduled cycles or coordinated projects. This tool rebuilds entire trees precisely every time.

Use Cases:

-   Resetting department folders at the start of each month or quarter.

-   Preparing controlled staging workspaces for internal reviews or updates.

-   Providing new teams with identical working environments.

-   Producing sandbox copies for workflow or permission testing.

* * * * *

4\. Backup, Archival & Business Continuity Teams
------------------------------------------------

Organizations that must preserve folder hierarchy and metadata benefit from the tool's duplicate-safe, non-destructive copying.

Use Cases:

-   Creating compliance-ready archive copies for record retention.

-   Taking quarter-end or year-end snapshots for financial or legal storage.

-   Capturing folder structures during ownership, leadership, or security transitions.

-   Building evidence-preserved trees for internal investigations or audits.

* * * * *

5\. Migration, Reorganization & IT Transition Teams
---------------------------------------------------

During migrations or structural reorganizations, teams need safe, accurate duplicates of folder environments before making changes.

Use Cases:

-   Duplicating structures into staging folders for migration testing.

-   Preparing pre-migration copies before transferring to OneDrive or SharePoint.

-   Generating shadow copies to compare source vs. migrated content.

-   Reorganizing large Drive areas by first cloning into clean layouts.

* * * * *

6\. Creative Professionals, Agencies & Freelancers
--------------------------------------------------

Creative work thrives on structure. This tool ensures every new client or project starts with the exact folder framework needed.

Use Cases:

-   Creating a fresh working folder for each new client or campaign.

-   Maintaining versioned folder sets for internal revisions.

-   Archiving completed client projects into clean, organized structures.

-   Preparing standardized pitch or presentation folders.

* * * * *

7\. Power Users Managing Complex Folder Hierarchies
---------------------------------------------------

Users who value precision and repeatability use this tool to automate copying without mistakes.

Use Cases:

-   Maintaining parallel folder trees for A/B workflows.

-   Creating testing copies to explore new organizational structures.

-   Copying massive archives across multiple runs without timeout risk.

-   Preserving execution logs for audit or documentation purposes.

* * * * *

8\. IT, Infrastructure & Workspace Administrators
-------------------------------------------------

For administrators supporting large organizations, this tool simplifies rollout, migration, and environment management.

Use Cases:

-   Rolling out standard folder frameworks across multiple teams.

-   Creating sandbox environments for permission or security testing.

-   Duplicating resource libraries for departments or business units.

-   Maintaining versioned template repositories.

-   Validating Drive reorganizations using staging copies.

* * * * *

9\. Team Leads, Project Managers & Department Heads
---------------------------------------------------

Leaders use this tool to keep teams aligned with standardized structures throughout a project lifecycle.

Use Cases:

-   Cloning project startup folders for new initiatives.

-   Spinning up versioned workspaces for milestone phases.

-   Maintaining parallel test spaces for experimentation.

-   Preparing onboarding-ready structures for new team members.

-   Archiving completed phases into structured, labeled copies.

* * * * *

10\. Compliance, Legal, Finance & Audit Departments
---------------------------------------------------

Highly regulated teams value accurate, tamper-resistant duplication for recordkeeping and review.

Use Cases:

-   Producing read-only snapshot copies for internal or external audits.

-   Duplicating sensitive folders for controlled legal or financial review.

-   Maintaining compliance-required backup structures.

-   Creating evidence-ready folder sets with preserved hierarchy.

-   Storing time-stamped archives linked to each executed copy job.

* * * * *

11\. Educators, Nonprofits, Freelancers & Students
--------------------------------------------------

These users often reset workspaces regularly or require repeated folder structures across semesters, batches, or projects.

Use Cases:

-   Resetting course materials at the start of each semester.

-   Generating identical working folders for each student or volunteer.

-   Duplicating resource packs for training or community programs.

-   Preparing structured portfolio copies for grants or submissions.

-   Archiving yearly nonprofit projects while keeping originals intact.

* * * * *

Requirements
============

### A Valid Google Account

The tool runs entirely inside Google Drive + Google Sheets, so you must be signed in with a Google Account.

### Access to Both Source and Destination Folders

You must have permission to:

-   Read the source folder and its contents

-   Create folders and files inside the destination folder

Without these permissions, the copy job cannot proceed.

### First-Time Script Authorization

The first time you run the tool, Google will ask you to grant permission to access Drive.\
Google may display the standard "unverified app" warning---this is normal for Apps Script tools that aren't published publicly.

### An Active Internet Connection (only at the start)

You only need to be online to trigger the first run.\
After that, the copy engine continues via time-based triggers even if your browser or computer is offline.

* * * * *

Get Tool and Documents
======================

-   [Tool](https://docs.google.com/spreadsheets/d/1fVHxhQlCNSWalqE9CUgprPba4uBarCpNdC5XlMKR_VA/copy)

-   [User Manual V1.0](https://docs.google.com/document/d/1PdNsuZ_GIPac5KTKAA4F6KEvlfco9pCQfAsLotnuu9A/copy)

-   [Test Cases for reference](https://docs.google.com/spreadsheets/d/1nKbSnOrZPNFgR2kuCPCXXKIjS4Tm8pd8fgmh6u2J1Ew/copy)

Version History
===============

V1.0 --- 01- Dec - 2025   Initial release

* * * * *

License
=======

This project is released under the MIT License, a widely used open-source license that allows personal, commercial, and organizational use with minimal restrictions. Users are free to use, modify, distribute, and incorporate the code into their own projects, provided that the original copyright notice and license terms are included in all copies or substantial portions of the software.

* * * * *

Support
=======

If you need help, have questions, or want to share feedback, support is always available.

🌐 Online Documents:\
Visit the official TechPoov documentation at https://techpoov.github.io

📧 Email Support:\
techpoov+GDrive-FolderCopy@gmail.com

🐞 Report Issues on GitHub:\
Submit bugs, feature requests, or enhancement ideas here:\
https://github.com/TechPoov/GDrive-FolderCopy/issues

