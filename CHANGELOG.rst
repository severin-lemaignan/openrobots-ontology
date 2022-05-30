^^^^^^^^^^^^^^^^^^^^^^^^^
Changelog for package oro
^^^^^^^^^^^^^^^^^^^^^^^^^

0.1.0 (2022-05-30)
------------------
* add a couple more types of actions
* hasEngagementLevel is a functional property
* Update pal-concepts.md
* reworked how engagement is expressed
  Now:
  - each `Agent` `experiences` its own instance of `EngagementSituation`
  - each such instance can have its own level via `hasEngagementLevel`
  - two agent can be marked as engaged using `jointEngagementWith` between
  the respective instances of `EngagementSituation`
* clarify Plan, Zone
* add Avatar as a disembodied agent
* add isPerceived
* Document how the knowledge base (and the ontology) concepts are predicates are used at PAL
* add EngagementSituation
* update date and creator metadata
* add catkin infrastructure to install the ontology to share/ontologies
* Contributors: Séverin Lemaignan
