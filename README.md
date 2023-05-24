# (ACMMM 2021 Oral Paper) Deep SfM Face Reconstruction Based on Massive Landmark Bundle Adjustment
This repository shows two tasks: Face landmark detection and Face 3D reconstruction.

They are described in this paper: Deep Unsupervised 3D SfM Face Reconstruction Based on Massive Landmark Bundle Adjustment. This work can be cited as:

```
@inproceedings{wang2021deep,
  title={Deep Unsupervised 3D SfM Face Reconstruction Based on Massive Landmark Bundle Adjustment},
  author={Wang, Yuxing and Lu, Yawen and Xie, Zhihua and Lu, Guoyu},
  booktitle={Proceedings of the 29th ACM International Conference on Multimedia},
  pages={1350--1358},
  year={2021}
}
```

## Installation
1. Clone the repository.
2. install dependencies.

```
pip install -r requirement.txt
```

# Face landmark detection
<div align=center><img src="https://github.com/BoomStarcuc/3DSfMFaceReconstruction/blob/master/data/RedAndGreen.png" width="420" height="200"/><img src="https://github.com/BoomStarcuc/3DSfMFaceReconstruction/blob/master/data/Picture1_crop.jpg" width="345" height="265"/></div>

## For inference
1. Download landmark pre-trained model at [GoogleDrive](https://drive.google.com/file/d/1tDqX2nG1qATqrd2fEb4Sgs4av25d9tgN/view?usp=sharing), and put it into ```FaceLandmark/model/```
2. Run the test file

```
python Facial_landmark.py
```


# Face 3D reconstruction
<div align=center><img src="https://github.com/BoomStarcuc/3DSfMFaceReconstruction/blob/master/data/Stirling ESRC 3D.png" width="420" height="190"/><img src="https://github.com/BoomStarcuc/3DSfMFaceReconstruction/blob/master/data/Facescape%20face.png" width="420" height="190"/></div>

## For inference
1. Download face 3D reconstruction pre-trained model at [GoogleDrive](https://drive.google.com/file/d/1t-3IXQHn5DmXpoumf5a8JfQgWxg54krW/view?usp=sharing), and put it into ```FaceReconstruction/checkpoints/```

3. Run the ```inference.py``` file to generate disparity map

```
python inference.py --dataset-dir './FaceReconstruction/test_image/' --output-dir './FaceReconstruction/output/' --pretrained './FaceReconstruction/checkpoints/dispnet_model_best.pth.tar' --resnet-layers 18 --output-disp 
```
4. Run the ```generate_ply.py``` file to generate point cloud ```.ply``` file

```
python generate_ply.py
```
