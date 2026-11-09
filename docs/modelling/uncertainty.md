# Uncertainty and confidence

Historical sources rarely give clean, certain facts. A chronicle might say a person
*probably* knew another person. A source might only let you say an event *did not occur
before* a certain date. A data model needs a way to record that kind of doubt honestly,
rather than forcing everything into a false certainty.

## Confidence levels

Instead of stating every relation as a flat fact, a data model
can attach a confidence level to it.

So "Person A *might have taught* Person B" becomes a normal relation record:

"Person A **taught** Person B"

with *might have* recorded as its confidence, "Probable" from this list: 

- Certain
- Probable
- Disputed

## Approximate dates

Dates are rarely known precisely either. Rather than guessing a single date, it's more
honest to record a **range**:

> "Did not occur before 1950" → start: 1950-01-01, end: Unknown (or an interpreted upper
> bound)

**Interval fields** store a date as a pair of fields (start and end) rather than one.
They can also accept dates typed in different formats or calendars (for example,
`300 AH`) and normalise them into that same start/end pair automatically, so the rest of
the model (sorting, filtering, comparing across entities) doesn't need to know how the
date was originally expressed.

## Uncertain relationships

The result is a database where "we don't know exactly when" or "we're not sure this is
true" is recorded as precisely as the source allows, rather than rounded off to a single,
misleadingly exact fact. What this looks like in the APIS web app (a Certainty field on
a relation, an interval field that parses dates automatically) is covered in [Custom
fields](../working-with-apis/custom-fields.md).
