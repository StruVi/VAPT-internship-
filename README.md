# VAPT-internship-
# 🛡️ Web Application Vulnerability Assessment and Penetration Testing (VAPT)

## 📌 Project Overview
This project involves performing a **Vulnerability Assessment and Penetration Testing (VAPT)** on the **OWASP Juice Shop** application. The goal is to identify and mitigate critical vulnerabilities such as **SQL Injection**, **Open Redirects**, and **Insecure Configurations** while documenting the findings in a professional report.

## 📊 Project Structure
```
📂 VAPT-Capstone-Project
├── 📜 README.md (This file)
├── 📂 Reports (Detailed VAPT Report + Scan Outputs)
│      └── VAPT_Vulnerability_Report.pdf
├── 📂 Screenshots (Evidence of Vulnerabilities)

```

## 🔍 Tools & Technologies Used
- **Nmap**: Network scanning and service detection
- **OWASP ZAP**: Web application vulnerability scanning
- **Docker**: Running OWASP Juice Shop securely in a local environment
- **Git & GitHub**: Version control and documentation

## 🛠️ Setup Instructions

### 1. Prerequisites
Ensure the following tools are installed:
- Docker
- Nmap
- OWASP ZAP
- Git

### 2. Clone the Repository
```bash
git clone https://github.com/your-username/VAPT-Capstone-Project.git
cd VAPT-Capstone-Project
```

### 3. Run OWASP Juice Shop
Ensure Docker is installed and running. Execute the following command to launch the Juice Shop container:

```bash
docker pull bkimminich/juice-shop
docker run -d -p 3000:3000 bkimminich/juice-shop
```
Access the application at: [http://localhost:3000](http://localhost:3000)

### 4. Perform Scanning

1. **Nmap Scan**
```bash
nmap -A -p 3000 --script vuln localhost > Reports/nmap_report.txt
```

2. **OWASP ZAP Scan** (GUI or headless mode)
```bash
zap.sh -cmd -quickurl http://localhost:3000 -quickout Reports/zap_report.html
```

## 📄 Findings Summary

| Vulnerability                  | Severity  | Mitigation                           |
|---------------------------------|-----------|-------------------------------------|
| SQL Injection (Time & Error)    | High      | Use parameterized queries, input validation |
| Open Redirect                   | High      | Validate and whitelist redirect URLs  |
| Content Security Policy (CSP)   | Medium    | Implement a strict CSP header         |
| Session ID in URL               | Medium    | Use secure cookies, avoid URL-based sessions |
| Information Disclosure (Private IP) | Low  | Sanitize server error responses       |

## Key Screenshots
1. **SQL Injection Evidence** - Extracted database content
2. **Open Redirect Proof** - Unvalidated redirection to external sites
3. **Missing Security Headers** - Lack of CSP and HSTS

## Security Recommendations
1. Implement **parameterized queries** to prevent SQL Injection.
2. Restrict redirects using a **whitelist** to mitigate Open Redirect.
3. Add **security headers** like `Content-Security-Policy` and `Strict-Transport-Security`.
4. Perform **regular security audits** using automated tools.

## Future Scope
- **API Security Testing**: Extend the scope to API endpoints.
- **Automation**: Set up CI/CD pipelines for automated VAPT.
- **Advanced Attacks**: Test for logic flaws and privilege escalation.

## Contributors
- Aswin Vibushan – B4 AICTE Cybersecurity Internship (Edunet Foundation)

## License
This project is licensed under the **MIT License**.

---


