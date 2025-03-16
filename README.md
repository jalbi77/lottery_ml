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

### **4️⃣ Docker (Containerisierung & Deployment)**
- Trennt Backend & Frontend in eigenständige Container
- Einheitliche Umgebung für Entwicklung & Produktion

### **5️⃣ CI/CD (Automatisiertes Testing & Deployment)**
- **GitHub Actions** für automatische Tests & Builds
- **Docker Hub** zur Speicherung der Images
- **Railway/Fly.io/VPS** als mögliche Deployment-Optionen

---

## 🛠 API-Endpunkte (FastAPI)
| **Endpoint**   | **Methode** | **Beschreibung** |
|---------------|------------|-----------------|
| `/predict`    | `POST`      | Generiert Lottozahlen mit Wahrscheinlichkeiten |
| `/history`    | `GET`       | Holt vergangene Ziehungen von der externen API |
| `/stats`      | `GET`       | Gibt statistische Analysen für das gewählte Lottoformat aus |
| `/config`     | `GET/POST`  | User wählt Lottoformat & speichert es temporär |
| `/health`     | `GET`       | Health-Check für die API |

---

## 🛠 DevOps & CI/CD-Ansatz

### **📌 Teststrategie** (Automatisierte Tests für Qualitätssicherung)
- **Unit-Tests:** Testen einzelne Code-Bestandteile (ML-Modelle, API-Methoden)
- **API-Tests:** Sicherstellen, dass die API korrekt funktioniert
- **Integrationstests:** Testen das Zusammenspiel von API & ML-Modell
- **Code-Qualitätschecks:** (Linting mit Flake8, Black, MyPy, Bandit für Security)

### **📌 CI/CD-Workflow**
1. **Code Push zu GitHub (Trigger)**
2. **Automatische Tests starten (Pytest, Linting, Type-Checking)**
3. **Docker-Container wird gebaut & getestet**
4. **Deployment (Railway/Fly.io oder lokal als Docker-Container)**
5. **Benachrichtigung über Erfolg/Fehlschlag**

### **📌 Docker-Setup**
- **Backend (FastAPI) als eigener Container**
- **Frontend (Streamlit) als eigener Container**
- **Docker-Compose für lokale Entwicklung & Tests**
- **Optional: Private Registry oder Docker Hub für Image-Hosting**

---

## 📅 Nächster Schritt
✅ **Finalisierung der CI/CD-Strategie & minimale GitHub Actions-Pipeline**
✅ **Erstellung des ersten Dockerfiles für FastAPI-Backend**
✅ **Einrichtung von Pytest für automatisierte Tests**

---

📢 Dieses Readme wird regelmäßig mit den neuesten Fortschritten aktualisiert! 🚀

