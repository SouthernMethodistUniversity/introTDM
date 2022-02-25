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

<img align="left" src="https://ithaka-labs.s3.amazonaws.com/static-files/images/tdm/tdmdocs/CC_BY.png"><br />

Adapted from notebook *Text Analysis: What Every Digital Humanist Should Know* created by [Nathan Kelber](http://nkelber.com) for [JSTOR Labs](https://labs.jstor.org/) under [Creative Commons CC BY License](https://creativecommons.org/licenses/by/4.0/)<br />
For notebooks from Text Analysis Pedagogy Institute, see [the TAPI site](https://nkelber.github.io/tapi2021/book/intro.html) 
**This notebook does not contain code but links to notebooks with code.**
___


# Text Analysis: What Every Digital Scholar Should Know

This notebook is a high-level overview of the fundamental text analysis methods common in the digital scholarship. This notebook will help any researcher interested in text analysis but unsure what methods might help their current research project.

This notebook discusses:

* What text analysis methods are useful for your discipline?
* What kinds of questions can a particular method answer?
* How difficult is a particular method to learn?


# Text Mining: What is it?

* Text Mining is also sometimes referred to as TDM (Text and Data mining).
* Broadly speaking, it’s the process by which computers are used to reveal information in and about text [(Marti Hearst definition)]([What Is Text Mining? -Marti Hearst](https://people.ischool.berkeley.edu/~hearst/text-mining.html)). 
* Computer algorithms can discern patterns in bodies of (often unstructured) text. 
    * *"Unstructured”* means that little is known about the semantic meaning of the text data and that it does not fit a defined data model or database. 
        * An *algorithm* is simply a computational process that creates an output from an input. 
    * In text analysis, the input would be the unstructured text, and the output would be indicators to help you reveal different things about the text. 
        * It should be noted that text analysis is more than just search, meaning it’s not just about discovery and knowing something is there. It’s also about exploring what does it mean for something to be there. 
    * Text analysis can be used for a variety of purposes. It can be used for exploratory and analytical research, such as seeking out patterns in scientific literature to pick up trends in medical research otherwise difficult to see from the vantage point of an individual reader. It can also be used in developing tools that we use in our daily lives, for example creating spam filters to identify spam e-mail. 
    * [What Is Text Mining? -Marti Hearst](https://people.ischool.berkeley.edu/~hearst/text-mining.html)
    * [IBM Cloud Computing Education Definition of TDM](https://www.ibm.com/cloud/learn/text-mining#toc-what-is-te-FY0KJh4c) 
    * Data mining is looking for patterns using computational methods, often across large data sets. 
    * TDM is when your data set consist of text.
    * For a TDM project you need to complete the following steps:
        1. Identify a research question or topic of interest.
        2. Search for and identify a data set that is available for use and relevant to your research interests. 
         * For an introductory project we recommend you find and use an already existing data set, rather then creating and/or cleaning a new dataset.
         * [Introduction to Data life cycle](https://github.com/SouthernMethodistUniversity/datalifecycle#introduction-to-the-stages-of-the-data-life-cycle)
        3. Apply the relevant computational methods.
         * Do you have a specific question you are trying to answer or are you doing an exploratory project? What type of analysis are you interested in? It may be useful to look for an article in your field on a topic you are interested in to see what the process will be like. 
            * The data and methodology sections are always useful to see where people are fiding data and how they are analyzing it.

## [Terminology](https://github.com/SouthernMethodistUniversity/introTDM/blob/main/sections/terminology.md)
* [Text analysis glossary](https://constellate.org/docs/key-terms/)
* When getting started with computational methods, looking up terms [(such as Text Mining)](https://en.wikipedia.org/wiki/Text_mining) on Wikipedia is helpful.  


# So how does text analysis work in general? 

Text analysis usually follows these steps:
* First, the text needs to be transformed from a form that human readers are familiar with to something that the computer can “read”. 
* This means we need to break the text into smaller pieces, and abstract (reduce) it into things that a computer can crunch.
* Counting is often what happens next. 
    * Some of the things that are often counted include words, phrases, and parts of speech. 
    * The number of these counts can be used to identify characteristics of texts. 
* Then, researchers can apply computational statistics to the counts of textual features, and develop hypotheses based on these counts.


# How does it impact research?

* In a general sense, the shift in the researcher’s perspective leads to shifts in research questions. Text analysis techniques are sometimes called *“distant reading”. 
    * This is a term coined by Stanford professor Franco Moretti, meaning “reading” literature not by studying particular texts, but by aggregating and analyzing massive amounts of texts and “reading” them at a “distance”. This scaling-up and “distancing” can bring out more insights from a very different vantage point. 
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
    
[Examples for discussion](https://teach.htrc.illinois.edu/teaching-resources/text-analysis-research-examples/) 
* How do the projects involve change over time, pattern recognition, or comparative analysis?
* What kind of text data do they use (time period, source, etc.)?
* What are their findings? 


## What kind of texts do I need for text analysis?

Text analysis depends on having a large number of texts in an accessible format. Since many text analysis methods rely on statistical models, it is generally true that having more texts [(a text corpus)](https://constellate.org/docs/key-terms/#corpus)will improve the outcomes of your analysis.
* It is also generally true that an ideal set of texts—or corpus—will be:
    * Full-text
    * Easily readable, such as plaintext files or Python strings
        * We will discuss formats more in our [Text as Data discussion.](https://github.com/SouthernMethodistUniversity/introTDM/blob/main/sections/TDMdata.md)


In practice, "easily-readable" means that you could hypothetically copy and paste the text. It is common, however, when doing text analysis to work with current works which are in copyright. If it is not possible to access "full-text" due to applicable copyright laws, the ideal corpus will give readers access to metadata or [n-gram](https://docs.constellate.org/key-terms/#n-gram) counts. (N-grams are a contiguous chain of n-items (i.e. words) where n is the number of items in the chain.) 
* While having the full texts for the documents in your corpus is ideal, a great deal can be still be discovered through the use of unigrams. Even when researchers have access to the full-texts of a corpus, it is common for them to create a list of n-gram counts for analysis. 
___
<font color="red">Read more</font>
* [Constellate Dataset Builder: full-text and n-gram content](https://constellate.org/docs/data-sources)
* [Bring your own data into Constellate](https://constellate.org/docs/import-data-into-constellate)
* [Hathitrust Digital Library](https://www.hathitrust.org/help_digital_library)


## I have my own data. What will it take to get it ready?

*Finding, cleaning and structuring data is often time consuming and labor intensive.* 
One of the most significant benefits of using a data base such as HathiTrust Digital Library, Constellate by ITHAKA or [any database](https://guides.smu.edu/az.php?t=45104) with a dataset builder is that it takes out *the vast majority* of effort in doing text analysis. For a major text analysis project, such as UNC Chapel Hill's [On the Books: Jim Crow and Algorithms of Resistance](https://onthebooks.lib.unc.edu/), about *90% of the labor is creating the corpus.* For your initial project we suggest assembling a data set from one of the previously mentioned databases. We will discuss this further in the [next workshop.](https://libcal.smu.edu/event/8767634)

If you have your own data, you will need to assess what it will take to make it ready for analysis. Here are some questions you should ask:

* How can I convert my data into plain text? 
    * <font color="red">Start learning</font> [Optical Character Recognition Basics](https://constellate.org/tutorials/ocr-basics.ipynb)
* How can I tokenize my texts (break up and separate the words)? 
    * <font color="red">Start learning</font> [Tokenize Text Files](https://constellate.org/tutorials/tokenizing-text-files.ipynb)
    * <font color="red">Start learning</font> [Tokenize Text Files with NLTK](https://constellate.org/tutorials/tokenize-text-files-with-nltk-for-research.ipynb)
    
Consider the data's current form as well as your current skill level or the size and skill of your project staff. The corpus creation process could take anywhere from a few hours to many years of labor. 
* If there is a significant amount of labor, you may need to write a grant proposal to hire help. 
    * If writing a grant, contact your library with questions about [Research Data Management](https://www.smu.edu/Libraries/scholarship/data/data-policy) since funding agencies often require your corpus to be committed to a disciplinary or institutional repository.*

In addition to the cleaned-up texts for your corpus, you will also need a strategy for dealing with textual metadata, information such as author, year, etc. Some of this is discussed in [Tokenize Text Files with NLTK](https://constellate.org/tutorials/tokenize-text-files-with-nltk-for-research.ipynb), but it would also help to have some experience with working with data at scale with either Excel or Python Pandas.

Read about downloading historical SEC filings via EDGAR: [Textual Analysis on SEC Filings](https://mingze-gao.com/posts/textual-analysis-on-sec-filings/)

Read about analyzing [U.S. political party platforms on women's issues](https://pudding.cool/projects/votes-for-women/)

Read about [examining chyrons (the text at the bottom of the screen) from three major cable networks](https://pudding.cool/2018/01/chyrons/)

Read about [The Emergence of Literary Diction](http://journalofdigitalhumanities.org/1-2/the-emergence-of-literary-diction-by-ted-underwood-and-jordan-sellers/)
___

<font color="red">Start learning</font>
[Pandas 1](https://constellate.org/tutorials/pandas-1.ipynb)


# How does it impact research?

* In a general sense, the shift in the researcher’s perspective leads to shifts in research questions. Text analysis techniques are sometimes called *“distant reading”.* 
    * This is a term coined by Stanford professor Franco Moretti, meaning “reading” literature not by studying particular texts, but by aggregating and analyzing massive amounts of texts and “reading” them at a “distance”. This scaling-up and “distancing” can bring out more insights from a very different vantage point. 
    * Text analysis doesn’t have to be the primary method in a research project. It may be just one step in the entire process, or it can be combined with close reading. This approach has been called *“intermediate reading” or “distant-close reading”.*
* This shift in research perspective allows for new kinds of research questions to be asked, or for old questions to be “answered” in new ways. Here are some of the possibilities that text analysis can bring to researchers:
    * It can explore questions not provable by human reading alone
    * It allows larger corpora for analysis
    * It allows studies that cover longer time spans
* Text analysis techniques are often best when combined with qualitative assessment and theoretical context. 
* Text analysis research questions explore a wide range of topics, from biomedical discovery to literary history. Research questions that are conducive for text analysis methods may involve these characteristics:
    * Change over time 
    * Pattern recognition 
    * Comparative analysis 
    
[Examples for discussion](https://teach.htrc.illinois.edu/teaching-resources/text-analysis-research-examples/) 
* How do the projects involve change over time, pattern recognition, or comparative analysis?
* What kind of text data do they use (time period, source, etc.)?
* What are their findings?     

# What disciplinary questions can text analysis answer?
## You can use text analysis to answer a wide variety of questions. 

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

[![N-gram)](https://github.com/SouthernMethodistUniversity/introTDM/blob/main/images/ngram.png)](https://github.com/SouthernMethodistUniversity/introTDM/blob/main/images/ngram.png)

In the cases where a database (such as Constellate) cannot supply full-text due to copyright laws (JSTOR and Portico content), they may supply three n-gram counts:
* Unigrams- A single-word construction, for example: "vegetable".
* Bigrams- An two-word construction, for example: "vegetable stock".
    * Notice how in the bigram example above the window of the gram slides across the text, so in bigrams, a word will occur with both the word preceding and following it. 
* Trigrams- A three-word construction, for example: "homemade vegetable stock".

While having the full texts for the documents in your corpus is ideal, a great deal can be still be discovered through the use of unigrams. Even when researchers have access to the full-texts of a corpus, it is common for them to create a list of n-gram counts for analysis. 

Read about using n-grams to [get a sense of language usage and change on Reddit](https://projects.fivethirtyeight.com/reddit-ngram/)

___

**TF/IDF** 
* Finding the significant words within a text. Example: “Given a decade of board reports, are there seasonal issues that crop up in summer vs. winter?”

___

**Significant Terms** 
* Search engines use significant terms analysis to match a user query with a list of appropriate documents. This method could be useful if you want to search your corpus for the most significant texts based on a word (or set of words). It can also be useful in reverse. For a given document, you could create a list of the ten most significant terms. This can be useful for summarizing the content of a document. 

<font color="red">Start learning</font> [Significant Terms Analysis](https://constellate.org/tutorials/finding-significant-terms.ipynb) and create a simple search engine

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
[![Topic Modeling](https://github.com/SouthernMethodistUniversity/introTDM/blob/main/images/topicmodel.png)](https://github.com/SouthernMethodistUniversity/introTDM/blob/main/images/topicmodel.png)
* For this kind of analysis, the text is [chunked](https://github.com/SouthernMethodistUniversity/introTDM/blob/main/sections/TDMdata.md#preparing-data), and stop words (frequently used words such as “the”, “and”, “if”) are removed since they reveal little about the substance of a text. 
* The computer treats the textual documents as **bags of words**, and guesses which words make up a “topic” based on their proximity to one another in the documents, with the idea the words that frequently co-occur are likely about the same thing. So the different colored groupings are the groups of words that the computer has statistically analyzed and determined are likely related to each other about a “topic”.
    * “Bag-of-words” is a concept where grammar and word order of the original text are disregarded and frequency is maintained. Here is an example of the beginning of The Gettysburg Address as a bag of words.
[![Bag Of Words](https://github.com/SouthernMethodistUniversity/introTDM/blob/main/images/bagwords.png)](https://github.com/SouthernMethodistUniversity/introTDM/blob/main/images/bagwords.png)

* Here are some tips for topic modeling:
* Treat topic modeling as one part of a larger analysis.
    * Understand what you input, including how you set your parameters, will affect the output. Some points to note are:
    * Be careful with how you set the number of texts analyzed, as well as number of topics generated
    * Be familiar with your input data
* Know that changing your stop word list can have really interesting impacts on your topics, so tread carefully/wisely.
* You’re going to want to go back to the text at some point. Make sure to examine your results to see if they make sense.
* Also, try to gain some basic understanding of your tool. *Reading some relevant documentation is especially important when the tool is within a “black box”.*
    * For example the HTRC algorithm only has a few parameters you can set, so it’s not suitable for really robust topic modeling. But for teaching and exploration of HT text specifically, [the HTRC topic modeling algorithm can be a good place to start!](https://analytics.hathitrust.org/algorithms)


<font color="red">Read more</font>
Keli Du's [A Survey on LDA Topic Modeling in Digital Humanities](https://www.researchgate.net/profile/Keli-Du/publication/349279379_A_Survey_On_LDA_Topic_Modeling_In_Digital_Humanities/links/6027a55ea6fdcc37a8222850/A-Survey-On-LDA-Topic-Modeling-In-Digital-Humanities.pdf)

<font color="red">Start learning</font> [Topic Analysis](https://constellate.org/tutorials/finding-significant-terms.ipynb) and create an interactive visualization


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

<font color="red">Read more</font>

* Melanie Walsh [Named Entity Recognition](https://melaniewalsh.github.io/Intro-Cultural-Analytics/05-Text-Analysis/12-Named-Entity-Recognition.html) 2021
* Zoe LeBlanc [Named Entity Recognition](https://nkelber.github.io/tapi2021/book/courses/ner.html) TAP Institute 2021
* Miguel Won, Patricia Murrieta-Flores, and Bruno Martins [Ensemble Named Entity Recognition (NER): Evaluating NER Tools in the Identification of Place Names in Historical Corpora](https://www.frontiersin.org/articles/10.3389/fdigh.2018.00002/full) (2018)
* Read about about how hyphenated names are hard to study [here](https://pudding.cool/2019/05/hyphens/) 
**Named Entity Recognition**
List every example of a kind of entity from these texts. Example: “What are all of the geographic locations mentioned by Tolstoy?”
Named entity extraction, which uses computers to learn about what names of people, places, and organizations are in the text.


## 5. Which of these texts are most similar?¶

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



<!-- #region -->


# Related 

# *Machine Learning(ML)* 
* Another key approach to text analysis is *Machine Learning (ML)*, 
You can use ML which is training computers to recognize patterns in text without explicit human programming. 
* Machine learning can either be *unsupervised (with minimal human intervention)* or *supervised (with more human intervention).* Here are some common, specific methods that are based on machine learning:  
    * Topic modeling, which explores the thematic topics present in the text. Remember that topic modeling is a bag-of-words approach. 
    * Naïve Bayes classification, which explores the categorization of texts, i.e. determining what categories that the researcher have named does a certain text belong to. 
* One key approach in ML for TDM is *Natural Language Processing (NLP)*, meaning using computers to understand the meaning, relationships, and semantics within human-language text. Generally for natural language processing, full text is needed. It is not a bag-of-words method. 
* Some common, specific methods under NLP are: Named entity extraction, Sentiment analysis and Stylometry.
    **Supervised Machine Learning** 
        * The advent of *supervised machine learning techniques have rapidly changed text analysis in the digital humanities. These methods "train" computers to identify and classify similar items based on data that has been labeled or tagged by experts. For example, On the Books: Jim Crow and Algorithms of Resistance was able to use machine learning to identify 1939 North Carolina Jim Crow laws enacted between Reconstruction and the Civil Rights Movement. 

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


<!-- #endregion -->

<!-- #region -->
[![theoretical Workflow](https://github.com/SouthernMethodistUniversity/introTDM/blob/main/images/idealwf.png)](https://github.com/SouthernMethodistUniversity/introTDM/blob/main/images/idealwf.png)


[![Actual Workflow](https://github.com/SouthernMethodistUniversity/introTDM/blob/main/images/realwf.png)](https://github.com/SouthernMethodistUniversity/introTDM/blob/main/images/realwf.png)
<!-- #endregion -->

## Looking for more learning materials? *Check out the following*

# Resources at SMU 
* [SMU Libraries Scholarship & Publishing](https://www.smu.edu/Libraries/scholarship)
* [High Performance Computing @ SMU](https://www.smu.edu/OIT/Services/HPC)
* [**Upcoming SMU Workshops**](https://libcal.smu.edu/calendar/?cid=-1&t=g&d=0000-00-00&cal=-1&inc=0)
* [Databases:Text Mining](https://guides.smu.edu/az.php?t=45104)

## Resources elsewhere
* [Constellate by Ithaka, a text analytics platform aimed at teaching and enabling a generation of researchers to text mine.](http://labs.jstor.org/projects/text-mining/)
* [Programming Historian](https://programminghistorian.org/)
* [TAP Institute 2021 DH Courses](https://nkelber.github.io/tapi2021/book/intro.html)
* [CodeLab](https://github.com/ZoeLeBlanc/CodeLab) by [Shane Lin](https://www.library.virginia.edu/staff/ssl2ab), [Zoe LeBlanc](https://zoeleblanc.com/), and [Brandon Walsh](https://scholarslab.lib.virginia.edu/people/brandon-walsh/)
* [PythonHumanities.com](https://pythonhumanities.com/about/) by [William Mattingly](https://wjbmattingly.com/)
* [Introduction to Cultural Analytics and Python](https://melaniewalsh.github.io/Intro-Cultural-Analytics/welcome.html) by [Melanie Walsh](https://melaniewalsh.org/)
* [Programming Historian](https://programminghistorian.org/en/lessons/) by various authors
* [The Carpentries](https://carpentries.org/workshops-curricula/) by various authors
* [Digital Humanities Research Institutes](https://www.dhinstitutes.org/curricula/) by various authors
* [Computational Humanities Research](https://discourse.computational-humanities-research.org/) <br />
* [YaleDHLab Lab Workshops](https://github.com/YaleDHLab/lab-workshops) <br />
* [Jupyter notebooks for digital humanities](https://github.com/quinnanya/dh-jupyter/blob/master/README.md)
  

-----
[Return to introduction](https://github.com/SouthernMethodistUniversity/introTDM)

Some content in this session based on [HTRC Digging Deeper, Reaching Further](https://teach.htrc.illinois.edu/teaching-materials/) used under a [Creative Commons Attribution-NonCommercial 4.0 International License.](https://creativecommons.org/licenses/by-nc/4.0/)


