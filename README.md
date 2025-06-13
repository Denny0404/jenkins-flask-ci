# CI/CD Integration Report – Jenkins + GitHub (Webhook-Based)

**Student Name:** Denish Akbari  
**Project Name:** flask-ci-pipeline  
**Trigger Type:** Webhook (via GitHub → Jenkins)  
**Platform:** GitHub Codespaces (code), Jenkins on Windows (CI server)

---

## ✅ Pipeline Stages Implemented

1. **Checkout** – Pulls latest code from GitHub repo
2. **Install Dependencies** – Installs Python Flask using:
   ```bat
   pip install -r requirements.txt
   ```
3. **Build** – Simulated with:
   ```groovy
   echo 'Simulating Flask app build...'
   ```
4. **Test** – Dummy test using:
   ```bat
   curl --version
   ```

---

## 🔧 Tools Used

- **GitHub**: Version control + webhook
- **Jenkins**: CI/CD server
- **Ngrok**: Exposed Jenkins to GitHub via webhook
- **Python/Flask**: App framework
- **Windows + BAT commands**: Jenkins runner environment

---

## ⚠️ Challenges & Solutions

| Problem | Solution |
|--------|----------|
| Jenkins error: `sh not found` | Switched from `sh` to `bat` (Windows shell) |
| Email error: `localhost:25 refused` | Commented out post mail block in Jenkinsfile |
| GitHub webhook not triggering | Solved using Ngrok + GitHub webhook to `/github-webhook/` |

---

## ✅ Outcome

- All pipeline stages executed successfully.
- GitHub pushes automatically triggered Jenkins builds.
- The system works end-to-end.