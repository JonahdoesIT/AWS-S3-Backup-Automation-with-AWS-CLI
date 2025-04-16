# AWS-S3-Backup-Automation-with-AWS-CLI
This project automates the backup of local files to an AWS S3 bucket using a Bash script and the AWS Command Line Interface (CLI). It checks the bucket’s access level, uploads files, logs results to a report, and includes resource cleanup.
## 📸 Screenshots

To enhance clarity and show your workflow, include screenshots for each of the steps below:

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

### ✅ Step 1: Install AWS CLI

1. Download the AWS CLI v2 for Windows:  
   [https://awscli.amazonaws.com/AWSCLIV2.msi](https://awscli.amazonaws.com/AWSCLIV2.msi)
![1 AWS CLI](https://github.com/user-attachments/assets/97faf379-704c-4556-8869-23a1bb048582)
![2 AWS CLI FINISH SETUP](https://github.com/user-attachments/assets/5affb7c7-5c1f-40ac-83ac-f29f3e6e5e46)


2. Install using the wizard and verify with:
aws --version
![3 AWS CLI DOWNLOAD CONFIRM](https://github.com/user-attachments/assets/3042b03d-05aa-4526-817d-4850a07fc031)

