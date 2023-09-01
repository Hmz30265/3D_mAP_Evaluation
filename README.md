# 3D_mAP_Evaluation
mean Average Precision in 6D pose estimation - This code evaluates the performance of a model in 3D detection objects.  


# Citation
Majority of this code is from the following project: https://github.com/Cartucho/mAP/tree/master , which is evaluation of 2D image object detection.

# Explaination
This evaluation uses IoU metric.(Intersection over Union)If IoU is over a threshold, it is considered as True Positive(TP), otherwise it is False Positive(FP). If IoU is equal to zero, it is considered as False Negative(FN). According to the number of TP, FP and FN, the code will draw a Precision and Recall curve. At different threshold, muiltiple precision will be calculated. Therefore we can add up precisions and get an average, which is average precision. Sum up all precisions of classes, get another mean, it is mean average precision(mAP).

# Prerequsite
You need to install

 Anaconda


Copy the Github repo:
  -git clone _____

  
Setup environment:
  -conda create mAP
  -conda activate mAP
  -conda install requirement.txt

 Run the evaluation code
  -python main.py

  
