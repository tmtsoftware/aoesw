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
note left: Set to laser components to ON
return Completed
lgsf -> lgsfTe ++: asterism
note left: Form asterism
return Completed

```