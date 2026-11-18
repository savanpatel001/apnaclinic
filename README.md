# 🏥 ApnaClinic - Smart Clinic Management System

[![License: MIT](https://img.shields.io/badge/License-MIT-teal.svg)](LICENSE)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)](index.html)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)](index.html)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)](index.html)
[![No Dependencies](https://img.shields.io/badge/Dependencies-Zero-success.svg)](index.html)

**ApnaClinic** is an all-in-one, lightweight, and modern **Smart Clinic & OPD Queue Management System** designed to streamline outpatient operations, reduce patient wait times, and provide complete visibility across clinic roles. 

Built as a high-performance Single Page Application (SPA) with zero external dependencies, it features tailored portals for Patients, Receptionists, Doctors, Waiting Room Displays, and Clinic Owners.

---

## 🌟 Key Features & Role Portals

ApnaClinic provides an integrated ecosystem with **Role-Based Access Control (RBAC)**:

```
                                ┌───────────────────────────────────────┐
                                │       ApnaClinic Central System       │
                                └───────────────────┬───────────────────┘
                                                    │
         ┌───────────────────┬──────────────────────┼──────────────────────┬───────────────────┐
         │                   │                      │                      │                   │
         ▼                   ▼                      ▼                      ▼                   ▼
  🧑 Mareez (Patient)   🏢 Reception           🩺 Doctor              📺 Waiting Room     👑 Malik (Owner)
  • Online Booking     • Walk-in Reg.         • Live OPD Queue       • TV Kiosk View     • Daily Analytics
  • Token Tracking     • Patient Search       • Consultation Notes   • Now Serving Token • Complete Records
  • Queue Status       • Token Confirmation   • Digital Prescriptions• Auto Live Updates • Role Passwords
```

### 1. 🧑 Mareez (Patient) Portal
* **Online Appointment Booking**: Quick self-service registration with name, mobile number, and department selection.
* **Token Confirmation**: Check-in confirmation using allocated token numbers.
* **Live Queue Status**: Real-time queue tracker showing the currently served token, your queue position, and estimated waiting time.

### 2. 🏢 Reception Desk Portal
* **Today's Patient Roster**: Tabular overview of all appointments categorized by status (`Booked`, `Confirmed`, `Serving`, `Done`).
* **One-Click Check-In**: Move patients from "Booked" to "Confirmed" upon arrival.
* **Walk-In Registration**: Instant token generation for on-spot walk-in patients without prior online appointments.
* **Live Search**: Instant multi-attribute search filtering by patient name, 10-digit mobile number, or token ID.

### 3. 🩺 Doctor Consultation Panel
* **Live Patient Stream**: View next waiting patients in real-time.
* **Consultation Flow**: One-click "Call Patient", start consultation, and track visit duration.
* **Digital Prescription & Clinical Notes**: Integrated medical notes editor for recording diagnoses, medications, dosages, and follow-up advice.
* **Consultation Completion**: Automatic timestamping upon completion to maintain accurate clinical audit logs.

### 4. 📺 Waiting Room TV Display (Kiosk Mode)
* **Digital Signage for Waiting Areas**: Distraction-free, high-contrast display designed for clinic TVs and wall monitors.
* **Prominent "Now Serving" Indicator**: Clear, large display showing active token and consulting doctor chamber.
* **Upcoming Queue Preview**: Real-time queue preview so patients can prepare for their turn without crowding the desk.

### 5. 👑 Malik (Clinic Owner / Admin) Portal
* **Executive Daily Reports**: Real-time KPI summary cards (Total Booked, Total Completed, In-Queue, Walk-ins vs. Online Bookings).
* **Patient Activity Visualizer**: Department-wise and status-wise distribution summaries.
* **Complete Patient History Archive**: Comprehensive searchable database of all past patient visits, consultation dates, and digital prescriptions.
* **Multi-Filter History View**: Filter historical records by department (`General OPD`, `Skin`, `Bones`, `Child`, `Dental`), completion status, and prescription presence.
* **Clinic Configuration & Security**:
  * Customizable Clinic Name & Token Prefix (e.g., `T-001`, `CL-001`).
  * Independent password management for Reception, Doctor, Waiting Room, and Malik roles.

---

## 🏥 Supported Departments

* 🩺 **General OPD** (General Medicine & Primary Care)
* 🧴 **Skin** (Dermatology)
* 🦴 **Bones** (Orthopedics)
* 👶 **Child** (Pediatrics)
* 🦷 **Dental** (Dental Care)

*(Additional departments can easily be configured in the codebase).*

---

## 🔐 Default Access Credentials

For quick testing and evaluation out of the box:

| Role | Password | Description |
| :--- | :---: | :--- |
| **🧑 Mareez (Patient)** | *None required* | Direct access for booking and queue tracking |
| **🏢 Reception** | `1234` | Patient check-ins, walk-ins, and desk management |
| **🩺 Doctor** | `1234` | Patient queue, consultations, and prescriptions |
| **📺 Waiting Room** | `1234` | Full-screen kiosk display for TV monitors |
| **👑 Malik (Owner)** | `1234` | Daily analytics, patient archive, and clinic settings |

> 💡 *All role passwords can be customized anytime from the **Malik Panel ➔ Settings** tab.*

---

## 🛠️ Technology Stack & Architecture

* **Frontend**: HTML5, Modern Semantic Elements
* **Styling**: Vanilla CSS3 (Custom Properties / Design Tokens, Flexbox, Responsive Grid, Smooth Transitions)
* **Logic**: Vanilla JavaScript (ES6+, Event Listeners, State Management, DOM Manipulation)
* **Persistence Layer**: LocalStorage abstraction layer (`clinic_patients`, `clinic_settings`, `clinic_session`)
* **Typography**: Clean system typography with modern UI font fallback stack (`Segoe UI`, `system-ui`, `-apple-system`)
* **Icons**: Universal Unicode / Emoji UI iconography for zero-latency asset rendering

### Clean Data Architecture
The data layer is completely separated into clean helper functions:
```javascript
loadPatients()       // Retrieves all patient records
savePatients()       // Persists patient state
loadSettings()       // Retrieves clinic configurations & passwords
saveClinicSettings() // Updates clinic name, prefix & role passwords
loadSession()        // Manages active role sessions
```
*This modular design allows trivial migration to **Firebase Firestore**, **Supabase**, or a **Node.js/Python REST API** by merely updating the persistence helpers.*

---

## 📁 Project Structure

```
apnaclinic/
├── index.html       # Complete Single-Page Application (HTML + CSS + JavaScript)
├── .gitignore       # Git ignore rules for clean repository state
├── LICENSE          # MIT Open Source License
└── README.md        # Comprehensive documentation & setup guide
```

---

## 🚀 Quick Start / How to Run

Because **ApnaClinic** has zero build steps and zero dependencies, getting started takes seconds:

### Option 1: Direct Browser Launch
Simply double-click or open `index.html` in any web browser (Chrome, Edge, Firefox, Safari, Brave):
```bash
# Windows
start index.html

# macOS
open index.html

# Linux
xdg-open index.html
```

### Option 2: Run with a Local Static Server
If using VS Code or Python:
```bash
# Python 3
python -m http.server 3000

# Node / npx
npx serve .
```
Then visit `http://localhost:3000` in your browser.

---

## 🌐 Deploy to GitHub Pages

You can host **ApnaClinic** for free on **GitHub Pages**:

1. Go to your repository settings on GitHub.
2. Navigate to **Pages** in the left sidebar.
3. Under **Branch**, select `main` and folder `/ (root)`.
4. Click **Save**.
5. Your live clinic system will be live at `https://savanpatel001.github.io/apnaclinic/` within minutes!

---

## 🗺️ Roadmap & Future Enhancements

- [ ] Cloud sync integration (Firebase Firestore / Supabase)
- [ ] WhatsApp & SMS notification triggers for token call alerts
- [ ] Printable PDF prescription generation with clinic letterhead
- [ ] Multi-doctor simultaneous chamber routing
- [ ] Pharmacy & Billing integration module

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).

---

## 👨‍💻 Author

**Savan Patel**  
* GitHub: [@savanpatel001](https://github.com/savanpatel001)  
* Email: [savanpatel4466@gmail.com](mailto:savanpatel4466@gmail.com)
