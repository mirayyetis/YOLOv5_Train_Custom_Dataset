# YOLOv5_Train_Custom_Dataset
## Training custom dataset with YOLOv5

 If you want to train a model, you first need to collect data. After collecting these images, you need to label them using **Roboflow**. An example dataset is provided above, and I've left a sample dataset named **sag_right-roboflow** for you to try.

If you want to train a model using the YOLOv5 algorithm via the command line, you need to follow these steps:

1) Download the yolov5-master folder to your computer and unzip it.
2) Upload your dataset to the **data** folder inside the yolov5-master. (But your data should be in the same structure as the **ilerisol_deneme** folder that I uploaded!)
3) We need to create a **data YAML** file. Copy the **coco128 YAML** file and create a YAML file for yourself named **custom_data**. Here, you need to adjust the relevant paths. Also, you need to write the labels you assigned to the labeled data in Roboflow. *(For example, I labeled the forward-left sign and set the label number to 6; accordingly, I edited my YAML file.)*
4) The **train.py** code is used in the training section.
5) You should enter the **cmd** and navigate to the yolov5-master folder. While in this folder, you need to run the following command:
**```python train.py --img 416 --batch 32 --epochs 100 --data custom_data.yaml --weights yolov5s.pt –-cache```**
Your training will begin. *(You can change the values of img, batch, and epoch here)*. When the training is complete, in the yolov5-master folder, you will find the **best.pt** file in the runs folder, which is your created model.
 6) If you encounter errors during training due to library versions, you need to install the versions listed in the **requirements.txt** file. To do this, go to the cmd, enter the yolov5-master folder, and run the following command:
**```python -m pip install -r requirements.txt```**

7) If you want to test the model you created with your computer camera, after placing the path of your **best.pt** file in the relevant place in **yolov5_real_time.py**, you can see the results by running the code.

**Labeling the data through Roboflow:**

![y](https://github.com/mirayyetis/YOLOv5_Train_Custom_Dataset/assets/121189200/b69f43cd-8fc0-46ce-b7da-2930e0febbd6)



**Image of the finished training:**

![x](https://github.com/mirayyetis/YOLOv5_Train_Custom_Dataset/assets/121189200/19a64baf-835d-42b9-aea9-2bf574c50cef)




