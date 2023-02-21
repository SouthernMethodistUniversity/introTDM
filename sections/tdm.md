
# Text data mining (TDM)
    * What is Data?
    * What is Text data mining (TDM)?
    * What is Text as Data?
    * What are Types of Text Mining?

# What is Data ?
* We begin without data. Then it is *observed*, or *made*, or *imagined*, or *generated.* After that, it goes through further transformations.
    * "What are the differences between data, a dataset, and a database?
        * *Data* are observations or measurements (unprocessed or processed) represented as text, numbers, or multimedia.
        * A *dataset* is a **structured** collection of data generally associated with a unique body of work.
        * A *database* is an **organized collection of data stored as multiple datasets.** Those datasets are generally stored and accessed electronically from a computer system that allows the data to be easily accessed, manipulated, and updated. - [Definition via USGS](https://www.usgs.gov/faqs/what-are-differences-between-data-dataset-and-database#:~:text=Data%20are%20observations%20or%20measurements,a%20unique%20body%20of%20work.) 
* For the purposes of this workshop, we recommend finding an already existing data set for your project, as creating, cleaning and/or structuring a new dataset is often time and labor intensive. 
    * Remember that just because data may be avaible digitally, it does *not* automatically exist as a dataset. You may have to do works manually (copying and pasting into a spreadsheet) or computationally (scarping the data) to create a dataset usable for computational analysis.  
* Read more about [Data Prep and Cleaning](https://digitalhumanities.berkeley.edu/data-prep-and-cleaning) and [Cleaning Text Data](https://medhieval.com/classes/hh2019/labs/cleaning-text-data/)


![data life cycle](../sections/images/rdc.png)

## Forms of data
There are many ways to represent data, just as there are many sources of data. For the purposes of this series we are focusing on already digitized text. 

## Raw data 
* Raw data is yet to be processed, meaning it has yet to be manipulated by a human or computer. Received or collected data could be in any number of formats, locations, etc.. It could be in any number of forms.
* But "raw data" is a relative term, inasmuch as when one person finishes processing data and presents it as a finished product, another person may take that product and work on it further, and for them that data is "raw data". 
    * For example, is "big data" "raw data"? How do we understand data that we have "scraped"?

## Processed/transformed
* Processing data puts it into a state more readily available for analysis, and makes the data legible. We will discuss what this means for text datat in a fe wminutes. )OCR, Tokenizing etc.). For instance it could be rendered as **structured data**. This can also take many forms, e.g., a table. 

# Data mining      
 * Data mining is looking for patterns using computational methods, often across large data sets. 
 * Computer algorithms can discern patterns in bodies of (often unstructured) text. 
    * *"Unstructured”* means that little is known about the semantic meaning of the text data and that it does not fit a defined data model or database. 
    * An [*algorithm*](https://onthebooks.lib.unc.edu/about/algorithms-of-resistance/) is simply a computational process that creates an output from an input. 
            * In text analysis, the input would be the unstructured text, and the output would be indicators to help you reveal different things about the text. 

# What is TDM?
"The difference between regular data mining and text mining is that in text mining the patterns are extracted from natural language text rather than from structured databases of facts." 
    * [What Is Text Mining? by Marti Hearst.](https://people.ischool.berkeley.edu/~hearst/text-mining.html) 
* Text analysis can be used for a variety of purposes. It can be used for exploratory and analytical research, such as seeking out patterns in scientific literature to pick up trends in medical research otherwise difficult to see from the vantage point of an individual reader. It can also be used in developing tools that we use in our daily lives, for example creating spam filters to identify spam e-mail. 
    * [IBM Cloud Computing Education Definition of TDM](https://www.ibm.com/cloud/learn/text-mining#toc-what-is-te-FY0KJh4c) 
 
# How does text analysis work in general? 
Text analysis usually follows these steps:
* First, the text needs to be transformed from a form that human readers are familiar with to something that the computer can “read”. 
* The text is broken into smaller pieces and abstracted (reduced) into things that a computer can process.
* *Counting* is often what happens next.
    * Some of the things that are often counted include words, phrases, and parts of speech. 
    * The number of these counts can be used to identify characteristics of texts. 
* Then, researchers can apply computational statistics to the counts of textual features, and develop hypotheses based on these counts.

## How does it impact research?
* In a general sense, the shift in the researcher’s perspective leads to shifts in research questions. Text analysis techniques are sometimes called [*“distant reading.”*](https://uta.pressbooks.pub/datanotebook/chapter/1-4-distant-reading/) 
    * This is a term attributed to Franco Moretti, meaning “reading” literature not by studying particular texts, but by aggregating and analyzing massive amounts of texts and “reading” them at a “distance”. This scaling-up and “distancing” can bring out more insights from a very different vantage point. 
    * It is also worth mentioning that text analysis doesn’t have to be the primary method in a research project. It may be just one step in the entire process, or it can be combined with close reading. This approach has been called *“intermediate reading” or “distant-close reading”.*
* This shift in research perspective allows for new kinds of research questions to be asked, or for old questions to be “answered” in new ways. Here are some of the possibilities that text analysis can bring to researchers:
    * It can explore questions not provable by human reading alone
    * It allows larger corpora for analysis
    * It allows studies that cover longer time spans

* Text analysis techniques are often best when combined with qualitative assessment and theoretical context. 
* Text analysis research questions explore a wide range of topics, from biomedical discovery to literary history. Research questions that are conducive for text analysis methods may involve these characteristics:
    * Change over time 
    * Pattern recognition 
    * Comparative analysis 
    * [Text analysis research examples from HTRC](https://teach.htrc.illinois.edu/teaching-resources/text-analysis-research-examples/) 
        * How do the projects involve change over time, pattern recognition, or comparative analysis?
        * What kind of text data do they use (time period, source, etc.)?
        * What are their findings?

## What kind of texts do I need for text analysis?

Text analysis depends on having a large number of texts in an accessible format. Since many text analysis methods rely on statistical models, it is generally true that having more texts [(a text corpus)](https://constellate.org/docs/key-terms/#corpus) will improve the outcomes of your analysis.
* It is also generally true that an ideal set of texts—or corpus—will be:
    * Full-text
    * Easily readable, such as plaintext files or Python strings
 
In practice, "easily-readable" means that you *could* hypothetically copy and paste the text. This may be made complicated if working with works which are in copyright. If it is not possible to access "full-text" due to applicable copyright laws, the ideal corpus will give readers access to metadata or [n-gram](https://docs.constellate.org/key-terms/#n-gram) counts. (N-grams are a contiguous chain of n-items (i.e. words) where n is the number of items in the chain.) 
* While having the full texts for the documents in your corpus is ideal, a great deal can be still be discovered through the use of unigrams. Even when researchers have access to the full-texts of a corpus, it is common for them to create a list of n-gram counts for analysis. 

### TDM projects 
For a TDM project you need to complete the following steps:
1. Identify a research question or topic of interest.
2. Search for and identify a data set that is available for use and relevant to your research interests. 
    - For an introductory project, we recommend you find and use an already existing data set, rather then creating and/or cleaning a new dataset.
3. Apply the relevant computational methods.
    - Do you have a specific question you are trying to answer or are you doing an exploratory project? 
     - What type of analysis are you interested in? It may be useful to look for an article in your field on a topic you are interested in to see what the process will be like. **The data and methodology sections are always useful to read** to see where people are finding data and how they are analyzing it.


#### I have my own data. What will it take to get it ready?

*Finding, cleaning and structuring data is often time consuming and labor intensive.* 
One of the most significant benefits of using a database such as HathiTrust Digital Library, Constellate by ITHAKA or [any database](https://guides.smu.edu/az.php?t=45104) with a dataset builder is that it takes out *the vast majority* of effort in doing text analysis. 

* For a major text analysis project, such as UNC Chapel Hill's [On the Books: Jim Crow and Algorithms of Resistance](https://onthebooks.lib.unc.edu/), about *90% of the labor is creating the corpus.* For your initial project we suggest assembling a data set from one of the previously mentioned databases.

If you have your own data, you will need to assess what it will take to make it ready for analysis. Here are some questions you should ask:

* You may need to use Optical Character Recognition (OCR) to convert your data into plain text? 
* You may need to tokenize  (break up and separate the words) your texts? 
    
Consider the data's current form as well as your current skill level or the size and skill of your project staff. The corpus creation process could take anywhere from a few hours to many years of labor. 
* If there is a significant amount of labor, you may need to write a grant proposal to hire help. 
    * If writing a grant, contact your library with questions about [Research Data Management](https://www.smu.edu/Libraries/scholarship/data/data-policy) since funding agencies often require your corpus to be committed to a disciplinary or institutional repository.

* In addition to the cleaned-up texts for your corpus, you will also need a strategy for dealing with textual metadata, information such as author, year, etc. It helps to have some experience with working with data at scale with either Excel or Python Pandas.

<!--* Read about downloading historical SEC filings via EDGAR: [Textual Analysis on SEC Filings](https://mingze-gao.com/posts/textual-analysis-on-sec-filings/)-->

* Read about analyzing [U.S. political party platforms on women's issues](https://pudding.cool/projects/votes-for-women/)

* Read about [examining chyrons (the text at the bottom of the screen) from three major cable networks](https://pudding.cool/2018/01/chyrons/)

* Read about [The Emergence of Literary Diction](http://journalofdigitalhumanities.org/1-2/the-emergence-of-literary-diction-by-ted-underwood-and-jordan-sellers/)



# What is Text as Data ?

When approaching text as data, here are some things to keep in mind:
* First, having textual data of sufficient quality is important. Textual data quality is determined by how it’s created. Hand-keyed text is often of the best quality, while text obtained by OCR, Optical Character Recognition, can vary in quality. Raw, uncorrected OCR text is dirty, and it can only become clean until it is corrected. (For example, Please note that HathiTrust OCR is dirty and uncorrected.
* When viewing text as data, we usually analyze them by corpus or corpora. As mentioned in previous modules, a “corpus” of text can refer to both a digital collection and an individual's research text dataset. Text corpora are bodies of text.
* When preparing text, one can think in terms of what [Geoffrey Rockwell has called text decomposition or re-composition.](https://geoffreyrockwell.com/publications/WhatIsTAnalysis.pdf) The text will be split, combined, or represented in ways that distinguish it from human readable text. It may involve discarding some text, and requires the researcher to shift their understanding of the text from human-legible object to data. What stays, what goes, and how things are manipulated is a researcher’s choice. While there are emerging best practices, there isn’t a step-by-step guide to follow.
## Cleaning text data can involve…
- Removing Duplicates
- Correcting Errors
- Removing Outliers
- Adjusting for Missing data
- Correcting OCR errors.
- Removing title and header information
- Removing html or xml tags.
- Splitting or combining files.
- Removing certain words or punctuation marks.
- Making text into lowercase.


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

## Read more 
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
 
![Chunking text](../sections/images/chunktext.png)
* As mentioned, preparing text often involves splitting and combining files. In text analysis, splitting files is commonly referred to as chunking text. It means splitting text into smaller pieces before analysis. The text may be divided by paragraph, chapter, or a chosen number of words (e.g. 1000 word chunks). Let’s say that we have a whole text that consist of speeches of Abraham Lincoln. Before conducting analysis, the researcher may need to split the text into individual speeches. This process can be called chunking text.

![Grouping text](../sections/images/groupingtext.png)
* An opposite process that needs to be done just as often is combining text into larger pieces before analysis, which can be referred to as grouping text. Let’s look at political speeches as an example. Say that this time we have individual texts of various speeches made by Abraham Lincoln as well as George Washington. Before conducting our analysis, we may need to group the texts by combining all speeches by Lincoln into one group and all speeches by Washington into another group. 

Both chunking (from the previous image) and grouping are ways of modifying the unit of analysis for the researcher, and it’s wholly dependent on what the researcher wants to study. Maybe someone wants to compare all of Abraham Lincoln to all of George Washington, then they could create two large “buckets” of data via chunking. Or someone only wants to compare the chapters in John F. Kennedy’s “Profiles in Courage” to see how descriptions of the figures it profiled are similar or different, then a researcher might split a single work out by chapter. Those are simplistic examples, but they highlight the kinds of splitting and combining that may happen. 

![Tokenizations](../sections/images/token.png)
* An additional step in preparation is called tokenization. Tokenization is simply the process of breaking text into pieces called tokens. Often certain characters, such as punctuation marks, are discarded in the process. 
Here’s a tokenized version of the beginning of The Gettysburg Address on the image above. The original text, which is in a human-readable form, has been translated into tokens. 
While the tokens can still be parsed by a human, it isn’t in a form we regularly read. It can now, however, be read and processed by a computer. 

* It is important to note that *different choices in text preparation will affect the results of the analysis.* 
* Depending on the amount of text and size of chunks, which stop words are removed and which characters are included, and whether to lowercase and normalize words, the eventual text that is ready for analysis can be very different. Additionally, preparation for analysis takes a lot of time and effort. This is where scripting becomes useful!

* [Additional information about how text preparation impacts results](https://ssrn.com/abstract=2849145)  
* [An argument against cleaning data](https://dhdebates.gc.cuny.edu/read/untitled-f2acf72c-a469-49d8-be35-67f9ac1e3a60/section/07154de9-4903-428e-9c61-7a92a6f22e51)


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


# Searching for Text Data 
* You can search for already existing datasets in the following:

**Databases**

# *Licensed content in Library databases*
* Only some databases allow for text mining withour additional permssions. Those are [marked on our A-Z list with the filter Text Mining](https://guides.smu.edu/az.php?t=45104) 
* [HathiTrust Research Center for TDM](https://github.com/SouthernMethodistUniversity/introTDM/blob/main/sections/HTRC.md)
* [JSTOR Constellate for TDM](https://github.com/SouthernMethodistUniversity/introTDM/blob/main/sections/Constellate.md)
* [Text data sets guide](https://guides.smu.edu/textdata)
    * Additional resources for [Datasets and Data Repositories](https://guides.smu.edu/data/overview)


*Policies for Mining Licensed Content* 
* If you are thinking of basing a research project on data extracted from a library database, contact your [subject librarian](https://www.smu.edu/libraries/help/librarian) to discuss issues around permissions (copyright and licensing agreements), formats and fees.

* In addition to [copyright](https://www.smu.edu/Libraries/scholarship/copyright) considerations, we must take into account what the database vendors’ own policies specify in regard to this type of use. When providing access to a database, the library enters into licensing agreements, which also dictate what types of data can be extracted and used. Many prohibit text and data mining and the use of software such as scripts, agents, or robots, but it may be possible to negotiate text mining rights.

*Non-consumptive or non-expressive use*

* Research in which computational analysis is performed on text, but *not* research in which a researcher reads or displays substantial portions of the text to understand the expressive content presented within it.
* Non-consumptive research complies with copyright law because of the distinction in law between “ideas” and “expressions”. It is sometimes called non-expressive use (because it works with “ideas” instead of specific “expressions”, hence the term “non-expressive”). 
    * Non-consumptive research complies with copyright law because of the distinction in law between “ideas” and “expressions”. It is sometimes called non-expressive use (because it works with “ideas” instead of specific “expressions”, hence the term “non-expressive”). 
* Foundation of [HTRC](https://www.hathitrust.org/htrc_ncup) work.


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

# Types of Text Mining
## What disciplinary questions can text analysis answer?

*You can use text analysis to answer a wide variety of questions. 

* Here are a few that are common:
1. What are these texts about?
2. How are these texts connected?
3. What emotions (or affects) are found within these texts?
4. What names are used in these texts?
5. Which of these texts are most similar?

## 1. What are these texts about?
* When it comes to a large body of texts, scholars tend to be most curious about the text's contents. What are the words, topics, concepts, and significant terms in these documents? There are a number of methods often used which vary in complexity and difficulty.
___

**Word Frequency** 
* Counting the frequency of a word in any given text. This includes Bag of Words and TF-IDF. Example: “Which of these texts focus on women?”
* If you search for digital humanities in [Google image search](https://www.google.com/search?q=digital+humanities&source=lnms&tbm=isch&sa=X&ved=2ahUKEwjmhrrwjeL0AhWvkIkEHfAbCfoQ_AUoA3oECAEQBQ), the most common result is a [word cloud](https://docs.constellate.org/key-terms/#tag-cloud). A word cloud visualizes the most frequent content words in a text or corpus. 
    * Before you can create a word cloud, however, you need to collect the word frequencies for all the words in your text. You may also need to use a [stop words list](https://docs.constellate.org/key-terms/#stop-words) to remove common [function words](https://docs.constellate.org/key-terms/#function-words) (grammatical word constructions like "the", "of", and "or").

<font color="red">Start learning</font> [Word Frequency Analysis](https://constellate.org/tutorials/exploring-word-frequencies.ipynb) and create a word cloud

___

**Collocation** 
* Examining where words occur close to one another. Example: “Where are women mentioned in relation to home ownership?”
* A type of collocation is [n-gram](https://docs.constellate.org/key-terms/#n-gram) counts. 
* N-grams are a contiguous chain of n-items (i.e. words) where n is the number of items in the chain. 

![N-gram)](../sections/images/ngram.png)

In the cases where a database (such as Constellate) cannot supply full-text due to copyright laws (JSTOR and Portico content), they may supply three n-gram counts:
* Unigrams- A single-word construction, for example: "vegetable".
* Bigrams- An two-word construction, for example: "vegetable stock".
    * Notice how in the bigram example above the window of the gram slides across the text, so in bigrams, a word will occur with both the word preceding and following it. 
* Trigrams- A three-word construction, for example: "homemade vegetable stock".

While having the full texts for the documents in your corpus is ideal, a great deal can be still be discovered through the use of unigrams. Even when researchers have access to the full-texts of a corpus, it is common for them to create a list of n-gram counts for analysis. 

Read about using n-grams to [get a sense of language usage and change on Reddit](https://projects.fivethirtyeight.com/reddit-ngram/)

___

**TF/IDF** 
* Tf-IDF (term frequency–inverse document frequency) is about finding the significant words within a text. Example: “Given a decade of board reports, are there seasonal issues that crop up in summer vs. winter?”

Read more about how to do TF/IDF [here](https://programminghistorian.org/en/lessons/analyzing-documents-with-tfidf) or [here.](https://ithaka.github.io/tdm-notebooks/finding-significant-terms.html)

___

**Significant Terms** 
* Search engines use significant terms analysis to match a user query with a list of appropriate documents. This method could be useful if you want to search your corpus for the most significant texts based on a word (or set of words). It can also be useful in reverse. For a given document, you could create a list of the ten most significant terms. This can be useful for summarizing the content of a document. 

___
**Topic Analysis** (or Topic Modeling)
* Discovering the topics within a group of texts. Example: “What are the most frequent topics discussed in this newspaper?” 
* While significant terms analysis reveals terms commonly found in a given document, a topic analysis can tell us what words tend to cluster together across a corpus. For example, if we were to study newspapers, we would expect that certain words would cluster together into topics that match the sections of the newspaper. We might see something like:

* Topic 1: baseball, ball, player, trade, score, win, defeat
* Topic 2: market, dow, bull, trade, run, fund, stock
* Topic 3: campaign, democratic, polls, red, vote, defeat, state

* We can recognize that these words tend to cluster together within newspaper sections such as "Sports", "Finance", and "Politics". If we have never read a set of documents, we might use a topic analysis to get a sense of what topics are in a given corpus. Given that Topic Analysis is an exploratory technique, it may require some expertise to fine-tune and get good results for a given corpus. However, if the topics can be discovered then they could potentially be used to train a model using [Machine Learning](https://docs.constellate.org/key-terms/#machine-learning) to discover the topics in a given document automatically.

# Topic modeling
* Topic modeling is a method of using statistical models for discovering the abstract "topics" that occur in a collection of documents.
* This image visualizes what happens in a topic model.
* For this kind of analysis, the text is [chunked](https://github.com/SouthernMethodistUniversity/introTDM/blob/main/sections/TDMdata.md#preparing-data), and stop words (frequently used words such as “the”, “and”, “if”) are removed since they reveal little about the substance of a text. 
* The computer treats the textual documents as **bags of words**, and guesses which words make up a “topic” based on their proximity to one another in the documents, with the idea the words that frequently co-occur are likely about the same thing. So the different colored groupings are the groups of words that the computer has statistically analyzed and determined are likely related to each other about a “topic”.
    * “Bag-of-words” is a concept where grammar and word order of the original text are disregarded and frequency is maintained. Here is an example of the beginning of The Gettysburg Address as a bag of words.

![Bag Of Words](../sections/images/bagwords.png)

* Here are some tips for topic modeling:
* Treat topic modeling as one part of a larger analysis.
    * Understand what you input, including how you set your parameters, will affect the output. Some points to note are:
    * Be careful with how you set the number of texts analyzed, as well as number of topics generated
    * Be familiar with your input data
* Know that changing your stop word list can have really interesting impacts on your topics, so tread carefully/wisely.
* You’re going to want to go back to the text at some point. Make sure to examine your results to see if they make sense.


<font color="red">Read more</font>
Keli Du's [A Survey on LDA Topic Modeling in Digital Humanities](https://www.researchgate.net/profile/Keli-Du/publication/349279379_A_Survey_On_LDA_Topic_Modeling_In_Digital_Humanities/links/6027a55ea6fdcc37a8222850/A-Survey-On-LDA-Topic-Modeling-In-Digital-Humanities.pdf)


## 2. How are these texts connected?
___
**Concordance** 
* Where is this word or phrase used in these documents? Example: “Which journal articles mention Maya Angelou’s phrase, ‘If you’re for the right thing, then you do it without thinking.’”
* The concordance has a long history in humanities study and Roberto Busa's concordance *Index Thomisticus*—started in 1946—is arguably the first digital humanities project. Before computers were common, they were printed in large volumes such as John Bartlett's 1982 reference book *A Complete Concordance to Shakespeare*—it was 1909 pages pages long! A concordance gives the context of a given word or phrase in a body of texts. For example, a literary scholar might ask: how often and in what context does Shakespeare use the phrase "honest Iago" in Othello? A historian might examine a particular politician's speeches, looking for examples of a particular "dog whistle".

<font color="red">Read more</font>

* Steven E. Jones [Roberto Busa, S.J., and the Emergence of Humanities Computing](https://www.routledge.com/Roberto-Busa-S-J-and-the-Emergence-of-Humanities-Computing-The-Priest/Jones/p/book/9781138587250) (2016)
* Julianne Nyhan and Marco Passarotti, eds. [One Origin of Digital Humanities: Fr Roberto Busa in His Own Words](https://www.amazon.com/One-Origin-Digital-Humanities-Roberto/dp/3030183114/) (2019)
___
**Network Analysis** 
* How are the authors of these texts connected? Example: “What local communities formed around civil rights in 1963?”

## 3. What emotions (or affects) are found within these texts?

**Sentiment Analysis** (Intermediate)
Sentiment analysis, which uses computers to explore what emotions are present in the text. Does the author use positive or negative language? Example: “How do presidents describe gun control?”
Sentiment analysis can help determine the emotions expressed in a given text. This can be determined using rule-based algorithms, [Machine Learning](https://docs.constellate.org/key-terms/#machine-learning), or both.

<font color="red">Start learning</font> [Sentiment Analysis with VADER](https://constellate.org/tutorials/finding-significant-terms.ipynb)

Read about [using sentiment analysis on SEC Filings](https://medium.com/@oshojha/useful-sentiment-analysis-mining-sec-filings-part-1-358942fc98ed)

## 4. What names are used in these texts?
**Named Entity Recognition** (or NER)
* Named Entity Recognition (NER) automatically identifies entities within a text and can helpful for extracting certain kinds of entities such as proper nouns. For example, NER could identify names of organizations, people, and places. It might also help identify things like dates, times, or dollar amounts.
* You can use NER to list every example of a kind of entity from these texts. Example: “What are all of the geographic locations mentioned by Tolstoy?”

<font color="red">Read more</font>

* Miguel Won, Patricia Murrieta-Flores, and Bruno Martins [Ensemble Named Entity Recognition (NER): Evaluating NER Tools in the Identification of Place Names in Historical Corpora](https://www.frontiersin.org/articles/10.3389/fdigh.2018.00002/full) (2018)
* Read about about how hyphenated names are hard to study [here](https://pudding.cool/2019/05/hyphens/) 


## 5. Which of these texts are most similar?

**Stylometrics and Authorship Attribution** 
* Stylometrics uses computers to speculate who wrote the text based on language style. You could use it to find the author of an anonymous document. 
    * Example: “Who wrote The Federalist Papers?”
* The digital humanities, and its precursor Humanities Computing, have a long history in the analysis of literature, particularly for analyzing genre and authorship. For example, the New Oxford Shakespeare surprised many scholars by assigning significant authorship of Shakespeare's "Henry VI," Parts 1, 2, and 3. It also lists as co-authors many Shakespeare contemporaries such as Thomas Nashe, George, Peele, Thomas Heywood, Ben Jonson, George Wilkins, Thomas Middleton, and John Fletcher.

<font color="red">Read more</font>
* Patrick Juola [How a Computer Program Helped Show J.K. Rowling Wrote A Cuckoo's Calling](https://www.scientificamerican.com/article/how-a-computer-program-helped-show-jk-rowling-write-a-cuckoos-calling/) (2013)
* Ros Barber [Big data or not enough? Zeta test reliability and the attribution of Henry VI](https://academic.oup.com/dsh/article-abstract/36/3/542/5918973?redirectedFrom=fulltext)


**Clustering**
* Which texts are the most similar? Example: “Is this play closer to comedy or tragedy?”

**Supervised Machine Learning**
* Are there other texts similar to this? Example: “Are there other Jim Crow laws like these we have already identified?

## Related 

### *Machine Learning(ML)* 
* Another key approach to text analysis is *Machine Learning (ML)*, 
You can use ML which is training computers to recognize patterns in text without explicit human programming. 
* Machine learning can either be *unsupervised (with minimal human intervention)* or *supervised (with more human intervention).* 
* Here are some common, specific methods that are based on machine learning:  
    * Topic modeling, which explores the thematic topics present in the text. Remember that topic modeling is a bag-of-words approach. 
    * Naïve Bayes classification, which explores the categorization of texts, i.e. determining what categories that the researcher have named does a certain text belong to. 
* One key approach in ML for TDM is *Natural Language Processing (NLP)*, meaning using computers to understand the meaning, relationships, and semantics within human-language text. Generally for natural language processing, full text is needed. It is not a bag-of-words method. 
* Some common, specific methods under NLP are: Named entity extraction, Sentiment analysis and Stylometry.
    **Supervised Machine Learning** 
       * The advent of *supervised machine learning techniques have rapidly changed text analysis in the digital humanities. These methods "train" computers to identify and classify similar items based on data that has been labeled or tagged by experts. For example, [On the Books: Jim Crow and Algorithms of Resistance](https://onthebooks.lib.unc.edu/) was able to [use machine learning](https://github.com/UNC-Libraries-data/OnTheBooks) to [identify 1939 North Carolina Jim Crow laws enacted between Reconstruction and the Civil Rights Movement.](https://onthebooks.lib.unc.edu/about/algorithms-of-resistance/) 

<font color="red">Read more</font>
* [Project Outcomes for On the Books](https://onthebooks.lib.unc.edu/otb-research/project-outcomes/)
* William Mattingly [Introduction to Machine Learning](https://nkelber.github.io/tapi2021/book/courses/machine-learning-william.html) TAP Institute 2021
* Grant Glass [Introduction to Machine Learning](https://nkelber.github.io/tapi2021/book/courses/machine-learning-grant.html) TAP Institute 2021

___

# **Text Visualization** 

 * Data visualization is the process of converting data sources into a visual representation. This representation is usually in graphical form. Broadly speaking, anything that displays data in some visual form can be called a data visualization, including both traditional graphs and charts, as well as more innovative data art. 
* Visualizations present particular ways of interpreting data. It is not a transparent, objective projection of what the data is. By selecting different types of visualization and adjusting parameters, the resulting visualization is a researcher’s specific way of interpreting and presenting data. 
*  ["Text data [can be] a bit more challenging to use to represent insights in charts and graphs because it's not numerical."](https://www.pluralsight.com/guides/text-data-visualization-and-insights-in-python)
* See examples of [text visualizations](https://towardsdatascience.com/a-complete-exploratory-data-analysis-and-visualization-for-text-data-29fb1b96fb6a)
* Read about [SEC Visualizations](https://www.theinformedjd.com/2016/04/sec-visualizations-rank-and-file/)
* Read about using Natural Language Processing [(NLP)](https://constellate.org/docs/key-terms/#nlp) to [analyze the Wall Street Bets Reddit group](https://medium.com/swlh/analyzing-the-wall-street-bets-reddit-group-with-natural-language-processing-296465f90f26)



![theoretical Workflow](../sections/images/idealwf.png)


![Actual Workflow](../sections/images/realwf.png)


## [Terminology](https://southernmethodistuniversity.github.io/introTDM/sections/terms.html)
* [Keywords in Digital Pedagogy in the Humanities: Text analysis](https://digitalpedagogy.mla.hcommons.org/keywords/text-analysis/)
* When getting started with computational methods, looking up terms [(such as Text Mining)](https://en.wikipedia.org/wiki/Text_mining) on Wikipedia is helpful.  
s)


#### Attribution: Some content on this page adapted from:

* *Text Analysis: What Every Digital Humanist Should Know* created by [Nathan Kelber](http://nkelber.com) for [JSTOR Labs](https://labs.jstor.org/) under [Creative Commons CC BY License.](https://creativecommons.org/licenses/by/4.0/) For notebooks from Text Analysis Pedagogy Institute, see [the TAPI site](https://nkelber.github.io/tapi2021/book/intro.html).  
 * [Research Data Oxford](https://researchdata.ox.ac.uk/home/managing-your-data-at-oxford/organising-your-data/) and used under a [Creative Commons Attribution 3.0 Unported License.](https://creativecommons.org/licenses/by/3.0/).
* [BOSTON COLLEGE LIBRARIES:Text & Data Mining](https://libguides.bc.edu/textdatamining/overview) and used under a [Creative Commons Attribution 4.0 International License.](https://creativecommons.org/licenses/by/4.0/).
* [NYU Text Data Mining](https://guides.nyu.edu/tdm/start)and used under a [ Creative Commons Attribution-NonCommercial 4.0 International License.](https://creativecommons.org/licenses/by-nc/4.0/).
* [HTRC Digging Deeper, Reaching Further](https://teach.htrc.illinois.edu/teaching-materials/) used under a [Creative Commons Attribution-NonCommercial 4.0 International License.](https://creativecommons.org/licenses/by-nc/4.0/)
* [USGS data management](https://www.usgs.gov/data-management) 





