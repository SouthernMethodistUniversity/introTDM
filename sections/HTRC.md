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

# HathiTrust Research Center

[HathiTrust Digital Library](https://www.hathitrust.org/digital_library)
[HathiTrust Research Center](https://analytics.hathitrust.org/)
* The HathiTrust Research Center (HTRC) enables computational analysis of the HathiTrust corpus.

[Creating datasets/worksets](https://analytics.hathitrust.org/staticworksets#top)

<!-- #region -->
## Recommended Worksets
* [Recommended Worksets](https://analytics.hathitrust.org/staticrecommendedworksets) are curated worksets created by real researchers of projects that utilize resources from the HathiTrust Digital Library and can be analyzed with tools built by the HTRC.

##  Algorithms
* [HTRC Algorithms](https://analytics.hathitrust.org/statisticalalgorithms) are web-based, click-and-run tools to perform computational text analysis on volumes in the HathiTrust Digital Library. 

[![HTRC for text analysis](https://github.com/SouthernMethodistUniversity/introTDM/blob/main/images/htrcta.png)](https://github.com/SouthernMethodistUniversity/introTDM/blob/main/images/htrcta.png)


* In a basic text analysis workflow, a researcher:
    * Gathers digitized text (text that has been scanned and OCR-ed) Note: OCR (Optical character recognition) refers to the mechanical or electronic conversion of images of typed, handwritten or printed text into machine-encoded text. 
     * Applies computational methods to that text, such as word counts, classification techniques, and topic modeling
    * And then analyzes the results generated by the algorithm or technique

* HathiTrust Research Center (HTRC) enters the workflow *at the points of providing digitized text at scale* from HathiTrust Digital Library (HTDL) and providing tools and services that enable computational research. 
* The researcher, of course, still brings her own analysis to bear on the results.


<!-- #endregion -->

## First, let’s go to the HathiTrust Digital Library (HTDL) interface. 
* [Go to HTDL site](https://www.hathitrust.org/)
* Click on the “LOG IN” button on the right to sign in.
* If you are affiliated to an HT partner institution (such as SMU), select your partner institution from the list and click on continue, then follow the directions for institutional log in.
* Once you are logged in, click on the “FULL-TEXT” tab to search in full text. Now you can start thinking about a search query to find volumes for your collection. Try building your own collection.
* View search results. You can facet in the sidebar, then select volumes.
* When you’re satisfied with your selection, click on the “Select Collection” bar and choose “[CREATE NEW COLLECTION]” from the drop-down menu. Then hit the “Add Selected” button on the right. 
* A pop-up window will appear that prompts you to add some metadata to your collection before the system creates it for you. Fill in the name and description of your new collection. You can choose to make the collection public or private, and we recommend writing a short description whenever you make collections public. When done, click on “Save Changes” to create your collection.
* After the collection is successfully created, you should see a a confirmation message above the search results. To view your collection, click on “My Collections” near the top right of the page. 
* This will bring you to all your collections. You can manage your collections here by viewing collections, changing the public or private status of a collection, and deleting collections you don’t need. Click on the title of the collection you just created to view it. 
* You will be able to see the title and description of your collection, as well as all the items in it. In order to import your newly created collection into HTRC Analytics for analysis, we need to download the metadata of the collection first. Click on the “Download Metadata” button on the left sidebar and select the “Download Item Metadata: Tab-Delimited Text (TSV)” option. (You will not be able to upload the JSON metadata of your collection to HTRC Analytics, so make sure to select the TSV option.) 



## Second, let’s go to the HathiTrust Research Center (HTRC) Analytics interface. 
* Go to [HTRC Analytics](https://analytics.hathitrust.org/)
* Look for the sign in/ sign up section on the top right part of the page.
* If you are affiliated to an HT partner institution (such as SMU), select your partner institution from the list and click on continue, then follow the directions for institutional log in.[FAQ page for sign in](https://wiki.htrc.illinois.edu/display/COM/Troubleshooting+and+FAQs#TroubleshootingandFAQs-UserAccountsandSign-in)
* Now, we are ready to import our HT Collection into HTRC Analytics as a workset. Click on the “Worksets” option on the header menu. This will bring you to the worksets page. 
* You can view your own worksets as well as public worksets on this page. To import your HT collection, click on “Create a workset” near the top right. 
* Name your workset and write a description if you like. When naming, please note that only characters A-Z, 0-9, (), -, or _  are allowed, so do not use spaces or other special characters. Click on “Choose file” to upload the TSV file we just downloaded. Check the “Make private workset” box if you want to create a private workset. Finally, hit the “Create Workset” button. 
* If successful, you should be brought back to your worksets page, and the new workset that you just created should be listed. Click on the name of the workset to view it. 

* Workset review!
    * How did it go?
    * What kind of search criteria did you use?
    * Did you find any challenges?




<!-- #region -->
# TDM tools 

* For performing text analysis, there are both pre-built tools and do-it-yourself tools that you can choose from. 

## Pre-built
* The benefits of pre-built tools are they are usually easy to use, they don’t require too much technical knowledge, and they can be very useful in teaching.

* The main drawback of pre-built tools is because they have predefined functions, they offer less control to the researcher and limit what a user can accomplish.

* [Voyant](https://voyant-tools.org/), [Lexos](https://wheatoncollege.edu/academics/special-projects-initiatives/lexomics/lexos-installers/), and [HTRC algorithms](https://analytics.hathitrust.org/algorithms) are examples of pre-built tools. The HTRC Topic Modeling algorithm, which identifies “topics” in a set of text based on words that have a high probability of occurring close together, is a representative HTRC algorithm that can be used for exploratory analysis. 

* Choosing a pre-built tool is based on the goal of the analysis. Each pre-built tool has its own strengths, outputs, and weaknesses. 
* For quick analysis and visualizations, Voyant and Lexos are all excellent choices. They don’t allow much parameterization, but they are very easy to use. To make concordances(seeing key words in context), AntConc or Voyant are tools programmed to do that. Voyant is both web-based and downloadable, so there no installation required unless desired by the researcher, while AntConc is software the user must install on their computer.
* [Weka](https://waikato.github.io/weka-wiki/) is the tool to use for researchers who want to try machine learning with a tool that has a visual front-end. It also needs to be installed.

### HTRC tools
* Use the HTRC algorithms as an example of how to use a pre-built tool for text analysis. The HTRC provides some algorithms through HTRC Analytics, and they can be used to analyze HTRC worksets.
* An algorithm is just a way of saying a computer function - text goes in, process happens, and results come out. 
* HTRC algorithms can extract, refine, analyze, and visualize worksets. They can basically perform “plug-and-play” text analysis. 
* Because they are built into HTRC Analytics, they are mostly limited in how much they can be tweaked or customized. The algorithms are primarily for users who don’t know how or don’t want to work with custom code. It can be a good tool for learning and just trying things out. 
* How do you choose which HTRC algorithm to use? Naturally, it depends on what you want to do. 
* Some of the algorithms are task oriented. For example, there are ones for running spellcheck reports, for creating word counts, for visualizing more frequently used words, and for generating a list of named entities. 
* Others algorithms are more analytic, like one that generates topic models, and another that compares salient words in two worksets.

#### Topic Modeling
* An example of specific text analysis method is *topic modeling.* One concept closely related to topic modeling is the bag-of-words model. 
    * “Bag-of-words” is a concept where grammar and word order of the original text are disregarded and frequency is maintained. Here is an example of the beginning of The Gettysburg Address as a bag of words.
    [![Bag of Words](https://github.com/SouthernMethodistUniversity/introTDM/blob/main/images/bagwords.png)](https://github.com/SouthernMethodistUniversity/introTDM/blob/main/images/bagwords.png)
* Topic modeling is a method of using statistical models for discovering the abstract "topics" that occur in a collection of documents.
 [![topic model](https://github.com/SouthernMethodistUniversity/introTDM/blob/main/images/topicmodel.png)](https://github.com/SouthernMethodistUniversity/introTDM/blob/main/images/topicmodel.png)
* For this kind of analysis, the text is chunked, and stop words (frequently used words such as “the”, “and”, “if”) are removed since they reveal little about the substance of a text. 
* The computer treats the textual documents as bags of words, and guesses which words make up a “topic” based on their proximity to one another in the documents, with the idea the words that frequently co-occur are likely about the same thing. 
* So the different colored groupings are the groups of words that the computer has statistically analyzed and determined are likely related to each other about a “topic”.

* Here are some tips for topic modeling:
    * Treat topic modeling as one part of a larger analysis.
    * Understand what you input, including how you set your parameters, will affect the output. Some points to note are:
    * Be careful with how you set the number of texts analyzed, as well as number of topics generated
    * Be familiar with your input data
    * Know that changing your stop word list can have really interesting impacts on your topics, so tread carefully/wisely.
    * You’re going to want to go back to the text at some point. Make sure to examine your results to see if they make sense.
    * Also, try to gain some basic understanding of your tool. **Reading some relevant documentation is especially important when the tool is within a “black box”.** Speaking of understanding your tools, it’s important to note that the HTRC algorithm only has two parameters you can set right now, so it’s not suitable for really robust topic modeling. But for teaching and exploration of HT text specifically, the HTRC topic modeling algorithm can be a good place to start.



## Do it yourself tools
* You can also use do-it-yourself tools for text analysis as an alternative, and these tools usually involve some degree of programming.
* The advantages of using do-it-yourself tools are you can set your own workflows and parameters, and it allows you to have more control over what you want to do.
* The drawback is they usually require technical knowledge and may be a lot harder to use. 


<!-- #endregion -->

<!-- #region -->
-----
[Return to introduction](https://github.com/SouthernMethodistUniversity/introTDM)


Some content in this session based on [HTRC Digging Deeper, Reaching Further](https://teach.htrc.illinois.edu/teaching-materials/) used under a [Creative Commons Attribution-NonCommercial 4.0 International License.](https://creativecommons.org/licenses/by-nc/4.0/)
<!-- #endregion -->