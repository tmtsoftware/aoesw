```plantuml
/'A better version of this diagram exists as a hand-drawn version
 ' by Jason Weiss using omnigraffle.  This is kept around for 
 ' reference.
 '/

state "On-Low" as Low
state "On-Medium" as Medium
Low : (Maintenance Only)
Medium: (Calibration Only)
Off --> Standby
Standby --> Ready
Standby -> Low
Ready --> Medium
Medium --> On
On --> Observation
Ready -> Standby
Observation -> Standby
Medium -> Ready
Ready -> On
On -> Ready
Observation -> On
Observation -> Off
Standby -> Off
Ready -> Off
Medium -> Off
Low -> Off
On -> Off
```