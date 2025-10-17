```plantuml
/'A better version of this diagram exists as a hand-drawn version
 ' by Jason Weiss using omnigraffle.  This is kept around for 
 ' reference.
 '/

state "On-Low" as Low
Off -down-> Standby
Standby -up-> Off
Standby -down-> Ready
Ready -up-> Standby
Ready -down-> On
Ready -right-> Low
Low -> On
Low -> Ready
On -up-> Ready
On -down-> Observation
Observation -> On
Observation -[#red,dashed]-> Off
Ready -[#red,dashed]-> Off
Low -[#red,dashed]-> Off
On -up[#red,dashed]-> Off
```