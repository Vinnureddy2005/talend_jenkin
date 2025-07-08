# Talend CI/CD Pipeline using Jenkins + GitHub

This project demonstrates a complete CI/CD workflow to execute a Talend ETL job using GitHub, Jenkins, and shell scripts.

## 📦 Tech Stack
- Talend Open Studio
- Jenkins (Pipeline + Git Plugins)
- GitHub (Repo + Webhook)
- Java 17+
- Ngrok (for webhook tunnel)

## 📄 Job Description
Reads a CSV file (`customers.csv`) and logs each row using `tLogRow`.

### Talend Components:
- `tFileInputDelimited`
- `tLogRow`

### Sample CSV:
id,name,email
1,John Doe,john@example.com
2,Jane Smith,jane@example.com
3,Alex Ray,alex@example.com


## 🔁 CI/CD Pipeline

### Steps:
1. Talend job is exported as `CustomerLoggerJob.zip`
2. Jenkins pipeline:
    - Clones the repo
    - Unzips the job
    - Runs `jenkins_run.sh` with CSV path as parameter
3. GitHub Webhook triggers the Jenkins job on each push

## ⚙️ Jenkins Parameters

| Name            | Description                        | Default Value                                     |
|-----------------|------------------------------------|--------------------------------------------------|
| `CSV_FILE_PATH` | Local path to the input CSV file   | `/Users/vineeshreddy/Downloads/customers.csv`   |

## ✅ Sample Output
1|John Doe|john@example.com
2|Jane Smith|jane@example.com
3|Alex Ray|alex@example.com

## 👨‍💻 Author
Vineesh Reddy – July 2025
