# Lotto-ML: Machine Learning für Lottozahlen-Vorhersagen

## 📌 Projektübersicht

Diese Anwendung nutzt Machine Learning, um Wahrscheinlichkeiten für zukünftige Lottozahlen zu berechnen. Die App ruft die letzten Ziehungen von einer externen API (z. B. Swisslos) ab und berechnet basierend auf verschiedenen Algorithmen die Wahrscheinlichkeiten für jede Zahl.

---

## 📐 Architektur & Komponenten

Die Anwendung besteht aus mehreren Komponenten, die in einem **modularen Ansatz** entwickelt werden:

### **1️⃣ FastAPI (Backend & ML-Berechnungen)**

- Stellt eine REST-API bereit, um Lottozahlen und Statistiken zu berechnen
- Holt Ziehungsdaten von einer externen API
- Führt Machine Learning-Modelle zur Wahrscheinlichkeitsberechnung aus

### **2️⃣ Streamlit (Frontend & UI)**

- Bietet eine einfache Benutzeroberfläche für die Anzeige von Wahrscheinlichkeiten
- Ermöglicht die Auswahl des Lottoformats (z. B. 6 aus 49, Eurojackpot)
- Kommuniziert mit FastAPI zur Datenverarbeitung

### **3️⃣ Machine Learning-Modell**

- Kombination aus:
  - Häufigkeitsanalyse (Statistik vergangener Zahlen)
  - Wahrscheinlichkeitsmodell (Poisson/Markov-Prozesse)
  - Random Forest für Mustererkennung
- Modelle sind dynamisch je nach Lottoformat auswählbar

### **4️⃣ CI/CD (Automatisiertes Testing & Deployment)**

- **GitHub Actions** für automatische Tests & Builds
- Automatische Code-Qualitätsprüfung
- Unit-Tests mit Pytest
- Nutzt eine `requirements-lock.txt` für stabile Abhängigkeiten
- Erweiterbar für Docker & Deployment

---

## 🛠 CI/CD-Setup (Automatisierte Tests & Code-Qualität)

### **📌 CI/CD-Workflow mit GitHub Actions**

1. **Code Push zu GitHub (Trigger) auf ****`main`**** oder ****`develop`**
2. **Automatische Tests starten:**
   - ✅ **Linting (****`flake8`****) zur Code-Qualitätsprüfung**
   - ✅ **Unit-Tests (****`pytest`****) zur Funktionalitätsprüfung**
3. **Fehlgeschlagene Pipelines blockieren das Merge**
4. **GitHub Actions nutzt ausschließlich ****`requirements-lock.txt`**** für Abhängigkeiten**
5. **Erweiterbar: Docker-Build & Deployment**

### **📌 GitHub Actions Workflow**

In `.github/workflows/main.yml` ist die CI/CD-Pipeline definiert:

- **Linting mit ****`flake8`** (Code-Qualität prüfen)
- **Unit-Tests mit ****`pytest`** (Funktionalität sicherstellen)
- **Nutzt ****`requirements-lock.txt`**** für Abhängigkeitsmanagement**
- **Vorbereitung für zukünftiges Docker-Building**

---

## 📅 Nächster Schritt



✅ Finalisierung der CI/CD-Pipeline mit Tests & Linting

✅ GitHub Actions auf requirements-lock.txt umgestellt

🕒 Docker-Setup & Build-Pipeline folgen als nächster Schritt

---

📢 Dieses Readme wird regelmäßig mit den neuesten Fortschritten aktualisiert! 🚀





