# Point-cloud-transfer-learning
This repository collects code, videos related to point cloud transfer learning

## Self-Supervised Learning for Domain Adaptation on Point-Clouds
Self-supervised learning (SSL) allows to learn useful representations from unlabeled data and has been applied effectively for domain adaptation (DA) on images. It is still unknown if and how it can be leveraged for domain adaptation for 3D perception. Here we describe the first study of SSL for DA on point clouds. We introduce a new family of pretext tasks, Deformation Reconstruction, motivated by the deformations encountered in sim-to-real transformations. The key idea is to deform regions of the input shape and use a neural network to reconstruct them. We design three types of shape deformation methods: (1) Volume-based: shape deformation based on proximity in the input space; (2) Feature-based: deforming regions in the shape that are semantically similar; and (3) Sampling-based: shape deformation based on three simple sampling schemes. As a separate contribution, we also develop a new method based on the Mixup training procedure for point-clouds. Evaluations on six domain adaptations across synthetic and real furniture data, demonstrate large improvement over previous work.
[[Paper](https://arxiv.org/pdf/2003.12641.pdf)] [[code](https://github.com/IdanAchituve/DefRec_and_PCM)]

## LiDARNet: A Boundary-Aware Domain Adaptation Model for Point Cloud Semantic Segmentation
We present a boundary-aware domain adaptation model for LiDAR scan full-scene semantic segmentation (LiDARNet). Our model can extract both the domain private features and the domain shared features with a two branch structure. We embedded Gated-SCNN into the segmentor component of LiDARNet to learn boundary information while learning to predict full-scene semantic segmentation labels. Moreover, we further reduce the domain gap by inducing the model to learn a mapping between two domains using the domain shared and private features. Besides, we introduce a new dataset (SemanticUSL). The dataset has the same data format and ontology as SemanticKITTI. We conducted experiments on real-world datasets SemanticKITTI, SemanticPOSS, and SemanticUSL, which have differences in channel distributions, reflectivity distributions, diversity of scenes, and sensors setup. Using our approach, we can get a single projection-based LiDAR full-scene semantic segmentation model working on both domains. Our model can keep almost the same performance on the source domain after adaptation and get an 8%-22% mIoU performance increase in the target domain.
[[paper](https://arxiv.org/abs/2003.01174)][[code](https://github.com/unmannedlab/LiDARNet)] come soon

## SqueezeSegV2: Improved Model Structure and Unsupervised Domain Adaptation for Road-Object Segmentation from a LiDAR Point Cloud
Earlier work demonstrates the promise of deep-learning-based approaches for point cloud segmentation; however, these approaches need to be improved to be practically useful. To this end, we introduce a new model SqueezeSegV2. With an improved model structure, SqueezeSetV2 is more robust against dropout noises in LiDAR point cloud and therefore achieves significant accuracy improvement. Training models for point cloud segmentation requires large amounts of labeled data, which is expensive to obtain. To sidestep the cost of data collection and annotation, simulators such as GTA-V can be used to create unlimited amounts of labeled, synthetic data. However, due to domain shift, models trained on synthetic data often do not generalize well to the real world. Existing domain-adaptation methods mainly focus on images and most of them cannot be directly applied to point clouds. We address this problem with a domain-adaptation training pipeline consisting of three major components: 1) learned intensity rendering, 2) geodesic correlation alignment, and 3) progressive domain calibration. When trained on real data, our new model exhibits segmentation accuracy improvements of 6.0-8.6% over the original SqueezeSeg. When training our new model on synthetic data using the proposed domain adaptation pipeline, we nearly double test accuracy on real-world data, from 29.0% to 57.4%. Our source code and synthetic dataset are open sourced. 
[[paper](https://ieeexplore.ieee.org/abstract/document/8793495)][[code](https://github.com/xuanyuzhou98/SqueezeSegV2)]

## 3D Transfer Learning - PointDAN
Domain Adaptation (DA) approaches achieved significant improvements in a wide range of machine learning and computer vision tasks (i.e., classification, detection, and segmentation). However, as far as we are aware, there are few methods yet to achieve domain adaptation directly on 3D point cloud data. The unique challenge of point cloud data lies in its abundant spatial geometric information, and the semantics of the whole object is contributed by including regional geometric structures. Specifically, most general-purpose DA methods that struggle for global feature alignment and ignore local geometric information are not suitable for 3D domain alignment. In this paper, we propose a novel 3D Domain Adaptation Network for point cloud data (PointDAN). PointDAN jointly aligns the global and local features in multi-level. For local alignment, we propose Self-Adaptive (SA) node module with an adjusted receptive field to model the discriminative local structures for aligning domains. To represent hierarchically scaled features, node-attention module is further introduced to weight the relationship of SA nodes across objects and domains. For global alignment, an adversarial-training strategy is employed to learn and align global features across domains. Since there is no common evaluation benchmark for 3D point cloud DA scenario, we build a general benchmark (i.e., PointDA-10) extracted from three popular 3D object/scene datasets (i.e., ModelNet, ShapeNet and ScanNet) for cross-domain 3D objects classification fashion. Extensive experiments on PointDA-10 illustrate the superiority of our model over the state-of-the-art general-purpose DA methods.
[[paper](https://proceedings.neurips.cc/paper/2019/hash/3341f6f048384ec73a7ba2e77d2db48b-Abstract.html)][[code](https://github.com/canqin001/PointDAN)]


## Complete & Label: A Domain Adaptation Approach to Semantic Segmentation of LiDAR Point Clouds
We study an unsupervised domain adaptation problem for the semantic labeling of 3D point clouds, with a particular focus on domain discrepancies induced by different LiDAR sensors. Based on the observation that sparse 3D point clouds are sampled from 3D surfaces, we take a Complete and Label approach to recover the underlying surfaces before passing them to a segmentation network. Specifically, we design a Sparse Voxel Completion Network (SVCN) to complete the 3D surfaces of a sparse point cloud. Unlike semantic labels, to obtain training pairs for SVCN requires no manual labeling. We also introduce local adversarial learning to model the surface prior. The recovered 3D surfaces serve as a canonical domain, from which semantic labels can transfer across different LiDAR sensors. Experiments and ablation studies with our new benchmark for cross-domain semantic labeling of LiDAR data show that the proposed approach provides 6.3-37.6% better performance than previous domain adaptation methods.
[[paper](https://openaccess.thecvf.com/content/CVPR2021/papers/Yi_Complete__Label_A_Domain_Adaptation_Approach_to_Semantic_Segmentation_CVPR_2021_paper.pdf)]

## SSPC-Net: Semi-supervised Semantic 3D Point Cloud Segmentation Network
Point cloud semantic segmentation is a crucial task in 3D scene understanding. Existing methods mainly focus on employing a large number of annotated labels for supervised semantic segmentation. Nonetheless, manually labeling such large point clouds for the supervised segmentation task is time-consuming. In order to reduce the number of annotated labels, we propose a semi-supervised semantic point cloud segmentation network, named SSPC-Net, where we train the semantic segmentation network by inferring the labels of unlabeled points from the few annotated 3D points. In our method, we first partition the whole point cloud into superpoints and build superpoint graphs to mine the long-range dependencies in point clouds. Based on the constructed superpoint graph, we then develop a dynamic label propagation method to generate the pseudo labels for the unsupervised superpoints. Particularly, we adopt a superpoint dropout strategy to dynamically select the generated pseudo labels. In order to fully exploit the generated pseudo labels of the unsupervised superpoints, we furthermore propose a coupled attention mechanism for superpoint feature embedding. Finally, we employ the cross-entropy loss to train the semantic segmentation network with the labels of the supervised superpoints and the pseudo labels of the unsupervised superpoints. Experiments on various datasets demonstrate that our semi-supervised segmentation method can achieve better performance than the current semi-supervised segmentation method with fewer annotated 3D points.
[[paper](https://arxiv.org/abs/2104.07861)][[code](https://github.com/MMCheng/SSPC-Net)]

## xMUDA: Cross-Modal Unsupervised Domain Adaptation for 3D Semantic Segmentation
Unsupervised Domain Adaptation (UDA) is crucial to tackle the lack of annotations in a new domain. There are many multi-modal datasets, but most UDA approaches are uni-modal. In this work, we explore how to learn from multi-modality and propose cross-modal UDA (xMUDA) where we assume the presence of 2D images and 3D point clouds for 3D semantic segmentation. This is challenging as the two input spaces are heterogeneous and can be impacted differently by domain shift. In xMUDA, modalities learn from each other through mutual mimicking, disentangled from the segmentation objective, to prevent the stronger modality from adopting false predictions from the weaker one. We evaluate on new UDA scenarios including day-to-night, country-to-country and dataset-to-dataset, leveraging recent autonomous driving datasets. xMUDA brings large improvements over uni-modal UDA on all tested scenarios, and is complementary to state-of-the-art UDA techniques.
[[paper](https://arxiv.org/abs/1911.12676)][[code](https://github.com/valeoai/xmuda)]


### 2D GAN Video
[[Youtube Channel](https://www.youtube.com/watch?v=UcHe0xiuvpg&list=RDCMUC34rW-HtPJulxr5wp2Xa04w&index=10)]

### 2D GAN Code
[[Keras-GAN Code](https://github.com/eriklindernoren/Keras-GAN)]
[[Pytorch-GAN Code](https://github.com/eriklindernoren/PyTorch-GAN)]
