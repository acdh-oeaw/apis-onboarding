# Example: William Shakespeare

## Historical source

>William Shakespeare was born in Stratford-upon-Avon, England, in April 1564. The exact date of his birth is not recorded, but it is most often celebrated around the world on 23 April.

>Shakespeare's baptism is recorded in the Parish Register at Holy Trinity Church, Stratford-upon-Avon on Wednesday 26 April 1564. Baptisms typically took place within three days of a new arrival, and parents were instructed by the Prayer Book to ensure that their children were baptised no later than the first Sunday after birth. This means that it's unlikely that Shakespeare was born any earlier than the previous Sunday, 23 April. Given that three days would be a reasonable interval between birth and baptism, 23 April has therefore come to be celebrated as his birthday.

>Shakespeare also died on 23 April; in 1616, when he was 52 years of age.

## Extracting information

Read closely, the passage gives: a person's name, birth and death dates (one inferred,
one exact); a place of baptism and the town and country it's in; a dated event (the
baptism) with a named source (the Parish Register); and the reasoning behind an inferred
date, which is worth recording as a note rather than discarding.

## Identifying entities

**Person (P1)**

| Attribute | Value |
|---|---|
| First name | William |
| Last name | Shakespeare |
| Born | 1564-04-23 |
| Died | 1616-04-23 |

**Place**

| Place | ID |
|---|---|
| Holy Trinity Church | PL1 |
| Stratford-upon-Avon | PL2 |
| England | PL3 |

**Event**

| Event | ID |
|---|---|
| Baptism | E1 |

## Modelling relationships

| Subject | Relation | Object | Date | Source |
|---|---|---|---|---|
| P1 | *participated in* | E1 | 1564-04-26 | Parish Register |
| E1 | *took place in* | PL1 | 1564-04-26 | Parish Register |
| PL2 | *is located in* | PL1 | — | — |

Each relation carries its own date and source, separate from the entities it connects. The same event or fact can be sourced and dated independently of the people and places
involved.

Once distilled into structured data like this, a project can answer questions like "which
events happened at Holy Trinity Church?" or "which people were baptised in April?"
without re-reading every biography.
