# Referrences
- KiCad main pages
    - [Linux version](https://www.kicad.org/download/linux/) []
    - [Forum](https://forum.kicad.info/)
    - [Documentation](https://docs.kicad.org/)
        - [Getting started](../Note/rsrc/doc/getting_started_in_kicad.pdf)
- Getting started
    - [Set time backup](#setup-auto-backup-time)
    - [Schematic setup before drawing](#1-before-design---setup-schematic-informations-about-title-date-paper)
- [Project 001](../Design/_001_Get_start/Get_Start/)

## Install KiCad 9 on Ubuntu
- Kicad default on apt only has version 6 so add link to newest version 9: 
    ```bash 
    sudo add-apt-repository ppa:kicad/kicad-9.0-releases
    ```

## Getting start new project
- In `KiCad` -> `New project` or `Ctrl N`  
    -> Tick `Create a new folder for project`  
    -> Remeber typing name for project -> `Save`

- Now we have `kicad_pcb` for pcb layout and `kicad_sch` for schematic

### Setup auto backup time
Go to `Preferences → Preferences → Common → Project Backup`
- Example: 3 days backup maybe set:
    - Tick auto back up project
    - Maximum backup to keep: 15
    - Maximum backup per day: 5
    - Maximum backup to keep: 40 minute

### Schematic
#### 1. Before design - Setup schematic informations about title, date, paper,...
- `File → Page Settings`
    - Example: 
        - `Issue date` set today by click `<<<`or set your custom time 
        - `Revision` like A,B,... or x.y.z 
            - x (Major): Not compatible with previous firmware versions, or includes large layout changes 
            - y (Minor): Hardware changes that are still compatible with previous firmware (added sensors, footprint adjustments, etc..)
            - z (Patch): Cosmetic or minor fixes such as silkscreen correction, re-routing, logo updates
        - `Title` can using upper case
        - `Comment`, `Company` ...

#### 2. Hotkeys combine in schematic mode
1. Interact with component
- `A`: Select component symbol
- `R`: Rotate component
- `X`: mirror component by horizontal
- `Y`: mirror component by vertical
- `ESC`: normal cursor mode
- `Click + G`: grab and drag component was clicked (still drag wire is connecting)
- `Click + M`: grab and drag only component

2. Set wire and routing
- `W`: place wire connect components
- `L`: place label, if they have similar name, they will be shorted
- `P`: convenience place a label power (5V, 3v3, GND, ...)
 
3. Draw (draw line without electricity)
- Most of them can find at `Place` on Toolbar
- `I`: draw a line, zigzag
