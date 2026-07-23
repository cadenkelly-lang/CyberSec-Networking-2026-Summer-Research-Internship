Welcome to ACEP!

# Contact Info

- John Haverlack
- jehaverlack@alaska.edu
- Cell: 907-699-8668

Please contact me anytime as needed.  Typically Mattermost is the best method for quick consults.  Google Meet / Zoom will work for remote meetings / screen shares.

# Onboarding Checklist
- [x] Access to Laptop
- Laptop / Linux Orientation
- [x] Access to UAF Email:   cckelly2@alaska.edu
- [x] Setup Mattermost https://mattermost.camio.acep.uaf.edu/signup_user_complete/?id=om57cmdsdjy1tnnkguzweojm6h&md=link&sbr=sa
- [x] Access to [ACEP Wiki](https://wiki.acep.uaf.edu/)
- Login with Gmail Account and have John set permissions
- [x] Setup Syncthing


In a terminal window on  you laptop:
```
sudo systemctl start syncthing@cckelly2
```

```
sudo systemctl enable syncthing@cckelly2.service
```

- Point your browser to http://localhost:8384
- Coordinate with John to add Remote and Share the **2026-ACEP-InfoSec-Internship** Folder

```
2026-ACEP-InfoSec-Internship/ (Syncthing Shared Folder)
└── PTG Notes (Obsidian Vault)
    ├── Diagrams
    ├── Library
    │   └── Images
    │       └── FlatIcon
    │           └── license
    └── Meetings
```

- [x] Obsidian Vault Notes ([MarkDown](https://www.markdowntutorial.com/))
- [x] Task Management
- [x] Setup Yubikey
- [x] Schedule Meeting Times (Google Calendar)
- [x] [Use of AI for UAF Work](https://wiki.acep.uaf.edu/en/facilities-and-services/infosec/ai-guidance)
#### AI Attribution

e.g. *Portions of this paper were developed with the assistance of generative AI tools for editorial support, organization, and proofreading. All security concepts, technical content and interpretations were developed and reviewed by the authors*.

# Resources
- Project Roadmap: [OT Cybersecurity Training Modules Development](https://docs.google.com/document/d/1HYFRyxuS-YhlIMTIFcYdyuW4PTY2tiZKe3iJn5Ki4ZQ/edit?tab=t.0#heading=h.c3h6apceak2e)
- Google Drive/Chat/Meet/Mail/Calendar/Gemini
- Zoom
- Obsidian Vault / Syncthing
- Mattermost Chat: https://mattermost.camio.acep.uaf.edu/

# Goals 

The primary goal is to build a portable training ground and then implement 2 network training modules using the training ground.

- **Module 1**: **Networking  Basics**: Develop challenges that teach participants how to correctly implement network segmentation, configure essential services like DHCP, DNS and NTP the core services of any Local Area Network (LAN)
- **Module 2**: **Firewall Basis**: Develop challenges that teach participants how to set up and configure basic firewall routers and multi-lan segmented networks.
# Tasks

- [x] Laptop / Linux Orientation (Debian 13 with Cinnamon Desktop)
- cli
- sudo access
- WiFi
- apt
- history
- ip a / route -n / ping
- nmap -sn 10.25.156.0/22

- [x] Add Terminology Descriptions
- [x] Review OSI model (Layers 1-5)
- [x] Network Diagrams (Excalidraw) Layer 1, Layer 2, Layer 3 - by this weekend, but not super high priority
- [x] SDDC Diagram - by this weekend. Working on learning it 6/5
- [x] **IPAM/Subnet/VLAN Spreadsheet - a place to track SDDC details. There is an example spreadsheet**
	- [x] Must be updated as I go more, but is as good as will get for now
- [x] Module 1: Plan
- [x] Module 2: Plan


## Build SDDC - 6/11 Done

### **Done
- ProxMox Cluster
- Core Services
  - OpnSense Firewall***
  - DNS
  - DHCP
  - NTP
  - VLANs
- Manged Switches


## Module 1: IP v4 Basics

- Anatomy of IPv4
- IP Address
- Network Address
- IP Subnet
- Subnet Mask
- Broadcast Address
- Ping

## Module 2: Segmented Network Firewall
- OpnSense Install
- Setup Services

# ~~Week 1-2

### Done
- Onboarding: 2026-06-03 @ 9 am 
- First Network Setup
- IPv4 Basics
- Installing ProxMox
- Diagrams
# Week 3-4
*  ~~Portable Training Ground Plan
* ~~Make portable training ground
- Module 1: Plan - starting mid week 3
- Module 2: Plan - starting mid week 3
