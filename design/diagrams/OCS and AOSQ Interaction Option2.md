```plantuml
!pragma teoz true
!include_many participants.puml
!includesub common.puml!variables
hide unlinked
participant "ESW\nOCS-AO\n//ESW.ocsao//" as ocsao

ocs -> aosq ++: Start calibration
loop For various telescope positions
aosq -> ocsao ++: Move telescope
ocsao -> tcs ++: move telescope
return Completed
return Completed
aosq -> aosq: Perform calibration/measurement
aosq -> ocsao ++: Take inst image
ocsao -> irisImager ++: Take image
return Completed
return Completed
aosq -> aosq : Perform calibration/measurement
end
aosq -> aosq: Finish calibration
return Completed
```