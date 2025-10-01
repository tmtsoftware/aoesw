```plantuml
title LGSF: Off
!include_many lgsf_participants.puml

alt "Transitioning from STANDBY"
seq -> laser: set to OFF
else "Transitioning from any other state (via Emergency Shutdown)"
seq -> llt: close cover
seq -> bdm: close shutter
seq -> laser: set to OFF
seq -> lpm: set to FULL
seq -> bto: open loops
seq -> bto: park
end

```