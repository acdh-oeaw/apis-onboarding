APIS (the Austrian Prosopographical Information System) is a database system designed
to help you model and explore complex historical data. At its core, it organises
information around the two concepts covered in [Data modelling](../modelling/introduction.md):
entities and relations.

## Architecture

Every APIS instance is built from the same core software,
[`apis-core-rdf`](https://github.com/acdh-oeaw/apis-core-rdf), plus shared ACDH-CH
defaults (`apis-acdhch-default-settings`) on top, regardless of the project's own data
model. On that shared foundation, each project defines:

- its own **data model**, which entity and relation types it needs (see [The APIS data
  model](data-model.md));
- a **pipeline** for getting data in, curated, searched and out again (see [The APIS data
  pipeline](data-pipeline.md));
- optionally, a handful of **plugins** for specific needs, such as importing references
  from Zotero or visualising data as a network graph (see
  [Extensions](../extensions/zotero.md)).

[Current list of all APIS
projects](https://acdh-oeaw.github.io/anero-instances/) 

## Try it yourself

Two live instances are open for exploring without touching real project data:

- [**Discworld**](https://discworld.acdh-dev.oeaw.ac.at/): a plain instance built on just
  `apis-core-rdf`, good for getting a feel for the core structure. Its [data model
  documentation](https://discworld.acdh-dev.oeaw.ac.at/documentation) describes its
  entities and relations.
- [**APIS Demo**](https://apis-demo.acdh-dev.oeaw.ac.at/): a fully featured instance
  showcasing additional plugins. Log in with
  username `dhri-all-demo` and password `demopass` to try data entry, enrichment,
  filtering and export yourself.
