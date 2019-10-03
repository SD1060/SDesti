---
title: "SDesti"
author: "Diogo Sayanda"
date: "June, 2019"
output:
  pdf_document:
    toc: yes
    toc_depth: '6'
  word_document:
    toc: yes
    toc_depth: '6'
  html_document:
    highlight: pygments
    keep_md: yes
    theme: united
    toc: yes
    toc_depth: 6
vignette: >
  %\VignetteIndexEntry{"SDesti"} 
  %\VignetteEncoding{UTF-8}
  %\VignetteEngine{knitr::knitr}
---

# Description

This package has been designed primarily to be used with biomonitoring epilithic organisms, Chlorophyll and Ash Free Dry Mass data from aquatic systems but can also be used to analyze any epibenthic or endobenthic organisms? data.

Epilithic organisms are any organisms that occur, on stony surfaces, or crevices, and can be quantified (number of organisms per stone, or any community related index), these can be: macroinvertebrates, periphyton, or macrophytes.

Periphyton Chlorophyll content and Ash Free Dry Mass data are extracted from samples collected by scraping the surface of stones, that are posteriorly treated following traditional laboratory protocols (Dowbush, et al. 2017).

The referred endpoint variables are identified by the program through the acronyms $SD$, $Index$, $Chla$ and 
$AFDM$:

*	$SD$ ? The original expression behind this acronym is ?Stone-Dwelling organisms?. In practice ?SD? indicates to the program that the data refers to number of individuals per stone, or sample replicate, and that the data file has the structure of the SData file (see below). This acronym can be used when the response is represented by the number of individuals (any taxon, or group of taxa) per replicate;

*	$Index$ ? This acronym indicates the program that the response variable is any biological index that resumes the community data for each replicate, and that the data follows exactly the IData file structure;

*	$Chla$ ? The original expression for this acronym is ?Chlorophyll-a? and it is the information that the program needs, to know that the data structure of the file complies exactly with the Chla data file (see below), and that the response is the quantity of any pigment, or metabolite, that was taken from biofilm scraped from rocky surfaces;

*	$AFDM$ ? This acronym is the most restrictive of all, refers to ?Ash Free Dry Mass? of periphyton samples, and it is the information the program needs, to know that the data has the structure of the Chla data file and that it must proceed with the needed calculations of AFDM.

Besides biological data, it is possible to include any environmental data related with physical, chemical, or biotic parameters to analyze the correlation between these covariates and the responses. The corresponding file must comply with the structure of the EData file (see below).

The present package is simple to use and performs the complete macroinvertebrate, or periphyton, data analysis, delivering the necessary information to evaluate the quality of the data, to analyze the quality of the results and adequacy of the analysis, to interpret the results and to answer to the objectives of environmental studies.

The program contains four user assessable functions that perform the following tasks:

#.	Data quality evaluation and descriptive analysis of a $Chla$, $AFDM$, $Index$, or $SD$ single data sample;

#.	Estimate the overall concentration of Chlorophyll, AFDM,  Index, or the density of epilithic individuals, per sampling site and per type of habitat within the designated site (stone size class);

#.	The usual descriptive analysis that precedes the adjustment of a multiple regression model: $2\times 2$ correlational patterns between the response and each environmental covariates and among pairs of covariates, multi-collinearity detection and, when applicable, estimation of the best shape parameter for the response;

#.	Adjustment of the most adequate multiple regression model to describe the temporal evolution of the variable of interest with the possibility of including environmental variables, while controlling for annual cycles and site related variability if applicable;

#.	Provide the complete information for the evaluation of the model assumptions, fit and adequacy.

# Data Structure

Due to the specificities of the data structure used in Chlorophyll/AFDM, environmental abiotic and epilithic organisms? monitoring, the data files for analysis must comply with one of five distinct structures:

*	One data structure for Chlorophyll/AFDM data;

*	One data structure for epilithic organisms? data;

*	One data structure for biotic index related data;

*	One data structure for environmental data;

*	One data structure for the stone profile composition for each sampling site.

The data files to be used in the analysis will depend on the study objectives and it is important that the user takes inconsideration that, in the scope of the data analysis, it is assumed that the sampling design was adequate and that the quantity of data is enough to obtain reliable results. The required information to perform the analysis is:

*	For the analysis of the quality of a $SD$, $Chla$, $Index$ or $AFDM$ data sample collected from one site it is sufficient to have one data file on the variable of interest. This file must comply with the respective format;

*	For the estimation of Chlorophyll concentrations, AFDM, Index per habitat area, or epilithic organisms? densities at a given site it is necessary to have two data files: one that includes information on the variable of interest and another data file with information on the habitat characteristics (stone profile composition) for the same sampling site;

*	For the study of the temporal patterns of the variable of interest, only one file containing the data collected from one or several sampling sites over time is necessary;

*	If the study of the response?s temporal patterns also aims to analyze its correlation with environmental measures, two data files are necessary: one containing data on the variable of interest and another on the environmental data.

It is relevant to underline that all statistical methods rely on assumptions that should be taken into consideration to increase data quality and get realistic results from the analysis. Biological systems are highly dynamic and variable and it is imperative to collect a significant amount of data to get representative samples to detect meaningful patterns of variation related with environmental stressors, considering the existence of annual cycles.

When modeling data that includes different sites, although the respective functions were designed to control some of the inter-site variation, it is assumed that the sampled areas are similar and that the variability associated with unmeasured environmental traits are incipient. For this reason it is high recommended that the number of distinct sites is kept within areas that can be considered relatively homegeneous for the response variable, i. e. if the natural environmental conditions are similar, one can expect to get equivalent samples in distinct sites. It is also important that the sampling design also considers a pilot study to define adequate sampling effort per site and that the exact sampling areas within each site are similar (relatively similar habitats) to reduce uncontrolled variability. The use of artificial substrate, or $in situ$ mesocosms should be also be considered in order to control the variability of the response.

For the above, monitoring programs must rely on the definition adequate sampling designs, validated and optimized sampling methods and standard equipment, include realistic time frames to distinguish random variability from temporal trends and control unmeasured sources of variability as much as possible.

For a sensible sampling design and planning, it is also important that the first year of any environmental study is a pilot study that aims to determine the number of sampling sites, define the exact data collection areas within each site, determine the minimum period between subsequent campaigns, establish the number of replicates within each site and have a first glimpse of the collected information.
