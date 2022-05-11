PAL Concepts
============

This file lists the main concepts used when programming our robots, and their mapping to their corresponding entities in the knowledge base.

## Robot's environment

### Classes

- POI (point of interest): `Point`
- ZOI (zone of interest): `ZoneOfInterest`

### Properties (`predicates`)

- current location of someone/something: `isAt`
  - `myself isAt ?loc` returns the current zone(s) the robot is in
  - `?people isAt room1, ?people rdf:type Human` returns all the people currently computed to be in room `room1`
- someone/something is actively tracked by the robot (seen, heard,...): `isPerceived` (`bool`)

## People

### Classes

- Person: `Human`
  - `?people rdf:type Human` returns the list of people known to the robot
  - `?people rdf:type Human, ?people isPerceived true` returns the list of people currently seen/heard by the robot

### Properties

- where a person/robot looks at: `looksAt`
  - `?people rdf:type Human, ?people looksAt myself` returns the list of people currently looking at the robot
  - conversely, `?people rdf:type Human, myself looksAt ?people` returns the list of people that the robot looks at
  - `?people looksAt ?obj, ?obj owl:differentFrom Agent` returns the list of things (but not robots or other people) people are currently looking at
- what a person/robot sees: `sees`
  - contrary to `lookAt`, `sees` means that someone is in the field of view, not necessarily in the focus of attention

#### Advanced: engagement

- engagement: being engaged with the robot (or between two people) is co-`experiencing` an `EngagementSituation` with that other agent. The predicate `jointEngagementWith` indicates that two `EngagementSituation` (experienced by two agents) are in fact mutual engagement. Therefore:
    - `?people experiences ?sit1, myself experiences ?sit2, ?sit1 jointEngagementWith ?sit2` returns the list of people currently engaged (or in the process of engaging/disengaging) with the robot
- the level of engagement can be `engaging`, `engaged`, `disengaging` or disengaged. The predicate `hasEngagementLevel` allows to know what is the engagement level of each participant:
    - `john experiences ?sit1, myself experiences ?sit2, ?sit1 jointEngagementWith ?sit2, ?sit1 hasEngagementLevel ?level` returns in `?level` the level of engagement of an hypothetical `john` with the robot
    - `?people experiences ?sit1, myself experiences ?sit2, ?sit1 jointEngagementWith ?sit2, ?sit1 hasEngagementLevel disengaging` returns the list of people currently in the process of disengaging from the robot


## Actions & behaviours
