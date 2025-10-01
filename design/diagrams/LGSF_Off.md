```plantuml
!pragma teoz true
!include_many participants.puml
!includesub common.puml!variables
hide unlinked

alt "Transitioning from STANDBY"
lgsf -> lgsfLaser ++: laserState
note left: Set to laser components to OFF
return Completed
else "Transitioning from any other state (via Emergency Shutdown)"
lgsf -> lgsfTe ++: lltCover
note left: Close LLT cover
lgsf -> lgsfBdm ++: select 
note left: Close BDM shutter
return Completed
& return
lgsf -> lgsfLaser ++: laserState
note left: Set laser components to OFF
return Completed
lgsf -> lgsfLp ++: select
note left: Set to FULL power mode
return Completed
lgsf -> lgsfOp ++: follow
note left: Open BTO loops
lgsf -> lgsfTe ++: follow
note left: Open BTO loops
return Completed
& return
lgsf -> lgsfOp ++: $TBD
note left: Park BTO mechanisms
lgsf -> lgsfTe ++: $TBD
note left: Park BTO mechanisms
return Completed
& return
end

```