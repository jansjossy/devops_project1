# devops_project1
# DevOps Internship - Final Project 1: Self-Healing Infrastructure
**User:** Jans

## 1. Architecture
- **Target Service:** Nginx (Localhost:80)
- **Monitoring:** Prometheus scrapes Nginx uptime every 5s.
- **Alerting Engine:** Alertmanager receives failure signals and triggers a webhook.
- **Remediation:** A Python/Flask webhook listener receives the POST request and executes an Ansible playbook (`heal.yml`) to restore the service.

## 2. Thresholds & Rules
- **Condition:** `up{job="nginx"} == 0`
- **Duration:** 5 seconds (Threshold before firing).

## 3. Evidence
- Configured `prometheus.yml`, `rules.yml`, and `alertmanager.yml`.
- Wrote an idempotent Ansible playbook to enforce Nginx uptime.
<img width="953" height="1020" alt="Screenshot 2026-02-17 123926" src="https://github.com/user-attachments/assets/7c1d8d7f-5942-4675-8df0-195af43167cb" />
<img width="953" height="1020" alt="Screenshot 2026-02-17 123923" src="https://github.com/user-attachments/assets/2ba267b7-2117-4f0b-ab5f-b64a9bc699ab" />
<img width="957" height="1020" alt="Screenshot 2026-02-17 123846" src="https://github.com/user-attachments/assets/134d1899-f973-4cc4-a19c-2af6ef0ec011" />
<img width="930" height="762" alt="Screenshot 2026-02-17 123837" src="https://github.com/user-attachments/assets/2795758d-15c2-49a2-9877-75e857b3aae9" />
<img width="965" height="1020" alt="Screenshot 2026-02-17 123748" src="https://github.com/user-attachments/assets/8f4f00b5-3d8e-463a-8cbc-7f843796f53a" />
<img width="965" height="1020" alt="Screenshot 2026-02-17 123729" src="https://github.com/user-attachments/assets/f2a90261-f7da-48b0-a3c5-2bef662f4b6e" />
<img width="965" height="1020" alt="Screenshot 2026-02-17 123709" src="https://github.com/user-attachments/assets/abf4f142-eb5a-4bdf-b03c-9ed4cf258cb7" />
<img width="965" height="1020" alt="Screenshot 2026-02-17 123617" src="https://github.com/user-attachments/assets/1912fd5f-2d38-49c0-be4c-4fbd7fc41c38" />
<img width="965" height="1020" alt="Screenshot 2026-02-17 123558" src="https://github.com/user-attachments/assets/3ae5ae46-359d-499c-844f-97c87da77222" />
<img width="965" height="1020" alt="Screenshot 2026-02-17 123534" src="https://github.com/user-attachments/assets/037be28a-b4cd-490e-b4ba-2ca8304487cf" />
<img width="953" height="1020" alt="Screenshot 2026-02-17 115107" src="https://github.com/user-attachments/assets/347988e3-6611-40a8-818d-452a0b42d370" />
<img width="822" height="762" alt="Screenshot 2026-02-17 114421" src="https://github.com/user-attachments/assets/b4754e2c-5988-467f-ace9-46de22fb69d3" />
<img width="894" height="762" alt="Screenshot 2026-02-17 113002" src="https://github.com/user-attachments/assets/d41c80d5-35be-4c8b-a27f-9152be255caa" />
