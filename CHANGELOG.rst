^^^^^^^^^^^^^^^^^^^^^^^^^
Changelog for package oro
^^^^^^^^^^^^^^^^^^^^^^^^^

2.4.0 (2024-12-03)
------------------
* replace oro:Agent by foaf:Agent, add foaf concepts like person, add PROV concepts like Person, Agent, Activity
* add foaf properties color and name, aligned with oro concepts
* add foaf, prov and dbpedia properties prefixes
* Contributors: Séverin Lemaignan

2.3.0 (2024-12-03)
------------------
* move/add more concepts from DBpedia
  Includes:
   - dbr:Shelf_(storage)
   - dbr:Coffee_table
   - dbr:Table_(furniture)
   - dbr:Cup
   - dbr:Book

* Contributors: Séverin Lemaignan

2.2.1 (2024-10-11)
------------------
* add dbr:Apple and dbr:Pear as type of food and fruit
* add concepts related to region of space and field of view
* add dbr and dbo prefixes for dbpedia
* Contributors: Séverin Lemaignan

2.2.0 (2024-07-30)
------------------
* [doc] finish doc in CMakeLists
* changed ament index resource name
  there is a mismatch between the ament index resource name
  as defined per this package ("ontologies") and the one
  that KnowledgeCore looks for ("ontology"). This is just a quick
  fix, waiting for discussing which name we want to use.
* Contributors: Séverin Lemaignan, lorenzoferrini

2.1.0 (2024-04-02)
------------------
* various updates, incl. automatic clean up coming from more recent version of Protege
* Contributors: Séverin Lemaignan

2.0.1 (2024-02-14)
------------------
* simplify generation of ament_index marker + correct path in marker file
* Contributors: Séverin Lemaignan

2.0.0 (2024-02-07)
------------------
* port to ROS2 packaging, using ament_index
* reinstate date/creator tags overwritten by 9bde4cc45c5
* add hasName and preferredName
* Contributors: Luka Juricic, Séverin Lemaignan

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
