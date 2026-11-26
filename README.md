# Windows Troubleshooting | Disk Management and Performance Optimization

## 1. Incident | Impact: Low (one employee workstation) | Priority: P3 – Medium

> "My computer is running slowly, affecting my ability to complete my daily tasks."

The marketing manager reported slow workstation performance to IT Support. Preliminary investigation identified the need for disk cleanup and scheduled hard drive defragmentation.

My objective is to address the disk maintenance issue, preserve required files, and configure automatic monthly disk optimization to support workstation performance.

## 2. Support Ticket

| Field            | Details                       |
| ---------------- | ----------------------------- |
| Reported by      | Marketing Manager             |
| Department       | Marketing                     |
| Category         | Hardware / Performance        |
| Subcategory      | Disk Management               |
| Ticket type      | Incident                      |
| Affected device  | Employee workstation          |
| Operating system | Windows                       |
| Affected drive   | Local Disk (C:)               |
| Reported issue   | Slow computer performance     |
| Business impact  | Reduced employee productivity |
| Assigned to      | IT Support                    |
| Tools            | Disk Cleanup, Optimize Drives |

## 3. Troubleshooting Workflow

```
Employee Reports Slow Performance
              ↓
Investigate Disk Maintenance
              ↓
Review Disk Cleanup Options
              ↓
Remove Unnecessary Thumbnails
              ↓
Preserve Temporary Files
              ↓
Configure Monthly Disk Optimization
              ↓
Verify Configuration
              ↓
Document and Resolve Incident
```

## 4. Step-by-Step Resolution

### Step 1 — Investigate the system drive

**Goal:** Identify the affected drive and review its storage configuration before making changes.

1. Open File Explorer.
2. Select This PC.
3. Locate Local Disk (C:).
4. Right-click Local Disk (C:).
5. Select Properties.
6. Review the available and used disk space.

📸 Screenshot 01 — Local Disk (C:) properties.
<img width="759" height="567" alt="image" src="https://github.com/user-attachments/assets/d855e5be-860e-4323-9971-9c191a90c163" />

### Step 2 — Analyze disk cleanup options

**Goal:** Identify unnecessary files that can be safely removed without deleting files that must be preserved.

1. From the drive Properties window, select the General tab.
2. Select Disk Cleanup.
3. Allow Windows to analyze the drive.
4. Review the Files to delete section.

Alternatively, launch Disk Cleanup using:

```
cleanmgr /d C:
```

Configure the following options:

| File category   | Required action |
| --------------- | --------------- |
| Thumbnails      | Selected        |
| Temporary files | Unselected      |

**Important:** Temporary files and Temporary Internet Files are different categories. The incident specifically requires preserving Temporary files.

📸 Screenshot 02 — Disk Cleanup configuration before execution.

### Step 3 — Perform disk cleanup

**Goal:** Remove unnecessary cached thumbnails while preserving required temporary files.

1. Confirm that Thumbnails is selected.
2. Confirm that Temporary files is unselected.
3. Select OK.
4. Select Delete Files.
5. Allow the cleanup process to complete.

Windows can automatically regenerate thumbnails when they are needed again.

📸 Screenshot 03 — Disk Cleanup execution.

### Step 4 — Investigate disk optimization settings

**Goal:** Review the existing drive optimization configuration.

1. Return to Local Disk (C:) Properties.
2. Select the Tools tab.
3. Under Optimize and defragment drive, select Optimize.
4. Locate the C: drive.
5. Review the media type, optimization status, and scheduled optimization settings.

Alternatively, launch Optimize Drives using:

```
dfrgui
```

**Technical consideration:** Traditional defragmentation is intended for mechanical hard disk drives (HDDs). Windows applies appropriate optimization operations, such as TRIM, for solid-state drives (SSDs).

📸 Screenshot 04 — Drive optimization status.

### Step 5 — Configure monthly disk optimization

**Goal:** Establish automatic preventive maintenance for the affected system drive.

1. In the Optimize Drives window, select Change settings.
2. Enable Run on a schedule (recommended).
3. Set Frequency to Monthly.
4. Select Choose to configure the affected drives.
5. Keep Local Disk (C:) selected.
6. Unselect Local Disk (D:).
7. Unselect Local Disk (E:).
8. Select OK to save the drive selection.
9. Select OK to save the schedule.

| Configuration          | Required setting |
| ---------------------- | ---------------- |
| Scheduled optimization | Enabled          |
| Frequency              | Monthly          |
| Local Disk (C:)        | Selected         |
| Local Disk (D:)        | Unselected       |
| Local Disk (E:)        | Unselected       |

📸 Screenshot 05 — Monthly optimization schedule.

📸 Screenshot 06 — Selected drive configuration.

### Step 6 — Verify the corrective actions

**Goal:** Confirm that all required maintenance tasks were completed successfully.

Review the final configuration and validate the following:

| Verification                   | Result     |
| ------------------------------ | ---------- |
| Disk Cleanup executed          | Successful |
| Thumbnails removed             | Confirmed  |
| Temporary files preserved      | Confirmed  |
| Scheduled optimization enabled | Confirmed  |
| Optimization frequency         | Monthly    |
| C: drive included              | Confirmed  |
| D: and E: drives excluded      | Configured |

📸 Screenshot 07 — Final lab verification.

**Additional production verification:** Confirm workstation responsiveness with the employee and investigate CPU, memory, or disk utilization if slow performance persists.

## 5. Ticket Resolution

| Field             | Resolution                                  |
| ----------------- | ------------------------------------------- |
| Identified issue  | Disk maintenance required                   |
| Corrective action | Windows Disk Cleanup                        |
| Files removed     | Cached thumbnails                           |
| Files preserved   | Temporary files                             |
| Preventive action | Monthly scheduled disk optimization         |
| Lab verification  | Successful                                  |
| Ticket status     | Ready for closure following user validation |

**Resolution notes:**

> Completed Disk Cleanup on the marketing manager's C: drive, removed unnecessary cached thumbnails while preserving temporary files, and configured automatic monthly disk optimization for the affected drive. All required lab configurations were successfully verified.

## 6. Technical Skills Demonstrated

- Windows workstation troubleshooting
- Disk management
- Storage performance troubleshooting
- Disk Cleanup
- HDD defragmentation and drive optimization
- Automated preventive maintenance
- Selective file cleanup
- Incident management
- Technical documentation
- Post-resolution verification

## 7. Business Impact

This solution supports workstation performance, removes unnecessary cached files, protects required temporary files, and establishes automated preventive maintenance.

The scheduled optimization reduces the need for manual intervention and supports ongoing workstation reliability.

**Effective IT Support is not just about fixing today's problems. It is also about preventing tomorrow's incidents.**

**Professional note:** I classified this incident as P3 because it affects one employee's productivity without a complete workstation outage. 
