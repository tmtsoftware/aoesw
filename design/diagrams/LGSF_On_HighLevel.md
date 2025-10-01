```plantuml
title LGSF: On
!include_many lgsf_participants.puml

seq -> bdm: close shutter
seq -> laser: set to OBSERVATION
seq -> lpm: set to FULL
seq -> bto: close loops
seq -> llt: open cover

```