# From sources to data

Historical sources describe the same things in inconsistent ways: a name spelled three
different ways, a date given in a different calendar, a role described in different
words from source to source. Turning sources into structured
data means resolving those inconsistencies, a process
called normalisation so that records about the same
person, date or concept can be found, compared and counted together.

| Historical sources | Structured data |
|---|---|
| Rich, contextual, and nuanced | Structured and relational |
| Ambiguous and open to interpretation | Explicitly modelled and documented |
| Narrative and descriptive | Consistent, comparable, and queryable |

## Normalisation

Converting whatever form a value takes in a source into one consistent, agreed form,
applied the same way across every record.

## Consistent names

The same person can appear under several spellings, abbreviations or transliterations
across sources. Normalisation picks one form to record and treats the others as
variants of it, rather than as different people.

## Controlled vocabularies

Free-text descriptions ("monk", "Buddhist monk", "religious, monastic") are replaced
with a single, agreed term from a fixed list, so every record that means the same thing
says the same thing. See [Controlled vocabularies](../modelling/controlled-vocabularies.md).

## Standardised dates

Dates recorded in different formats or calendars (`23 April 1564`, `300 AH`) are
converted into one standard form, so records can be sorted and compared regardless of how
the original date was written.

## Unique identifiers

Each entity gets one stable identifier within the project, and ideally a link to an
external, shared identifier (an authority file record),
so it can be told apart from every other entity with a similar name. See [Linked open
data](../modelling/linked-open-data.md).
