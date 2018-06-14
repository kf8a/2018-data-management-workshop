# Data Workshop
KBS-LTER

2018-06-12

---

Thanks to Data Carpentry http://www.datacarpentry.org

---

### Data sources for the workshop

https://lter.kbs.msu.edu/docs/workshop-data-2018.zip

---

## Data sources

- [KBS LTER data catalog](https://lter.kbs.msu.edu/datatables)
- [GLBRC sustainability catalog](https://data.sustainability.glbrc.org)
- [Environmental Data Initiative (EDI)](https://portal.edirepository.org/nis/home.jsp)
- [Data One](https://www.dataone.org)
- [Dryad](https://datadryad.org)

Note:
Here are some data sources that might be useful.

---

## Data in context (metadata)

---

## Metadata exercise

`metadata/` <!-- .element: class="fragment" data-fragment-index="1" -->


Note:
This study was examining the effect of wolf spiders on insect abundances
Take a look at the files and lets talk about what you would like to know about
the data

---

What, Why, Where, When and Who

---

- Contact
- Description
    - Project
    - Experiment
- Protocols
- Attributes and units
- Comments

Note:
Err on the side of putting it in the data. For example if you have microplots in treatment 1 that might seem like metadata but it might be better to put it into the data because then it would be easier to combine with other data.

---

#### Unstructured metadata

```
# Agronomic Yields - Annual Crops
#
# Original Data Source: https://lter.kbs.msu.edu/datatables/51
# The newest version of the data https://lter.kbs.msu.edu/datatables/51.csv
# Full EML Metadata: https://lter.kbs.msu.edu/datasets/23.eml
#
#     VARIATE TABLE
# Date		    harvest date
# Treatment		treatment
# Replicate		replicate
# Crop		    crop species collected
# Yield_bu_A	bushelsPerAcre	crop kernel/seed harvested at crop harvest in bu/A (at standardized moisture for corn 15.5%, wheat/soybean 13%; conversions for corn: 56 pounds/bushel wheat/soybeans: 60 pounds/bushel)
# Yield_kg_ha	kilogramsPerHectare	crop kernel/seed harvested at crop harvest in kg/ha (at standardized moisture for corn 15.5%, wheat/soybean 13%)
# Year		    crop year
#
#
Date,Treatment,Replicate,Crop,Yield_bu_A,Yield_kg_ha,Year
#,,,,bushelsPerAcre,kilogramsPerHectare,
```

---

#### Structured metadata

```xml
  <dataTable id="/datatables/25">
  <entityName>
  Kellogg Biological Station LTER: Soil Microbial Biomass via Chloroform Fumigation (KBS011-001)
  </entityName>
  <entityDescription>
    Soil microbial biomass carbon and nitrogen as determined by chloroform fumigation - incubation.
  </entityDescription>
  <attributeList>
  <attribute>
    <attributeName>date</attributeName>
      <attributeDefinition>date of sampling</attributeDefinition>
      <measurementScale>
        <dateTime>
          <formatString>YYYY-MM-DD</formatString>
          <dateTimePrecision>1</dateTimePrecision>
          <dateTimeDomain>
```

---

#### So what.


https://portal.edirepository.org/nis/mapbrowse?packageid=knb-lter-kbs.20.36 <!-- .element: class="fragment" data-fragment-index="1" -->

Note:
So what, that looks like a lot of work.
Having structured metadata enables us to write programs that use the data. For
example you remember the analysis programs on the EDI portal site. Nobody is
siting around to write these program but John Porter wrote a style-sheet to
translate the structured metadata into an analysis program.

---

### Tidy data

Well structured and portable

Note:

Data prep can take up to 80% of the time spent in data analysis and it needs to
be repeated many times over the course of the analysis or across multiple
analysis. Data tidying is the process of structuring datasets to make analysis
and reuse easier.  We can make data more portability between analysis programs,
between researchers and between questions

---

> Like families, tidy datasets are all alike, but every messy dataset is messy in its own way.

<div style="text-align: right"> Hadly Wickham 2014 </div>

Note:
The principles of tidy data provide a standard way of structuring data so that
we do not have to re-invent the wheel for each new project.

Here we are focusing mostly on datasets that have a row and column structure.

---

### Principles of tidy data

- Each variable forms a column. <!-- .element: class="fragment" data-fragment-index="1" -->
- Each observation forms a row. <!-- .element: class="fragment" data-fragment-index="2" -->
- Each type of observational unit forms a table. <!-- .element: class="fragment" data-fragment-index="3" -->

Note:

The characteristics of a tidy dataset are:

Each variable is in a column. These are the things that are measured for example
temperature.

Each observation is a row. All variables that are measured on the same
observation are together. An observation might be a sample, it might be a
capture record, it might be...

Each type of observation has it's own table

In database lingo this is organization is known as 3rd normal form. "[Every]
non-key [attribute] must provide a fact about the key, the whole key, and
nothing but the key."

---

[Data Organization in Spreadsheets](http://www.datacarpentry.org/spreadsheet-ecology-lesson/)


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

1. Put all your variables in columns. <!-- .element: class="fragment" data-fragment-index="1" -->
2. Put each observation in its own row. <!-- .element: class="fragment" data-fragment-index="2" -->
3. Don't combine multiple pieces of information in one cell. <!-- .element: class="fragment" data-fragment-index="3" -->
4. Leave the raw data raw - don't change it! <!-- .element: class="fragment" data-fragment-index="4" -->
5. Export the cleaned data to a text-based format like CSV (comma-separated values). <!-- .element: class="fragment" data-fragment-index="5" -->


Note:

All variables should go into columns, the variables are the things that
you are measuring like temperature, height, carbon, number of a species

Each observation should be in it's own row (tidy data) so each sample on it's
own row (tidy data)

Don't combine multiple pieces of information in one cell.
Sometimes it just seems like one thing, but think if that's the only way you’ll want to be able to use or sort that data.

Export the cleaned data to a text-based format like CSV (comma-separated values) format.
This ensures that anyone can use the data, and is required by most data repositories.

---

![organization](http://www.datacarpentry.org/spreadsheet-ecology-lesson/fig/multiple-info.png)

Note:

For example in this spread sheet we have the species and sex combined in one
column a better way to handle it would be split out the species and sex into
their own column like this

---

![](http://www.datacarpentry.org/spreadsheet-ecology-lesson/fig/single-info.png)

---

![](http://oshtemo.kbs.msu.edu/bohms/messy2.png)

Note:
Here we have columns that are not variables we did not measure dates but counted beetles a better way to oranize this data whould be

---

![](http://oshtemo.kbs.msu.edu/bohms/clean2.png)

Note:

Pivot tables

---

![](http://oshtemo.kbs.msu.edu/bohms/3rd-normal-form.png)


Note:

How does this table violate the tidy data principles?

Birth date should be the same for each mouse, so in repeating it in the table we
are allowing for error. We should probably organize it into two tables one with
the sample_date, mouse_id and weight and the other one with the mouse_id and
birth_date.

---

## Spreadsheet exercise

Your job is to combine and organize the dataset in <!-- .element: class="fragment" data-fragment-index="1" -->
`messy-data/` <!-- .element: class="fragment" data-fragment-index="1" -->

Note:
This is a simplified dataset from a small mammal community in southern Arizona.
They are studying the effects of rodents and ants on the plant community for
about 40 years. The rodents are sampled from a series of 24 plots. In the
dataset we have there are two years of observations gathered by different
graduate students. Your job is to combine the data and to improve the
organization.  In small groups discuss what is wrong with the dataset and
improve the organization

---

## Common spreadsheet errors

Note:
I wanted to run through a couple of common spreadsheet errors

---

Using multiple tables/tabs

![tables](http://www.datacarpentry.org/spreadsheet-ecology-lesson/fig/2_datasheet_example.jpg)

---

Problematic null values

![null_values](http://www.datacarpentry.org/spreadsheet-ecology-lesson/fig/3_white_table_1.jpg)

Note:
White et. al., 2013 in Ideas in Ecology and Evolution

---

Using formatting to convey information

![formatting](http://www.datacarpentry.org/spreadsheet-ecology-lesson/fig/formatting.png)

---

Placing comments in cells

![comments](http://oshtemo.kbs.msu.edu/bohms/comments.jpeg)

Note:
Depending on the settings they might be essentially invisible
They often get lost when going to a different analysis program

---

# Key points

- Never modify your raw data. Always make a copy before making any changes.  <!-- .element: class="fragment" data-fragment-index="1" -->
- Keep track of all of the steps you take to clean your data. <!-- .element: class="fragment" data-fragment-index="2" -->
- Organize your data according to tidy data principles. <!-- .element: class="fragment" data-fragment-index="3" -->

---

## Archive Format Exercise

What is in the files in the archive/ directory?


Note:
- Archive-1 penguins csv
- Archive-2 rainfall ods
- Archive-3 meterology netcdf
- Archive-4 radar monitoring data matlab
- Archive-5 populations wk1
- Archive-6 leaf litter wk3
- Archive-7 mle carbon xlsx

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
- R, Matlab, Mathematica, Jpython, etc.
- Database

Prevention is better than curing <!-- .element: class="fragment" data-fragment-index="1" -->

---

## Data  organization in SQL

Note:

Database tables are just like the spreadsheet tables except typed

---

### Tasks
- selecting subset of data
- group subsets of data
- calculations
- combine data

---

Working with data vs working with code that works with data

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

TDR data

---

R (MLE Carbon)

---

Thank you

---

![](http://oshtemo.kbs.msu.edu/bohms/mesocosm2009.jpeg)

---


![](http://oshtemo.kbs.msu.edu/bohms/mesocosm2011.jpeg)

---
