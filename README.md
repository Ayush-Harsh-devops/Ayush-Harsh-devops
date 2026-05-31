<div align="center">

<img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&size=32&duration=3000&pause=1000&color=00F7FF&center=true&vCenter=true&width=600&lines=Hi+%F0%9F%91%8B+I'm+Ayush+Harsh;DevOps+%26+Cloud+Engineer;AWS+%7C+Azure+%7C+Kubernetes;Terraform+%7C+CI%2FCD+%7C+MLOps;Automating+Everything" alt="Typing SVG" />

<br/>

[![AWS](https://img.shields.io/badge/AWS_SAA--C03-Certified-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white)](https://www.credly.com/badges/cd40f64f-115b-408c-8fad-feb52e049c51)
[![Azure](https://img.shields.io/badge/Azure_AZ--104-Certified-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white)](https://learn.microsoft.com/en-in/users/ayushharsh-2978/credentials/6b535bcb3b78debd)
[![GitHub](https://img.shields.io/badge/GitHub-Ayush--Harsh--devops-181717?style=for-the-badge&logo=github)](https://github.com/Ayush-Harsh-devops)
[![Email](https://img.shields.io/badge/Email-harsh4ayush85%40gmail.com-D14836?style=for-the-badge&logo=gmail)](mailto:harsh4ayush85@gmail.com)

</div>

---

## 👨‍💻 About Me

```bash
$ whoami
Ayush Harsh — DevOps & Cloud Engineer

$ cat skills.txt
Cloud       : AWS (SAA-C03) · Azure (AZ-104)
IaC         : Terraform · Ansible
Containers  : Docker · Kubernetes · Helm
CI/CD       : Jenkins · GitHub Actions · ArgoCD
Monitoring  : Prometheus · Grafana · Alertmanager · Loki
MLOps       : MLflow · FastAPI · Scikit-learn
OS          : Linux (Ubuntu) · Bash scripting

$ cat current_focus.txt
→ Production-grade Kubernetes & GitOps
→ Platform Engineering
→ ML Pipelines on EKS with MLflow
→ Infrastructure Automation at scale
```

---

## 🛠️ Tech Stack

<div align="center">

**Cloud & IaC**

<img src="https://skillicons.dev/icons?i=aws,azure,gcp,terraform,ansible" />

**Containers & Orchestration**

<img src="https://skillicons.dev/icons?i=docker,kubernetes,helm,githubactions,jenkins" />

**Languages & APIs**

<img src="https://skillicons.dev/icons?i=python,fastapi,bash,go" />

**Monitoring & Observability**

<img src="https://skillicons.dev/icons?i=prometheus,grafana" />

> Alertmanager · Loki · Promtail · cAdvisor · Node Exporter

**Tools & OS**

<img src="https://skillicons.dev/icons?i=linux,ubuntu,git,github,vscode" />

</div>

---

## 📌 Featured Projects

> 🔗 [github.com/Ayush-Harsh-devops/devops-project](https://github.com/Ayush-Harsh-devops/devops-project)

---

### 🔄 01 — CI/CD Complete Pipeline

**Tech Stack:** `Jenkins` `GitHub Actions` `ArgoCD` `AWS EKS` `Docker` `Trivy` `SonarQube`

## 🏗️ Architecture
Code Push → GitHub Actions → Trivy Scan → SonarQube Gate
→ Docker Build   → ECR Push   → ArgoCD GitOps → EKS

| Feature | Detail |
|---------|--------|
| Security | Trivy scan blocks on CRITICAL/HIGH CVEs |
| Quality | SonarQube gate — zero merge on failure |
| Deploy | ArgoCD auto-sync + self-heal |
| Uptime | Zero-downtime rolling updates |
| Alerts | Slack notifications on every build |

---

### 🌍 02 — IaC Multi-Environment AWS Terraform

**Tech Stack:** `Terraform` `AWS VPC` `EKS` `RDS` `KMS` `Secrets Manager`
## 🏗️ Architecture
modules/
├── vpc  → Public/Private subnets, NAT, Flow Logs
├── eks  → Cluster, Node Groups, KMS encryption
└── rds  → PostgreSQL, Multi-AZ, Performance Insights
environments/
├── dev  → t3.medium · SPOT · db.t3.micro
└── prod → t3.large  · ON_DEMAND · Multi-AZ · 30d backup

```bash
# Deploy dev environment
terraform workspace new dev
terraform plan -var-file=environments/dev/terraform.tfvars
terraform apply -var-file=environments/dev/terraform.tfvars
```

---

### ☸️ 03 — Kubernetes E-commerce App

**Tech Stack:** `Helm` `ArgoCD` `PostgreSQL` `Redis` `Prometheus` `AWS ALB`

## 🏗️ Architecture
ALB (HTTPS) → Frontend → Backend(:3000) → PostgreSQL
→ Redis (cache)

| Feature | Detail |
|---------|--------|
| Scaling | HPA 3→10 pods on CPU/Memory |
| Uptime | PodDisruptionBudget min 2 pods |
| Security | Non-root · ReadOnlyRootFS · Drop ALL caps |
| Deploy | Helm + ArgoCD GitOps |

```bash
helm upgrade --install ecommerce k8s/helm/ \
  -f k8s/helm/values.yaml \
  -n ecommerce --create-namespace \
  --atomic --timeout 5m
```

---

### 📊 04 — Monitoring & Observability Stack

**Tech Stack:** `Prometheus` `Grafana` `Alertmanager` `Loki` `cAdvisor` `Node Exporter`

## 🏗️ Architecture
Node Exporter ─→ Prometheus ─→ Grafana Dashboards
cAdvisor      ─→             ─→ Alertmanager ─→ Slack
App metrics   ─→             ─→ Loki (logs)  ─→ Email

| Feature | Detail |
|---------|--------|
| Metrics | CPU · Memory · Disk · Network · Container |
| Alerts | 12 rules — warning + critical levels |
| Routing | Slack `#devops-alerts` + Email on CRITICAL |
| Logs | Loki + Promtail log aggregation |
| Retention | 15 days metrics · 10GB storage cap |

```bash
# Start full stack
chmod +x scripts/setup.sh && ./scripts/setup.sh

# Check active alerts
curl -s http://localhost:9093/api/v2/alerts | \
  jq '.[] | {alert: .labels.alertname, status: .status.state}'
```

---

### 🤖 05 — MLOps Pipeline on Kubernetes

**Tech Stack:** `Python` `MLflow` `FastAPI` `Docker` `AWS EKS` `Prometheus`
## 🏗️ Architecture
Train → MLflow Track → Register → FastAPI Serve
→ Docker Build  → ECR Push → EKS Deploy
→ GitHub Actions CI/CD     → HPA Scale

| Feature | Detail |
|---------|--------|
| Model | House Price Prediction (Scikit-learn) |
| Tracking | MLflow experiment + model registry |
| API | FastAPI `/predict` endpoint |
| Scale | HPA 2→10 pods on CPU |
| Monitor | Prometheus model metrics |

```bash
# Train + track
python train.py

# Test prediction
curl -X POST http://localhost:8000/predict \
  -H "Content-Type: application/json" \
  -d '{"sqft": 1500, "bedrooms": 3, "bathrooms": 2}'
```

---

## 📜 Certifications

| Certification | Badge |
|---------------|-------|
| AWS Solutions Architect Associate (SAA-C03) | [![Credly](https://img.shields.io/badge/Credly-Verify-FF6B00?style=flat&logo=credly)](https://www.credly.com/badges/cd40f64f-115b-408c-8fad-feb52e049c51) |
| Microsoft Azure Administrator (AZ-104) | [![Microsoft](https://img.shields.io/badge/Microsoft-Verify-0078D4?style=flat&logo=microsoft)](https://learn.microsoft.com/en-in/users/ayushharsh-2978/credentials/6b535bcb3b78debd) |

---

## 📈 GitHub Stats

<div align="center">

<img src="https://github-readme-stats.vercel.app/api?username=Ayush-Harsh-devops&show_icons=true&theme=tokyonight&hide_border=true&count_private=true" height="165"/>
<img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Ayush-Harsh-devops&layout=compact&theme=tokyonight&hide_border=true" height="165"/>

<img src="https://github-readme-streak-stats.herokuapp.com/?user=Ayush-Harsh-devops&theme=tokyonight&hide_border=true" />

</div>

---

## 🔥 DevOps Philosophy

```bash
#!/bin/bash
# My Engineering Mindset

while true; do
  Build    → "Automate everything that can be automated"
  Test     → "If it's not tested, it's broken"
  Secure   → "Security is not optional"
  Deploy   → "Zero downtime or it doesn't count"
  Monitor  → "You can't fix what you can't measure"
  Improve  → "Consistency beats perfection"
  sleep 0  # Never stop
done
```

---

<div align="center">

*⭐ If you find these projects useful, please star the repo!*

**📞 +91 7903944895 · 📧 harsh4ayush85@gmail.com**

</div>
