# MSEF-Project-Models
This repository contains the finalized YOLOv11 models, paper and additional resources for a MSEF States 2026 qualifying research project. The project itself centers around the use of Computer Vision based models in the mapping of litter items, the goal being to facilitate cleanup events and density specific information through automated mapping.

## Project Abstract
Rampant litter densities are a global issue as industrialization has increased consumer activity, resulting in urban regions with high volumes of trash, with little being known about the specific distribution of these items. Due to the issues of ecosystem health, microplastic emissions, and water pollution, increasing efforts have been initiated to help track and map litter products within regions with the goals of removing litter products or identifying which regions require the most aid. One solution is crowdmapping, a process where community members mark specific regions corresponding to identifying litter and add such instances to a growing database. Applications of crowdmapping are enhanced through the automation of detection, a practice that this project aims to facilitate by engineering a set of Computer Vision models for identifying a wide range of litter products. This design enables the complete identification and localization of 7 litter object varieties within images, with full inference speed across all models combined under 1 second. The developed softwares also show promising accuracy over existing frameworks: as demonstrated through most model F1 scores in the range 0.8 to 0.9 and mAP50 values from 0.8 to 0.95 across models compared to the current benchmarks of roughly 0.7 F1 scores and 0.65 mAP50 currently used in similar tasks. As a proposed application of this software, the trained models are being implemented into an autonomous litter crowdmapping software capable of user upload and litter identification based on uploaded images.

## Design Process

The design process served as a multipurposed comparison: first evaluating how the use of more precise instance segmentation pixel masking could improve accuracy in trained models and second using these trained models for automated mapping. The results showed definite increases in accuracy for instance segmentation models across current Computer Vision benchmarks for this given application (see Section 7 of research paper for analysis of this conclusion based on model performance). This therefore provides evidence in favor of instance segmentation having higher real-world usability for litter mapping.

After identifying the litter products with estimated highest presence nationally for the development process, 7 object classes were selected for training for recognition: Plastic Bottles, Drink Cans, Plastic Bags, Plastic Films, Food Containers and Wrappers, Drinking Straws and Plastic Cups.

The design process employed over 25 respective datasets forming over 56,000 collective images for training. This high quantity (especially for testing with a 70:20:10 Training, Validation, Testing split) acts as an exceedingly large dataset for the Deep Learning development process. When compared to the accuracy of existing models, the proposed system (as shown in the paper analysis section) improves upon existing accuracy to a high degree based on several standardized accuracy metrics.


## Examples of Model Performance

The following 3 inference outputs show successful model predictions on input images.

![Image 1](image.png)
![Image 2](image.png)
![Image 3](image.png)

## Existing and Future Applications
