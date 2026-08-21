```plantuml
title LGSF: Off
!include_many lgsf_participants.puml

alt "Transitioning from STANDBY"
seq -> laser: set to OFF
else "Transitioning from any other state (via Emergency Shutdown)"
seq -> bdm: close shutter
seq -> laser: set to OFF
seq -> bto: open loops
seq -> lpm: set to FULL
seq -> llt: close cover
seq -> bto: park
end

```