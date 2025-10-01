```plantuml
!pragma teoz true
!include_many participants.puml
!includesub common.puml!variables
hide unlinked

ocs -> aosq ++: Prepare calibration
return Completed
loop For various telescope positions
ocs -> tcs ++: move telescope
return Completed
ocs -> aosq ++: Perform calibration/measurement
return Completed
ocs -> irisImager ++: Take image
return Completed
ocs -> aosq ++: Perform calibration/measurement
return Completed
end
ocs -> aosq ++: Finish calibration
return Completed
```