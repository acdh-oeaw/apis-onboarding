# Custom fields

Some values don't fit a standard text or date field. APIS projects commonly add a few
kinds of custom field to handle them.

## Interval fields

Dates can be entered as ranges rather than single values, via the
[`django-interval`](https://github.com/acdh-oeaw/django-interval) plugin. An interval
field stores a date as a pair of fields (start and end) rather than one, so "not before
1950" can be recorded honestly instead of rounded to a single date. See [Approximate
dates](../modelling/uncertainty.md#approximate-dates).

## Custom date parsers

The same plugin accepts dates typed in different formats or calendars and parses them
into a standard start/end range automatically:

![An interval field: typing "300 AH - 19c" is parsed into the interval Aug. 18, 0912 -
Dec. 31, 1899](../assets/images/web-app/interval-field.png)

The result is a list where exact, open-ended and double-bounded ranges sit side by side,
and can still be sorted and filtered by date:

![A list of dates recorded as "after X" / "before Y" ranges rather than single exact
dates](../assets/images/web-app/date-ranges-example.png)

## JSON form fields

For attributes that don't fit a fixed field at all (such as several alternative name
spellings, each with its own date range), a JSON (flexible) field lets you add as many
rows as a record needs:

![An "Alternative names" JSON field with two editable rows (name, variant type, start
year, end year) and an "Add row"
button](../assets/images/web-app/json-field-alt-names.png)
