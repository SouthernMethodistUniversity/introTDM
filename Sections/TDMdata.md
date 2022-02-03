---
jupyter:
  jupytext:
    formats: ipynb,md
    text_representation:
      extension: .md
      format_name: markdown
      format_version: '1.3'
      jupytext_version: 1.13.6
  kernelspec:
    display_name: Python 3 (ipykernel)
    language: python
    name: python3
---

For a discussion of what is text and data mining? Refer to this [introductory session](https://github.com/SouthernMethodistUniversity/introTDM/blob/main/introTDM.md)


# How do you find data for TDM projects ?

## Glossary
 > "What are the differences between data, a dataset, and a database?
  * *Data* are observations or measurements (unprocessed or processed) represented as text, numbers, or multimedia.
  * A *dataset* is a structured collection of data generally associated with a unique body of work.
  * A *database* is an organized collection of data stored as multiple datasets. Those datasets are generally stored and accessed electronically from a computer system that allows the data to be easily accessed, manipulated, and updated. 
  - [Definition via USGS](https://www.usgs.gov/faqs/what-are-differences-between-data-dataset-and-database#:~:text=Data%20are%20observations%20or%20measurements,a%20unique%20body%20of%20work.) 
* For the purposes of this workshop series, we recommend finding an already existing data set for your project, as  creating, cleaning and/or structuring a new dataset is often time and labor intensive. 
* Read more about [Data Prep and Cleaning](https://digitalhumanities.berkeley.edu/data-prep-and-cleaning) and [Cleaning Text Data](https://medhieval.com/classes/hh2019/labs/cleaning-text-data/)


<!-- #region jupyter={"source_hidden": true} tags=[] -->
## What makes a useful dataset?

For the purposes of completing a project in a semester, we recommend choosing an already existing 'good' data set so that you can start [your analysis.](https://www.usgs.gov/data-management/analyze)

* What do we mean by a 'good' data set? 

The considerations you should keep in mind for [creating a data set,](https://researchdata.ox.ac.uk/home/managing-your-data-at-oxford/organising-your-data/) are the same things you want to look for when searching for a dataset for research. 
    
   * Is there a [Data dictionary](https://www.usgs.gov/data-management/data-dictionaries) or any kind of documentation that states how the date was derived and why it was recording in the way it was. 
    
   * Good documentation makes material *understandable, verifiable, and reusable* (by you or by others).
    
   * What are the file naming conventions? 
    
   * Is there metadata ?
       * Metadata is simply ‘data about data’.  It is related to the broader contextual information that describes your data, but is usually more structured in that it conforms to set standards and is machine readable.  One typical use of metadata is to create a catalogue record for a dataset held in an archive. By using a standard set of tags, an automatic system can tell where the information about the title, creator, description and so forth begin and end.
    
   * Data that is not structured or cleaned is referred to as unstructured, noisy or dirty. *A messy data set can be used but you will need to spend time [processing that data:](https://www.usgs.gov/data-management/process) either cleaning, structuring and/or organizing it.* 

<!-- #endregion -->

# You can search for already existing datasets in the following:

**Databases**
*Licensed content in Library databases*
Some databases allow for text mining. Those are [marked on our A-Z list with ](https://guides.smu.edu/az.php?t=45104) *

*Policies for Mining Licensed Content* 
If you are thinking of basing a research project on data extracted from a library database, contact your [subject librarian](https://www.smu.edu/libraries/help/librarian) to discuss issues around permissions (copyright and licensing agreements), formats and fees.

In addition to [copyright](https://www.smu.edu/Libraries/scholarship/copyright) considerations, we must take into account what the database vendors’ own policies specify in regard to this type of use. When providing access to a database, the library enters into licensing agreements, which also dictate what types of data can be extracted and used. Many prohibit text and data mining and the use of software such as scripts, agents, or robots, but it may be possible to negotiate text mining rights.


*Licensed content in Library databases*
Some databases allow for text mining. Those are [marked on our A-Z list with the filter Text Mining](https://guides.smu.edu/az.php?t=45104) 
* [HathiTrust Research Center for TDM](https://github.com/SouthernMethodistUniversity/introTDM/blob/main/Sections/HathiTrustResearchCenter.md)
* [JSTOR Constellate for TDM](https://github.com/SouthernMethodistUniversity/introTDM/blob/main/Sections/JSTORConstellate.md)

*Policies for Mining Licensed Content* 
If you are thinking of basing a research project on data extracted from a library database, contact your [subject librarian](https://www.smu.edu/libraries/help/librarian) to discuss issues around permissions (copyright and licensing agreements), formats and fees.

In addition to [copyright](https://www.smu.edu/Libraries/scholarship/copyright) considerations, we must take into account what the database vendors’ own policies specify in regard to this type of use. When providing access to a database, the library enters into licensing agreements, which also dictate what types of data can be extracted and used. Many prohibit text and data mining and the use of software such as scripts, agents, or robots, but it may be possible to negotiate text mining rights.

**Open access (OA) or Public Domain information**

You can [search](https://guides.smu.edu/internetsearching) the open web using a web browser such as Chrome or Firefox, adding specific terms such as: data, datasets, API, file format (such as .csv). [Advanced search](https://www.google.com/advanced_search) options amy also allow for searching for specific file types. 
Try searching: 
* [Wikidata](https://www.wikidata.org/wiki/Wikidata:Main_Page)
* [Wikipedia](https://en.wikipedia.org/wiki/Main_Page)
* [Library of Congress Labs](https://labs.loc.gov/)
* [Digital Public Library](https://dp.la/)
* [Project Gutenberg](https://www.gutenberg.org/)
* You can also look at the archive for [*Data Is Plural* a weekly newsletter of datasets](https://www.data-is-plural.com/)

Depending on the the type of data, the collecting agency or you field their might be open access repositories with that data available.
* Data collected by the [U.S. government may be publicly available.](https://usafacts.org/data/)
* Your discipline may have a OA repository, such as [ARVIX, which has articles in the fields of physics, mathematics, computer science, quantitative biology, quantitative finance, statistics, electrical engineering and systems science, and economics.](https://arxiv.org/)

**Data and methodology sections of research and data journalism articles**

When reading articles on topics of interest, always pay attention to the *data and methodology sections.* 
* Where did these researchers find their data set they are using? 
* If they created it, did they make it accessible in a repository on a website, or a Github repository?

Read some data journalism articles on [The Pudding](https://pudding.cool/), [ProPublica](https://www.propublica.org/datastore) or this [roundup of data journalism projects from 2021](https://datajournalism.com/read/blog/best-data-journalism-projects-2021)



Some content on this page adapted from:
* [Research Data Oxford](https://researchdata.ox.ac.uk/home/managing-your-data-at-oxford/organising-your-data/) and used under a [Creative Commons Attribution 3.0 Unported License.](https://creativecommons.org/licenses/by/3.0/).
* [BOSTON COLLEGE LIBRARIES:Text & Data Mining](https://libguides.bc.edu/textdatamining/overview) and used under a [Creative Commons Attribution 4.0 International License..](https://creativecommons.org/licenses/by/4.0/).
* [NYU Text Data Mining](https://guides.nyu.edu/tdm/start)and used under a [ Creative Commons Attribution-NonCommercial 4.0 International License.](https://creativecommons.org/licenses/by-nc/4.0/).
* Also see:[USGS data management](https://www.usgs.gov/data-management) 
