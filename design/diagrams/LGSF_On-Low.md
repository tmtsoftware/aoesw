```plantuml
!pragma teoz true
!include_many participants.puml
!includesub common.puml!variables
hide unlinked


lgsf -> lgsfLp ++: select
note left: Set to LOW power mode
return Completed
lgsf -> lgsfLaser ++: laserState
note left: Set to laser components to OBSERVATION
return Completed
lgsf -> lgsfOp ++: follow
note left: Close BTO loops
lgsf -> lgsfTe ++: follow
note left: Close BTO loops
return Completed

& return
```