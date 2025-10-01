```plantuml
!pragma teoz true
!include_many participants.puml
!includesub common.puml!variables
hide unlinked

lgsf -> lgsfBdm ++: select 
note left: Close BDM shutter
return Completed
lgsf -> lgsfLp ++: select
note left: Set to FULL power mode
return Completed
lgsf -> lgsfLaser ++: laserState
note left: Set to laser components to OBSERVATION
return Completed
alt If loops not closed
lgsf -> lgsfOp ++: follow
note left: Close BTO loops
lgsf -> lgsfTe ++: follow
note left: Close BTO loops
return Completed
& return
end
lgsf -> lgsfTe ++: lltCover
note left: Open LLT cover
return Completed
```