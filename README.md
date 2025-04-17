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

### 🛠️ Step 1: Install AWS CLI

1. Download the AWS CLI v2 for Windows:  
   [https://awscli.amazonaws.com/AWSCLIV2.msi](https://awscli.amazonaws.com/AWSCLIV2.msi)
![1 AWS CLI](https://github.com/user-attachments/assets/97faf379-704c-4556-8869-23a1bb048582)
2. Run the installer and follow the prompts to complete installation.
![2 AWS CLI FINISH SETUP](https://github.com/user-attachments/assets/5affb7c7-5c1f-40ac-83ac-f29f3e6e5e46)
3. Verify installation in the terminal:
   aws --version
![3 AWS CLI DOWNLOAD CONFIRM](https://github.com/user-attachments/assets/3042b03d-05aa-4526-817d-4850a07fc031)
## 🚀 Step 2: Configure AWS CLI Credentials

Once the AWS CLI is installed, configure it with your AWS account credentials so you can manage resources from the command line.
### 1. Open Your Terminal

- On Windows: Open **Command Prompt**, **PowerShell**, or **Windows Terminal**.
- On Mac: Open **Terminal**.
- On Linux: Open your preferred terminal app.

### 2. Run the Configuration Command

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

