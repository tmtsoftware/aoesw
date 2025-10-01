```plantuml
title LGSF: Ready
!include_many lgsf_participants.puml

seq -> bdm: close shutter
seq -> lpm: set to FULL
seq -> laser: set to ON
seq -> bto: form asterism

```