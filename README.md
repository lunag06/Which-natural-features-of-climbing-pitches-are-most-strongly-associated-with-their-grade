# What natural features of a route are key factors in determining its grade ? 
This project aims to determine whether there's a clear link between a route natural features and its grade. More specifically, we are interested in determing which of these natural elements impact the more the grade. To do so, we scraped data with Camptocamp API, we annotated the data and we implemented four logistic linear bayesian regressions with mixed effect thanks to bambi library. 

# What documents are available ?
Here, you'll find our paper as well as all data and codes to replicate our study.

All codes are available in French (language we used) and in English. Here's a quick description of all codes:
- ScrapingCodePropreEn.ipynb / ScrapingCodePropreFR.ipynb : code we used to scrap the data from CamptoCamp API
- 1_SplitingPitchesEn.ipynb / 1_SplitLongueursFR.ipynb : code that cleans data and split routes per pitches
- 2_NumberOfTerms_AND_Sequence_ExtractionEN.ipynb / 2_ExtractionNbTermes_ET_SequencesFR.ipynb : code that extracts the number each natural element per description (so per pitch).
- 3_WeightsAnnotationEN.ipynb / 3_PonderationAnnotationFR.ipynb (French): code that extracts all couples with one natural element and one related adjective.
- 4_WeightScoresEN.ipynb / 4_ScorePonderationFR.ipynb (French): code that attributes a grade to the couples the most present detected in the previous notebook.
-  AnalyseModeleATotalFR.ipynb / AnalysisModelATotalEN.ipynb: model A analysis
 - AnalyseModeleBTotalFR.ipynb / AnalysisModelBTotalEN.ipynb: model B analysis
 - AnalyseModeleCTotalFR.ipynb / AnalysisModelCTotalEN.ipynb: model C analysis
 - AnalyseModeleDTotalFR.ipynb / AnalysisModelDTotalEN.ipynb: model D analysis

All data computed during each step of the analysis are available in the Data folder

# How to replicate the analysis ?
For the whole replication, we recommand using the same library versions we used:
Python 3.13.17


You'll have to run the codes in the following order : 

- Scraping :
  ScrapingCodePropreEn.ipynb (English) or ScrapingCodePropreFR.ipynb (French)

- Data annotation:
  Step 1 : 1_SplitingPitchesEn.ipynb (English) or 1_SplitLongueursFR.ipynb (French)
  
  Step 2 : 2_NumberOfTerms_AND_Sequence_ExtractionEN.ipynb (English) or 2_ExtractionNbTermes_ET_SequencesFR.ipynb (French)
  
  Step 3 : 3_WeightsAnnotationEN.ipynb (English) or 3_PonderationAnnotationFR.ipynb (French)
  
  Step 4 : 4_WeightScoresEN.ipynb or 4_ScorePonderationFR.ipynb (French)
  
- Data analysis:
  Run those 4 notebooks in whatever order suits you better:
  
  AnalysisModelATotalEN.ipynb (English) / AnalyseModeleATotalFR.ipynb (French) 
  AnalysisModelBTotalEN.ipynb (English) / AnalyseModeleBTotalFR.ipynb (French) 
  AnalysisModelCTotalEN.ipynb (English) / AnalyseModeleCTotalFR.ipynb (French) 
  AnalysisModelDTotalEN.ipynb (English) / AnalyseModeleDTotalFR.ipynb (French)
  
  Then, run this final notebook to get the comparison between the models : ComparaisonModeles.ipynb
