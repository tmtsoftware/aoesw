```plantuml
/'A better version of this diagram exists as a hand-drawn version
 ' by Jason Weiss using omnigraffle.  This is kept around for 
 ' reference.
 '/

state "On-Low" as Low
Off -down-> Standby
Standby -down-> Ready
On --> Observation
Ready -up-> Standby
Ready -down-> On
Low -> On
Low -> Ready
Ready -right-> Low
On -> Ready
Observation -> On
Observation -up[#red,dashed]-> Off
Standby -> Off
Ready -up[#red,dashed]-> Off
Low -up[#red,dashed]-> Off
On -up[#red,dashed]-> Off
```