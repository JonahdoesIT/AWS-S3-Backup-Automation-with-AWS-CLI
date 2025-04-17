# AWS-S3-Backup-Automation-with-AWS-CLI
This project automates the backup of local files to an AWS S3 bucket using a Bash script and the AWS Command Line Interface (CLI). It checks the bucket’s access level, uploads files, logs results to a report, and includes resource cleanup.
## 📸 Screenshots


- 🧑‍💻 AWS CLI configuration – `/screenshots/aws-cli-setup/`
- 🪣 S3 bucket creation & listing – `/screenshots/s3-bucket-creation/`
- 📁 Local file creation – `/screenshots/local-files-setup/`
- 🧾 Script setup & execution – `/screenshots/script-execution/`
- 🔍 S3 verification (CLI & browser) – `/screenshots/s3-verification/`
- 🧹 Cleanup – `/screenshots/cleanup/`
## 🛠️ Tools & Technologies Used

- AWS CLI (v2)
- Amazon S3
- Bash scripting
- Git Bash (for Unix-like terminal on Windows)
- PowerShell or Terminal
- Optional: AWS Console for verification
## 🚀 Step-by-Step Walkthrough

---

### 🛠️ Step 1: Install AWS CLI

✅ 1. Download the AWS CLI v2 for Windows:  
   [https://awscli.amazonaws.com/AWSCLIV2.msi](https://awscli.amazonaws.com/AWSCLIV2.msi)
![1 AWS CLI](https://github.com/user-attachments/assets/97faf379-704c-4556-8869-23a1bb048582)
✅ 2. Run the installer and follow the prompts to complete installation.
![2 AWS CLI FINISH SETUP](https://github.com/user-attachments/assets/5affb7c7-5c1f-40ac-83ac-f29f3e6e5e46)
✅ 3. Verify installation in the terminal:
   aws --version
![3 AWS CLI DOWNLOAD CONFIRM](https://github.com/user-attachments/assets/3042b03d-05aa-4526-817d-4850a07fc031)
## 🚀 Step 2: Configure AWS CLI Credentials

Once the AWS CLI is installed, configure it with your AWS account credentials so you can manage resources from the command line.
### ✅1. Open Your Terminal

- On Windows: Open **Command Prompt**, **PowerShell**, or **Windows Terminal**.
- On Mac: Open **Terminal**.
- On Linux: Open your preferred terminal app.

### ✅2. Run the Configuration Command

Type: aws configure
![4 AWS CLI CONFIGURE](https://github.com/user-attachments/assets/4953d688-5e5c-440e-b758-c9506204b532)
You will need your

-Access key ID
-Secret Access key
-Default region
-Default output format

When you run "aws configure", your credentials and settings are saved to:

- **Windows:**
C:\Users\<YourUsername>\.aws\credentials
You can view the contents with powershell

$HOME\.aws\credentials
⚠️ Important: These credentials are saved in plain text. Never upload this file to GitHub. Use .gitignore to exclude it if needed.

## 📦 Step 3: S3 Bucket Creation
To create the S3 bucket for file backups, use the AWS CLI:
aws s3 mb s3://jarvis-s3-backup-lab-2025 
![5 AWS s3 Bucket creation](https://github.com/user-attachments/assets/5731ffaa-7f7c-420e-95c1-3f8ab20fcb3e)
We can confirm the bucket was created by running s3 ls
![6 CONFIRM S3 BUCKET WAS CREATED](https://github.com/user-attachments/assets/6072231c-5bca-4351-802f-844848d9ab19)

## 📁 Step 4: Create Local Files to Upload
To simulate a real backup scenario, we'll create a directory with a couple of test files. These will later be uploaded to the S3 bucket.
### ✅ 1. Create a Local Backup Directory

Open your terminal (PowerShell or Command Prompt) and run:
mkdir files-to-backup

✅ 2. Create Sample Files in That Directory
Use these commands to add content to the files:

bash
echo Sample content for File 1 > files-to-backup/file1.txt
echo Sample content for File 2 > files-to-backup/file2.txt
These simulate basic logs, config files, or document backups

![7 MKDIR SAMPLE CONTENT](https://github.com/user-attachments/assets/b5d4f862-da56-49da-b6b8-e368e187093c)

## 🧾 Step 5: Create & Run S3 Backup Script

This step creates a Bash script that automates:
- Verifying if the S3 bucket is public or private
- Uploading files from the files-to-backup folder
- Verifying uploads
- Writing a report to upload_report.txt
![7Create script in notepad](https://github.com/user-attachments/assets/8ae56fed-7680-475d-aa78-2f938cfb0864)
![8 Save script](https://github.com/user-attachments/assets/fe38ba3a-c0a1-427a-820b-270cd6341fc0)
After saving our script we will need to change the permissions to make it executable.
![9 Chmod and run script](https://github.com/user-attachments/assets/0966ad2d-04f7-4324-a4f9-9a6b2030b7b8)

## 🚀 Step 6: Verify Output
After running the script with:./s3_backup.sh

You should see terminal output indicating the script has executed successfully, followed by the creation of a file named: upload_report.txt

This file contains:

✅ The current ACL (Access Control List) status of the S3 bucket

✅ A log of each uploaded file (including the source and destination)

✅ A verification list showing the uploaded files in the S3 bucket
![10 script ran successfuly  output file](https://github.com/user-attachments/assets/2b581d23-933a-4c6d-b1c3-647c8c743d82)

## 🔍 Step 7: Validate in AWS Console & Test Public Access
After running the backup script and generating upload_report.txt, use these steps to manually verify the files in AWS and test access behavior.
✅ 1. List Files in Your S3 Bucket

To confirm the files are really there:
aws s3 ls s3://jarvis-s3-backup-lab-2025
![11 confirm files were uploaded via cli](https://github.com/user-attachments/assets/d3c76de7-5009-4b1d-94d8-69bd391faff3)

✅ 2. Check Bucket ACL (Access Control List)
Use the following command to review the permissions assigned to your S3 bucket: aws s3api get-bucket-acl --bucket jarvis-s3-backup-lab-2025

![12 s3 access = private](https://github.com/user-attachments/assets/a4a38160-8bce-4284-b71c-3612b6d27092)

This command returns the Access Control List (ACL), which includes:

✅The bucket owner

✅Any grants given to other users or groups

✅Whether the bucket is private or public

## 🧹 Step 8: Clean Up AWS Resources
To avoid unwanted charges and keep our AWS environment clean, we will delete the resources you created during this lab.
✅ 1. Delete the Files From the S3 Bucket

This command will remove all files you uploaded:
aws s3 rm s3://jarvis-s3-backup-2025 --recursive

✅2. After removing the files time to delete the bucket:
aws s3 rb s3://jarvis-s3-backup-2025

![14 remove files and bucket- cleanup](https://github.com/user-attachments/assets/757c6d4a-f12e-4c75-9493-8fadc5bfa610)

## 🧾 Step 9: Final Summary

This project demonstrates the automation of secure file backups to Amazon S3 using Bash and the AWS CLI. Key skills covered:

---

### 🧠 What I Learned

- How to install and configure AWS CLI on Windows
- How to create and manage S3 buckets using the CLI
- How to automate cloud operations with Bash scripting
- How to verify security settings (ACL & bucket policy)
- How to validate file uploads via CLI and browser
- How to responsibly clean up cloud resources to avoid charges

