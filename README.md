SYSTEMS Manager for dArkOSRE

SYSTEMS Manager is a Bash-based EmulationStation utility for dArkOSRE that lets you dynamically switch and manage game system paths between /roms/ and /roms2/ depending on where your ROMs are actually stored.

It provides both automatic detection and manual selection through a dialog-based interface designed for R36S devices.

Description:

This tool scans your EmulationStation es_systems.cfg and intelligently migrates system paths between primary and secondary ROM storage locations:

- /roms/ (active SD1 / primary storage)
- /roms2/ (secondary SD card or backup storage)

It ensures systems only appear active when ROMs are actually present, helping keep EmulationStation clean and fast.

Features:
- Automatic ROM detection and system migration between /roms/ and /roms2/
- Manual system selection via checklist UI
- Smart empty-folder detection and rollback to /roms2/

- Full multilingual support:
  - English
  - French
  - Spanish
  - Portuguese
  - Italian
  - German
  - Polish
- Safe configuration handling with automatic backups
- Interactive dialog-based UI for handheld devices
- EmulationStation restart prompt after changes
- Gamepad support via gptokeyb integration
- Skip system types like ports, tools, and themes automatically

Requirements:
- dArkOS/RE
- EmulationStation installed
- dialog package
- gptokeyb input daemon
- Standard Linux utilities (bash, sed, grep, compgen)

Installation:
- Copy the script to your Tools folder

Usage:

When launched, the tool presents a main menu with three options:

- Manual Selection:
    - Choose which systems are active in /roms/ using a checklist interface
- Automated Scan
    - Automatically detects ROM presence and migrates systems between /roms/ and /roms2/
- Undo All Changes
    - Restores all system paths back to /roms2/

After any changes, you will be prompted to restart EmulationStation for updates to take effect.

How It Works:
- Parses /etc/emulationstation/es_systems.cfg
- Reads each system entry:
    - name
    - fullname
    - path
    - extension
- Detects ROM presence using file extensions
- Moves system paths:
    - /roms2/ → /roms/ when ROMs are found
    - /roms/ → /roms2/ when folders are empty or unselected
- Creates automatic backup of configuration before changes

Safety Features:
- Automatically creates backup:
    - es_systems.cfg.bak
- Skips system categories:
    - ports
    - tools
    - themes
- Prevents duplicate migrations using internal tracking
- Requires confirmation before restarting EmulationStation

Notes:
- Designed specifically for dual-SD or split-ROM setups
- Intended specifically for the R36S
- Requires proper /roms2/ mount or SD2 insertion
-Will refuse to run if /roms2/ is not detected in config


License:

MIT License

Copyright (c) 2026 djparent
