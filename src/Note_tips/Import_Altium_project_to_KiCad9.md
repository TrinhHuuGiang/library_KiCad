1. Get backup from altium
2. import into kicad 9
3. Fix missing label or footprint libraries by add library by hand, [see here](../Note/_006_lib_symbol.md)
    - Note that footprint from Altium is read only, so we can copy layout footprint move into new library.
4. Fix missing file `SchDoc`:
    - Solution 1: Find back up newest of `SchDot`, try rename it to `SchDoc`, go to online [Altium 365 viewer](https://www.altium.com/viewer/?srsltid=AfmBOor7egUqZpN7ofJBRk9Jsmv1E4aCEty4yX0AnrlhgtxMF2EGkwk8) try import and check right Schematic.
        - Modify file `PrjPcb`, find to line component `SchDot` and rename to `SchDoc`
        - Now reopen project `PrjPcb` by KiCad, it will auto find `SchDoc` and create right `Schematic`.
5. Fix PCB 3d model wrong layout:
    - clink on 3d model wrong in pcb, in properties try rotate right direction.