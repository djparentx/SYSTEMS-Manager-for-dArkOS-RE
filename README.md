# SYSTEMS Manager (R36S - dArkOSRE)

by djparent

A Bash-based EmulationStation utility for the R36S that dynamically manages system ROM paths between /roms/ and /roms2/, keeping your system list clean and accurate based on where your games are stored.

---

## Overview

SYSTEMS Manager is designed for dual-storage setups on the R36S, allowing you to automatically or manually switch EmulationStation systems between primary and secondary ROM locations.

It ensures only systems with actual ROMs appear, improving both organization and performance.

---

## Features

- Automatic ROM detection and system migration  
- Manual system selection via checklist UI  
- Smart empty-folder detection with automatic rollback  
- Dual-path management:
  - /roms/ (primary SD / active storage)  
  - /roms2/ (secondary SD / backup storage)  
- Multi-language support (EN, FR, ES, PT, IT, DE, PL)  
- Automatic configuration backups  
- Controller-friendly dialog interface  
- EmulationStation restart prompt after changes  
- Gamepad support via gptokeyb  
- Skips non-ROM systems (ports, tools, themes)  

---

## How It Works

The script parses:

/etc/emulationstation/es_systems.cfg

For each system, it reads:

- name  
- fullname  
- path  
- extension  

Then:

- Scans for ROM files using defined extensions  
- Moves system paths based on content:

  - /roms2/ → /roms/ when ROMs are found  
  - /roms/ → /roms2/ when folders are empty or deselected  

- Tracks changes to prevent duplicate operations  
- Prompts for EmulationStation restart after changes  

---

## Usage

When launched, the main menu provides:

- Manual Selection  
  Choose which systems should use /roms/ via checklist  

- Automated Scan  
  Detects ROMs and automatically assigns correct paths  

- Undo All Changes  
  Restores all systems back to /roms2/  

---

## Safety Features

- Creates automatic backup:

  /etc/emulationstation/es_systems.cfg.bak  

- Skips system categories:
  - ports  
  - tools  
  - themes  

- Prevents duplicate migrations  
- Requires confirmation before restarting EmulationStation  

---

## Requirements

- R36S running dArkOSRE  
- EmulationStation installed  

Required tools:

- dialog  
- gptokeyb  
- bash, sed, grep, compgen  

---

## Installation

1. Copy the script to your Tools folder on the R36S  

2. Run it

---

## Notes

- Designed specifically for R36S dual-SD setups  
- Requires /roms2/ to be properly mounted or SD2 inserted  
- Will not run if /roms2/ is not detected in configuration  
- Helps keep EmulationStation clean, fast, and organized  

---

## License

MIT License  

Copyright (c) 2026 djparent  

---
