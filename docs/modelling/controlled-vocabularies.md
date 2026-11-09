# Controlled vocabularies

A controlled vocabulary is a set of standardised
concepts used to describe entities, instead of free text.

Free text is flexible but inconsistent: one record might describe someone's role as
"monk", another as "Buddhist monk", another as "religious, monastic"; three ways of
saying something that, for searching and counting, should be treated as one value. A
controlled vocabulary replaces that free text with a fixed list of agreed terms, so every
record that means the same thing says the same thing.

This matters because it:

- **replaces inconsistent free-text descriptions** with a single, agreed term for each
  concept.
- **makes historical data consistent, searchable, and comparable**: you can reliably
  filter or count records by vocabulary term, which you can't do with free text.

## Example: a profession vocabulary

Vocabularies are often organised hierarchically, grouping specific terms under broader
categories:

```
Profession
├── Religious
│   ├── Theologian
│   ├── Monk
│   └── Abbot
├── Political & Administrative
│   ├── Ruler
│   ├── Vizier
│   ├── Judge
│   └── Chancery Official
├── Scholarly
│   ├── Philosopher
│   ├── Historian
│   ├── Grammarian
│   └── Philologist
└── Literary
    ├── Poet
    ├── Translator
    └── Scribe
```

Recording that a Person's profession is "Scribe" (rather than typing "he was a scribe" as
free text) means every "Scribe" across the whole project is directly comparable: you can
list all of them, filter by them, or combine them with other projects that use the same
vocabulary.

A vocabulary term can also be used as a point of disambiguation:
projects often link their own vocabulary terms to an external, shared vocabulary, (such as Getty [AAT](https://www.getty.edu/research/tools/vocabularies/aat/)). 
