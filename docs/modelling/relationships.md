# Relationships

A relation is a connection between two entities. It always has
a direction and a label: it says *this* entity relates to *that* one in a specific,
named way. The database
stores the relation once, but can display it from either entity's side. See [The APIS
data model](../apis/data-model.md).


## Subject, predicate and object

Every relation is a subject–predicate–object statement: a subject entity, a predicate (the
relation label), and an object entity.

- Person **author of** Work
- Person **biographer of** Person
- Work **composed at** Place
- Work **commentary on** Work
- Work **is cited in** Work
- Instance **owned by** Person
- Instance **written at** Place
- Place **located within** Place

## Additional relationship information

A relation can carry information of its own, separate from the two entities it
connects: most commonly a confidence level and a reference
to the source that supports it. See [Uncertainty and confidence](uncertainty.md).

## Dates, sources and references

A relation is often true only for a period, or only according to one source, so dates
and references belong on the relation itself, not on either entity. The [Shakespeare
example](../data/shakespeare-example.md) shows this directly: *P1 participated in E1*
carries its own date (1564-04-26) and source (Parish Register), independent of either
entity's own attributes.

## Example: TibSchol

The TibSchol project models Tibetan Buddhist scholastic texts using four entity
types: **Person**, **Place**, **Work**, **Instance**, connected by relations such as:

- Person **author of** Work
- Work **commentary on** Work
- Work **composed at** Place
- Work **has as an instance** Instance
- Instance **written at** Place
- Person **active at** Place

Laid out as a grid, with the entity on the left as the subject and the entity along the
top as the object, part of the model looks like this:

| Subject ↓ \ Object → | Person | Place | Work | Instance |
|---|---|---|---|---|
| **Person** | biographer of ↔ biographed by, parent of ↔ child of, sibling of, student of ↔ teacher of, … | active at | author of, biographed in, translator of, … | owner of, scribe of, sponsor of, … |
| **Place** | place of activity of | located within ↔ contains | place of composition for | place of scribing for |
| **Work** | addressed to, composed by, translated by, … | composed at | commentary on ↔ has as a commentary, is cited in ↔ cites | has as an instance |
| **Instance** | owned by, copied/written by, sponsored by | written at | instance of | has source ↔ is source for |

