# NWPU_YRCC2
A dataset for ice segmentation
## Overview
Ice caps, ice plugs, or ice dams are often formed in high latitude rivers in winter, which could change the hydraulic, thermal, and geometric boundary conditions of water flow and form a unique ice phenomenon in winter. Ice plugs or ice dams, i.e., drift ice in the river channel blocking the cross section of water flow, may cause water level rise, inundate farmland houses, damage the coastal hydraulic structures, cause shipping interruption, or cause hydraulic power loss. Therefore, river ice monitoring is necessary in preparing for potential hazards. Accurate fine-grained ice semantic segmentation is a key technology in the study of river ice monitoring, which can provide more information for ice situation analysis, change trend prediction, and so on.

We built a UAV image dataset named NWPU_YRCC2 for fine-grained river ice semantic segmentation. All UAV images were collected in the Ningxia–Inner Mongolia reach of the Yellow River, since the ice phenomenon in this reach is very typical and diverse. The dataset consists of 1525 precisely labeled images covering typical river ice images with different characteristics.
### Paper Link
The paper can be downloaded from this [link](https://www.researchgate.net/publication/349258007_ICENETv2_A_Fine-Grained_River_Ice_Semantic_Segmentation_Network_Based_on_UAV_Images).
Please cite our paper when using the dataset.
 ```
@article{zhang2021icenetv2,
  title={ICENETv2: A Fine-Grained River Ice Semantic Segmentation Network Based on UAV Images},
  author={Zhang, Xiuwei and Zhou, Yang and Jin, Jiaojiao and Wang, Yafei and Fan, Minhao and Wang, Ning and Zhang, Yanning},
  journal={Remote Sensing},
  volume={13},
  number={4},
  pages={633},
  year={2021},
  publisher={Multidisciplinary Digital Publishing Institute}
}
```
## Dataset Details
We selected the Ningxia–Inner Mongolia reach of the Yellow River as our study area. The Yellow River is one of the world’s longest rivers, with a total length of 5464 km and a drainage area of 752,443 km2. Since the middle section of the river runs through the Loess Plateau, it carries a large amount of sediment. It spans 23 longitudes from east to west and 10 latitudes from north to south, hence there are considerable differences in elevation between the east and west, and in landforms among different regions. Since the basin is located in the middle latitude zone, the influence of atmospheric circulation and monsoon circulation is relatively complex. Due to the complexity of climate and landform, the ice phenomenon is very typical and diverse in spring and winter, especially in the Ningxia–Inner Mongolia reach. Therefore, this reach is selected so as to study fine-grained river ice segmentation.

There are no suitable UAV image datasets for the fine-grained river ice segmentation of the Yellow River. Therefore, we built the NWPU_YRCC2 dataset. The NWPU_YRCC2 dataset contains four categories: Shore ice, drift ice, water, and others. It is necessary to distinguish shore ice and drift ice, since the calculation of drift ice cover density, which is an important factor in the actual freeze-up date forecast, just considers the ratio of drift ice and excludes shore ice. The aerial images were taken annually from 2015 to 2019 at the Ningxia–Inner Mongolia reach of the Yellow River from November to March. During data collection, an ASN216 fixed-wing drone with a visible light camera Canon 5DS and a DJI Inspire 1 were used to capture images and videos. The UAV images are taken in nadir view or oblique view during data capture. However, when calculating the drift ice cover density, the UAV images are required to be captured in nadir view. The flying height of the drones ranges from 30 m to 600 m. Finally, 200 videos were captured, ranging in length from 10 min to 50 min. The maximum image resolution and maximum video resolution of the Canon 5DS camera on ASN216 are 8688 × 5792 and 1920 × 1080, respectively, while the maximum image resolution and maximum video resolution of the camera on DJI Inspire 1 are 4000 × 3000 and 4096 × 2160, respectively. To keep the resolution of the input image of the model consistent, we resized the images to 1600 × 640. From the videos and images obtained from aerial photography, 305 typical images containing four categories of targets are carefully selected. These images are mainly collected during the freeze-up period. We use Photoshop software to label each pixel of the images into four categories: Shore ice, drift ice, water, and others. The reason why we do not use other annotation tools such as Labelme and Image Labeler is that they are difficult to use for marking the boundary between these four categories. It is worth mentioning that this annotation work is very time-consuming. We divided 305 images into training set, validation set, and test set at a ratio of 6:2:2. Then, they are expanded to 1525 images to form the NWPU_YRCC2 dataset by data augmentation operations, including the brightness adjustment, flipping, and clipping. The brightness adjustment includes two ways, increasing brightness and decreasing brightness. For flipping, we used both horizontal and vertical flipping.
## Data Orgnization
-Dataset
    
        --TUM
      
        --KITTI
      
        --Tanks_and_Temples
      
        --CPC
     
     -Pipeline
     
     -Evaluation
     
     -vlfeat-0.9.21
