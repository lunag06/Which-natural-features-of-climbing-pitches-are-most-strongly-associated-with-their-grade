# Which natural features of climbing pitches are most strongly associated with their grade?
This project studies the association between the natural terrain features mentioned in community-written route descriptions and the grade of outdoor climbing pitches. Data were scraped from the Camptocamp API, annotated from the French descriptions (feature counts, transitions between features, qualifier scores) and analysed with four Bayesian cumulative ordinal logistic mixed-effects models fitted with bambi (PyMC).

The full paper is available here: [our paper](GourrierLuna2026_11_15.pdf)

## What documents are available ?
Here, you'll find our paper as well as all data and codes to replicate our study.

All codes are available in French (language we used) and in English. Language is indicated with FR or EN at the end of the file names Here's a quick description of all codes:

- [ScrapingCodePropreFR](ScrapingCodePropreFR.ipynb) / [ScrapingCodePropreEn](ScrapingCodePropreEn.ipynb) : code we used to scrap the data from CamptoCamp API
  
- [1_SplitLongueursFR](1_SplitLongueursFR.ipynb) / [1_SplitingPitchesEn](1_SplitingPitchesEn.ipynb) : code that cleans data and split routes per pitches
  
- [2_ExtractionNbTermes_ET_SequencesFR](2_ExtractionNbTermes_ET_SequencesFR.ipynb) / [2_NumberOfTerms_AND_Sequence_ExtractionEN](2_NumberOfTerms_AND_Sequence_ExtractionEN.ipynb) : code that extracts the number each natural element per description (so per pitch).
 
- [3_PonderationAnnotationFR](3_PonderationAnnotationFR.ipynb) / [3_WeightsAnnotationEN](3_WeightsAnnotationEN.ipynb) : code that extracts all couples with one natural element and one related adjective.
  
- [4_ScorePonderationFR](4_ScorePonderationFR.ipynb) / [4_WeightScoresEN](4_WeightScoresEN.ipynb) : code that assigns a score to the most frequent (element, qualifier) pairs.
  
-  [AnalyseModeleATotalFR](AnalyseModeleATotalFR.ipynb) / [ AnalysisModelATotalEN]( AnalysisModelATotalEN.ipynb) : model A analysis (within/between-route decomposition)
 
 - [AnalyseModeleBTotalFR.ipynb](AnalyseModeleBTotalFR.ipynb) / [AnalysisModelBTotalEN](AnalysisModelBTotalEN.ipynb) : model B analysis (baseline)
   
 - [AnalyseModeleCTotalFR](AnalyseModeleCTotalFR.ipynb) / [AnalysisModelCTotalEN](AnalysisModelCTotalEN.ipynb) : model C analysis (transitions between natural elements)
   
 - [AnalyseModeleDTotalFR](AnalyseModeleDTotalFR.ipynb) / [AnalysisModelDTotalEN](AnalysisModelDTotalEN.ipynb) : model D analysis (weighted annotation)

 - [ComparaisonModelesFR](ComparaisonModelesFR.ipynb) / [ModelsComparisonEN](ModelsComparisonEN.ipynb) : comparison between the four models

 - You'll also find notebooks to test each model analysis on smaller samples (eg : [AnalyseModeleA300FR](AnalyseModeleA300FR.ipynb) / [ AnalysisModelA300EN]( AnalysisModelA300EN.ipynb))

All data computed during each step of the analysis are available in the Data folder

## How to replicate the analysis ?
For the whole replication, we recommand using the same library versions we used:
Python 3.13.17. Please refer to requirements.txt for all librairies versions.


You'll have to run the codes in the following order : 

- ### Scraping :
  [ScrapingCodePropreFR](ScrapingCodePropreFR.ipynb) or  [ScrapingCodePropreEn](ScrapingCodePropreEn.ipynb)

- ### Data annotation:
  
  Step 1 : [1_SplitLongueursFR](1_SplitLongueursFR.ipynb) or [1_SplitingPitchesEn](1_SplitingPitchesEn.ipynb) 

  Step 2 : [2_ExtractionNbTermes_ET_SequencesFR](2_ExtractionNbTermes_ET_SequencesFR.ipynb) or [2_NumberOfTerms_AND_Sequence_ExtractionEN](2_NumberOfTerms_AND_Sequence_ExtractionEN.ipynb)
  
  Step 3 : [3_PonderationAnnotationFR](3_PonderationAnnotationFR.ipynb) or [3_WeightsAnnotationEN](3_WeightsAnnotationEN.ipynb)
  
  Step 4 :[4_ScorePonderationFR](4_ScorePonderationFR.ipynb) or  [4_WeightScoresEN](4_WeightScoresEN.ipynb)

     
- ### Data analysis:
  Run those 4 notebooks in whatever order suits you better:

  [AnalyseModeleATotalFR](AnalyseModeleATotalFR.ipynb) / [ AnalysisModelATotalEN]( AnalysisModelATotalEN.ipynb)
  
  [AnalyseModeleBTotalFR.ipynb](AnalyseModeleBTotalFR.ipynb) / [AnalysisModelBTotalEN](AnalysisModelBTotalEN.ipynb)

  [AnalyseModeleCTotalFR](AnalyseModeleCTotalFR.ipynb) / [AnalysisModelCTotalEN](AnalysisModelCTotalEN.ipynb)

  [AnalyseModeleDTotalFR](AnalyseModeleDTotalFR.ipynb) / [AnalysisModelDTotalEN](AnalysisModelDTotalEN.ipynb)
  
  Then, run this final notebook to get the comparison between the models : [ComparaisonModelesFR](ComparaisonModelesFR.ipynb) / [ModelsComparisonEN](ModelsComparisonEN.ipynb)

## Notes 
The results of the paper rely on data collected on 2026-09-07. Camptocamp keeps evolving, so running the scraping again will return a different dataset. To reproduce the paper exactly, start from Step 1 with the data provided in the Data folder.
The dictionary of natural elements and the scores assigned to the pairs were built by hand. The descriptions and the dictionary are in French, including in the English notebooks.
