# Data Workshop 2018

---

## Data sources

- [KBS LTER data catalog](https://lter.kbs.msu.edu/datatables)
- [GLBRC sustainability catalog](https://data.sustainability.glbrc.org)
- [Data Portal - Home | Environmental Data Initiative (EDI)](https://portal.edirepository.org/nis/home.jsp)
- [Data One](https://www.dataone.org)
- [Dryad](https://datadryad.org)

---

> ...tidy datasets are all alike, but every messy dataset is messy in its own way.

<div style="text-align: right"> Hadly Wickham 2014 </div>

---

Each variable forms a column.

Each observation forms a row.

Each type of observational unit forms a table.

---

[Data Organization in Spreadsheets](http://www.datacarpentry.org/spreadsheet-ecology-lesson/)



      From Data Carpetry Spreadsheet in ecology lesson
---

Keeping track of your changes

![spreadsheet](https://raw.githubusercontent.com/datacarpentry/spreadsheet-ecology-lesson/gh-pages/fig/spreadsheet-setup.png
"spreadsheet notes")

Note:
When cleaning up a dataset or doing a quick and dirty analysis it is easy
to end up with a very different spreadsheet than you started with. Keep track of
the changes in log in a separate tab.
That way you can figure out what you did when Reviewer #3 asks to see a
different method of analysis. Also note that I said to keep track of your
changes to the data, I did not talk about data analysis. While spreadsheets are
good for a quick and dirty analysis, the emphasis should be on "quick and
dirty", documenting a spreadsheet analysis is a bit work.

----

## Spreadsheet organization

1. Put all your variables in columns.
2. Put each observation in its own row.
3. Don't combine multiple pieces of information in one cell.
4. Leave the raw data raw - don't change it!
5. Export the cleaned data to a text-based format like CSV (comma-separated values) format.

Note:
all variables should go into columns, the variables are the things that
you are measuring like temperature, height, carbon, number of a species

Each observation should be in it's own row (tidy data) so each sample on it's
own row

Don't combine multiple pieces of information in one cell. Sometimes it just seems like one thing, but think if that's the only way you’ll want to be able to use or sort that data.

Export the cleaned data to a text-based format like CSV (comma-separated values) format. This ensures that anyone can use the data, and is required by most data repositories.

---

## Spreadsheet organization

![organization](http://www.datacarpentry.org/spreadsheet-ecology-lesson/fig/multiple-info.png
"Spreadsheet Organization")

---

## Spreadsheet exercise

https://ndownloader.figshare.com/files/2252083

---

## Common spreadsheet errors

---

Using multiple tables

![tables](http://www.datacarpentry.org/spreadsheet-ecology-lesson/fig/2_datasheet_example.jpg "multiple tables")

---

Using multiple tabs

---

Problematic null values

![null_values](http://www.datacarpentry.org/spreadsheet-ecology-lesson/fig/3_white_table_1.jpg "problematic null values")

---

Using formatting to convey information

![formatting](http://www.datacarpentry.org/spreadsheet-ecology-lesson/fig/formatting.png "don't use formatting for information")

---

Making it pretty

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
what would you like to see?

---

- What why where when who
  - Description
  - Units
  - Protocols
  - Comments


---

  https://github.com/EDIorg/MetadataTemplates

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

Data vs presentation

---

## Data  organization in SQL

---

### What is SQL good for

- rapid access to large amounts of information
- input validation and checking
- one source of truth
- generating convenient representations of the data for analysis

---

### SQL is bad at

- version control

---

### The parts of an SQL statement

- action
- object
- modifier


not always in that order

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
