# Which natural features of climbing pitches are most strongly associated with their grade?
This project studies the association between the natural terrain features mentioned in community-written route descriptions and the grade of outdoor climbing pitches. Data were scraped from the Camptocamp API, annotated from the French descriptions (feature counts, transitions between features, qualifier scores) and analysed with four Bayesian cumulative ordinal logistic mixed-effects models fitted with bambi (PyMC).

The full paper is available here: [our paper](GourrierLuna2026_11_15.pdf)

## What documents are available ?
Here, you'll find our paper as well as all data and codes to replicate our study.

All codes are available in French (language we used) and in English. Here's a quick description of all codes:

- ScrapingCodePropreEn.ipynb / ScrapingCodePropreFR.ipynb : code we used to scrap the data from CamptoCamp API
  
- 1_SplitingPitchesEn.ipynb / 1_SplitLongueursFR.ipynb : code that cleans data and split routes per pitches
  
- 2_NumberOfTerms_AND_Sequence_ExtractionEN.ipynb / 2_ExtractionNbTermes_ET_SequencesFR.ipynb : code that extracts the number each natural element per description (so per pitch).
 
- 3_WeightsAnnotationEN.ipynb / 3_PonderationAnnotationFR.ipynb (French): code that extracts all couples with one natural element and one related adjective.
  
- 4_WeightScoresEN.ipynb / 4_ScorePonderationFR.ipynb (French): code that assigns a score to the most frequent (element, qualifier) pairs.
  
-  AnalyseModeleATotalFR.ipynb / AnalysisModelATotalEN.ipynb: model A analysis (within/between-route decomposition)
 
 - AnalyseModeleBTotalFR.ipynb / AnalysisModelBTotalEN.ipynb: model B analysis (baseline)
   
 - AnalyseModeleCTotalFR.ipynb / AnalysisModelCTotalEN.ipynb: model C analysis (transitions between natural elements)
   
 - AnalyseModeleDTotalFR.ipynb / AnalysisModelDTotalEN.ipynb: model D analysis (weighted annotation)

 - ComparaisonModelesFR.ipynb / ModelsComparisonEN.ipynb : comparison between the four models

All data computed during each step of the analysis are available in the Data folder

## How to replicate the analysis ?
For the whole replication, we recommand using the same library versions we used:
Python 3.13.17. Please refer to requirements.txt for all librairies versions.


You'll have to run the codes in the following order : 

- ### Scraping :
  ScrapingCodePropreEn.ipynb (English) or ScrapingCodePropreFR.ipynb (French)

- ### Data annotation:
  
  Step 1 : 1_SplitingPitchesEn.ipynb (English) or 1_SplitLongueursFR.ipynb (French)
  
  Step 2 : 2_NumberOfTerms_AND_Sequence_ExtractionEN.ipynb (English) or 2_ExtractionNbTermes_ET_SequencesFR.ipynb (French)
  
  Step 3 : 3_WeightsAnnotationEN.ipynb (English) or 3_PonderationAnnotationFR.ipynb (French)
  
  Step 4 : 4_WeightScoresEN.ipynb or 4_ScorePonderationFR.ipynb (French)
  
- ### Data analysis:
  Run those 4 notebooks in whatever order suits you better:
  
  AnalysisModelATotalEN.ipynb (English) / AnalyseModeleATotalFR.ipynb (French)
  
  AnalysisModelBTotalEN.ipynb (English) / AnalyseModeleBTotalFR.ipynb (French)
  
  AnalysisModelCTotalEN.ipynb (English) / AnalyseModeleCTotalFR.ipynb (French)
  
  AnalysisModelDTotalEN.ipynb (English) / AnalyseModeleDTotalFR.ipynb (French)
  
  Then, run this final notebook to get the comparison between the models : ComparaisonModelesFR.ipynb / ModelsComparisonEN.ipynb

## Notes 
The results of the paper rely on data collected on 2026-09-07. Camptocamp keeps evolving, so running the scraping again will return a different dataset. To reproduce the paper exactly, start from Step 1 with the data provided in the Data folder.
The dictionary of natural elements and the scores assigned to the pairs were built by hand. The descriptions and the dictionary are in French, including in the English notebooks.
