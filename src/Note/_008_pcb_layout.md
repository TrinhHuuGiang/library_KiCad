### Topic
1. Pre setup before layout footprint to pcb
    - [Declare number copper layer](#1-declare-how-many-copper-layer-for-board)
    - [Setup board stack (layer)](#2-board-stackup)
    - [Design rule - very importance]()

#### Setup page size
- `File -> Page Settings`
    - Choose `page size`-> `Issue date` -> `Revision` -> ...

#### Define how PCB will be menufactured
- `File -> Board setup`

##### 1. Declare how many copper layer for board
- `Board stackup` -> `Physical Stackup` -> `Copper layer`: 2, 4, 6, ..., 32
    - By default 2 layer generate: `F. Cu` and `B. Cu`
    - If we choose more, each pair layer will append: `In1.Cu + In2.Cu`, ... 
##### 2. Board stackup
- Choose Board stackup will using option below
###### a. Compulsory stacks:
- `F. Courtyard` and `B. Courtyard`: Commonly not use for main board, it suitable using wrap around when design foot print for component. But still using these stack for `rule check` when more than 1 `Courtyard` overlapping or inside other `Courtyard`.
- `F. Cu` and `B. Cu` or more: `Cu` is `copper layer` after we choose at `Physical Stackup`
- `Edge.Cuts` is the boundary run along with where cut board machine will cut through
- `Margin` is a support layer but can not `DRC`, it using for reference how long distance between `Edge.Cuts` and Courtyard of `footprint`

###### b. Optional:
- `F. Fab` and `B. Fab` is fabrication layer, using write some note for footprint but not real print.
- `F. Adhesive` and `B. Adhesive`: ignore, only adhensive layer but never export to send factory :v
- ... other user command layer.

#### Design rule

##### 1. Constrains
- Minimum clearance: distance between copper objects like `track - track`, `track - pad`, `via - track`
- Minimum trackwidth: minimum width for track.
- Minimum connection width: each pad alway connect out side with a cross shape (max 4 connection), this parameter point out minimum width of each connection.
- Annular width: the width of ring around through hole
- Via diameter: Via is using connect a copper layer with others layer
- Through hole: cover in annular ring
- Hole to hole clearance: minimum clearance from through hole or drill hole (no electric)
- Copper to hole (drill or through): min distance form track or copper to hole

###### Tips when send for factory or DIY: 
- Factory
    - Minimum clearance  `>= 0.2mm` == `8 mil`
    - Minimum trackwidth `>= 0.2mm` == `8 mil`
    - Minimum connection width `>= 0.25mm` == `10 mil`
    - Minimum annular width `>= 0.2mm` == `8 mil`
    - Minimum via diameter (out side D) `>= 2*annular+hole == 0.2 + 0.3 == 0.7 mm` == `28-30 mil`
    - Minimum through hole (in side D) `>= 0.3mm` == `12 mil`
    - Hole to hole clearance `>= 0.25mm` == `10 mil`
    - Copper to hole clearance `>= 0.25mm` == `10 mil`
    - Note: Via maybe smaller but depend on ability of the factory
- DIY
    - Minimum clearance  `>= 0.25mm` == `10 mil`
    - Minimum trackwidth `>= 0.25mm` == `10 mil`
    - Minimum connection width `>= 0.25mm` == `10 mil`
    - Minimum annular width `>= 0.25 mm` == `10mil`
    - Minimum via diameter (out side D) `1 mm` == `40 mil`
    - Minimum through hole (in side D) `>= 0.5 mm` == `20 mil`
    - Hole to hole clearance `>= 0.3 mm` == `12 mil`
    - Copper to hole clearance `>= 0.3mm` == `12 mil`
    - Note: Via size larger `Factory` sometime equal with a standard through hole

##### 2. Set violation severity
- Keep default or modify 3 level: Error, warning, Ignore