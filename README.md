<<<<<<< HEAD
# Table of contents
1.	[Purpose](#purpose)
2.	[Inputs](#inputs)
3.	[Outputs](#outputs)
4.	[Constraints](#constraints)
5.	[Dependencies](#dependencies)
    * [5.1 Code Language](#codelanguage)
        * [5.1.1 package requirements](#packagerequirements)
6.	[Code](#code)
7.	[Tests](#tests)
8.	[Provenance](#provenance)
9.	[Citations](#citations)
---

# Large River Monitoring Forum Biogeographic Analysis Package – Biodiversity Indices

## Purpose <a name="purpose"></a>

The Large River Monitoring Forum (LRMF) is a USGS led initiative to bring together researchers from across the nation involved in monitoring species and populations of fishes in large river systems.  The forum works collaboratively to understand best practices in monitoring and to study the trends in fish populations through space in time in response to environmental drivers.  
The initial work of the forum focused on comparisons of methods and documented in five large river systems (Ward et al. 2017).  The analyses presented here build on that work by taking the data compiled in that effort (Counihan et al. 2016) and allowing the user to explore trends in biodiversity by river reach through time.  Specifically, this package summarizes the data for five commonly used biodiversity indices: 
*	Margalef Species Riches Index (Margalef 1958)
*	Shannon-Wiener Indices (Shannon 1948; )
*	Simpson (Simpson 1949)
*	Hill Numbers (Hill 1973)
*	Pielou’s Species Evenness (Pielou 1966)

## Inputs <a name="inputs"></a>
The bases of the analyses are the fish assemblage data Large River Monitoring Forum Fish Assemblage Database 2016 (https://www.sciencebase.gov/catalog/item/575ee33fe4b04f417c2b05ca).  That dataset includes data for the Colorado, Columbia, Mississippi, Illinois and Tallapoosa Rivers.  For each river the fish assemblage data collected during the monitoring efforts was compiled and summarized as the mean number of individuals of that species in that reach for a given year.  
The analysis package was developed with the following environment(s):
*  Python 2.7.13 with math module
*  Anaconda 4.3.1, with Jupyter Notebook
*  Pandas 0.19.2
*  Matplotlib 2.0.0
*  Numpy 1.11.3

## Outputs 
The output of the analyses are variants of five biodiversity indices used by biologist to characterize species assemblages (Clarke and Gorley 2006). The presentation of these indices is not an endorsement of the use of these indice but rather to present options to output indices that are commonly used. For more information on these indices please thoroughly read the references provided below (e.g., Washington 1984).  For each of the indices tables are generated showing the values for each river reach and each year.  Those tables are then used to graph the trends in diversity through time for each reach.  

*  Margalef Species Richness Index 
*  Shannon-Wiener Indexes, Log(e), Log(2), Log(10)
*  Simpsons:
    *  Lambda
    *  1-Lambda
    *  Lambda'
    *  1-Lambda'
* Hill Numbers:
    *  N1
    *  N2
    *  N-Inf
    *  N10
    *  N10'
    *  N21
    *  N21'
*  Pielou's Species Evenness Index



## Constraints 
These data were compiled for a set of analyses related to the fish assemblages on portions of the five large rivers. The data represent a subset of the monitoring data that are collected for each of the rivers and in some cases a subset of the gear used in the monitoring protocols, so it is important that any re-analyses with this data be done with a clear understanding of the criteria used in compiling this data. Electrofishing sampling was done for the four of the rivers (Colorado, Illinois, Mississippi, and Tallapoosa) and gillnetting was done on the Columbia River.

## Dependencies 
These analyses are currently reliant on a local copy of the LRMF Fish Assemblage dataset (Counihan et al 2016).

Code execution dependencies
*  Code Language
    <br>This code is written in Python 3.x. with the math module.
    *  Python package requirements 
    <br>The required packages for proper code execution include:
        *  Anaconda 4.3.1, with Jupyter Notebook 
        *  Pandas 0.19.2
        *  Matplotlib 2.0.
        *  Numpy 1.11.3

Input dependencies

    CSV formatting
    Inputs for the script are text files exported from LRMF river feature datasets (https://www.sciencebase.gov/catalog/item/575ee33fe4b04f417c2b05ca), and have the following column ordering: ObjectID, River, RiverSeg, Year, sp1, sp2...spN. The following assumptions are therefore made, regarding input formatting:

      - Existence of the field "River", with river name.
      - Existence of the field "RiverSeg" with river segment names.
      - Existence of the field "Year" with year for which observations were made.
      - Species survey data begins at the fifth column and continues to end of table.




## Tests 
In order to verify results from this script, a csv file of fish species assemblage data for the Columbia River was used as input for the script and as input into PRIMER version 7 (Clarke & Gorley 2015), a software package for calculating biodiveristy indices for species assemblage data.  Upon completion, results from the script and Primer 7 matched.


## Provenance 

This code was written to be consistent with the format of the 2016 Fish Assemblage database developed by the Large River Monitoring Forum (Counihan et al. 2016; https://www.sciencebase.gov/catalog/item/575ee33fe4b04f417c2b05ca).  If additional surveys are included either adding years, river reaches or whole rivers, the format will need to be consistent with the format of the original dataset. 

## Citations 
Clarke, K. R., and R. N. Gorley. 2006. Primer v6: User Manual/Tutorial.  Primer-E Ltd. United Kindom. 190 p.

Clarke, K.R., Gorley, R.N., Somerfield, P.J. & Warwick, R.M. 2014. Change in Marine Communities: An Approach to Statistical Analysis and Interpretation, 3rd edition. PRIMER-E Ltd: Plymouth, UK. 262 pp
Clarke, K.R., Gorley, R.N.  2015.  Primer v7: User Manual / Tutorial.  PRIMER-E Ltd: Plymouth, UK. 300 pp

Counihan, T.D., Waite, I.R., Casper, Andy, Ward, David, Sauer, Jennifer, Irwin, Elise, Chapman, Colin, Paukert, Craig, Ickes, Brian, Kosovich, John, and Bayer, J.M., 2016, Large River Monitoring Forum Fish Assemblage Database 2016: U.S. Geological Survey, https://doi.org/10.5066/F7CN723D.

Hill, M 1973. Diversity and evenness: a unifying notation and its consequences. Ecology 54: 427– 432.  https://doi.org/10.2307/1934352

Margalef, R. 1958 Information theory in ecology. General Systems, 3 (1958), pp. 36-71

Pielou, E. C., 1966. The measurement of diversity in different types of biological collections. Journal of Theoretical Biology, 13, 131–44.  https://doi.org/10.1016/0022-5193(66)90013-0

Shannon, C.E. 1948. A mathematical theory of communication. Bell System Technical Journal, 27, 379–423.  https://doi.org/10.1002/j.1538-7305.1948.tb01338.x

Simpson, E. 1949. Measurement of diversity. - Nature, Lond. 163: 688.  https://doi.org/10.1038/163688a0

Spellerberg, I. F., and P. J. Fedor.  2003. A tribute to Claude Shannon (1916–2001) and a plea for more rigorous use of species richness, species diversity and the ‘Shannon–Wiener’ Index.  Global Ecology and Biodiversity. https://doi.org/10.1046/j.1466-822X.2003.00015.x

Ward, D., A. Casper, T. Counihan, J. Bayer, I. Waite, J. Kosovich, C. Chapman, E. Irwin, J. Saur, B. Ickes, A. McKerrow.  2017.  Long-term fish monitoring in large rivers: Utility of “benchmarking” across basins. Fisheries.  https://doi.org/10.1080/03632415.2017.1276330

Washington, H.G., 1984. Diversity, biotic and similarity indices: a review with special relevance to aquatic ecosystems. Water research, 18(6), pp.653-694.  https://doi.org/10.1016/0043-1354(84)90164-7





This code was written to calculate a number of indices describing biodiversity calculated from results of fish surveys on the five major rivers studied by the Large River Monitoring Forum (LRMF).  Results of these calculations are then plotted by river segment and year, with png format images saved along with a csv file containing the input data with columns of biodiversity indices appended.

Since this was written specifically to receive LRMF data as inputs, it was tailored accordingly.  Inputs for the script are text files exported from LRMF river feature datasets (https://www.sciencebase.gov/catalog/item/575ee33fe4b04f417c2b05ca), and have the following column ordering: ObjectID, River, RiverSeg, Year, sp1, sp2...spN.  The following assumptions are therefore made, regarding input formatting:

    1.  Existence of the field "River", with river name.
    2.  Existence of the field "RiverSeg" with river segment names.
    3.  Existence of the field "Year" with year for which observations were made.
    4.  While order of 1-3 is inconsequential, species survey data begins at the fifth column and continues to end of table.
    
This was developed with the following environment(s):

    1.  Python 3.6.7 with math module
    2.  Anaconda 1.8.4, with Jupyter Notebook
    3.  Pandas 0.23.4
    4.  Matplotlib 3.0.2
    5.  Numpy 1.15.4
    
The following Biodiversity Indices are calculated and plotted:

    1.  Margalef Species Richness Index
    2.  Shannon-Wiener Indexes, Log(e), Log(2), Log(10)
    3.  Simpsons:
        a.  Lambda
        b.  1-Lambda
        c.  Lambda'
        d.  1-Lambda'
    4. Hill Numbers:
        a.  N1
        b.  N2
        c.  N-Inf
        d.  N10
        e.  N10'
        f.  N21
        g.  N21'
    5.  Pielou's Species Evenness Index
=======
# LRMF-Biodiversity-BAP
Calculates and plots biodiveristy indices for fish population survey data collected by the Large River Monitoring Forum.  Plots and input data with appended indices are saved in .png and .csv format.  Indices calculated are: Margalef Species Richness Index (d); Shannon-Wiener Log(e) Log(2) and Log(10) indices (H');  Simpson's Diversity Indices (Lambda, 1-Lambda, Lambda' and 1-Lambda'); Hill Numbers N1, N2, N-Inf, N10, N10', N21, N21'; Pielou's Evenness Index.
>>>>>>> 140c25491bf620f47e5d1153030a3aa2304f5113
