# Cybersecurity Research Internship - Networking Training Modules - Summer 2026

## Project Overview

This repository contains documentation, diagrams, and training materials developed during my Summer 2026 research internship with the Alaska Center for Energy and Power (ACEP).

The project focuses on developing cybersecurity training modules for rural Alaskan Communities. The goal is to create accessible, cost-effective, hands-on cybersecurity education through a virtualized cyber range environment covering networking fundamentals (with a focus on network segmentation), system administration, and firewall configuration.

The training environment uses virtualization and network simulation to allow students to explore real-world networking and cybersecurity concepts in a controlled environment. These are the initial materials I made once my internship ended, but John is likely to continue workin/iterating upon them after I go. 

My internship was funded by the National Science Foundation's Research Experiences for Undergraduates program.

---

## Project Architecture

The project network architecture is documented at both the physical (Layer 1) and logical (Layer 3) levels.

### Layer 1 - Physical Network Architecture

The Layer 1 diagram shows the physical components of the training environment, including servers, switches, network connections, and hardware organization.

<img src="Diagrams/Training%20Ground%20Network%20Diagrams/6.26%20Final%20PTG%20Diagram.png" width="850">

### Layer 3 - Logical Network Architecture

The Layer 3 diagram shows the logical network design, including IP addressing, network segmentation, student stations, and firewall boundaries.

<img src="Diagrams/Training%20Ground%20Network%20Diagrams/jehaverlack-layer3-student-station.excalidraw.png" width="850">

---

## Training Modules

### Module 1 - Networking Fundamentals

Topics covered:

- Linux command line fundamentals
- IPv4 addressing and subnetting
- MAC addresses and network communication
- DHCP
- DNS
- NTP
- LAN
- Network segmentation

### Module 2 - Firewall Configuration and Security

Topics covered:

- Firewall concepts
- OPNsense services configuration: DHCP/DNS/NTP
- Firewall rules, configuration, testing
- Rule testing and validation
- Feedback Form, etc. as QR code in slides

---

## Repository Structure
## Repository Structure

```text
CyberSec-Networking-2026-Summer-Research-Internship/
├── .obsidian/                             # Obsidian workspace configuration (ignored)
├── Daily Personal Notes/                  # Daily internship journal entries
├── Diagrams/
│   ├── ACEP Intern Presentation Diagrams/
│   ├── Training Ground Network Diagrams/
│   ├── Training Module 1 Diagrams/
│   └── Training Module 2 Diagrams/
├── Meetings/                              # Mostly orientation notes and some notes John made for my feedback after a demo-run of a module early on
├── Module Slides and PDFs/                # Training slide decks and reference PDFs
├── Project Technical Notes/               # Technical documentation and research notes
├── Publications and Media/                # Interview, Article, and End of Year Presentation; Their posted article and the EOY presentation still need to be added. Can view raw files from downloading
├── .gitignore
├── LICENSE
└── README.md
```
Media Materials (You could also download the raw files from Publications and Media folder):

[Download Interview Video](https://github.com/cadenkelly-lang/CyberSec-Networking-2026-Summer-Research-Internship/raw/refs/heads/main/Publications%20and%20Media/Interview.mp4)

Article: PDF in the Folder which you can view. I will upload a link to the full article once they publish it, after my internship

End of year presentation: They will post it on Youtube. If it is a public video, I will place it here in the same manner I did for the interview video
