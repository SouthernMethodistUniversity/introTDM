For a discussion of what is text and data mining? Refer to this [introductory session](https://github.com/SouthernMethodistUniversity/introTDM/blob/main/sections/TDMintro.md)

# How do you find data for TDM projects ?

## Glossary
 > "What are the differences between data, a dataset, and a database?
  * *Data* are observations or measurements (unprocessed or processed) represented as text, numbers, or multimedia.
  * A *dataset* is a structured collection of data generally associated with a unique body of work.
  * A *database* is an organized collection of data stored as multiple datasets. Those datasets are generally stored and accessed electronically from a computer system that allows the data to be easily accessed, manipulated, and updated. 
  - [Definition via USGS](https://www.usgs.gov/faqs/what-are-differences-between-data-dataset-and-database#:~:text=Data%20are%20observations%20or%20measurements,a%20unique%20body%20of%20work.) 
* For the purposes of this workshop series, we recommend finding an already existing data set for your project, as creating, cleaning and/or structuring a new dataset is often time and labor intensive. 
    * Remember that just because data may be avaible digitally, it does *not* automatically exist as a dataset. You may have to do works manually (copying and pasting into a spreadsheet) or computationally (scarping the data) to create a dataset usable for computational analysis.  
* Read more about [Data Prep and Cleaning](https://digitalhumanities.berkeley.edu/data-prep-and-cleaning) and [Cleaning Text Data](https://medhieval.com/classes/hh2019/labs/cleaning-text-data/)



# What are the stages of data ?
* We begin without data. Then it is *observed*, or *made*, or *imagined*, or *generated.* After that, it goes through further transformations.

[![data life cycle](https://github.com/SouthernMethodistUniversity/introTDM/blob/main/images/rdc.png)](https://github.com/SouthernMethodistUniversity/introTDM/blob/main/images/rdc.png)


## Raw data 
* Raw data is yet to be processed, meaning it has yet to be manipulated by a human or computer. Received or collected data could be in any number of formats, locations, etc.. It could be in any number of forms.
* But "raw data" is a relative term, inasmuch as when one person finishes processing data and presents it as a finished product, another person may take that product and work on it further, and for them that data is "raw data". 
    * For example, is "big data" "raw data"? How do we understand data that we have "scraped"?

## Processed/transformed

* Processing data puts it into a state more readily available for analysis, and makes the data legible. For instance it could be rendered as **structured data**. This can also take many forms, e.g., a table. 

* Here are a few you're likely to come across, all representing the same data:

### XML

```
<Cats> 
    <Cat> 
        <firstName>Smally</firstName> <lastName>McTiny</lastName> 
    </Cat> 
    <Cat> 
        <firstName>Kitty</firstName> <lastName>Kitty</lastName> 
    </Cat> 
    <Cat> 
        <firstName>Foots</firstName> <lastName>Smith</lastName> 
    </Cat> 
    <Cat> 
        <firstName>Tiger</firstName> <lastName>Jaws</lastName> 
    </Cat> 
</Cats> 
```

### JSON

```
{"Cats":[ 
    { "firstName":"Smally", "lastName":"McTiny" }, 
    { "firstName":"Kitty", "lastName":"Kitty" }, 
    { "firstName":"Foots", "lastName":"Smith" }, 
    { "firstName":"Tiger", "lastName":"Jaws" } 
]} 
```

### CSV
```
First Name,Last Name/n
Smally,McTiny/n
Kitty,Kitty/n
Foots,Smith/n
Tiger,Jaws/n
```

# Text as Data 

When approaching text as data, here are some things to keep in mind:

* First, having textual data of sufficient quality is important. Textual data quality is determined by how it’s created. Hand-keyed text is often of the best quality, while text obtained by OCR, Optical Character Recognition, can vary in quality. Raw, uncorrected OCR text is dirty, and it can only become clean until it is corrected. (For example, Please note that HathiTrust OCR is dirty and uncorrected.
* When viewing text as data, we usually analyze them by corpus or corpora. As mentioned in previous modules, a “corpus” of text can refer to both a digital collection and an individual's research text dataset. Text corpora are bodies of text.
* When preparing text, one can think in terms of what [Geoffrey Rockwell has called text decomposition or re-composition.](https://geoffreyrockwell.com/publications/WhatIsTAnalysis.pdf) The text will be split, combined, or represented in ways that distinguish it from human readable text. It may involve discarding some text, and requires the researcher to shift their understanding of the text from human-legible object to data. What stays, what goes, and how things are manipulated is a researcher’s choice. While there are emerging best practices, there isn’t a step-by-step guide to follow.

## What makes a useful dataset?

For the purposes of completing a project in a semester, we recommend choosing an already existing 'good' data set so that you can start [your analysis.](https://www.usgs.gov/data-management/analyze)

* What do we mean by a 'good' data set? 

The considerations you should keep in mind for [creating a data set,](https://researchdata.ox.ac.uk/home/managing-your-data-at-oxford/organising-your-data/) are the same things you want to look for when searching for a dataset for research. 
    
   * Is there a [Data dictionary](https://www.usgs.gov/data-management/data-dictionaries) or any kind of documentation that states how the date was derived and why it was recording in the way it was. 
    
   * Good documentation makes material *understandable, verifiable, and reusable* (by you or by others).
    
   * What are the file naming conventions? 
    
   * Is there metadata?
       * Metadata is simply ‘data about data’.  It is related to the broader contextual information that describes your data, but is usually more structured in that it conforms to set standards and is machine readable.  One typical use of metadata is to create a catalogue record for a dataset held in an archive. By using a standard set of tags, an automatic system can tell where the information about the title, creator, description and so forth begin and end.
    
   * Data that is not structured or cleaned is referred to as unstructured, noisy or dirty. *A messy data set can be used but you will need to spend time [processing that data:](https://www.usgs.gov/data-management/process) either cleaning, structuring and/or organizing it.* 

Read more: 
* Read more about [Data in digital humanities](https://github.com/SouthernMethodistUniversity/data) 
* [Datasets as Primary Sources: An Archaeological Dig into Our Collective Brains, Part 1](https://blogs.loc.gov/thesignal/2022/02/datasets-as-primary-sources-an-archaeological-dig-into-our-collective-brains-part-1/)
* [DH@ Berkley:Data Prep and Cleaning](https://digitalhumanities.berkeley.edu/data-prep-and-cleaning)
* "Data cleaning is the process of fixing or removing incorrect, corrupted, incorrectly formatted, duplicate, or incomplete data within a dataset. When combining multiple data sources, there are many opportunities for data to be duplicated or mislabeled." 
    * How do you clean data?
        * Step 1: Remove duplicate or irrelevant observations
        * Step 2: Fix structural errors
        * Step 3: Filter unwanted outliers
        * Step 4: Handle missing data
        * Step 5: Validate and QA (quality assurance)
            * [Guide To Data Cleaning: Definition, Benefits, Components, And How To Clean Your Data](https://www.tableau.com/learn/articles/what-is-data-cleaning) 

# Preparing Data
* After gathering the data needed for research and before conducting the actual analysis, data often requires preparation (also sometimes refereed ot as pre-processing the data). Preparing data can take a lot of time and effort.
* Examples of what may be necessary to do before the data is in a workable state: 
    * Correcting OCR errors.
    * Removing title and header information.
    * Removing html or xml tags.
    * Splitting or combining files. 
    * Removing certain words or punctuation marks.
    * Making text into lowercase.
    
[![Chunking text](https://github.com/SouthernMethodistUniversity/introTDM/blob/main/images/chunktext.png)](https://github.com/SouthernMethodistUniversity/introTDM/blob/main/images/chunktext.png)
* As mentioned, preparing text often involves splitting and combining files. In text analysis, splitting files is commonly referred to as chunking text. It means splitting text into smaller pieces before analysis. The text may be divided by paragraph, chapter, or a chosen number of words (e.g. 1000 word chunks). Let’s say that we have a whole text that consist of speeches of Abraham Lincoln. Before conducting analysis, the researcher may need to split the text into individual speeches. This process can be called chunking text.

[![Grouping text](https://github.com/SouthernMethodistUniversity/introTDM/blob/main/images/groupingtext.png)](https://github.com/SouthernMethodistUniversity/introTDM/blob/main/images/groupingtext.png)
* An opposite process that needs to be done just as often is combining text into larger pieces before analysis, which can be referred to as grouping text. Let’s look at political speeches as an example. Say that this time we have individual texts of various speeches made by Abraham Lincoln as well as George Washington. Before conducting our analysis, we may need to group the texts by combining all speeches by Lincoln into one group and all speeches by Washington into another group. 

Both chunking (from the previous image) and grouping are ways of modifying the unit of analysis for the researcher, and it’s wholly dependent on what the researcher wants to study. Maybe someone wants to compare all of Abraham Lincoln to all of George Washington, then they could create two large “buckets” of data via chunking. Or someone only wants to compare the chapters in John F. Kennedy’s “Profiles in Courage” to see how descriptions of the figures it profiled are similar or different, then a researcher might split a single work out by chapter. Those are simplistic examples, but they highlight the kinds of splitting and combining that may happen. 

[![Tokenizations](https://github.com/SouthernMethodistUniversity/introTDM/blob/main/images/token.png)](https://github.com/SouthernMethodistUniversity/introTDM/blob/main/images/token.png)
* An additional step in preparation is called tokenization. Tokenization is simply the process of breaking text into pieces called tokens. Often certain characters, such as punctuation marks, are discarded in the process. 
Here’s a tokenized version of the beginning of The Gettysburg Address on the image above. The original text, which is in a human-readable form, has been translated into tokens. 
While the tokens can still be parsed by a human, it isn’t in a form we regularly read. It can now, however, be read and processed by a computer. 

* It is important to note that *different choices in text preparation will affect the results of the analysis.* 
* Depending on the amount of text and size of chunks, which stop words are removed and which characters are included, and whether to lowercase and normalize words, the eventual text that is ready for analysis can be very different. Additionally, preparation for analysis takes a lot of time and effort. This is where scripting becomes useful!

* [Additional information about how text preparation impacts results](https://ssrn.com/abstract=2849145)  
* [An argument against cleaning data](https://dhdebates.gc.cuny.edu/read/untitled-f2acf72c-a469-49d8-be35-67f9ac1e3a60/section/07154de9-4903-428e-9c61-7a92a6f22e51)


# Approaches to TDM
* See our [introduction to TM methods ](https://github.com/SouthernMethodistUniversity/introTDM/blob/main/sections/TDMintro.md).
* The TDM approaches you want to use will dictate your preprocessing choices.  


### The importance of using open data formats
A small detour to discuss (the ethics of?) data formats. For accessibility, future-proofing, and preservation, keep your data in open, sustainable formats. A demonstration:

Sustainable formats are generally unencrypted, uncompressed, and follow an open standard. A small list:

* ASCII
* PDF 
* .csv
* FLAC
* TIFF
* JPEG2000
* MPEG-4
* XML
* RDF
* .txt
* .r

How do you decide the formats to store your data when you transition from 'raw' to 'processed/transformed' data? What are some of your considerations?

## Tidy data
There are guidelines to the processing of data, sometimes referred to as **Tidy Data**.<sup>1</sup> One manifestation of these rules:
1. Each variable is in a column.
2. Each observation is a row.
3. Each value is a cell.

Look back at our example of cats to see how they may or may not follow those guidelines. **Important note**: Some data formats allow for more than one dimension of data! How might that complicate the concept of **Tidy Data**?

```
{"Cats":[
    {"Calico":[
    { "firstName":"Smally", "lastName":"McTiny" },
    { "firstName":"Kitty", "lastName":"Kitty" }],
    "Tortoiseshell":[
    { "firstName":"Foots", "lastName":"Smith" }, 
    { "firstName":"Tiger", "lastName":"Jaws" }]}]}
```

 <sup>1</sup>[Wickham, Hadley. "Tidy Data". Journal of Statistical Software.](https://www.jstatsoft.org/article/view/v059i10)

## Forms of data

There are many ways to represent data, just as there are many sources of data. For the purposes of this series we are focusing on already digitized text. In the next session workshop in this series, you will see how a .csv file can be processed an analysed using Python. 

# You can search for already existing datasets in the following:

**Databases**

# *Licensed content in Library databases*
* Only some databases allow for text mining. Those are [marked on our A-Z list with the filter Text Mining](https://guides.smu.edu/az.php?t=45104) 
* [HathiTrust Research Center for TDM](https://github.com/SouthernMethodistUniversity/introTDM/blob/main/sections/HTRC.md)
* [JSTOR Constellate for TDM](https://github.com/SouthernMethodistUniversity/introTDM/blob/main/sections/Constellate.md)
* Additional resources for [Datasets and Data Repositories](https://guides.smu.edu/data/overview)

*Policies for Mining Licensed Content* 
* If you are thinking of basing a research project on data extracted from a library database, contact your [subject librarian](https://www.smu.edu/libraries/help/librarian) to discuss issues around permissions (copyright and licensing agreements), formats and fees.

* In addition to [copyright](https://www.smu.edu/Libraries/scholarship/copyright) considerations, we must take into account what the database vendors’ own policies specify in regard to this type of use. When providing access to a database, the library enters into licensing agreements, which also dictate what types of data can be extracted and used. Many prohibit text and data mining and the use of software such as scripts, agents, or robots, but it may be possible to negotiate text mining rights.

*Non-consumptive or non-expressive use*

* Research in which computational analysis is performed on text, but *not* research in which a researcher reads or displays substantial portions of the text to understand the expressive content presented within it.
* Non-consumptive research complies with copyright law because of the distinction in law between “ideas” and “expressions”. It is sometimes called non-expressive use (because it works with “ideas” instead of specific “expressions”, hence the term “non-expressive”). 
    * Non-consumptive research complies with copyright law because of the distinction in law between “ideas” and “expressions”. It is sometimes called non-expressive use (because it works with “ideas” instead of specific “expressions”, hence the term “non-expressive”). 
* Foundation of [HTRC](https://github.com/SouthernMethodistUniversity/introTDM/blob/main/sections/HTRC.md) work.


**Open access (OA) or Public Domain information**

You can [search](https://guides.smu.edu/internetsearching) the open web using a web browser such as Chrome or Firefox, adding specific terms such as: data, datasets, API, file format (such as .csv). [Advanced search](https://www.google.com/advanced_search) options amy also allow for searching for specific file types. 
Try searching: 
* [Wikidata](https://www.wikidata.org/wiki/Wikidata:Main_Page)
* [Wikipedia](https://en.wikipedia.org/wiki/Main_Page)
* [Wikisource](https://en.wikisource.org/wiki/Main_Page)
* [Library of Congress Labs](https://labs.loc.gov/)
* [Digital Public Library](https://dp.la/)
* [Project Gutenberg](https://www.gutenberg.org/)
* You can also look at the archive for [*Data Is Plural* a weekly newsletter of datasets](https://www.data-is-plural.com/)

Depending on the the type of data, the collecting agency or you field their might be open access repositories with that data available.
* Data collected by the [U.S. government may be publicly available.](https://usafacts.org/data/)
* Your discipline may have a OA repository, such as [arXiv, which has articles in the fields of physics, mathematics, computer science, quantitative biology, quantitative finance, statistics, electrical engineering and systems science, and economics.](https://arxiv.org/)


### *Highly recommended practice:* Read the Data and methodology sections of research and/or data journalism articles

When you are considering learning new methodologies, we highly recommend searching for academic or data journalism articles where the authors have asked similar questions or used related methodologies. 
* When reading these articles, pay particular attentions to the literature review, and to the *data and methodology sections.* 
* Where did these researchers find their data set they are using? 
* If they created it, did they make it accessible in a repository on a website, or a Github repository?

Read some data journalism articles on [The Pudding](https://pudding.cool/), [ProPublica](https://www.propublica.org/datastore) or this [roundup of data journalism projects from 2021](https://datajournalism.com/read/blog/best-data-journalism-projects-2021)



# Next Session
* In the next workshop we will be introducing Python. 
* Python is a commonly-used programming language, and it’s very useful for working with data. 
    * It is also an [interpreted language, which basically means it follows step-by-step directions.](https://www.freecodecamp.org/news/compiled-versus-interpreted-languages/) 
    * Additionally, Python is generally easy to learn with its relatively simple syntax. For example, one of its learner-friendly features is it avoids excess punctuation. 



Some content on this page adapted from:
    
* [Research Data Oxford](https://researchdata.ox.ac.uk/home/managing-your-data-at-oxford/organising-your-data/) and used under a [Creative Commons Attribution 3.0 Unported License.](https://creativecommons.org/licenses/by/3.0/).
* [BOSTON COLLEGE LIBRARIES:Text & Data Mining](https://libguides.bc.edu/textdatamining/overview) and used under a [Creative Commons Attribution 4.0 International License..](https://creativecommons.org/licenses/by/4.0/).
* [NYU Text Data Mining](https://guides.nyu.edu/tdm/start)and used under a [ Creative Commons Attribution-NonCommercial 4.0 International License.](https://creativecommons.org/licenses/by-nc/4.0/).
* [HTRC Digging Deeper, Reaching Further](https://teach.htrc.illinois.edu/teaching-materials/) used under a [Creative Commons Attribution-NonCommercial 4.0 International License.](https://creativecommons.org/licenses/by-nc/4.0/)
* Also see:[USGS data management](https://www.usgs.gov/data-management) 
