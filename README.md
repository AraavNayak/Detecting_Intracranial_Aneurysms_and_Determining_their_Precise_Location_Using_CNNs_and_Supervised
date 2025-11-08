
<h1>Intracranial Aneurysm Detection</h1>
<br>
<ins>Overview</ins>: In this project, I present a 5-fold EfficientNetV2 ensemble to detect and precisely locate intracranial aneurysms across various types of medical images, including CTA, MRA, and T1 post-contrast and T2-weighted MRI. I begin by loading in DICOM images from the dataset and extracting the aneurysm position information from slices of each image. After applying windowing and statistical normalization, I obtain windowing parameters based on the modality (CT - Computed Tomography, MR - Magnetic Resonance) with a robust fallback strategy for unexpected or unlabeled series. I then extracted 2D pixel array from DICOM and apply preprocessing (for 2D DICOM series). I subsequently processed DICOM series and returned it as a NumPy array, which enabled me to train and perform inference with my 5-fold EfficientNetV2 ensemble for precise aneurysm localization.

<br><div>
<ins>Problem</ins>: Intracranial aneurysms affect around 3% of the global population. Unfortunately, up to 50% of these aneurysms are only diagnosed after they rupture, which can result in severe illness or death. Worldwide, intracranial aneurysms cause approximately 500,000 deaths each year, and roughly half of the victims are younger than 50.
<br><div><br>
<ins>Model Evaluation</ins>: My submission was evaluated by a weighted multilabel area under the ROC curve (AUC ROC score) between the predicted probabilities and the observed targets, where the score for Aneurysm Present is assigned a weight of 13, while all the other scores are assigned a weight of 1 which emphasizes the importance of identifying true positives to prevent fatal ruptures. The final score was the average of the fourteen AUC ROC scores with these weights.


