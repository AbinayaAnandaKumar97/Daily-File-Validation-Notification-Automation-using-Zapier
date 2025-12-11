**Daily File Validation & Notification Automation using Zapier**

**Motivation / Problem Statement**
In my previous company, datasets received from customers via SFTP were stored across multiple folders in Azure Blob Storage. For example, we had 10 customer folders (e.g., ABC), and each customer folder contained 10 subfolders representing different types of data. Each subfolder stored 30 days of data.
At the end of every month, we needed to manually verify that all files were present and generate a report to inform the customers regarding the missing files. Checking all folders manually was time-consuming and error-prone. 
In total, that’s 30 files × 10 folders = 300 files for each customer, taking roughly 1 hour per month per customer, or 12 hours per customer annually.
To demonstrate a practical automation solution, I replicated this scenario using Google Drive, building a workflow that automatically validates files, sends alerts if any are missing, and logs the results, since I didn’t have access to Azure.

**Approach/Solution**
I built a Zapier workflow to automate file validation. The automation:
✅ Validates folders daily for missing files
✅ Checks specific files: ABC-AC-DataSet-[MMDDYYYY].xlsx (and other category files)
✅ Searches in Google Drive
✅ Sends email alerts only when files are missing
✅ Updates a table with Status = "Missing" and Alert Sent = ✅
✅ Supports manual trigger + scheduled runs (daily automatic + test button)

**Workflow Steps**
1️⃣ Schedule - Runs daily at 12 AM (every day, including weekends)
2️⃣ Code	Generates - today's filenames dynamically based on the date to compare
3️⃣ Google Drive Search - Searches the specified folder for the files
4️⃣ Filter - Continues only if a file is not found
5️⃣ Email Alert - Sends alert to abinayaanandakumar97@gmail.com if a file is missing
6️⃣ Table Update	- Updates ACData record: Status = Missing, Alert Sent = ✅

<img width="514" height="869" alt="image" src="https://github.com/user-attachments/assets/64e2b32a-92c7-415f-a5be-6f0657719561" />

**Impact**
✅ Eliminates manual verification of hundreds of files.
✅ Saves ~1 hour per month per customer (~12 hours per year per customer).
✅ Ensures timely alerts for missing datasets.
✅ Provides a clear, auditable log for reporting.
✅ Demonstrates hands-on skills with Zapier, JavaScript, workflow automation, and cloud storage validation

**Learning & AI Assistance**

I used AI tools to learn, experiment, and get guidance while building this workflow, but the idea, approach, problem-solving, and implementation were entirely my own.
