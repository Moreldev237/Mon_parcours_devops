# 🐧 Linux pour DevOps - Les Fondations

![Linux DevOps](https://img.shields.io/badge/Linux-DevOps_Foundation-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![Niveau](https://img.shields.io/badge/Niveau-Fondamental-green)
![Pratique](https://img.shields.io/badge/100%25-Pratique-blue)

## 📖 Table des Matières
- [🎯 Pourquoi Linux en DevOps?](#-pourquoi-linux-en-devops)
- [🚀 Problèmes Résolus](#-problèmes-résolus)
- [🔧 Compétences Clés](#-compétences-clés)
- [📁 Structure des Projets Linux](#-structure-des-projets-linux)
- [🏗️ Projet 1 : Mastery des Commandes](#️-projet-1--mastery-des-commandes)
- [🔍 Projet 2 : Analyse Système](#-projet-2--analyse-système)
- [⚙️ Projet 3 : Automatisation Bash](#️-projet-3--automatisation-bash)
- [🔒 Projet 4 : Sécurité Serveur](#-projet-4--sécurité-serveur)
- [🐳 Projet 5 : Environnement Docker](#-projet-5--environnement-docker)
- [📊 Métriques d'Évaluation](#-métriques-dévaluation)
- [🎓 Pour les Formateurs](#-pour-les-formateurs)
- [📚 Ressources](#-ressources)

## 🎯 Pourquoi Linux en DevOps?

### **La Réalité du Terrain**
```bash
# 90% des serveurs mondiaux tournent sous Linux
# 100% des top 500 supercalculateurs utilisent Linux
# Tous les outils DevOps majeurs sont Linux-first
```

### **6 Raisons Fondamentales**

| Raison | Impact DevOps | Exemple Concret |
|--------|--------------|-----------------|
| **1. Conteneurs Natifs** | Docker/K8s sont Linux natifs | `docker run` = isolation Linux |
| **2. Automatisation** | Scripting puissant (Bash) | CI/CD pipelines |
| **3. Performance** | Léger, stable, performant | Moindre coût cloud |
| **4. Communauté** | Support massif open-source | Résolution rapide des bugs |
| **5. Sécurité** | Contrôle granulaire | CIS Benchmarks |
| **6. Cloud Native** | AWS/Azure/GCP = Linux | AMI, VM, containers |

## 🚀 Problèmes Résolus par Linux

### **Problème 1 : Incompatibilité des Environnements**
```bash
# AVANT : "Ça marche sur ma machine"
$ npm start  # ✅ Local
$ npm start  # ❌ Production

# APRÈS : Linux uniformise
$ docker build -t app .  # ✅ Build une fois
$ docker run app         # ✅ Tourne partout
```

### **Problème 2 : Coûts de Licence**
```
Windows Server : ~$1,000/serveur/an
Linux (RHEL)   : ~$349/serveur/an
Linux (Ubuntu) : $0 🎉
```

### **Problème 3 : Automatisation Limitée**
```bash
# PowerShell vs Bash
Get-ChildItem -Recurse | Where-Object {...}  # ❌ Complexe
find . -name "*.log" -type f                 # ✅ Simple & puissant
```

### **Problème 4 : Monitoring Fragile**
```bash
# Windows : WMI compliqué
# Linux   : Tout est un fichier !
cat /proc/meminfo      # Mémoire
cat /proc/cpuinfo      # CPU
cat /proc/loadavg      # Charge système
```

## 🔧 Compétences Clés Linux pour DevOps

### **Niveau 1 : Survie (Junior DevOps)**
```bash
✅ Navigation système (cd, ls, pwd)
✅ Gestion fichiers (cp, mv, rm, chmod)
✅ Processus (ps, top, kill)
✅ Édition (vim/nano)
✅ Réseau (ping, curl, netstat)
```

### **Niveau 2 : Opérationnel (Mid DevOps)**
```bash
⭐ Scripting Bash
⭐ Gestion services (systemd)
⭐ Monitoring (journalctl, sar)
⭐ SSH avancé (keys, tunneling)
⭐ Performance (iotop, vmstat)
```

### **Niveau 3 : Expert (Senior DevOps)**
```bash
🔥 Kernel tuning (sysctl)
🔥 Debugging avancé (strace, perf)
🔥 Sécurité (SELinux, AppArmor)
🔥 Container internals (cgroups, namespaces)
🔥 Automation avancée (Ansible modules)
```

## 📁 Structure des Projets Linux

```
linux-devops-mastery/
├── 📁 01-command-mastery/
│   ├── challenges/
│   │   ├── file_management.sh
│   │   ├── text_processing.sh
│   │   └── system_info.sh
│   └── solutions/
│
├── 📁 02-system-analysis/
│   ├── monitoring-scripts/
│   │   ├── health_check.sh
│   │   ├── resource_monitor.py
│   │   └── alert_system.sh
│   └── dashboards/
│
├── 📁 03-bash-automation/
│   ├── ci-cd-scripts/
│   ├── backup-scripts/
│   └── deployment-scripts/
│
├── 📁 04-server-security/
│   ├── hardening-scripts/
│   ├── audit-scripts/
│   └── compliance-checks/
│
├── 📁 05-docker-environment/
│   ├── docker-setup/
│   ├── container-troubleshooting/
│   └── k8s-preparation/
│
└── 📁 labs/
    ├── lab1-basics/
    ├── lab2-networking/
    ├── lab3-storage/
    └── lab4-security/
```

## 🏗️ Projet 1 : Mastery des Commandes

### **Objectif** : Maîtriser 100+ commandes essentielles
```bash
# Challenge : Fichier de 10,000 lignes
$ cat large_file.log | command_magic > result.txt

# Solution DevOps :
$ grep "ERROR" large_file.log | awk '{print $2}' | sort | uniq -c | sort -nr
```

### **Commandes DevOps Critiques**
```bash
# 1. Debugging conteneurs
$ docker inspect <container> | jq '.[].State'
$ kubectl logs -f <pod> --tail=50

# 2. Analyse réseau
$ ss -tulpn | grep :80
$ tcpdump -i eth0 port 443 -w capture.pcap

# 3. Performance
$ perf stat docker run myapp
$ pidstat -d -p $(pgrep docker)
```

### **Exercice Pratique** : 
```bash
# Créer un script qui:
# 1. Trouve tous les fichiers .log modifiés aujourd'hui
# 2. Compte les erreurs par type
# 3. Envoie un rapport Slack si > 100 erreurs
# 4. Archive les vieux logs
```

## 🔍 Projet 2 : Analyse Système

### **Script de Health Check Automatisé**
```bash
#!/bin/bash
# health_check.sh - Monitor système complet

echo "🔍 HEALTH CHECK - $(date)"
echo "========================"

# 1. CPU
LOAD=$(uptime | awk -F'load average:' '{print $2}')
echo "📊 Load Average: $LOAD"

# 2. Mémoire
FREE_MEM=$(free -m | awk 'NR==2{printf "%.2f%%", $3*100/$2}')
echo "💾 Memory Usage: $FREE_MEM"

# 3. Disque
DISK_USAGE=$(df -h / | awk 'NR==2{print $5}')
echo "💿 Disk Usage: $DISK_USAGE"

# 4. Docker
if systemctl is-active --quiet docker; then
    CONTAINERS=$(docker ps -q | wc -l)
    echo "🐳 Running Containers: $CONTAINERS"
fi

# 5. Alerting (exemple Slack)
if [[ "${DISK_USAGE%\%}" -gt 90 ]]; then
    curl -X POST -H 'Content-type: application/json' \
    --data "{\"text\":\"🚨 Disk usage > 90% on $(hostname)\"}" \
    $SLACK_WEBHOOK
fi
```

## ⚙️ Projet 3 : Automatisation Bash

### **Pipeline CI/CD Local Simulé**
```bash
#!/bin/bash
# ci-pipeline.sh - Pipeline DevOps complet

set -e  # Exit on error

echo "🚀 Starting CI/CD Pipeline"
echo "=========================="

# Phase 1: Code Quality
echo "📝 Running Linters..."
find . -name "*.sh" -exec shellcheck {} \;
find . -name "*.py" -exec pylint {} \;

# Phase 2: Tests
echo "🧪 Running Tests..."
docker build -t app-test -f Dockerfile.test .
docker run --rm app-test pytest

# Phase 3: Security Scan
echo "🔒 Security Scanning..."
trivy image app-test
gitleaks detect --source . -v

# Phase 4: Build
echo "🏗️ Building Application..."
docker build -t app:latest .

# Phase 5: Deploy (Simulation)
echo "🚀 Deploying..."
if [[ "$ENVIRONMENT" == "prod" ]]; then
    kubectl apply -f k8s/production/
else
    kubectl apply -f k8s/staging/
fi

echo "✅ Pipeline completed successfully!"
```

## 🔒 Projet 4 : Sécurité Serveur

### **Hardening Script Automatisé**
```bash
#!/bin/bash
# server_hardening.sh - Sécurisation automatique

echo "🛡️  Server Hardening Script"
echo "============================"

# 1. Mise à jour système
apt update && apt upgrade -y

# 2. Configuration SSH
sed -i 's/#PermitRootLogin yes/PermitRootLogin no/' /etc/ssh/sshd_config
sed -i 's/PasswordAuthentication yes/PasswordAuthentication no/' /etc/ssh/sshd_config
echo "AllowUsers devops-user" >> /etc/ssh/sshd_config

# 3. Configuration Firewall
ufw default deny incoming
ufw default allow outgoing
ufw allow ssh
ufw allow 443/tcp
ufw --force enable

# 4. Audit logging
apt install -y auditd
auditctl -e 1

# 5. Docker Security
cat > /etc/docker/daemon.json << EOF
{
  "userns-remap": "default",
  "log-driver": "json-file",
  "log-opts": {
    "max-size": "10m",
    "max-file": "3"
  },
  "live-restore": true
}
EOF

# 6. Monitoring installation
apt install -y prometheus-node-exporter

echo "✅ Hardening completed. Reboot recommended."
```

## 🐳 Projet 5 : Environnement Docker

### **Setup Docker Optimisé pour DevOps**
```bash
#!/bin/bash
# docker-devops-setup.sh

echo "🐳 Docker DevOps Environment Setup"
echo "=================================="

# Installation Docker
curl -fsSL https://get.docker.com -o get-docker.sh
sh get-docker.sh

# Docker Compose
curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
chmod +x /usr/local/bin/docker-compose

# Docker non-root user
usermod -aG docker $USER

# Configuration pour production
mkdir -p /etc/docker
cat > /etc/docker/daemon.json << EOF
{
  "data-root": "/var/lib/docker",
  "log-driver": "json-file",
  "log-opts": {
    "max-size": "10m",
    "max-file": "3"
  },
  "storage-driver": "overlay2",
  "iptables": true,
  "ip-forward": true,
  "metrics-addr": "0.0.0.0:9323",
  "experimental": false
}
EOF

# Outils DevOps
docker run -d --name portainer --restart always \
  -p 9000:9000 \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -v portainer_data:/data \
  portainer/portainer-ce

echo "✅ Docker DevOps setup complete!"
echo "📊 Portainer: http://localhost:9000"
```

## 📊 Métriques d'Évaluation

### **Checklist de Compétences**
```bash
# Score votre niveau (/100 points)
# Chaque compétence = 5 points

□ 01. Navigation système fluide (cd, ls, pwd, find)
□ 02. Gestion permissions (chmod, chown, umask)
□ 03. Process monitoring (ps, top, htop, kill)
□ 04. Network debugging (netstat, ss, tcpdump, curl)
□ 05. Disk management (df, du, fdisk, mount)
□ 06. Text processing (grep, sed, awk, cut, sort)
□ 07. Bash scripting (variables, loops, functions)
□ 08. Service management (systemctl, journalctl)
□ 09. Package management (apt, yum, dpkg, rpm)
□ 10. User management (useradd, passwd, sudo)
□ 11. Cron jobs & automation
□ 12. SSH key management & tunneling
□ 13. Log analysis & rotation
□ 14. Kernel modules & parameters
□ 15. Container basics (docker, podman)
□ 16. Security basics (firewall, fail2ban)
□ 17. Performance tuning
□ 18. Backup & recovery
□ 19. Troubleshooting methodology
□ 20. Documentation & knowledge sharing
```

### **Certifications Recommandées**
1. **Linux Foundation Certified System Administrator (LFCS)**
2. **Red Hat Certified System Administrator (RHCSA)**
3. **CompTIA Linux+**

## 🎓 Pour les Formateurs

### **Structure du Module Linux**
```
Semaine 1: Bases & Navigation
├── Système de fichiers
├── Commandes essentielles
└── Gestion des processus

Semaine 2: Scripting & Automation
├── Bash scripting
├── Outils texte (grep, awk, sed)
└── Cron & scheduling

Semaine 3: Administration Système
├── Gestion utilisateurs
├── Services systemd
└── Monitoring de base

Semaine 4: DevOps Spécifique
├── Environnement Docker
├── Debugging production
└── Sécurité serveur
```

### **Exercices Pratiques pour la Classe**
```bash
# Exercice 1: Trouver la fuite mémoire
# Donné: Serveur lent, mémoire pleine
# Trouver: Process coupable et solution

# Exercice 2: Debugger un service web
# Donné: Nginx retourne 502
# Trouver: Cause et fixer

# Exercice 3: Automatiser un déploiement
# Créer un script qui:
# 1. Pull le code
# 2. Build l'image
# 3. Test
# 4. Déploie
```

### **Évaluation des Élèves**
- **40%** : Projets pratiques
- **30%** : Examens techniques
- **20%** : Participation aux labs
- **10%** : Documentation écrite

## 📚 Ressources

### **Livres Essentiels**
1. **"The Linux Command Line"** - William Shotts
2. **"How Linux Works"** - Brian Ward
3. **"Bash Cookbook"** - Carl Albing

### **Cours en Ligne**
- [Linux Foundation Courses](https://training.linuxfoundation.org)
- [Coursera: Linux for Developers](https://www.coursera.org/learn/linux-for-developers)
- [Udemy: Linux Mastery](https://www.udemy.com/course/linux-mastery/)

### **Communautés**
- [r/linuxadmin](https://www.reddit.com/r/linuxadmin/)
- [Stack Overflow Linux](https://stackoverflow.com/questions/tagged/linux)
- [DevOps Discord Communities](https://discord.gg/devops)

### **Outils Pratiques**
```bash
# Pour l'apprentissage
$ watch -n 1 'ps aux --sort=-%mem | head -10'
$ alias ll='ls -la'
$ export HISTTIMEFORMAT="%d/%m/%y %T "

# Pour le monitoring
$ sudo apt install htop iotop iftop nmon
```

---

## 🎯 Prochaines Étapes

Après avoir maîtrisé Linux, passez à:

1. **[🐳 Docker & Conteneurs](./02-docker-basics/README.md)**
2. **[☸️ Kubernetes Fundamentals](./03-kubernetes/README.md)**
3. **[🔄 CI/CD avec GitHub Actions](./04-ci-cd/README.md)**

---

**⚠️ Rappel Important** : Linux n'est pas un outil optionnel en DevOps, c'est **LA FONDATION**. Tout ce que vous construirez ensuite (containers, Kubernetes, cloud) repose sur ces compétences.

**🌟 Conseil** : Passez au moins 2-3 semaines sur Linux avant de continuer. Une fondation solide vous sauvera des heures de debugging plus tard!

---

**💡 Astuce du Jour** : 
```bash
# Créez un fichier .bashrc avec vos alias DevOps
echo "alias k='kubectl'" >> ~/.bashrc
echo "alias d='docker'" >> ~/.bashrc
echo "alias tf='terraform'" >> ~/.bashrc
source ~/.bashrc
```

*"Maîtrisez Linux, et le reste du DevOps suivra naturellement."*

---
**📅 Prochain Module** : [Docker & Containerization](./02-docker-basics/README.md)

*Dernière mise à jour: $(date)*