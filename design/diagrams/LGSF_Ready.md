```plantuml
!pragma teoz true
!include_many participants.puml
!includesub common.puml!variables
hide unlinked

lgsf -> lgsfBdm ++: select 
note left: Close BDM shutter
return Completed
alt If transitioning to READY
lgsf -> lgsfTe ++: lltCover
note left: Open LLT cover
return Completed
end
lgsf -> lgsfLaser ++: laserState
note left: Set to laser components to ON
return Completed
lgsf -> lgsfLp ++: select
note left: Set to FULL power mode
return Completed
lgsf -> lgsfTe ++: asterism
note left: Form asterism
return Completed
lgsf -> lgsfTe ++: follow
note left: Enable LUT-based loops and\nstop K-MIrror follow mode
lgsf -> lgsfOp ++: follow
note left: Enable LUT-based loops
return Completed
& return

```