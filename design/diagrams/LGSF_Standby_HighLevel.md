```plantuml
title LGSF: Standby
!include_many lgsf_participants.puml

seq -> llt: close cover
seq -> bdm: close shutter
seq -> lpm: set to FULL
seq -> bto: open loops
seq -> laser: set to STANDBY
seq -> bto: park

```