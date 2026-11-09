# Data entry

Data collected in spreadsheets or other formats, before the beginning or the project or in the early stages beforethe data model is finalised is typically ingested by the APIS developer after agreeing how it is reshaped into the APIS data model. 

Once the APIS instance is up and running, data is entered through standard web forms, one record at a time.

## Creating and editing entities

![A standard "Create" form for a Person entity, with fields for name, alternative names,
life dates, gender and origin](../assets/images/web-app/data-entry-form.png)

Every attribute from the project's data model gets a field on the form; editing a record
later reopens the same form, pre-filled.

## Creating places using maps

Some fields have special support: a Place record, for instance, can be created or edited
by selecting a point on a map instead of typing coordinates by hand:

![Searching for a place on a map, which fills in its label and coordinates in the form
below](../assets/images/web-app/data-entry-map.png)

## Importing from authority sources

Where a project has configured authority sources (such
as GND), the entry form can search them directly. Picking a result
stores both the source URL and any sameAs links it carries:

![Searching GND for "Skopje" while entering a Place record, with one of several matching
authority records to pick from](../assets/images/web-app/authority-search.png)

Once attached, those links show up on the entity's own page, each with a menu to merge in
further data or remove the link:

![An entity's view page with a "Linked Open Data" row listing gnd, viaf, wikidata,
loc-rwo-agents, gnd and geonames links, each with a
dropdown](../assets/images/web-app/entity-with-lod-links.png)

That stored link is what makes [enrichment](#enriching-data) possible later.

## Enriching data

Once an entity is linked to an external authority record (see [Importing from authority
sources](data-entry.md#importing-from-authority-sources)), that record's own data can be
pulled into your project rather than retyped. Each suggested change can be reviewed and
accepted individually, rather than overwriting the record outright:

![A list of proposed updates from a linked GND record — same_as links, forename and
surname — each with a checkbox to accept or skip it](../assets/images/web-app/enriching.png)
