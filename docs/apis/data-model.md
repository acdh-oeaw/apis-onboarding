# The APIS data model

A project's data model (its entity types, attributes and relations) is the one part of
an APIS instance that's different for every project. [Data
modelling](../modelling/introduction.md) covers the general concepts; this page shows
what the result looks like in practice, across projects of different sizes.

## Data model examples

A small model, like the one on [Introduction to data
modelling](../modelling/introduction.md), stays easy to read at a glance. A project with
more entity types and a longer history of relations grows a correspondingly larger
model. This is one real project's full set of entities and relation types:

![A dense diagram of six entity types (function, institution, person, place, event,
salary) connected by dozens of named relation types, each line a distinct relation
label](../assets/images/data-modelling/complex-data-model.png)

It's fine that this is hard to read at a glance. Nobody browses the whole model at once.
Day to day, a researcher only ever sees one entity's relations at a time (see [Detail
views](../working-with-apis/detail-views.md)); a diagram like this exists to give an overview of how the data is organised in the project.

A model is sometimes easier to read as a grid: the subject entity down the side, the
object entity along the top, and each cell listing the relations that could exist between
them. Here is the full relations grid for the TibSchol project, introduced in
[Relationships](../modelling/relationships.md):

![A grid with Person, Place, Work and Instance as both rows and columns, each cell
listing the relation labels that can connect that pair of entity
types](../assets/images/apis/data-model-example-relations-grid.png)
