```plantuml
!pragma teoz true
!include_many participants.puml
!includesub common.puml!variables
hide unlinked

lgsf -> lgsfBdm ++: select 
note left: Open shutter
return Completed
```