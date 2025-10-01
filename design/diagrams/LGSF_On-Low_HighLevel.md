```plantuml
title LGSF: On-Low
!include_many lgsf_participants.puml

seq -> lpm: set to LOW
seq -> laser: set to OBSERVATION
seq -> bto: close loops

```