```plantuml
!pragma teoz true
!include_many participants.puml
!includesub common.puml!variables
hide unlinked

lgsf -> lgsfOp ++: follow
note left: Open BTO loops
lgsf -> lgsfTe ++: follow
note left: Open BTO loops
return Completed
& return
lgsf -> lgsfLaser ++: laserState
note left: Set to laser components to ON
return Completed
lgsf -> lgsfLp ++: select
note left: Set to FULL power mode
return Completed
lgsf -> lgsfLaser ++: laserState
note left: Set to laser components to OBSERVATION
return Completed
lgsf -> lgsfTe ++: follow
note left: Close BTO loops with LUT & PACs and\nstart K-Mirror following TCS demands
lgsf -> lgsfOp ++: follow
note left: Close BTO loops with LUT & PACs
return Completed
& return
```