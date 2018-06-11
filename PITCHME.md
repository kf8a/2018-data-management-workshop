# Data Workshop 2018
KBS-LTER

---

## Data sources

- [KBS LTER data catalog](https://lter.kbs.msu.edu/datatables)
- [GLBRC sustainability catalog](https://data.sustainability.glbrc.org)
- [Data Portal - Home | Environmental Data Initiative (EDI)](https://portal.edirepository.org/nis/home.jsp)
- [Data One](https://www.dataone.org)
- [Dryad](https://datadryad.org)

Note:
Here are some data sources that might be useful.

---

> ...tidy datasets are all alike, but every messy dataset is messy in its own way.

<div style="text-align: right"> Hadly Wickham 2014 </div>

---

@ul

Each variable forms a column.

Each observation forms a row.

Each type of observational unit forms a table.

@ulend


Note:

The characteristics of a tidy dataset are:

Each variable is in a column. These are the things that are measured for example
temperature.

Each observation is a row. All variables that are measured on the same
observation are together. An observation might be a sample, it might be a
capture record, it might be...

Each type of observation has it's own table

---

[Data Organization in Spreadsheets](http://www.datacarpentry.org/spreadsheet-ecology-lesson/)


From Data Carpetry Spreadsheet in ecology lesson

---

A spreadsheet is not a lab notebook


Note:
Most of the problems with spreadsheet use are a result of thinking of a
spreadsheet like a lab notebook. We make notes in the margins, draw doodles and
diagrams, intersperse it with graphs of interesting side projects.  While people
especially those that are close in time and space can generally figure out what
is meant, computers are clueless. If you want your data to be re-used in the
future creating datasets that are computer accessible is important

---

Keeping track of your changes

![spreadsheet](https://raw.githubusercontent.com/datacarpentry/spreadsheet-ecology-lesson/gh-pages/fig/spreadsheet-setup.png)

Note:
When cleaning up a dataset or doing a quick and dirty analysis it is easy to end
up with a very different spreadsheet. So we need to keep track of the changes.
One way to do that is to keep a log in a separate tab.

That way you can figure out what you did when Reviewer #3 asks to see a
different analysis

Also I talked about changes to data or "data wrangling" and "quick and dirty"
analysis. For repeatable analyses there are better tools that a spreadsheet.

---

## Spreadsheet organization

1. Put all your variables in columns.
2. Put each observation in its own row.
3. Don't combine multiple pieces of information in one cell.
4. Leave the raw data raw - don't change it!
5. Export the cleaned data to a text-based format like CSV (comma-separated values) format.


Note:

All variables should go into columns, the variables are the things that
you are measuring like temperature, height, carbon, number of a species

Each observation should be in it's own row (tidy data) so each sample on it's
own row

Don't combine multiple pieces of information in one cell.
Sometimes it just seems like one thing, but think if that's the only way you’ll want to be able to use or sort that data.

Export the cleaned data to a text-based format like CSV (comma-separated values) format.
This ensures that anyone can use the data, and is required by most data repositories.

---

## Spreadsheet organization

![organization](http://www.datacarpentry.org/spreadsheet-ecology-lesson/fig/multiple-info.png)


---

## Spreadsheet exercise

https://ndownloader.figshare.com/files/2252083

---

## Common spreadsheet errors

Note:
I wanted to run through a couple of common spreadsheet errors

---

Using multiple tables

![tables](http://www.datacarpentry.org/spreadsheet-ecology-lesson/fig/2_datasheet_example.jpg)

---

Using multiple tabs

---

Problematic null values

![null_values](http://www.datacarpentry.org/spreadsheet-ecology-lesson/fig/3_white_table_1.jpg)

---

Using formatting to convey information

![formatting](http://www.datacarpentry.org/spreadsheet-ecology-lesson/fig/formatting.png)

---

Making it pretty

It is not a lab notebook
---

Placing comments in cells

---

Combining values

---

## Data in context (metadata)

---

## Metadata exercise

http://url-of-data


Note:
which info do you want to see.

---

What, Why, Where, When and Who

---

- Description
- Units
- Protocols
- Comments

---

https://github.com/EDIorg/MetadataTemplates

---

Structured metadata

```xml
<eml:eml xmlns:eml="eml://ecoinformatics.org/eml-2.1.1" xmlns:stmml="http://www.xml-cml.org/schema/stmml-1.1" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="eml://ecoinformatics.org/eml-2.1.1 http://lter.kbs.msu.edu/docs/eml/eml.xsd" packageId="knb-lter-kbs.11.25" system="KBS LTER">
<dataset id="/datasets/14.eml">
<title>
Microbial Biomass Dynamics at the Kellogg Biological Station, Hickory Corners, MI (1989 to 1996)
</title>
<creator>
<individualName>
<givenName>David</givenName>
<surName>Harris</surName>
</individualName>
<organizationName>UC Davis</organizationName>
<address>
<deliveryPoint>122 Hunt Hall</deliveryPoint>
<city>Davis</city>
<administrativeArea>CA</administrativeArea>
<postalCode>95616</postalCode>
</address>
<phone phonetype="phone">(530) 754-7517</phone>
<phone phonetype="fax">(530)752-4361</phone>
</creator>
```

---

## Data Archiving

---

Why CSV?

![file_formats](http://oshtemo.kbs.msu.edu/bohms/file-extension.png "file formats")

Note:
Here I looked up the approximate years when spreadsheet programs introduced and
replaced file formats. I then added 14 years as the legacy time period when the
same or other spreadsheets support the format. 14 years was the time between the
release of the last spreadsheet that defaulted to .wk1 files to the time that MS
ended support for .wk1

ASCII has been around since 1960 and it's still in use 80 years later. I have a
reasonable degree of confidence that it will be readable in the future.

CSV is generally preferred by repositories, due to it's durability and
compatibility.

---

## Cleaning messy datasets

- http://openrefine.org
- SQL

---

## Data  organization in SQL

---

Buffet vs ordering from a menu

---

Working with data vs working with code that works with data

---

### Tasks
- selecting subset of data
- group subsets of data
- do calculations
- combine data

---

### What is SQL good for

- rapid access
- input validation and checking
- one source of truth
- representation of data for analysis

---

### SQL is bad at

- version control

---

### The parts of an SQL statement

- action
- object
- modifier

Not always in that order

---

Selecting data

```SQL
select *
from table
where ants > 1
```
---

Deleting data

```SQL
delete
from ants
where number_of_ants > 5000
```
---

Updating data

```SQL
update
ants
set number_of_ants = 0
where number_of_ants == -9999
```

---

Saving queries

```SQL
create view select * from table where number_of_ants > 1
```

---

SQL joins

```SQL
select number_of_ants, preciptation
from ants
join weather on ants.date = weather.date
```

---

## Graphing in R

---
