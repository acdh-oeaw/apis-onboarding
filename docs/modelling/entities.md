## Entities
An entity is a concept or an object: a "thing" a project
records. Projects add whatever else their sources need: Inscription, Monument, Object, Expression,
Profession, Function, and so on. Which entity types a project uses, and what they're called, is defined by that
project's own data model. TibSchol, for instance, makes use of four entity types:
**Person**, **Place**, **Work**, **Instance** to model Tibetan Buddhist scholastic
texts.

## Attributes

An attribute is information that belongs to an entity
directly, rather than connecting it to another entity. Compare with a
relation, which always links two entities together.

- **Person**: name, date of birth, death, nationality, …
- **Work**: name, date of composition, topic, …
- **Instance**: title, volume, number of folios, …
- **Place**: name, coordinates, …

A good rule of thumb: if the value is a fact *about* the entity (a name, a date, a
number), it's an attribute. If the value is really another entity in disguise (a place of
birth, an author), it belongs in a relation instead. See
[Relationships](relationships.md).
