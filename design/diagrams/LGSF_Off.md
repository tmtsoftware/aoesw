```plantuml
!pragma teoz true
!include_many participants.puml
!includesub common.puml!variables
hide unlinked

alt "Transitioning from STANDBY"
lgsf -> lgsfLaser ++: laserState
note left: Set to laser components to OFF
return Completed
else "Transitioning from UNKNOWN"
lgsf -> lgsfBdm ++: select 
note left: Close BDM shutter
return Completed
lgsf -> lgsfLaser ++: laserState
note left: Set laser components to OFF
return Completed
lgsf -> lgsfOp ++: follow
note left: Open BTO loops
lgsf -> lgsfTe ++: follow
note left: Open BTO loops
return Completed
& return
lgsf -> lgsfLp ++: select
note left: Set to FULL power mode
lgsf -> lgsfOp ++: park
note left: Park BTO mechanisms
lgsf -> lgsfTe ++: lltCover
note left: Close LLT cover
lgsf -> lgsfTe ++: park
note left: Park BTO mechanisms
return Completed
& return
& return
& return
end

```