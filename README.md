**Correlation of Object Detection with Visual Saliency & Depth Estimation**

*Abstract*

Accurate object detection remains a critical challenge in computer vision, particularly in complex scenes involving occlusion, scale variation, and small objects. Although modern deep learning models achieve high detection accuracy, understanding how complementary visual tasks contribute to detection performance remains an important research direction. Human visual perception relies on attention and spatial reasoning, motivating the exploration of auxiliary tasks such as visual saliency and depth estimation.
Previous research has explored multi-task learning approaches that combine object detection with saliency or depth estimation, but these studies mainly evaluate end-to-end performance rather than analysing the underlying relationships between tasks. Bartolo et al. investigated correlations between object detection accuracy, visual saliency, and depth estimation using offline experiments and annotated datasets, showing stronger correlations between saliency and detection performance.
The VisualCue Framework extends that analysis by introducing a real-time, annotation- free framework integrating RT-DETR for object detection, Score-CAM for attention mapping, the Segment Anything Model (SAM) for object segmentation, and Zoe Depth for monocular depth estimation. Experiments conducted on the COCO 2017 unlabelled dataset evaluate spatial correlations between attention maps, segmentation masks, and depth representations. Results show stronger alignment between model attention and segmented object regions than with depth cues, supporting the effectiveness of the framework for practical computer vision applications.

*Key Features*

• Real-time Object Detection using RT-DETR

• Attention Mapping with Score-CAM

• Segmentation using Segment Anything Model (SAM)

• Depth Estimation with ZoeDepth

• Correlation Analysis using Pearson Coefficient

• Works on unlabelled datasets (no manual annotation needed)

*Architecture*
<img width="846" height="526" alt="image" src="https://github.com/user-attachments/assets/4c002fcd-fcf1-4f72-8dbe-dcc393227525" />

 ***The pipeline consists of four components: (A) RT-DETR - Object Detection, (B) Score-CAM - Attention Mapping, (C) SAM - Segmentation, and (D) ZoeDepth - Depth Estimation, followed by Pearson Correlation Analysis.***

*Dataset*

The COCO 2017 Unlabelled Dataset was used to evaluate the framework in
an annotation-free setting. A subset of 100 representative images was selected across 15 object categories like Airplane, Bed, Elephant, Giraffe, Pizza, Person, Motorcycle, Parking Meter, Horse, Stop Sign, Zebra, Bear, Cake, Teddy Bear, and Hot Dog to cover diverse object categories and scene complexity while maintaining computational feasibility. These images were used to analyse the correlation between detection attention, segmentation masks, and depth representations within the integrated pipeline.
Dataset Link: https://www.kaggle.com/datasets/awsaf49/coco-2017-dataset

*Hardware configurations*

• GPU: NVIDIA RTX 3060 / 4060 / 4070 (recommended) - Required for RT- DETR,SAM, and Zoe Depth fast inference

• CPU: Intel i5 / i7

• RAM: Minimum 16 GB (32 GB recommended for large batches) • Storage: 50–80 GB for dataset + model outputs

*Tech Stack*

• Language: Python 3.8+

• Frameworks: PyTorch, Torchvision

• Libraries: Numpy,opencv,matplotlib,pandas,scipy

Results

<img width="390" height="259" alt="image" src="https://github.com/user-attachments/assets/e8a756f4-c92a-497f-82c9-f8045e9d2b94" />

<img width="304" height="284" alt="image" src="https://github.com/user-attachments/assets/a82810f4-f1f2-488c-a231-f5c8bbf0f932" />  <img width="340" height="344" alt="image" src="https://github.com/user-attachments/assets/b638e924-c3e1-46ea-ad34-cfea013b3856" />

***Figure 2: Representative Pipeline Results for a Sample Imag***

***(a) RT-DETR Detection Output (First row left) - bounding boxes drawn around detected objects with confidence scores. (b) SAM Segmentation Mask (First row right) - white regions represent detected object areas; black regions are background. (c) Score-CAM Attention Map (Second row left) - a heatmap where warm colours (red/yellow) indicate regions the model focuses on most strongly, and cool colours (blue) indicate low attention. (d) ZoeDepth Depth Map (Second row right) - colours represent relative depth: colours like red and orange indicate regions closer to the camera, while colours like blue and purple indicate regions further away. The colour bar on the right shows the corresponding depth scale.***






