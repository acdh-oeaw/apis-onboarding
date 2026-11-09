# RDF representation

Entities can be exported as RDF,
following CIDOC CRM, so project data can be read and reused
outside APIS using open, shared standards. Here's a Person record from the
[OEBL](https://www.biographien.ac.at/oebl) project…

![A Person record "Berta Heiss" with biographical fields on the left, and empty relation
groups (Institution, Place, Person, …) on the
right](../assets/images/web-app/rdf-source-entity.png)

…and an abridged excerpt of what it exports as, in Turtle syntax:

```turtle
@prefix crm: <http://www.cidoc-crm.org/cidoc-crm/> .
@prefix oebl-appellation: <https://oebl-pfp.acdh-ch-dev.oeaw.ac.at/appellation/> .
@prefix oebl-attr: <https://oebl-pfp.acdh-ch-dev.oeaw.ac.at/attributes/> .
@prefix oebl-person: <https://oebl-pfp.acdh-ch-dev.oeaw.ac.at/apis/apis_ontology.person/> .
@prefix owl: <http://www.w3.org/2002/07/owl#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

oebl-person:78709 a crm:E21_Person ;
    rdfs:label "Berta Heiss" ;
    crm:P1_is_identified_by oebl-appellation:78709,
        oebl-attr:gnd-identifier_78709, oebl-attr:doi-identifier_78709 ;
    owl:sameAs <https://d-nb.info/gnd/101173947X>, <https://doi.org/10.1553/0x00281d32> .

oebl-attr:birth_78709 a crm:E67_Birth ;
    rdfs:label "Geburt von Berta Heiss" ;
    crm:P4_has_time-span oebl-attr:birth_time-span_78709 ;
    crm:P98_brought_into_life oebl-person:78709 .

oebl-attr:death_78709 a crm:E69_Death ;
    rdfs:label "Tod von Berta Heiss" ;
    crm:P100_was_death_of oebl-person:78709 ;
    crm:P4_has_time-span oebl-attr:death_time-span_78709 .

oebl-attr:birth_time-span_78709 a crm:E52_Time-Span ;
    crm:P82a_begin_of_the_begin "1875-01-13"^^xsd:date ;
    crm:P82b_end_of_the_end "1875-01-13"^^xsd:date .

oebl-attr:gnd-identifier_78709 a crm:E42_Identifier ;
    rdfs:label "101173947X" ;
    crm:P2_has_type oebl-attr:gnd-identifier_type .
```

The project's own entities,
events and relations all map onto standard CIDOC CRM classes and properties before
export.

## CIDOC CRM

CIDOC CRM is a shared conceptual model for cultural heritage
data, built around *events* that link people, places and objects together, rather than
attributes sitting directly on an entity. Mapping a project's model onto it is a one-off
exercise done per project, not something each record has to specify individually.

## Entities and events

A Person is `crm:E21_Person`. Their birth and death aren't attributes on the person
record. Each is its own event entity, `crm:E67_Birth` and `crm:E69_Death`, with its own
time-span. This mirrors the [Shakespeare example](../data/shakespeare-example.md): an
event (the baptism) carries the date and source, not the person.

## Identifiers and external references

A project's own internal ID and any linked external identifiers (GND, DOI, …) each become
an `crm:E42_Identifier`, typed by what kind of identifier it is. External
sameAs links are exported as `owl:sameAs` statements
alongside them, the same links picked up during [data
entry](../working-with-apis/data-entry.md#importing-from-authority-sources).

## Representing relationships

A relation in the project's own model becomes a CIDOC CRM property connecting an entity
to an event: `crm:P98_brought_into_life` connects a birth event to the person it brought
into life; `crm:P100_was_death_of` connects a death event to the person who died;
`crm:P4_has_time-span` attaches the event's date range. The pattern is the same
subject–predicate–object shape covered in [Relationships](../modelling/relationships.md).
