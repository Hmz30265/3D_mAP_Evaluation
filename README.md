# 3D_mAP_Evaluation
mean Average Precision in 6D pose estimation - This code evaluates the performance of a model in 3D detection objects.  

```diff
- WARNING:This code has NOT been tested with any real dataset!
```

# Citation
Majority of this code is from the following project: https://github.com/Cartucho/mAP/tree/master , which is evaluation of 2D image object detection.

Key function of calculating IoU is from:
```
@article{ravi2020pytorch3d,
    author = {Nikhila Ravi and Jeremy Reizenstein and David Novotny and Taylor Gordon
                  and Wan-Yen Lo and Justin Johnson and Georgia Gkioxari},
    title = {Accelerating 3D Deep Learning with PyTorch3D},
    journal = {arXiv:2007.08501},
    year = {2020},
}
```

# Explaination
This evaluation uses IoU metric.(Intersection over Union)If IoU is over a threshold, it is considered as True Positive(TP), otherwise it is False Positive(FP). If IoU is equal to zero, it is considered as False Negative(FN). 

<img width="671" alt="IoU_explain" src="https://github.com/MattMiaozhuangHe/3D_mAP_Evaluation/assets/133658992/a0a30968-69f2-4982-b876-1497e1c483eb">


According to the number of TP, FP and FN, the code will draw a Precision and Recall curve. At different threshold, muiltiple precision will be calculated. Therefore we can add up precisions and get an average, which is average precision. Sum up all precisions of classes, get another mean, it is mean average precision(mAP).

Here is an simple Precision and Recall curve that this data set generates:

![book](https://github.com/MattMiaozhuangHe/3D_mAP_Evaluation/assets/133658992/730d3b56-4ee1-4774-8a19-f57d221abe77)



The key function to calculate IoU: box3d_overlapis() at line 659 is from Pytorch3D package: https://pytorch3d.org/docs/iou3d.



# Prerequsite
You need to install

 Anaconda


Copy the Github repo:
```
git clone https://github.com/MattMiaozhuangHe/3D_mAP_Evaluation.git
```
  
Setup environment:
```
conda create mAP
conda activate mAP
conda install torch
conda install pytorchvision
```

# Run the evaluation code
```
python main.py
```
#### Create the detection-results files

- Create a separate detection-results text file.
- Use **matching names** for the files (e.g. ground-truth: "image_1.txt", detection-results: "image_1.txt").
- In these files, each line should be in the following format:
    ```
    <class_name> <confidence> <right bot front> <left top back>
    ```
![image](https://github.com/MattMiaozhuangHe/3D_mAP_Evaluation/assets/133658992/1f24cef8-bf48-4116-b425-6926ca520bc9)


- E.g. "image_1.txt":
    ```
    book 0.460851 200 200 200 300 300 300
    ```
  
