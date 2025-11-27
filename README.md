# GdriveFolderCopy
Automated Google Drive folder replication tool with recursive copy support, progress persistence, detailed logging, duplicate avoidance, and trigger-based resume for large directory trees.

Google Drive Folder Copy Manager (GDFCM) &nbsp;   <br>
![GitHub all releases](https://img.shields.io/github/downloads/TechPoov/GDriveCrawlerToGSheet/total.svg)

Efficient, resumable, and structured recursive folder copying inside Google Drive.
Designed and developed by TechPoov.

1. Overview

The Google Drive Folder Copy Manager (GDFCM) is a Google Apps Script–powered automation tool that copies folder structures and their contents from one location in Google Drive to another.

It is built for users who need a reliable, resumable, and transparent folder copy process, especially when working with large or deeply nested directory trees.

2. Key Features

Recursive Folder Copying
Automatically copies entire folder hierarchies (subfolders + files).

Progress Persistence & Auto-Resume
Uses triggers and state storage to resume long copy jobs safely.

Duplicate Avoidance
Prevents accidental overwrites by skipping files already present in the destination.

Row-Based Job Management
Supports multiple copy jobs via the Spreadsheet “Profile” sheet.

Execution Logging
Writes detailed logs for each completed or failed job.

Email Notifications
Sends a summary email when each job finishes (Completed or Error).

Graceful Timeout Handling
Stops before Apps Script’s hard limit and resumes automatically.

3. What This Tool Does Not Do (v1.0 Limitations)

The following features are intentionally not implemented in v1.0:

Copying permissions or shared settings

Timestamps preservation (Drive does not allow setting custom timestamps)

Syncing two folders

Version comparison or delta copy

Hash-based file integrity validation (MD5/SHA)

Cross-account migration

UI-based front-end screens

Advanced deduplication logic

Bulk Shared Drive processing

These may be considered in future releases.

4. Architecture Summary
4.1 Controller-Based Execution

The main driver (runController) orchestrates:

Profile row selection

State loading/saving

Time-sliced execution

Trigger scheduling

4.2 Queue-Driven Folder Copy

Each copy job uses a Breadth-First Search (BFS) queue:

[
  { srcId: <folderId>, destId: <folderId> },
  ...
]


This ensures stable recursion even for large folder trees.

4.3 State Persistence

State is stored in ScriptProperties to survive:

Script timeouts

Execution gaps

Trigger-based continuation

4.4 Logging & Notifications

All job completions or errors are written to a Log sheet and emailed to the active user.

5. Profile Sheet Configuration

Your spreadsheet must contain the following columns starting from Row 2:

Column	Field Name	Description
A	Source_Folder_Name	For human reference only
B	Source_Folder_ID	Folder ID to copy from
C	Destination_Folder_Name	For reference
D	Destination_Folder_ID	Parent folder where copied folder will be created
E	Copied_Folder_Name	New folder name in the destination
F	Copy (Yes/No)	“Yes” = Run this job
G	Status	Auto-updated (Running / Completed / Error)
H	LastUpdatedOn	Auto-updated timestamp
6. How to Run the Tool

Open the Google Sheet containing the Profile sheet.

Go to the top menu → Copy Gdrives

Select Start Copy

The tool will begin copying eligible rows (Copy = Yes).

If the process exceeds the execution window, the tool will:

Save state

Schedule a trigger

Resume automatically after 1 minute

To view logs at any time, use:
Copy Gdrives → View Logs

7. Logging & Monitoring

The Log sheet is auto-created with the following fields:

Field	Description
Date	When the job finished
SourceFolderName	Name from Profile sheet
StartsAt	Timestamp when job started
EndsAt	Timestamp when job ended
Details	Completed/Error + counts
RowNumber	Profile sheet row number
ExecutionID	Unique ID for traceability

Each copy job produces a single log entry.

8. Error Handling Behavior
8.1 Configuration Errors

Examples:

Missing folder ID

Invalid folder ID

Missing Copied_Folder_Name

These:

Mark the row as Error

Write to the Log sheet

Send email

Move on to the next row

8.2 Runtime Errors

If an error occurs during:

File copy

Folder read

Subfolder creation

The entire job is marked Error and logged.

(Future versions will support per-file continuation.)

9. Progress & Resume Logic

Execution window: 6 minutes

Safe margin: 1 minute

If the script is about to time out:

State is saved

A time-based trigger is created

Work resumes after 1 minute

This allows completion of extremely large folder structures.

10. Folder Structure Preservation

The tool preserves:

Folder names

Subfolder hierarchy

File names

File MimeType

File content

Limitations:
DriveApp does not allow assigning custom created or modified timestamps to new copies.

11. Performance Notes

Uses BFS queue to minimize deep recursion overhead.

Avoids unnecessary metadata reads.

Performs duplicate avoidance via name-based checks.

May incur additional Drive API calls for getFilesByName and getFoldersByName, especially in large folders.

Future versions may include caching for optimization.

12. Security Notes

Script can only access files/folders the active user has permission to access.

No external networks or APIs are used.

All operations stay within Google's ecosystem.

13. Planned for Future Releases

v1.1 Goals

Continue copying after file-level errors

Basic integrity verification

Retry/backoff for rate limiting

Performance improvements (folder-level caching)

v1.2 Goals

Metadata parity checking

Optional copy modes (Files Only, Folders Only)

Per-item log entries

Duplicate merge/reporting options

14. Version History
v1.0 – Initial Public Release

Recursive folder copy

State persistence

Auto-resume triggers

Duplicate avoidance

Logging & email notifications

Multi-job processing via Profile sheet
