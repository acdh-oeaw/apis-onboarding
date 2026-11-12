# Linked open data

Historical names are ambiguous: the same person or place can appear under different
spellings, languages, abbreviations, or transliterations across your sources. "Skopje"
might also appear as "Üsküb", or under a dozen historical variants.
[Linked open data
(LOD)](https://en.wikipedia.org/wiki/Linked_data#Linked_open_data) is how
projects deal with that ambiguity. The core idea is to link each entity to a
stable record in an external database, rather than relying only on how it is
spelled in your own data.

## Disambiguation

A sameAs link (an external URL pointing to a record for
the same real-world person, place or thing in an authority
file such as GND,
VIAF or Wikidata) confirms which
real-world entity a record actually refers to. It sits alongside the entity's own
attributes, not instead of them: your project still records its own name, dates and so
on, with the external link as an added, disambiguating reference.

## Interoperability

Linking your own [controlled vocabulary](controlled-vocabularies.md) terms to a shared
external vocabulary (such as the Getty
[AAT](https://www.getty.edu/research/tools/vocabularies/aat/)) makes a term comparable
not just within your project, but across every other project that links to the same
external term, because everyone is pointing at the same identifier instead of their own
spelling.

## Data enrichment

A stored link is also what makes **enrichment** possible: pulling in an alternative name,
a profession, or other attributes already recorded in the linked authority record, rather
than retyping them. See [Enriching data](../working-with-apis/data-entry.md#enriching-data)
for what that looks like in practice.

Linked open data also works the other way: publishing a project's own data in a shared,
open format means someone outside the project can read and reuse it without knowing
anything about the software it came from. See [RDF Representation](../interoperability/rdf.md).
