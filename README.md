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

<p align="center">
  <img src="Images/Image%201.png" alt="Image 1" />
  <img src="Images/Image%202.png" alt="Image 2" />
  <img src="Images/Image%203.png" alt="Image 3" />
</p>

## Existing and Future Applications

The current software is being implemented into a website through which users have access to a full map of where litter is located globally as well as a separate feature to uploading images.

The process works as follows:

<ol>
  <li>Users are able to upload images of litter regardless of the number or types of litter within it via the website.</li>
  <li>The images are saved in a database.</li>
  <li>A CPU or GPU processes the images and applies the model inferences to them, noting each instance of a litter product within the image and what product it is.</li>
  <li>The predictions are provided back to the database and made publicly available, highlighting both the images were taken, the images themselves and the litter products within them.</li>
</ol>


### Why the Data Matters

For informing both communities themselves and larger scale trends in environmental decisionmaking, data on the types and locations of litter products is crucial. Local governments as well as organizers of cleanup initiatives are able to use this data in determining which regions most commonly have the highest number of litter products, therefore improving the accuracy of the information known about the litter densities and the issue more generally.

### Why Deep Learning Models are Used

In crowdmapping, or the process of recording the instances of a certain occurrence collected by a group of potentially non-researchers, it is essential to be able to confirm such uploads in aiding with the credibility of the system. If users had to both take images and manually count the instances of products within them, this process would lead to a less efficient system which discourages user upload because of the increased amount of work required for a single upload. By promoting a system that automates the annotation process, this issue is largely resolved.

The main reason for automation is that the bottleneck in crowdmapping for litter is not the images themselves, but the manual need for classifying and counting the instances of litter within an image; our system eliminates this issue by using AI for the image analysis process instead.

### Further Applications

While the crowdmapping method is effective, by employing other applications, the value of the system increases significantly. For example, by gaining visual surveys of larger areas using UAV based images or drones, the models can be applied on a larger scale for density tracking with little manual involvement.

Additionally, applying the models for sorting between recyclable and non-recyclable products is a further application where automated predictions in high-speed sorting tasks is similarly effective to other applications.

## The Website

The website through which this process is done is located at [https://naveenstewart.pythonanywhere.com/](https://naveenstewart.pythonanywhere.com/). Below is a preview of how the mapping software is used for individual tracking:

<p align="center">
  <img src="Images/website.png" alt="Image">
</p>



## Proven Effectiveness

On a local scale (though the software can be used globally), this technique of crowdmapping has already shown its effectiveness based on audit data in a local cleanup event. Centered in the town of North Reading, MA, USA a proposed usage of the system during a cleanup event showed an approximate 2.2 times increase in the number of per volunteer litter items collected. In the most recent cleanup audit, the mapping system had roughly 700 instances of litter items mapped over a 2 month period before the cleanup. The resulting statistics were as follows:

Compared to 3 prior cleanups, the effectiveness of the proposed system was demonstrated under controlled external conditions. These prior events happened in May 2024, October 2024 and October 2025. Based on the application of the software across various object classes, the following are notable statistics derived from the audit data:

<ol>
<li>For the litter products directly mapped by the software: Plastic Lids, Plastic Bottles, Cans, Straws and Plastic Cups had 3.1272, 1.9428, 1.6526, 1.9531 and 2.1863 respectively times more products per active volunteer collected at this event compared to the average in the 3 previous ones. </li>
<li>For the litter item of Mini Alcohol Bottles which were not affected by the software and not directly mapped, this value per volunteer decreased below the average from previous audits with a 0.9336 per volunteer items collected ratio (representing a decrease). </li>
<li>For the object classes affected by the software which were mapped prior to the event using automated AI-based classification, the average increase factor in per volunteer items collected was 2.1724. </li>
<li>Despite having only roughly 40% of the total volunteers during this event, by employing the software for coordinated locating and collection of litter products, the event was able to collect roughly as many items as in the 2 previous events. </li>
</ol>
The results show a more than double (factor of 2.1724) effectiveness of the software, as validated by the control object class which was not mapped which decreased in the amount collected. The results of this event validate the usage of the software and imply possible further use on larger scale.


#Takeaways, and what this Repository Offers

This repository contains the formalized paper on the results of the training process along with commentary on accuracy differences between the proposed instance segmentation models and baselines.

Additionally, there are the models themselves included in the repository along with certain python scripts relevant to the project development.

The models are available for use in pretraining further models along with directly applying to potential litter systems. We hope that the broader environmental management research community uses them wherever applicable.
