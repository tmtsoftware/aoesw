```plantuml
!pragma teoz true
!include_many participants.puml
!includesub common.puml!variables
hide unlinked

lgsf -> lgsfTe ++: lltCover
note left: Close LLT cover
lgsf -> lgsfBdm ++: select 
note left: Close BDM shutter
return Completed
& return
lgsf -> lgsfLp ++: select
note left: Set to FULL power mode
return Completed
lgsf -> lgsfOp ++: follow
note left: Open BTO loops
lgsf -> lgsfTe ++: follow
note left: Open BTO loops
return Completed
& return
lgsf -> lgsfLaser ++: laserState
note left: Set laser components to STANDBY
return Completed
lgsf -> lgsfOp ++: $TBD
note left: Park BTO mechanisms
lgsf -> lgsfTe ++: $TBD
note left: Park BTO mechanisms
return Completed
& return

```