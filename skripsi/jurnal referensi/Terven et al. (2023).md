Citation:Terven,J.;
Córdova-Esparza,D.-M.;
Romero-González,J.-A.A
ComprehensiveReviewofYOLO
ArchitecturesinComputerVision:
FromYOLOv1toYOLOv8and
YOLO-NAS.Mach.Learn.Knowl.Extr.
2023,5,1680–1716. https://doi.org/
10.3390/make5040083
AcademicEditors:GuoqingChao
andXianzhiWang
Received:19October2023
Revised:12November2023
Accepted:17November2023
Published:20November2023
Copyright: ©2023 by the authors.
LicenseeMDPI, Basel, Switzerland.
Thisarticle isanopenaccessarticle
distributed under the terms and
conditionsof theCreativeCommons
Attribution(CCBY) license(https://
creativecommons.org/licenses/by/
4.0/).
machine learning &
knowledge extraction
Review
AComprehensiveReviewofYOLOArchitecturesinComputer
Vision:FromYOLOv1toYOLOv8andYOLO-NAS
JuanTerven1,* ,Diana-MargaritaCórdova-Esparza2 andJulio-AlejandroRomero-González2
1 InstitutoPolitecnicoNacional,CICATA-Qro,Queretaro76090,Mexico
2 FacultaddeInformática,UniversidadAutónomadeQuerétaro,Queretaro76230,Mexico;
diana.cordova@uaq.mx(D.-M.C.-E.); julio.romero@uaq.mx(J.-A.R.-G.)
* Correspondence: jrtervens@ipn.mx
Abstract:YOLOhasbecomeacentralreal-timeobjectdetectionsystemforrobotics,driverlesscars,
andvideomonitoringapplications.WepresentacomprehensiveanalysisofYOLO’sevolution,
examiningtheinnovationsandcontributionsineachiterationfromtheoriginalYOLOuptoYOLOv8,
YOLO-NAS,andYOLOwithtransformers.Westartbydescribingthestandardmetricsandpostpro
cessing;then,wediscussthemajorchangesinnetworkarchitectureandtrainingtricksforeachmodel.
Finally,wesummarizetheessentiallessonsfromYOLO’sdevelopmentandprovideaperspectiveon
itsfuture,highlightingpotentialresearchdirectionstoenhancereal-timeobjectdetectionsystems.
Keywords:YOLO;objectdetection;deeplearning;computervision
1.Introduction
Real-timeobjectdetectionhasemergedasacriticalcomponentinnumerousapplica
tions,spanningvariousfieldssuchasautonomousvehicles,robotics,videosurveillance,
andaugmentedreality.Amongthedifferentobjectdetectionalgorithms,theYOLO(You
OnlyLookOnce)frameworkhasstoodoutforitsremarkablebalanceofspeedandaccuracy,
enablingtherapidandreliableidentificationofobjectsinimages.Sinceitsinception,the
YOLOfamilyhasevolvedthroughmultipleiterations,eachbuildingupontheprevious
versionstoaddresslimitationsandenhanceperformance(seeFigure1).Thispaperaims
toprovideacomprehensivereviewof theYOLOframework’sdevelopment, fromthe
originalYOLOv1tothelatestYOLOv8,elucidatingthekeyinnovations,differences,and
improvementsacrosseachversion.
YOLOv8
YOLO-NAS
Figure1.AtimelineofYOLOversions.
InadditiontotheYOLOframework,thefieldofobjectdetectionandimageprocessing
hasdevelopedseveralothernotablemethods.TechniquessuchasR-CNN(Region-based
ConvolutionalNeuralNetworks) [1]anditssuccessors,FastR-CNN[2]andFasterR
CNN[3],haveplayedapivotalroleinadvancingtheaccuracyofobjectdetection.These
Mach.Learn.Knowl.Extr.2023,5,1680–1716.https://doi.org/10.3390/make5040083 https://www.mdpi.com/journal/make
Mach. Learn. Knowl. Extr. 2023, 5
1681
methods rely on a two-stage process, where selective search generates region proposals,
and convolutional neural networks classify and refine these regions. Another significant
approach is the Single-Shot MultiBox Detector (SSD) [4], which, similar to YOLO, focuses
on speed and efficiency by eliminating the need for a separate region proposal step. Addi
tionally, methods like Mask R-CNN [5] have extended capabilities to instance segmentation,
enabling precise object localization and pixel-level segmentation. These developments,
alongside others such as RetinaNet [6] and EfficientDet [7], have collectively contributed
to the diverse landscape of object detection algorithms. Each method presents unique
tradeoffs between speed, accuracy, and complexity, catering to different application needs
and computational constraints.
Other great reviews include [8–10]. However, thereviewfrom[8]coversuntilYOLOv3,
and [9] covers until YOLOv4, leaving behind the most recent developments. Our pa
per, different from [10], shows in-depth architectures for most YOLO architectures pre
sented and covers other variations, such as YOLOX, PP-YOLOs, YOLO with transformers,
and YOLO-NAS.
This paper begins by exploring the foundational concepts and architecture of the
original YOLO model, which set the stage for subsequent advances in the YOLO family.
Following this, we dive into the refinements and enhancements introduced in each version,
ranging from YOLOv2 toYOLOv8. Theseimprovementsencompassvariousaspectssuchas
network design, loss function modifications, anchor box adaptations, and input resolution
scaling. By examining these developments, we aim to offer a holistic understanding of the
YOLO framework’s evolution and its implications for object detection.
In addition to discussing the specific advancements of each YOLO version, the paper
highlights the tradeoffs between speed and accuracy that have emerged throughout the
framework’s development. This underscores the importance of considering the context and
requirements of specific applications when selecting the most appropriate YOLO model.
Finally, we envision the future directions of the YOLO framework, touching upon potential
avenues for further research and development that will shape the ongoing progress of
real-time object detection systems.
2. YOLOApplications across Diverse Fields
YOLO’s real-time object detection capabilities have been invaluable in autonomous
vehicle systems, enabling quick identification and tracking of various objects such as
vehicles, pedestrians [11,12], bicycles, and other obstacles [13–16]. These capabilities have
been applied in numerous fields, including action recognition [17] in video sequences for
surveillance [18], sports analysis [19], and human-computer interaction [20].
YOLO models have been used in agriculture to detect and classify crops [21,22], pests,
and diseases [23], assisting in precision agriculture techniques and automating farming
processes. They have also been adapted for face detection tasks in biometrics, security, and
facial recognition systems [24,25].
In the medical field, YOLO has been employed for cancer detection [26,27], skin
segmentation [28], and pill identification [29], leading to improved diagnostic accuracy
and more efficient treatment processes. In remote sensing, it has been used for object
detection and classification in satellite and aerial imagery, aiding in land use mapping,
urban planning, and environmental monitoring [30–33].
Security systems have integrated YOLO models for real-time monitoring and analysis
of video feeds, allowing rapid detection of suspicious activities [34], social distancing,
and face mask detection [35]. The models have also been applied in surface inspection to
detect defects and anomalies, enhancing quality control in manufacturing and production
processes [36–38].
In traffic applications, YOLO models have been utilized for tasks such as license
plate detection [39] and traffic sign recognition [40], contributing to developing intelligent
transportation systems and traffic management solutions. They have been employed in
wildlife detection and monitoring to identify endangered species for biodiversity conser
Mach. Learn. Knowl. Extr. 2023, 5
1682
vation and ecosystem management [41]. Lastly, YOLO has been widely used in robotic
applications [42,43] and object detection from drones [44,45]. Figure 2 shows a bibliometric
network visualization of all the papers found in Scopus with the word YOLO in the title
and filtered by object detection keyword. Then, we manually filtered all the papers related
to applications.
Figure 2. Bibliometric network visualization of the main YOLO Applications created with [46].
3. Object Detection Metrics and Non-Maximum Suppression (NMS)
The average precision (AP), traditionally called mean average precision (mAP), is the
commonly used metric for evaluating the performance of object detection models. It
measures the average precision across all categories, providing a single value to compare
different models. The COCO dataset makes no distinction between AP and mAP. In the
rest of this paper, we will refer to this metric as AP.
In YOLOv1 and YOLOv2, the dataset utilized for training and benchmarking was
PASCALVOC 2007 andVOC 2012[47]. However,fromYOLOv3onwards,thedatasetused
is Microsoft COCO (Common Objects in Context) [48]. The AP is calculated differently for
these datasets. The following sections will discuss the rationale behind AP and explain
how it is computed.
3.1. How AP Works?
The AP metric is based on precision–recall metrics, handling multiple object categories,
and defining a positive prediction using Intersection over Union (IoU).
Precision and recall: Precision measures the accuracy of the model’s positive predic
tions, while recall measures the proportion of actual positive cases that the model correctly
identifies. There is often a tradeoff between precision and recall; for example, increasing
the number of detected objects (higher recall) can result in more false positives (lower
precision). To account for this tradeoff, the AP metric incorporates the precision–recall
curve that plots precision against recall for different confidence thresholds. This metric
provides a balanced assessment of precision and recall by considering the area under the
precision–recall curve.
Handling multiple object categories: Object detection models must identify and local
ize multiple object categories in an image. The AP metric addresses this by calculating each
category’s average precision (AP) separately and then taking the mean of these APs across
Mach. Learn. Knowl. Extr. 2023, 5
1683
all categories (that is why it is also called mean average precision). This approach ensures
that the model’s performance is evaluated for each category individually, providing a more
comprehensive assessment of the model’s overall performance.
Intersection over Union: Object detection aims to accurately localize objects in images
by predicting bounding boxes. The AP metric incorporates the Intersection over Union
(IoU) measure to assess the quality of the predicted bounding boxes. IoU is the ratio of
the intersection area to the union area of the predicted bounding box and the ground
truth bounding box (see Figure 3). It measures the overlap between the ground truth and
predicted bounding boxes. The COCO benchmark considers multiple IoU thresholds to
evaluate the model’s performance at different levels of localization accuracy.
Figure 3. Intersection over Union (IoU). (a) The IoU is calculated by dividing the intersection of
the two boxes by the union of the boxes; (b) examples of three different IoU values for different
box locations.
3.2. Computing AP
The AP is computed differently in the VOC and in the COCO datasets. In this section,
we describe how it is computed for each dataset.
3.2.1. VOC Dataset
This dataset includes 20 object categories. To compute the AP in VOC, we follow the
next steps:
1.
2.
3.
For each category, calculate the precision–recall curve by varying the confidence
threshold of the model’s predictions.
Calculate each category’s average precision (AP) using an interpolated 11-point sam
pling of the precision–recall curve.
Compute the final average precision (AP) by taking the mean of the APs across all
20 categories.
3.2.2. Microsoft COCO Dataset
This dataset includes 80 object categories and uses a more complex method for calcu
lating AP. Instead of using an 11-point interpolation, it uses a 101-point interpolation, i.e.,
it computes the precision for 101 recall thresholds from 0 to 1 in increments of 0.01. Also,
the AP is obtained by averaging over multiple IoU values instead of just one, except for a
commonAP metric called AP50, which is the AP for a single IoU threshold of 0.5. The steps
for computing AP in COCO are the following:
1.
2.
For each category, calculate the precision–recall curve by varying the confidence
threshold of the model’s predictions.
Compute each category’s average precision (AP) using 101 recall thresholds.
Mach. Learn. Knowl. Extr. 2023, 5
1684
3.
4.
5.
Calculate AP at different Intersection over Union (IoU) thresholds, typically from
0.5 to 0.95 with a step size of 0.05. A higher IoU threshold requires a more accurate
prediction to be considered a true positive.
For each IoU threshold, take the mean of the APs across all 80 categories.
Finally, compute the overall AP by averaging the AP values calculated at each
IoU threshold.
The differences in AP calculation make it hard to directly compare the performance
of object detection models across the two datasets. The current standard uses the COCO
AP due to its more fine-grained evaluation of how well a model performs at different
IoU thresholds.
3.3. Non-Maximum Suppression (NMS)
Non-maximum suppression (NMS) is a post-processing technique used in object
detection algorithms to reduce the number of overlapping bounding boxes and improve the
overall detection quality. Object detection algorithms typically generate multiple bounding
boxes around the same object with different confidence scores. NMS filters out redundant
and irrelevant bounding boxes, keeping only the most accurate ones. Algorithm 1 describes
the procedure. Figure 4 shows the typical output of an object detection model containing
multiple overlapping bounding boxes and the output after NMS.
Algorithm 1 Non-Maximum Suppression Algorithm
Require: Set of predicted bounding boxes B, confidence scores S, IoU threshold τ, confi
dence threshold T
Ensure: Set of filtered bounding boxes F
1: F ←∅
2: Filter the boxes: B ← {b ∈ B | S(b) ≥ T}
3: Sort the boxes B by their confidence scores in descending order
4: while B= ∅do
5:
6:
7:
8:
9:
10:
11:
12:
13:
Select the box b with the highest confidence score
Addb to the set of final boxes F: F ← F∪{b}
Remove b from the set of boxes B: B ← B−{b}
for all remaining boxes r in B do
Calculate the IoU between b and r: iou ← IoU(b,r)
if iou ≥ τ then
Remove r from the set of boxes B: B ← B−{r}
end if
end for
14: end while
Figure 4. Non-maximum suppression (NMS). (a) Typical output of an object detection model contain
ing multiple overlapping boxes. (b) Output after NMS.
We are ready to start describing the different YOLO models.
Mach. Learn. Knowl. Extr. 2023, 5
1685
4. YOLO: YouOnlyLookOnce
YOLO, byJoseph Redmon et al., was published at CVPR 2016 [49]. It presented for
the first time a real-time end-to-end approach for object detection. The name YOLO stands
for “You Only Look Once”, referring to the fact that it was able to accomplish the detection
task with a single pass of the network, as opposed to previous approaches that either used
sliding windows followed by a classifier that needed to run hundreds or thousands of
times per image or the more advanced methods that divided the task into two-steps, where
the first step detects possible regions with objects or regions proposals and the second step
run a classifier on the proposals. Also, YOLO used a more straightforward output based
only on regression to predict the detection outputs as opposed to Fast R-CNN [2], which
used two separate outputs, a classification for the probabilities and a regression for the
boxes coordinates.
4.1. How Does YOLOv1 Work?
YOLOv1 unified the object detection steps by detecting all the bounding boxes simulta
neously. To accomplish this, YOLO divides the input image into an S × S grid and predicts
B bounding boxes of the same class, along with its confidence for C different classes per
grid element. Each bounding box prediction consists of five values: Pc,bx,by,bh,bw, where
Pc is the confidence score for the box that reflects how confident the model is that the box
contains an object and how accurate the box is. The bx and by coordinates are the centers of
the box relative to the grid cell, and bh and bw are the height and width of the box relative to
the full image. The output of YOLO is a tensor of S×S×(B×5+C) optionally followed
by non-maximum suppression (NMS) to remove duplicate detections.
In the original YOLO paper, the authors used the PASCAL VOC dataset [47], which
contains 20 classes (C = 20), a grid of 7×7 (S = 7), and at most 2 classes per grid element
(B = 2), giving a 7×7×30output prediction.
Figure 5 shows a simplified output vector considering a three-by-three grid, three
classes, and a single class per grid for eight values. In this simplified case, the output of
YOLO would be 3×3×8.
YOLOv1 achieved an average precision (AP) of 63.4 on the PASCAL VOC2007 dataset.
Figure 5. YOLOoutputprediction. The figure depicts a simplified YOLO model with a three-by-three
grid, three classes, and a single class prediction per grid element to produce a vector of eight values.
4.2. YOLOv1 Architecture
TheYOLOv1architecturecomprises24convolutionallayersfollowedby2fullyconnected
layers that predict the bounding box coordinates and probabilities. All layers used leaky
Mach.Learn.Knowl.Extr.2023,5 1686
rectifiedlinearunitactivations[50]exceptforthelastone,whichusedalinearactivation
function. InspiredbyGoogLeNet [51]andNetworkinNetwork[52],YOLOuses1×1
convolutionallayerstoreducethenumberoffeaturemapsandkeepthenumberofparameters
relativelylow.Asactivationlayers,Table1describestheYOLOv1architecture.Theauthors
alsointroducedalightermodelcalledFastYOLO,composedofnineconvolutionallayers.
Table1.YOLOarchitecture.Thearchitecturecomprises24convolutionallayerscombining3×3
convolutionswith1×1convolutionsforchannelreduction.Theoutputisafullyconnectedlayer
thatgeneratesagridof7×7with30valuesforeachgridcelltoaccommodatetenboundingbox
coordinates(2boxes)with20categories.
Type Filters Size/Stride Output
Conv 64 7×7/2 224×224
MaxPool 2×2/2 112×112
Conv 192 3×3/1 112×112
MaxPool 2×2/2 56×56
1× Conv 128 1×1/1 56×56
Conv 256 3×3/1 56×56
Conv 256 1×1/1 56×56
Conv 512 3×3/1 56×56
MaxPool 2×2/2 28×28
4× Conv 256 1×1/1 28×28
Conv 512 3×3/1 28×28
Conv 512 1×1/1 28×28
Conv 1024 3×3/1 28×28
MaxPool 2×2/2 14×14
2× Conv 512 1×1/1 14×14
Conv 1024 3×3/1 14×14
Conv 1024 3×3/1 14×14
Conv 1024 3×3/2 7×7
Conv 1024 3×3/1 7×7
Conv 1024 3×3/1 7×7
FC 4096 4096
Dropout0.5 4096
FC 7×7×30 7×7×30
4.3.YOLOv1Training
Theauthorspre-trainedthefirst20layersofYOLOataresolutionof224×224using
theImageNetdataset[53].Then,theyaddedthelastfourlayerswithrandomlyinitialized
weightsandfine-tunedthemodelwiththePASCALVOC2007andVOC2012datasets[47]
ataresolutionof448×448toincreasethedetailsformoreaccurateobjectdetection.
Foraugmentations,theauthorsusedrandomscalingandtranslationsofatmost20%
oftheinputimagesize,aswellasrandomexposureandsaturationwithanupper-end
factorof1.5intheHSVcolorspace.
YOLOv1usedalossfunctioncomposedofmultiplesum-squarederrors,asshownin
Figure6. Inthelossfunction,λcoord=5isascalefactorthatgivesmoreimportancetothe
boundingboxespredictions,andλnoobj=0.5isascalefactorthatdecreasestheimportance
oftheboxesthatdonotcontainobjects.
Mach. Learn. Knowl. Extr. 2023, 5
1687
Figure 6. YOLO cost function: includes localization loss for bounding box coordinates, confidence
loss for object presence or absence, and classification loss for category prediction accuracy.
The first two terms of the loss represent the localization loss; it computes the error in
the predicted bounding boxes locations (x,y) and sizes (w,h). Note that these errors are
only computed in the boxes containing objects (represented by the 1obj
ij ), only penalizing if
an object is present in that grid cell. The third and fourth loss terms represent the confidence
loss; the third term measures the confidence error when the object is detected in the box
(1obj
ij ), and the fourth term measures the confidence error when the object is not detected in
the box (1noobj
ij
). Since most boxes are empty, this loss is weighted down by the λnoobj term.
The final loss component is the classification loss that measures the squared error of the class
conditional probabilities for each class only if the object appears in the cell (1obj
i
4.4. YOLOv1 Strengths and Limitations
).
The simple architecture of YOLO, along with its novel full-image one-shot regression,
made it much faster than the existing object detectors, allowing real-time performance.
Mach. Learn. Knowl. Extr. 2023, 5
1688
However, while YOLOperformed faster than any object detector, the localization error
was larger compared with state-of-the-art methods, such as Fast R-CNN [2]. There were
three major causes of this limitation:
1.
It could only detect at most two objects of the same class in the grid cell, limiting its
ability to predict nearby objects.
2.
3.
It struggled to predict objects with aspect ratios not seen in the training data.
It learned from coarse object features due to the downsampling layers.
5. YOLOv2: Better, Faster, and Stronger
YOLOv2 was published at CVPR 2017 [54] by Joseph Redmon and Ali Farhadi. It
included several improvements over the original YOLO to make it better, keeping the same
speed and also being stronger—capable of detecting 9000 categories. The improvements
were the following:
1.
2.
3.
4.
5.
6.
7.
8.
Batch normalization on all convolutional layers improves convergence and acts as a
regularizer to reduce overfitting.
High-resolution classifier. Like YOLOv1, they pre-trained the model with ImageNet
at 224 × 224. However, this time, they fine-tuned the model for ten epochs on Ima
geNet with a resolution of 448 × 448, improving the network performance on higher
resolution input.
Fully convolutional. They removed the dense layers and used a fully convolu
tional architecture.
Use anchor boxes to predict bounding boxes. They use a set of prior boxes or anchor
boxes, which are boxes with predefined shapes used to match prototypical shapes of
objects as shown in Figure 7. Multiple anchor boxes are defined for each grid cell, and
the system predicts the coordinates and the class for every anchor box. The size of the
network output is proportional to the number of anchor boxes per grid cell.
Dimension clusters. Picking good prior boxes helps the network learn to predict
more accurate bounding boxes. The authors ran k-means clustering on the training
bounding boxes to find good priors. They selected five prior boxes, providing a good
tradeoff between recall and model complexity.
Direct location prediction. Unlike other methods that predicted offsets [3], YOLOv2
followed the same philosophy and predicted location coordinates relative to the grid
cell. The network predicts five bounding boxes for each cell, each with five values tx,
ty, tw, th, and to, where to is equivalent to Pc from YOLOv1 and the final bounding
box coordinates are obtained as shown in Figure 8.
Finer-grained features. YOLOv2, compared with YOLOv1, removed one pooling
layer to obtain an output feature map or grid of 13 × 13 for input images of 416 × 416.
YOLOv2 also uses a passthrough layer that takes the 26 × 26 × 512 feature map
and reorganizes it by stacking adjacent features into different channels instead of
losing them via a spatial subsampling. This generates 13×13×2048 feature maps
concatenated in the channel dimension with the lower resolution 13 × 13 × 1024 maps
to obtain 13 × 13 × 3072 feature maps. See Table 2 for the architectural details.
Multi-scale training. Since YOLOv2 does not use fully connected layers, the inputs
can be of different sizes. To make YOLOv2 robust to different input sizes, the au
thors trained the model randomly, changing the input size—from 320 ×320 up to
608 ×608—every ten batches.
With all these improvements, YOLOv2 achieved an average precision (AP) of 78.6%
on the PASCAL VOC2007 dataset compared to the 63.4% obtained by YOLOv1.
Mach.Learn.Knowl.Extr.2023,5 1689
Figure7.Anchorboxes.YOLOv2definesmultipleanchorboxesforeachgridcell.
Figure8.Boundingboxprediction.Thebox’scentercoordinatesareobtainedwiththepredicted
tx, tyvaluespassingthroughasigmoidfunctionandoffsetbythelocationofthegridcellcx, cy.
Thewidthandheightofthefinalboxusethepriorwidthpwandheightphscaledbyetwandeth,
respectively,wheretwandtharepredictedbyYOLOv2.
Table2.YOLOv2architecture.Darknet-19backbone(layers1to23)plusthedetectionheadcomposed
ofthelastfourconvolutionallayersandthepassthroughlayerthatreorganizesthefeaturesofthe
17thoutputof26×26×512into13×13×2048, followedbyconcatenationwiththe25thlayer.
Thefinalconvolutiongeneratesagridof13×13with125channelstoaccommodate25predictions
(5coordinates+20classes)forfiveboundingboxes.
Num Type Filters Size/Stride Output
1 Conv/BN 32 3×3/1 416×416×32
2 MaxPool 2×2/2 208×208×32
3 Conv/BN 64 3×3/1 208×208×64
4 MaxPool 2×2/2 104×104×64
5 Conv/BN 128 3×3/1 104×104×128
6 Conv/BN 64 1×1/1 104×104×64
7 Conv/BN 128 3×3/1 104×104×128
8 MaxPool 2×2/2 52×52×128
9 Conv/BN 256 3×3/1 52×52×256
10 Conv/BN 128 1×1/1 52×52×128
11 Conv/BN 256 3×3/1 52×52×256
12 MaxPool 2×2/2 52×52×256
13 Conv/BN 512 3×3/1 26×26×512
14 Conv/BN 256 1×1/1 26×26×256
15 Conv/BN 512 3×3/1 26×26×512
16 Conv/BN 256 1×1/1 26×26×256
17 Conv/BN 512 3×3/1 26×26×512
18 MaxPool 2×2/2 13×13×512
19 Conv/BN 1024 3×3/1 13×13×1024
20 Conv/BN 512 1×1/1 13×13×512
Mach.Learn.Knowl.Extr.2023,5 1690
Table2.Cont.
Num Type Filters Size/Stride Output
21 Conv/BN 1024 3×3/1 13×13×1024
22 Conv/BN 512 1×1/1 13×13×512
23 Conv/BN 1024 3×3/1 13×13×1024
24 Conv/BN 1024 3×3/1 13×13×1024
25 Conv/BN 1024 3×3/1 13×13×1024
26 Reorglayer17 13×13×2048
27 Concat25and26 13×13×3072
28 Conv/BN 1024 3×3/1 13×13×1024
29 Conv 125 1×1/1 13×13×125
5.1.YOLOv2Architecture
ThebackbonearchitectureusedbyYOLOv2iscalledDarknet-19,containing19con
volutional layersand5max-poolinglayers. SimilartothearchitectureofYOLOv1, it
isinspiredintheNetworkinNetwork[52]using1×1convolutionsbetweenthe3×3
toreducethenumberofparameters. Inaddition,asmentionedabove, theyusebatch
normalizationtoregularizeandhelpconvergence.
Table2showstheentireDarknet-19backbonewiththeobjectdetectionhead.When
usingthePASCALVOCdataset,YOLOv2predictsfiveboundingboxes,eachwithfive
valuesand20classes,whenusingthePASCALVOCdataset.
Theobjectclassificationheadreplacesthelastfourconvolutionallayerswithasingle
convolutional layerwith1000filters, followedbyaglobalaveragepoolinglayerand
aSoftmax.
5.2.YOLO9000IsaStrongerYOLOv2
Theauthorsintroducedamethodfortrainingjointclassificationanddetectioninthe
samepaper. ItusedthedetectionlabeleddatafromCOCO[48]tolearnbounding-boxcoor
dinatesandclassificationdatafromImageNettoincreasethenumberofcategoriesitcan
detect.Duringtraining,theycombinedbothdatasetssuchthatwhenadetectiontraining
imageisused, itbackpropagatesthedetectionnetwork.Whenaclassificationtraining
imageisused,itbackpropagatestheclassificationpartofthearchitecture.Theresultisa
YOLOmodelcapableofdetectingmorethan9000categories,hencethenameYOLO9000.
6.YOLOv3
YOLOv3[55]waspublishedinArXivin2018byJosephRedmonandAliFarhadi.
It includedsignificantchangesandabiggerarchitecturetobeonparwiththestateof
theartwhilekeepingreal-timeperformance. Inthefollowing,wedescribedthechanges
concerningYOLOv2.
1. Boundingboxprediction.LikeYOLOv2,thenetworkpredictsfourcoordinatesfor
eachboundingboxtx,ty,tw,andth;however,thistime,YOLOv3predictsanobjectness
scoreforeachboundingboxusinglogisticregression.Thisscoreis1fortheanchor
boxwiththehighestoverlapwiththegroundtruthand0fortherestoftheanchor
boxes.YOLOv3,asopposedtoFasterR-CNN[3],assignsonlyoneanchorboxtoeach
groundtruthobject.Also,ifnoanchorboxisassignedtoanobject,itonlyincreases
classificationlossbutnotlocalizationlossorconfidenceloss.
2. ClassPrediction. Insteadofusingasoftmaxfortheclassification,theyusedbinary
cross-entropytotrainindependent logisticclassifiersandposetheproblemasa
multilabelclassification.Thischangeallowsassigningmultiplelabelstothesame
box,whichmayoccuronsomecomplexdatasets[56]withoverlappinglabels.For
example,thesameobjectcanbeaPersonandaMan.
3. Newbackbone.YOLOv3featuresalargerfeatureextractorcomposedof53convo
lutional layerswithresidualconnections. Section6.1describesthearchitecturein
moredetail.
Mach. Learn. Knowl. Extr. 2023, 5
1691
4.
5.
6.
Spatial pyramid pooling (SPP) Although not mentioned in the paper, the authors
also added to the backbone a modified SPP block [57] that concatenates multiple max
pooling outputs without subsampling (stride = 1), each with different kernel sizes
k ×k, where k = 1, 5, 9, 13 allowing a larger receptive field. This version is called
YOLOv3-spp and was the best-performing version, improving the AP50 by 2.7%.
Multi-scale Predictions. Similar to feature pyramid networks [58], YOLOv3 predicts
three boxes at three different scales. Section 6.2 describes the multi-scale prediction
mechanism in more detail.
Bounding box priors. Like YOLOv2, the authors also use k-means to determine the
bounding-box priors of anchor boxes. The difference is that in YOLOv2, they used a
total of five prior boxes per cell, and in YOLOv3, they used three prior boxes for three
different scales.
6.1. YOLOv3 Architecture
The architecture backbone presented in YOLOv3 is called Darknet-53. It replaced all
max-pooling layers with strided convolutions and added residual connections. In total, it
contains 53 convolutional layers. Figure 9 shows the architecture details.
Figure 9. YOLOv3 Darknet-53 backbone. The architecture of YOLOv3 is composed of 53 convolu
tional layers, each with batch normalization and Leaky ReLU activation. Also, residual connections
connect the input of the 1×1 convolutions across the whole network with the output of the 3×3
convolutions. The architecture shown here consists of only the backbone; it does not include the
detection head composed of multi-scale predictions.
The Darknet-53 backbone obtains Top-1 and Top-5 accuracies comparable with ResNet
152 but almost two time faster.
6.2. YOLOv3 Multi-Scale Predictions
In addition to a larger architecture, an essential feature of YOLOv3 is the multi-scale
predictions, i.e., predictions at multiple grid sizes. This helped to obtain finer-detailed
boxes and significantly improved the prediction of small objects, which was one of the
main weaknesses of the previous versions of YOLO.
The multi-scale detection architecture shown in Figure 10 works as follows: the first
output, marked as y1, is equivalent to the YOLOv2 output, where a 13×13 grid defines the
Mach. Learn. Knowl. Extr. 2023, 5
1692
output. The second output y2 is composed by concatenating the output after the (Res ×4)
of Darknet-53 with the output after (the Res ×8). The feature maps have different sizes, i.e.,
13 ×13 and 26×26,sothere is an upsampling operation before the concatenation. Finally,
using an upsampling operation, the third output y3 concatenates the 26×26 feature maps
with the 52 × 52 feature maps.
Figure 10. YOLOv3 multi-scale detection architecture. The output of the Darknet-53 backbone is
branched to three different outputs marked as y1, y2, and y3, each of increased resolution. The final
predicted boxes are filtered using non-maximum suppression. The CBL (Convolution–BatchNorm
Leaky ReLU) blocks comprise one convolution layer with batch normalization and Leaky ReLU. The
Res blocks comprise one CBL followed by two CBL structures with a residual connection, as shown
in Figure 9.
For the COCO dataset with 80 categories, each scale provides an output tensor with a
shape of N ×N×[3×(4+1+80)] where N×N isthesize of the feature map (or grid
cell), the 3 indicates the boxes per cell, and the 4 + 1 includes the four coordinates and the
objectness score.
6.3. YOLOv3 Results
WhenYOLOv3 wasreleased, the benchmark for object detection had changed from
PASCAL VOC to Microsoft COCO [48]. Therefore, from here on, all the YOLOs are
evaluated on the MS COCO dataset. YOLOv3-spp achieved an average precision AP of
36.2% and AP50 of 60.6% at 20 FPS, achieving the state of the art at the time and being two
times faster.
7. Backbone, Neck, and Head
At this time, the architecture of object detectors started to be described in three parts:
the backbone, the neck, and the head. Figure 11 shows a high-level backbone, neck, and
head diagram.
The backbone is responsible for extracting useful features from the input image. It is
typically a convolutional neural network (CNN) trained on a large-scale image classification
task, such as ImageNet. The backbone captures hierarchical features at different scales, with
lower-level features (e.g., edges and textures) extracted in the earlier layers and higher-level
features (e.g., object parts and semantic information) extracted in the deeper layers.
Mach. Learn. Knowl. Extr. 2023, 5
1693
Figure 11. The architecture of modern object detectors can be described as the backbone, the neck,
and the head. The backbone, usually a convolutional neural network (CNN), extracts vital features
from the image at different scales. The neck refines these features, enhancing spatial and semantic
information. Lastly, the head uses these refined features to make object detection predictions.
The neck is an intermediate component that connects the backbone to the head. It
aggregates and refines the features extracted by the backbone, often focusing on enhancing
the spatial and semantic information across different scales. The neck may include addi
tional convolutional layers, feature pyramid networks (FPN) [58], or other mechanisms to
improve the representation of the features.
The head is the final component of an object detector; it is responsible for making
predictions based on the features provided by the backbone and neck. It typically consists
of one or more task-specific subnetworks that perform classification, localization, and,
more recently, instance segmentation and pose estimation. The head processes the fea
tures the neck provides, generating predictions for each object candidate. In the end, a
post-processing step, such as non-maximum suppression (NMS), filters out overlapping
predictions and retains only the most confident detections.
In the rest of the YOLO models, we will describe the architectures using the backbone,
neck, and head.
8. YOLOv4
Two years passed, and there was no new version of YOLO. It was not until April
2020 that Alexey Bochkovskiy, Chien-Yao Wang, and Hong-Yuan Mark Liao released, in
ArXiv, the paper for YOLOv4 [59]. At first, it felt odd that different authors presented a new
“official” version of YOLO; however, YOLOv4 kept the same YOLO philosophy—real-time,
open source, single shot, and the darknet framework—and the improvements were so
satisfactory that the community rapidly embraced this version as the official YOLOv4.
YOLOv4 tried to find the optimal balance by experimenting with many changes
categorized as bag of freebies and bag of specials. Bag-of-freebies methods only change the
training strategy and increase training cost but do not increase the inference time, the most
common being data augmentation. On the other hand, bag-of-specials methods slightly
increase the inference cost but significantly improve accuracy. Examples of these methods
are those for enlarging the receptive field [57,60,61], combining features [58,62–64], and
post-processing [50,65–67], among others.
We summarize the main changes of YOLOv4 in the following points:
• AnEnhancedArchitecture with Bag-of-Specials (BoS) Integration. The authors tried
multiple architectures for the backbone, such as ResNeXt50 [68], EfficientNet-B3 [69],
and Darknet-53. The best-performing architecture was a modification of Darknet-53
with cross-stage partial connections (CSPNet) [70], and Mish activation function [66]
Mach. Learn. Knowl. Extr. 2023, 5
1694
as the backbone (see Figure 12. For the neck, they used the modified version of
spatial pyramid pooling (SPP) [57] from YOLOv3-spp and multi-scale predictions as
in YOLOv3, but with a modified version of path aggregation network (PANet) [71]
instead of FPN as well as a modified spatial attention module (SAM) [72]. Finally,
for the detection head, they used anchors, as in YOLOv3. Therefore, the model was
called CSPDarknet53-PANet-SPP. The cross-stage partial connections (CSP) added to
the Darknet-53 help reduce the computation of the model while keeping the same
accuracy. The SPP block, as in YOLOv3-spp, increases the receptive field without
affecting the inference speed. The modified version of PANet concatenates the features
instead of adding them as in the original PANet paper.
• Integrating Bag of Freebies (BoF) for an Advanced Training Approach. Apart from the
regular augmentations such as random brightness, contrast, scaling, cropping, flip
ping, and rotation, the authors implemented mosaic augmentation that combines four
images into a single one, allowing the detection of objects outside their usual context
and also reducing the need for a large mini-batch size for batch normalization. For reg
ularization, they used DropBlock [73], which works as a replacement for Dropout [74]
but for convolutional neural networks as well as class label smoothing [75,76]. For
the detector, they added CIoU loss [77] and cross-mini-batch normalization (CmBN)
for collecting statistics from the entire batch instead of from single mini-batches as in
regular batch normalization [78].
• Self-adversarial Training (SAT). To make the model more robust to perturbations,
an adversarial attack is performed on the input image to create a deception that
the ground-truth object is not in the image but keeps the original label to detect the
correct object.
• HyperparameterOptimization with Genetic Algorithms. To find the optimal hyperpa
rameters used for training, they use genetic algorithms on the first 10% of periods and
a cosine annealing scheduler [79] to alter the learning rate during training. It starts
reducing the learning rate slowly, followed by a quick reduction halfway through the
training process, ending with a slight reduction.
Table 3 lists the final selection of BoFs and BoS for the backbone and the detector.
Table 3. YOLOv4 final selection of bag of freebies (BoF) and bag of specials (BoS). BoF are methods
that increase performance with no inference cost but longer training times. On the other hand, BoS
are methods that slightly increase the inference cost but significantly improve accuracy.
Backbone
Detector
Bag of Freebies
Data augmentation- Mosaic- CutMix
Regularization- DropBlock
Class label smoothing
Bag of Specials
Mish activation
Cross-stage partial connections
Bag of Freebies
Data augmentation- Mosaic- Self-adversarial training
CIoU loss
Cross-mini-batch normalization (CmBN)
Eliminate grid sensitivity
Multiple anchors for a single ground truth
Cosine annealing scheduler
Optimal hyperparameters
Random training shapes
Bag of Specials
Mish activation
Spatial pyramid pooling block
Multi-input weighted residual connections Spatial attention module (SAM)
Path aggregation network (PAN)
Distance-IoU non-maximum suppression
Mach. Learn. Knowl. Extr. 2023, 5
1695
Figure 12. YOLOv4 architecture for object detection. The modules in the diagram are CMB: convolu
tion + batch normalization + Mish activation, CBL: convolution + batch normalization + Leaky ReLU,
UP: upsampling, SPP: spatial pyramid pooling, and PANet: path aggregation network. Diagram
inspired by [80].
Evaluated on MS COCO dataset test-dev 2017, YOLOv4 achieved an AP of 43.5% and
AP50 of 65.7% at more than 50 FPS on an NVIDIA V100.
9. YOLOv5
YOLOv5[81] was released a couple of months after YOLOv4 in 2020 by Glen Jocher,
founder and CEO of Ultralytics. It uses many improvements described in the YOLOv4
section but developed in Pytorch instead of Darknet. YOLOv5 incorporates an Ultralytics
algorithm called AutoAnchor. This pre-training tool checks and adjusts anchor boxes if
they are ill-fitted for the dataset and training settings, such as image size. It first applies a
k-means function to dataset labels to generate initial conditions for a genetic evolution (GE)
algorithm. The GE algorithm then evolves these anchors over 1000 generations by default,
using CIoU loss [77] and Best Possible Recall as its fitness function. Figure 13 shows the
detailed architecture of YOLOv5.
Mach. Learn. Knowl. Extr. 2023, 5
1696
Figure 13. YOLOv5 architecture. The architecture uses a modified CSPDarknet53 backbone with a
Stem, followed by convolutional layers that extract image features. A spatial pyramid pooling fast
(SPPF) layer accelerates computation by pooling features into a fixed-size map. Each convolution has
batch normalization and SiLU activation. The network’s neck uses SPPF and a modified CSP-PAN,
while the head resembles YOLOv3. Diagram based on [82,83].
YOLOv5 Architecture
The backbone is a modified CSPDarknet53 that starts with a Stem, a strided convolu
tion layer with a large window size to reduce memory and computationalcosts, followedby
convolutional layers that extract relevant features from the input image. The SPPF (spatial
pyramid pooling fast) layer and the following convolution layers process the features at
various scales, while the upsample layers increase the resolution of the feature maps. The
Mach. Learn. Knowl. Extr. 2023, 5
1697
SPPF layer aims to speed up the computation of the network by pooling features of different
scales into a fixed-size feature map. Each convolution is followed by batch normalization
(BN) and SiLU activation [84]. The neck uses SPPF and a modified CSP-PAN, while the
head resembles YOLOv3.
YOLOv5 uses several augmentations such as Mosaic, copy paste [85], random affine,
MixUp[86], HSV augmentation, random horizontal flip, as well as other augmentations
from the albumentations package [87]. It also improves the grid sensitivity to make it more
stable to runaway gradients.
YOLOv5providesfive scaledversions: YOLOv5n(nano),YOLOv5s(small),YOLOv5m
(medium), YOLOv5l (large), and YOLOv5x (extra-large), where the width and depth of
the convolution modules vary to suit specific applications and hardware requirements.
For instance, YOLOv5n and YOLOv5s are lightweight models targeted for low-resource
devices, while YOLOv5x is optimized for high performance, albeit at the expense of speed.
The YOLOv5 released version at the time of this writing is v7.0, including YOLOv5
versions capable of classification and instance segmentation.
YOLOv5 isopen sourceand actively maintained byUltralytics, withmorethan250con
tributors and new improvements frequently. YOLOv5 is easy to use, train, and deploy.
Ultralytics provides a mobile version for iOS and Android and many integrations for
labeling, training, and deployment.
Evaluated on MS COCO dataset test-dev 2017, YOLOv5x achieved an AP of 50.7%
with an image size of 640 pixels. Using a batch size of 32, it can achieve a speed of 200 FPS
on an NVIDIAV100. Using a larger input size of 1536 pixels and test-time augmentation
(TTA), YOLOv5 achieves an AP of 55.8%.
10. Scaled-YOLOv4
One year after YOLOv4, the same authors presented Scaled-YOLOv4 [88] at CVPR
2021. Differently from YOLOv4, Scaled YOLOv4 was developed in Pytorch instead of
Darknet. Themainnoveltywastheintroductionofscaling-up andscaling-downtechniques.
Scaling up means producing a model that increases accuracy at the expense of a lower
speed; on the other hand, scaling down entails producing a model that increases speed,
sacrificing accuracy. In addition, scaled-down models need less computing power and can
run on embedded systems.
The scaled-down architecture was called YOLOv4-tiny; it was designed for low-end
GPUs and can run at 46 FPS on a Jetson TX2 or 440 FPS on RTX2080Ti, achieving 22% AP
on MSCOCO.
The scaled-up model architecture was called YOLOv4-large, which included three
different sizes: P5, P6, and P7. This architecture was designed for cloud GPU and achieved
state-of-the-art performance, surpassing all previous models [6,7,89] with 56% AP on
MSCOCO.
11. YOLOR
YOLOR [90] was published in ArXiv in May 2021 by the same research team of
YOLOv4. Itstands for You Only Learn One Representation. In this paper, the authors followed
a different approach; they developed a multi-task learning approach that aims to create a
single model for various tasks (e.g., classification, detection, pose estimation) by learning
a general representation and using sub-networks to create task-specific representations.
With the insight that the traditional joint learning method often leads to suboptimal feature
generation, YOLOR aims to overcome this by encoding the implicit knowledge of neural
networks to be applied to multiple tasks, similar to how humans use past experiences to
approach new problems. The results showed that introducing implicit knowledge into the
neural network benefits all the tasks.
Evaluated on MS COCO dataset test-dev 2017, YOLOR achieved an AP of 55.4% and
AP50 of 73.3% at 30 FPS on an NVIDIA V100.
Mach. Learn. Knowl. Extr. 2023, 5
1698
12. YOLOX
YOLOX[91] waspublished in ArXiv in July 2021 by Megvii Technology. Developed
in Pytorch and using YOLOV3 from Ultralytics as a starting point, it has five principal
changes: an anchor-free architecture, multiple positives, a decoupled head, advanced label
assignment, and strong augmentations. It achieved state-of-the-art results in 2021 with an
optimal balance between speed and accuracy with 50.1% AP at 68.9% FPS on the Tesla V100.
In the following, we describe the five main changes of YOLOX with respect to YOLOv3:
1.
Anchor-free. Since YOLOv2, all subsequent YOLO versions were anchor-based de
tectors. YOLOX, inspired by anchor-free state-of-the-art object detectors, such as
CornerNet [92], CenterNet [93], and FCOS [94], returned to an anchor-free architec
ture simplifying the training and decoding process. The anchor-free increased the AP
by 0.9 points concerning the YOLOv3 baseline.
2.
3.
4.
5.
Multi positives. To compensate for the large imbalances and the lack of anchors
produced, the authors use center sampling [94] where they assigned the center 3×3
area as positives. This approach increased AP by 2.1 points.
Decoupled head. In [95,96], it was shown that there could be a misalignment between
the classification confidence and localization accuracy. Due to this, YOLOX separates
these two into two heads (as shown in Figure 14), one for classification tasks and
the other for regression tasks, improving the AP by 1.1 points and speeding up the
model convergence.
Advanced label assignment. In [97], it was shown that the ground-truth label as
signment could have ambiguities when the boxes of multiple objects overlap and
formulate the assigning procedure as an Optimal Transport (OT) problem. YOLOX,
inspired by this work, proposed a simplified version called simOTA. This change
increased AP by 2.3 points.
Strong augmentations. YOLOX uses MixUP [86] and Mosaic augmentations. The
authors found that ImageNet pretraining was no longer beneficial after using these
augmentations. The strong augmentations increased AP by 2.4 points.
Figure 14. Difference between YOLOv3 head and YOLOX decoupled head. For each level of the
FPN, they used a 1×1 convolution layer to reduce the feature channel to 256. Then, they added
two parallel branches with two 3×3 convolution layers each for the class confidence (classification)
and localization (regression) tasks. The IoU branch is added to the regression head.
13. YOLOv6
YOLOv6 [98] was published in ArXiv in September 2022 by the Meituan Vision AI
Department. The network design consists of an efficient backbone with RepVGG or
CSPStackRep blocks, a PAN topology neck, and an efficient decoupled head with a hybrid
channel strategy. In addition, the paper introduces enhanced quantization techniques
using post-training quantization and channel-wise distillation, resulting in faster and more
Mach. Learn. Knowl. Extr. 2023, 5
1699
accurate detectors. Overall, YOLOv6 outperforms previous state-of-the-art models, such as
YOLOv5, YOLOX,andPP-YOLOE,onaccuracy and speed metrics.
Figure 15 shows the detailed architecture of YOLOv6.
Figure 15. YOLOv6 architecture. The architecture uses a new backbone with RepVGG blocks [99].
The spatial pyramid pooling fast (SPPF) and Conv modules are similar to YOLOv5. However,
YOLOv6 uses a decoupled head. Diagram based on [100].
The main novelties of this model are summarized below:
1.
2.
3.
4.
5.
Anew backbone based on RepVGG[99] called EfficientRep, which uses higher par
allelism than previous YOLO backbones. For the neck, they use PAN [71] enhanced
with RepBlocks [99] or CSPStackRep [70] Blocks for the larger models. And following
YOLOX,they developed an efficient decoupled head.
Label assignment using the Task alignment learning approach introduced in TOOD [101].
Newclassification and regression losses. They used a classification VariFocal loss [102]
and an SIoU [103]/GIoU [104] regression loss.
A self-distillation strategy for the regression and classification tasks.
A quantization scheme for detection using RepOptimizer [105] and channel-wise
distillation [106], which helped to achieve a faster detector.
The authors provide eight scaled models, from YOLOv6-N to YOLOv6-L6. Evaluated
on the MS COCO dataset test-dev 2017, the largest model achieved an AP of 57.2% at
around 29 FPS on an NVIDIA Tesla T4.
14. YOLOv7
YOLOv7[107] was published in ArXiv in July 2022 by the same authors of YOLOv4
and YOLOR. Atthe time, it surpassed all known object detectors in speed and accuracy
in the range of 5 FPS to 160 FPS. Like YOLOv4, it was trained using only the MS COCO
dataset without pre-trained backbones. YOLOv7 proposed a couple of architecture changes
and a series of bag-of-freebies methods, which increased the accuracy without affecting the
inference speed, affecting only the training time.
Figure 16 shows the detailed architecture of YOLOv7.
Mach. Learn. Knowl. Extr. 2023, 5
1700
Figure 16. YOLOv7 architecture. Changes in this architecture include the ELAN blocks that combine
features of different groups by shuffling and merging cardinality to enhance the model learning and
modified RepVGG without identity connection. Diagram based on [108].
The architecture changes of YOLOv7 are:
• Extended efficient layer aggregation network (E-ELAN). ELAN [109] is a strategy
that allows a deep model to learn and converge more efficiently by controlling the
shortest longest gradient path. YOLOv7 proposed E-ELANthatworksformodelswith
unlimited stacked computational blocks. E-ELAN combines the features of different
groupsby shufflingandmerging cardinality to enhance the network’s learning without
destroying the original gradient path.
• Model scaling for concatenation-based models. Scaling generates models of dif
ferent sizes by adjusting some model attributes. The architecture of YOLOv7 is a
concatenation-based architecture in which standard scaling techniques, such as depth
scaling, cause a ratio change between the input channel and the output channel of
a transition layer, which, in turn, leads to a decrease in the hardware usage of the
model. YOLOv7 proposed a new strategy for scaling concatenation-based models in
which the depth and width of the block are scaled with the same factor to maintain
the optimal structure of the model.
The bag of freebies used in YOLOv7 includes:
• Plannedre-parameterized convolution. Like YOLOv6, the architecture of YOLOv7
is also inspired by re-parameterized convolutions (RepConv) [99]. However, they
found that the identity connection in RepConv destroys the residual in ResNet [62]
and the concatenation in DenseNet [110]. For this reason, they removed the identity
connection and called it RepConvN.
• Coarselabelassignment for auxiliary head and fine label assignment for the lead head.
The lead head is responsible for the final output, while the auxiliary head assists with
the training.
• Batchnormalization in conv-bn-activation. This integrates the mean and variance
of batch normalization into the bias and weight of the convolutional layer at the
inference stage.
• Implicitknowledge inspired in YOLOR [90].
• Exponential moving average as the final inference model.
Mach. Learn. Knowl. Extr. 2023, 5
1701
Comparison with YOLOv4 and YOLOR
In this section, we highlight the enhancements of YOLOv7 compared to previous
YOLO models developed by the same authors.
Compared to YOLOv4, YOLOv7achieved a 75% reduction in parameters and a 36%
reduction in computation while simultaneously improving the average precision (AP)
by 1.5%.
In contrast to YOLOv4-tiny, YOLOv7-tiny managed to reduce parameters and compu
tation by 39% and 49%, respectively, while maintaining the same AP.
Lastly, compared to YOLOR, YOLOv7 reduced the number of parameters and compu
tation by 43% and 15%, respectively, along with a slight 0.4% increase in AP.
Evaluated on the MS COCO dataset test-dev 2017, YOLOv7-E6 achieved an AP of
55.9% and AP50 of 73.5% with an input size of 1280 pixels with a speed of 50 FPS on an
NVIDIAV100.
15. DAMO-YOLO
DAMO-YOLO[111] was published in ArXiv in November 2022 by Alibaba Group.
Inspired by the current technologies, DAMO-YOLO included the following:
1.
2.
3.
4.
5.
A neural architecture search (NAS). They used a method called MAE-NAS [112]
developed by Alibaba to find an efficient architecture automatically.
A large neck. Inspired by GiraffeDet [113], CSPNet [70], and ELAN [109], the authors
designed a neck that can work in real-time called Efficient-RepGFPN.
A small head. The authors found that a large neck and a small neck yield better per
formance, and they only left one linear layer for classification and one for regression.
They called this approach ZeroHead.
AlignedOTA label assignment. Dynamic label assignment methods, such as OTA [97]
and TOOD[101], have gained popularity due to their significant improvements over
static methods. However, the misalignment between classification and regression
remains a problem, partly because of the imbalance between classification and regres
sion losses. To address this issue, their AlignOTA method introduces focal loss [6]
into the classification cost and uses the IoU of prediction and ground-truth box as the
soft label, enabling the selection of aligned samples for each target and solving the
problem from a global perspective.
Knowledge distillation. Their proposed strategy consists of two stages: the teacher
guiding the student in the first stage and the student fine-tuning independently in
the second stage. Additionally, they incorporate two enhancements in the distillation
approach: the Align Module, which adapts student features to the same resolution
as the teacher’s, and Channel-wise Dynamic Temperature, which normalizes teacher
and student features to reduce the impact of real value differences.
The authors generated scaled models named DAMO-YOLO-Tiny/Small/Medium,
with the best model achieving an AP of 50.0 % at 233 FPS on an NVIDIA V100.
16. YOLOv8
YOLOv8[114] was released in January 2023 by Ultralytics, the company that devel
opedYOLOv5. YOLOv8providedfivescaledversions: YOLOv8n(nano),YOLOv8s(small),
YOLOv8m (medium), YOLOv8l (large) and YOLOv8x (extra-large). YOLOv8 supports
multiple vision tasks such as object detection, segmentation, pose estimation, tracking,
and classification.
YOLOv8 Architecture
Figure 17 shows the detailed architecture of YOLOv8. YOLOv8usesasimilarbackbone
as YOLOv5 with some changes on the CSPLayer, now called the C2f module. The C2f
module (cross-stage partial bottleneck with two convolutions) combines high-level features
with contextual information to improve detection accuracy.
Mach. Learn. Knowl. Extr. 2023, 5
1702
YOLOv8 uses an anchor-free model with a decoupled head to process objectness,
classification, and regression tasks independently. This design allows each branch to focus
on its task and improves the model’s overall accuracy. In the output layer of YOLOv8, they
used the sigmoid function as the activation function for the objectness score, representing
the probability that the bounding box contains an object. It uses the softmax function for the
class probabilities, representing the objects’ probabilities belonging to each possible class.
YOLOv8 uses CIoU [77] and DFL [115] loss functions for bounding-box loss and
binary cross-entropy for classification loss. These losses have improved object detection
performance, mainly when dealing with smaller objects.
Figure 17. YOLOv8 architecture. The architecture uses a modified CSPDarknet53 backbone. The
C2f module replaces the CSPLayer used in YOLOv5. A spatial pyramid pooling fast (SPPF) layer
accelerates computation by pooling features into a fixed-size map. Each convolution has batch
normalization and SiLU activation. The head is decoupled to process objectness, classification, and
regression tasks independently. Diagram based on [116].
YOLOv8 also provides a semantic segmentation model called YOLOv8-Seg model.
The backbone is a CSPDarknet53 feature extractor, followed by a C2f module instead of
Mach. Learn. Knowl. Extr. 2023, 5
1703
the traditional YOLO neck architecture. The C2f module is followed by two segmentation
heads, which learn to predict the semantic segmentation masks for the input image. The
model has similar detection heads to YOLOv8, consisting of five detection modules and a
prediction layer. The YOLOv8-Seg model has achieved state-of-the-art results on various
object detection and semantic segmentation benchmarks while maintaining high speed
and efficiency.
YOLOv8 can be run from the command line interface (CLI), or it can also be installed
as a PIP package. In addition, it comes with multiple integrations for labeling, training,
and deploying.
Evaluated on the MS COCO dataset test-dev 2017, YOLOv8x achieved an AP of 53.9%
with an image size of 640 pixels (compared to 50.7% of YOLOv5 on the same input size)
with a speed of 280 FPS on an NVIDIA A100 and TensorRT.
17. PP-YOLO, PP-YOLOv2, and PP-YOLOE
PP-YOLO models have been growing parallel to the YOLO models we described.
However, we decided to group them in a single section because they began with YOLOv3
and had been gradually improving upon the previous PP-YOLO version. Nevertheless,
these models have been influential in the evolution of YOLO. PP-YOLO [89], similar to
YOLOv4 and YOLOv5, was based on YOLOv3. It was published in ArXiv in July 2020
by researchers from Baidu Inc. The authors used the PaddlePaddle [117] deep learning
platform, hence its PP name. Following the trend we have seen starting with YOLOv4,
PP-YOLO added ten existing tricks to improve the detector’s accuracy, keeping the speed
unchanged. According to the authors, this paper was not intended to introduce a novel
object detector but to show how to build a better detector step by step. Most of the tricks
PP-YOLO uses are different from the ones used in YOLOv4, and the ones that overlap use
a different implementation. The changes in PP-YOLO concerning YOLOv3 are:
1.
A ResNet50-vd backbone replacing the DarkNet-53 backbone with an architectureaug
mented with deformable convolutions [118] in the last stage and a distilled pre-trained
model, which has a higher classification accuracy on ImageNet. This architecture is
called ResNet5-vd-dcn.
2.
3.
4.
5.
6.
7.
8.
9.
A larger batch size to improve training stability; they went from 64 to 192, along with
an updated training schedule and learning rate.
Maintained moving averages for the trained parameters, used instead of the final
trained values.
DropBlock is applied only to the FPN.
An IoU loss is added in another branch along with the L1-loss for bounding-box
regression.
An IoU prediction branch is added to measure localization accuracy along with an
IoU-aware loss. During inference, YOLOv3 multiplies the classification probability
and objectiveness score to compute the final detection. PP-YOLO also multiplies the
predicted IoU to consider the localization accuracy.
Grid-sensitive approach similar to YOLOv4, it is used to improve the bounding-box
center prediction at the grid boundary.
Matrix NMS [119] is used, which can be run in parallel, making it faster than tradi
tional NMS.
CoordConv [120] is used for the 1×1 convolution of the FPN and on the first convolu
tion layer in the detection head. CoordConv allows the network to learn translational
invariance, improving the detection localization.
10. Spatial Pyramid Pooling is used only on the top feature map to increase the receptive
field of the backbone.
17.1. PP-YOLO Augmentations and Preprocessing
PP-YOLO used the following augmentations and preprocessing:
Mach. Learn. Knowl. Extr. 2023, 5
1704
1.
2.
3.
4.
5.
6.
Mixup Training [86] with a weight sampled from Beta(α,β) distribution, where α =
1.5 and β = 1.5.
Random Color Distortion.
RandomExpand.
Random Crop and Random Flip with a probability of 0.5.
RGB channel z-score normalization with a mean of [0.485,0.456,0.406] and a standard
deviation of [0.229,0.224,0.225].
Multiple image sizes evenly drawn from [320, 352, 384, 416, 448, 480, 512, 544,
576, 608].
Evaluated on the MS COCO dataset test-dev 2017, PP-YOLO achieved an AP of 45.9%
and AP50 of 65.2% at 73 FPS on an NVIDIA V100.
17.2. PP-YOLOv2
PP-YOLOv2[121] was published in ArXiv in April 2021 and added four refinements to
PP-YOLO that increased performance from 45.9% AP to 49.5% AP at 69 FPS on an NVIDIA
V100. The changes to PP-YOLOv2 concerning PP-YOLO are the following:
1.
Backbone changed from ResNet50 to ResNet101.
2.
3.
4.
5.
Path aggregation network (PAN) instead of FPN, similar to YOLOv4.
Mish activation function. Unlike YOLOv4andYOLOv5,theyonlyappliedtheMishac
tivation function in the detection neck to keep the backbone unchanged with the ReLU.
Larger input sizes help to increase performance on small objects. They expanded the
largest input size from 608 to 768 and reduced the batch size from 24 to 12 images per
GPU. The input sizes are evenly drawn from [320, 352, 384, 416, 448, 480, 512, 544, 576,
608, 640, 672, 704, 736, 768].
A modified IoU-aware branch. They modified the calculation of the IoU-aware loss
calculation using a soft label format instead of a soft weight format.
17.3. PP-YOLOE
PP-YOLOE [122] was published in ArXiv in March 2022. It added improvements
upon PP-YOLOv2, achieving a performance of 51.4% AP at 78.1 FPS on an NVIDIA
V100. Figure 18 shows a detailed architecture diagram. The main changes to PP-YOLOE
concerning PP-YOLOv2 are:
1.
Anchor-free. Following the time trends driven by the works of [91–94], PP-YOLOE
uses an anchor-free architecture.
2.
3.
4.
5.
New backbone and neck. Inspired by TreeNet [123], the authors modified the ar
chitecture of the backbone and neck with RepResBlocks, combining residual and
dense connections.
Task alignment learning (TAL). YOLOX was the first to bring up the problem of
task misalignment, where the classification confidence and the location accuracy
do not agree in all cases. To reduce this problem, PP-YOLOE implemented TAL as
proposed in TOOD [101], which includes a dynamic label assignment combined with
a task-alignment loss.
Efficient task-aligned head (ET-head). Different from YOLOX, where the classification
and locations heads were decoupled, PP-YOLOE instead used a single head based on
TOOD to improve speed and accuracy.
Varifocal (VFL) and distribution focal loss (DFL). VFL [102] weights loss of positive
samples using target score, giving higher weight to those with high IoU. This priori
tizes high-quality samples during training. Similarly, both use IoU-aware classification
score (IACS) as the target, allowing for joint learning of classification and localization
quality, leading to consistency between training and inference. On the other hand,
DFL[115] extends focal loss from discrete to continuous labels, enabling successful
optimization of improved representations that combine quality estimation and class
Mach. Learn. Knowl. Extr. 2023, 5
1705
prediction. This allows for an accurate depiction of flexible distribution in real data,
eliminating the risk of inconsistency.
Figure 18. PP-YOLOE architecture. The backbone is based on CSPRepResNet, the neck uses a path
aggregation network, and the head uses ES layers to form an efficient task-aligned head (ET-head).
Diagram based on [124].
Like previous YOLO versions, the authors generated multiple scaled models by
varying the width and depth of the backbone and neck. The models are called PP-YOLOE-s
(small), PP-YOLOE-m (medium), PP-YOLOE-l (large), and PP-YOLOE-x (extra-large).
18. YOLO-NAS
YOLO-NAS [125] was released in May 2023 by Deci, a company that develops
production-grade models and tools to build, optimize, and deploy deep learning mod
els. YOLO-NAS is designed to detect small objects, improve localization accuracy, and
enhance the performance-per-compute ratio, making it suitable for real-time edge-device
applications. In addition, its open-source architecture is available for research use.
The novelty of YOLO-NAS includes the following:
• Quantization-awaremodules[126],calledQSPandQCI,thatcombinere-parameterization
for 8-bit quantization to minimize the accuracy loss during post-training quantization.
• Automaticarchitecture design using AutoNAC, Deci’s proprietary NAS technology.
• Hybridquantizationmethodtoselectively quantize certain parts of a model to balance
latency and accuracy instead of standard quantization, where all the layers are affected.
• Apre-training regimen with automatically labeled data, self-distillation, and
large datasets.
TheAutoNACsystem,whichwasinstrumentalincreatingYOLO-NAS,isversatileand
can accommodate anytask, the specifics of the data, the environment for making inferences,
and the setting of performance goals. It assists users in identifying the most suitable
structure, which offers the perfect blend of precision and inference speed for their particular
Mach. Learn. Knowl. Extr. 2023, 5
1706
use. This technology considers the data and hardware and other elements involved in the
inference process, such as compilers and quantization. In addition, RepVGG blocks were
incorporated into the model architecture during the NAS process for compatibility with
post-training quantization (PTQ). They generated three architectures by varying the depth
and positions of the QSP and QCI blocks: YOLO-NASS, YOLO-NASM, and YOLO-NASL
(S, M, L for small, medium, and large, respectively). Figure 19 shows the model architecture
for YOLO-NASL.
Figure 19. YOLO-NAS architecture. The architecture is found automatically via a neural architecture
search (NAS) system called AutoNAC to balance latency vs. throughput. They generated three
architectures called YOLO-NASS (small), YOLO-NASM (medium), and YOLO-NASL (large), varying
the depth and positions of the QSP and QCI blocks. The figure shows the YOLO-NASL architecture.
The model was pre-trained on Objects365 [127], which contains two million images
and 365 categories, and then the COCO dataset was used to generate pseudo-labels. Finally,
the models are trained with the original 118k training images of the COCO dataset.
At this writing, three YOLO-NAS models have been released in FP32, FP16, and INT8
precisions, achieving an AP of 52.2% on MS COCO with 16-bit precision.
19. YOLOwith Transformers
With the rise of the transformer [128] taking over most deep learning tasks from
language and audio processing to vision, it was natural for transformers and YOLO to
be combined. One of the first attempts at using transformers for object detection was
“You Only Look at One Sequence” or YOLOS [129], which turned a pre-trained vision
transfomer (ViT) [130] from image classification to object detection, achieving 42.0 % AP on
MSCOCOdataset. The changes made to ViT were two: (1) replace one [CLS] token used
in classification with one hundred [DET] tokens for detection, and (2) replace the image
Mach. Learn. Knowl. Extr. 2023, 5
1707
classification loss in ViT with a bipartite matching loss similar to the end-to-end object
detection with transformers [131].
Many works have combined transformers with YOLO-related architectures tailored
to specific applications. For example, Zhang et al. [132], motivated by the robustness of
vision transformers to occlusions, perturbations, and domain shifts, proposed ViT-YOLO, a
hybrid architecture that combines CSP-Darknet [59] and multi-head self-attention (MHSA
Darknet) in the backbone, along with bidirectional feature pyramid networks (BiFPN) [7]
for the neck and multi-scale detection heads like YOLOv3. Their specific use case was for
object detection in drone images. Figure 20 shows the detailed architecture of ViT-YOLO.
Figure 20. ViT-YOLO architecture. The backbone MHSA-Darknet combines multi-head self-attention
blocks (MHSA-DarkBlock)withcross-stagepartial-connection blocks (CSPDark block). The neck uses
BiFPN to aggregate features from different backbone levels, and the head comprises five multi-scale
detection heads.
MSFT-YOLO[133] adds transformer-based modules to the backbone and detection
heads intending to detect defects on the steel surface. NRT-YOLO [134] (nested residual
transformer) tries to address the problem of tiny objects in remote sensing images. Adding
an extra prediction head, feature fusion layers, and a residual transformer module, NRT
YOLO improved YOLOv5l by5.4% in the DOTAdata set [135].
In remote sensing applications, YOLO-SD [136] tried to improve the detection accuracy
for small ships in synthetic-aperture radar (SAR) images. They started with YOLOX [91]
Mach.Learn.Knowl.Extr.2023,5 1708
coupledwithmulti-scaleconvolution(MSC)toimprovethedetectionatdifferentscales
andfeaturetransformermodulestocaptureglobal features. Theauthorsshowedthat
thesechangesimprovedtheaccuracyofYOLO-SDcomparedwithYOLOXintheHRSID
dataset[137].
AnotherinterestingattempttocombineYOLOwithdetectiontransformer(DETR)[131]
isthecaseofDEYO[138],comprisingtwostages:aYOLOv5-basedmodelfollowedbya
DETR-likemodel.Thefirststagegenerateshigh-qualityqueriesandanchorsthatinputto
thesecondstage.Theresultsshowafasterconvergencetimeandbetterperformancethan
DETR,achieving52.1%APintheCOCOdetectionbenchmark.
20.Discussion
Thispaperexamined16YOLOversions,rangingfromtheoriginalYOLOmodelto
themostrecentYOLO-NAS.Table4providesanoverviewoftheYOLOversionsdiscussed.
Fromthistable,wecanidentifyseveralkeypatterns:
• Anchors:TheoriginalYOLOmodelwasrelativelysimpleanddidnotemployan
chors,whilethestateoftheartreliedontwo-stagedetectorswithanchors.YOLOv2
incorporatedanchors,leadingtoimprovementsinbounding-boxpredictionaccuracy.
ThistrendpersistedforfiveyearsuntilYOLOXintroducedananchorlessapproach
thatachievedstate-of-the-artresults. Sincethen,subsequentYOLOversionshave
abandonedtheuseofanchors.
• Framework: Initially,YOLOwasdevelopedusingtheDarknet framework,with
subsequentversionsfollowingsuit.However,whenUltralyticsportedYOLOv3to
PyTorch,theremainingYOLOversionsweredevelopedusingPyTorch,leadingtoa
surgeinenhancements.AnotherdeeplearninglanguageutilizedisPaddlePaddle,an
open-sourceframeworkinitiallydevelopedbyBaidu.
• Backbone:ThebackbonearchitecturesofYOLOmodelshaveundergonesignificant
changesovertime.StartingwiththeDarknetarchitecture,whichcomprisedsimple
convolutionalandmaxpoolinglayers,latermodelsincorporatedcross-stagepartial
connections(CSP) inYOLOv4, reparameterizationinYOLOv6andYOLOv7,and
neuralarchitecturesearchinDAMO-YOLOandYOLO-NAS.
• Performance:WhiletheperformanceofYOLOmodelshasimprovedovertime,itis
worthnotingthattheyoftenprioritizebalancingspeedandaccuracyratherthansolely
focusingonaccuracy.ThistradeoffisessentialtotheYOLOframework,allowingfor
real-timeobjectdetectionacrossvariousapplications.
Table4.SummaryofYOLOarchitectures.Themetricshownisforthebestmodelreportedoneach
correspondingpaper.ForYOLOandYOLOv2,thedatasetusedwasVOC2007,whiletherestused
COCO2017.TheNAS-YOLOmodelreportedhas16-bitprecision.
Version Date Anchor Framework Backbone AP(%)
YOLO 2015 No Darknet Darknet24 63.4
YOLOv2 2016 Yes Darknet Darknet24 78.6
YOLOv3 2018 Yes Darknet Darknet53 33.0
YOLOv4 2020 Yes Darknet CSPDarknet53 43.5
YOLOv5 2020 Yes Pytorch YOLOv5CSPDarknet 55.8
PP-YOLO 2020 Yes PaddlePaddle ResNet50-vd 45.2
Scaled-YOLOv4 2021 Yes Pytorch CSPDarknet 56.0
PP-YOLOv2 2021 Yes PaddlePaddle ResNet101-vd 50.3
YOLOR 2021 Yes Pytorch CSPDarknet 55.4
YOLOX 2021 No Pytorch YOLOXCSPDarknet 51.2
PP-YOLOE 2022 No PaddlePaddle CSPRepResNet 54.7
YOLOv6 2022 No Pytorch EfficientRep 52.5
YOLOv7 2022 No Pytorch YOLOv7Backbone 56.8
DAMO-YOLO 2022 No Pytorch MAE-NAS 50.0
YOLOv8 2023 No Pytorch YOLOv8CSPDarknet 53.9
YOLO-NAS 2023 No Pytorch NAS 52.2
Mach. Learn. Knowl. Extr. 2023, 5
1709
Tradeoff between Speed and Accuracy
The YOLO family of object detection models has consistently focused on balancing
speed and accuracy, aiming to deliver real-time performance without sacrificing the quality
of detection results. As the YOLOframeworkhasevolvedthroughitsvariousiterations, this
tradeoff has been a recurring theme, with each version seeking to optimize these competing
objectives differently. In the original YOLO model, the primary focus was on achieving
high-speed object detection. The model utilized a single convolutional neural network
(CNN) to directly predict object locations and classes from the input image, enabling real
time processing. However, this emphasis on speed led to a compromise in accuracy, mainly
when dealing with small objects or objects with overlapping bounding boxes.
Subsequent YOLO versions introduced refinements and enhancements to address
these limitations while maintaining the framework’s real-time capabilities. For instance,
YOLOv2 (YOLO9000) introduced anchor boxes and passthrough layers to improve the
localization of objects, resulting in higher accuracy. In addition, YOLOv3 enhanced the
model’s performance by employing a multi-scale feature extraction architecture, allowing
for better object detection across various scales.
The tradeoff between speed and accuracy became more nuanced as the YOLO frame
work evolved. Models like YOLOv4 and YOLOv5 introduced innovations, such as new
network backbones, improved data augmentation techniques, and optimized training
strategies. These developments led to significant gains in accuracy without drastically
affecting the models’ real-time performance.
From YOLOv5, all official YOLO models have fine-tuned the tradeoff between speed
and accuracy, offering different model scales to suit specific applications and hardware
requirements. For instance, these versions often provide lightweight models optimized for
edge devices, trading accuracy for reduced computational complexity and faster processing
times. Figure 21 [139] shows the comparison of the different model scales from YOLOv5
to YOLOv8. The figure presents a comparative analysis of different versions of YOLO
models in terms of their complexity and performance. The left graph plots the number of
parameters (in millions) against the mean average precision (mAP) on the COCO validation
set, ranging from IOU thresholds of 50 to 95. It illustrates a clear trend where an increase in
the number of parameters enhances the model’s accuracy. Each model includes various
scales indicated by n (nano), s (small), m (medium), l (large), and x (extra-large).
Figure 21. Performance comparison of YOLO object detection models. The left plot illustrates the
relationship between model complexity (measured by the number of parameters) and detection
accuracy (COCO mAP50-95). The right plot shows the tradeoff between inference speed (latency on
A100 TensorRT FP16) and accuracy for the same models. Each model version is represented by a
distinct color, with markers indicating size variants from nano to extra. Plots taken from [139].
The right graph contrasts the inference latency on an NVIDIA A100 GPU, utilizing
TensorRT FP16, with the same mAP performance metric. Here, the tradeoff between the
inference speed and the detection accuracy is evident. Lower latency values, indicating
faster model inference, typically result in reduced accuracy. Conversely, models with higher
Mach. Learn. Knowl. Extr. 2023, 5
1710
latency tend to achieve better performance on the COCO mAP metric. This relationship is
pivotal for applications where real-time processing is crucial, and the choice of model is
influenced by the requirement to balance speed and accuracy.
21. The Future of YOLO
As the YOLO framework continues to evolve, we anticipate that the following trends
and possibilities will shape future developments:
Incorporation of Latest Techniques. Researchers and developers will continue to
refine the YOLO architecture by leveraging state-of-the-art methods in deep learning, data
augmentation, and training techniques. This ongoing innovation will likely improve the
model’s performance, robustness, and efficiency.
Benchmark Evolution. The current benchmark for evaluating object detection models,
COCO2017, mayeventually be replaced by a more advanced and challenging benchmark.
This mirrors the transition from the VOC 2007 benchmark used in the first two YOLO
versions, reflecting the need for more demanding benchmarks as models grow more
sophisticated and accurate.
Proliferation of YOLO Models and Applications. As the YOLO framework progresses,
we expect to witness an increase in the number of YOLO models released each year, along
with a corresponding expansion of applications. As the framework becomes more versatile
and powerful, it will likely be employed in more varied domains, from home appliance
devices to autonomous cars.
Expansion into New Domains. YOLO models have the potential to expand beyond
object detection and segmentation, exploring domains such as object tracking in videos
and 3D keypoint estimation. We anticipate YOLO models will transition into multi-modal
frameworks, incorporating both vision and language, video, and sound processing. As
these models evolve, they may serve as the foundation for innovative solutions catering to
a broader spectrum of computer vision and multimedia tasks.
Adaptability to Diverse Hardware. YOLO models will further span hardware plat
forms, from IoT devices to high-performance computing clusters. This adaptability will
enable deploying YOLO models in various contexts, depending on the application’s re
quirements and constraints. In addition, by tailoring the models to suit different hardware
specifications, YOLO can be made accessible and effective for more users and industries.
22. Conclusions
The YOLO framework has undergone significant development since its inception,
evolving into a sophisticated and efficient real-time object detection system. The recent
advancements in YOLO, including YOLOv8, YOLO-NAS, and YOLO with transformers,
have demonstrated new frontiers in object detection and shown that YOLO is still a vital
research area. A combination of architectural improvements, training techniques, and
dataset augmentation has driven the performance improvements of the YOLO family.
Moreover, the transfer learning approach has been a crucial factor in YOLO’s success,
enabling the framework to be adapted to various object detection tasks.
Despite the success ofYOLO,therearestillseveralchallenges that needtobeaddressed
in real-time object detection, such as occlusion, scale variation and pose estimation. One
of the significant areas where YOLO can be improved is in handling small objects, which
remain a challenge for most object detection systems. Additionally, YOLO’s efficiency
comes at the cost of reduced accuracy compared to some state-of-the-artsystems, suggesting
a need for a tradeoff between speed and accuracy.
In the future, we can expect further improvements to the YOLO framework, with
the integration of novel techniques such as attention mechanisms, contrastive learning,
and generative adversarial networks. The development of YOLO has shown that real
time object detection is a rapidly evolving field, and there is much scope for innovation
and improvement. The YOLO family has set an exciting benchmark, and we can expect
Mach. Learn. Knowl. Extr. 2023, 5
1711
other researchers to build on its success to develop more efficient and accurate object
detection systems.
Author Contributions: Conceptualization, J.T. and D.-M.C.-E.; methodology, J.T. and D.-M.C.-E.;
validation, J.T., D.-M.C.-E. and J.-A.R.-G.; formal analysis, J.T. and D.-M.C.-E.; investigation, J.T.,
D.-M.C.-E. and J.-A.R.-G.; resources, J.T., D.-M.C.-E. and J.-A.R.-G.; writing—original draft prepara
tion, J.T. and D.-M.C.-E.; writing—review and editing, J.-A.R.-G.; visualization, J.T. and D.-M.C.-E.;
project administration, J.T.; funding acquisition, J.T. All authors have read and agreed to the published
version of the manuscript.
Funding: This research was funded by Instituto Politecnico Nacional grant number SIP 20232290.
Data Availability Statement: Not applicable.
Acknowledgments: We thank the Instituto Politecnico Nacional through the Research and Postgrad
uate Secretary (SIP) project number 20232290 and the National Council of Humanities, Sciences, and
Technologies (CONAHCYT) for its support through the National Research System (SNI).
Conflicts of Interest: The authors declare no conflict of interest.
References
1.
2.
3.
4.
5.
6.
7.
8.
9.
Girshick, R.; Donahue, J.; Darrell, T.; Malik, J. Rich feature hierarchies for accurate object detection and semantic segmentation.
In Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition, Columbus, OH, USA, 23–28 June 2014;
pp. 580–587.
Girshick, R. Fast r-cnn. In Proceedings of the IEEE International Conference on Computer Vision, Santiago, Chile, 7–13 December
2015; pp. 1440–1448.
Ren, S.; He, K.; Girshick, R.; Sun, J. Faster r-cnn: Towards real-time object detection with region proposal networks. IEEE Trans.
Pattern Anal. Mach. Intell. 2016, 39, 1137–1149. [CrossRef] [PubMed]
Liu, W.; Anguelov, D.; Erhan, D.; Szegedy, C.; Reed, S.; Fu, C.-Y.; Berg, A.C. SSD: Single Shot Multibox Detector. In Proceedings
of the Computer Vision–ECCV 2016: 14th European Conference, Proceedings, Part I 14, Amsterdam, The Netherlands, 11–14
October 2016; pp. 21–37.
He, K.; Gkioxari, G.; Dollár, P.; Girshick, R. Mask R-CNN. In Proceedings of the IEEE International Conference on Computer
Vision, Venice, Italy, 22–29 October 2017; pp. 2961–2969.
Lin, T.Y.; Goyal, P.; Girshick, R.; He, K.; Dollár, P. Focal loss for dense object detection. In Proceedings of the IEEE International
Conference on Computer Vision, Venice, Italy, 22–29 October 2017; pp. 2980–2988.
Tan, M.; Pang, R.; Le, Q.V. Efficientdet: Scalable and efficient object detection. In Proceedings of the IEEE/CVF Conference on
Computer Vision and Pattern Recognition, Seattle, WA, USA, 13–19 June 2020; pp. 10781–10790.
Bhavya Sree, B.; Yashwanth Bharadwaj, V.; Neelima, N. An Inter-Comparative Survey on State-of-the-Art Detectors—R-CNN,
YOLO,andSSD. In Intelligent Manufacturing and Energy Sustainability: Proceedings of ICIMES 2020; Springer: Berlin/Heidelberg,
Germany, 2021; pp. 475–483.
Diwan, T.; Anirudh, G.; Tembhurne, J.V. Object detection using YOLO: Challenges, architectural successors, datasets and
applications. Multimed. Tools Appl. 2023, 82, 9243–9275. [CrossRef] [PubMed]
10. Hussain, M. YOLO-v1 to YOLO-v8, the Rise of YOLO and Its Complementary Nature toward Digital Manufacturing and
Industrial Defect Detection. Machines 2023, 11, 677. [CrossRef]
11. Lan, W.; Dang, J.; Wang, Y.; Wang, S. Pedestrian detection based on YOLO network model. In Proceedings of the 2018 IEEE
International Conference on Mechatronics and Automation (ICMA), Changchun, China, 5–8 August 2018; pp. 1547–1551.
12. Hsu,W.Y.;Lin, W.Y. Adaptivefusionofmulti-scale YOLOforpedestrian detection. IEEE Access 2021, 9, 110063–110073. [CrossRef]
13. Benjumea, A.; Teeti, I.; Cuzzolin, F.; Bradley, A. YOLO-Z: Improving small object detection in YOLOv5 for autonomous vehicles.
arXiv 2021, arXiv:2112.11798.
14. Dazlee, N.M.A.A.; Khalil, S.A.; Abdul-Rahman, S.; Mutalib, S. Object detection for autonomous vehicles with sensor-based
technology using yolo. Int. J. Intell. Syst. Appl. Eng. 2022, 10, 129–134. [CrossRef]
15. Liang, S.; Wu, H.; Zhen, L.; Hua, Q.; Garg, S.; Kaddoum, G.; Hassan, M.M.; Yu, K. Edge YOLO: Real-time intelligent object
detection system based on edge-cloud cooperation in autonomous vehicles. IEEE Trans. Intell. Transp. Syst. 2022, 23, 25345–25360.
[CrossRef]
16. Li, Q.; Ding, X.; Wang, X.; Chen, L.; Son, J.; Song, J.Y. Detection and identification of moving objects at busy traffic road based on
YOLOv4. J. Inst. Internet, Broadcast. Commun. 2021, 21, 141–148.
17. Shinde, S.; Kothari, A.; Gupta, V. YOLO-based human action recognition and localization. Procedia Comput. Sci. 2018, 133, 831–838.
[CrossRef]
18. Ashraf, A.H.; Imran, M.; Qahtani, A.M.; Alsufyani, A.; Almutiry, O.; Mahmood, A.; Attique, M.; Habib, M. Weapons detection for
security and video surveillance using CNN and YOLO-v5s. CMC-Comput. Mater. Contin. 2022, 70, 2761–2775.
Mach. Learn. Knowl. Extr. 2023, 5
1712
19. Zheng, Y.; Zhang, H. Video Analysis in Sports by Lightweight Object Detection Network under the Background of Sports
Industry Development. Comput. Intell. Neurosci. 2022, 2022, 3844770. [CrossRef] [PubMed]
20. Ma, H.; Celik, T.; Li, H. Fer-yolo: Detection and classification based on facial expressions. In Proceedings of the Image and
Graphics: 11th International Conference, ICIG 2021, Proceedings, Part I 11, Haikou, China, 6–8 August 2021; pp. 28–39.
21. Tian, Y.; Yang, G.; Wang, Z.; Wang, H.; Li, E.; Liang, Z. Apple detection during different growth stages in orchards using the
improved YOLO-V3 model. Comput. Electron. Agric. 2019, 157, 417–426. [CrossRef]
22. Wu,D.;Lv, S.; Jiang, M.; Song, H. Using channel pruning-based YOLO v4 deep learning algorithm for the real-time and accurate
detection of apple flowers in natural environments. Comput. Electron. Agric. 2020, 178, 105742. [CrossRef]
23. Lippi, M.; Bonucci, N.; Carpio, R.F.; Contarini, M.; Speranza, S.; Gasparri, A. A Yolo-based pest detection system for precision
agriculture. In Proceedings of the 2021 29th Mediterranean Conference on Control and Automation (MED), Puglia, Italy, 22–25
June 2021; pp. 342–347.
24. Wang,Y.; Zheng, J. Real-time face detection based on YOLO. In Proceedings of the 2018 1st IEEE International Conference on
knowledge innovation and Invention (ICKII), Jeju, Republic of Korea, 23–27 July 2018; pp. 221–224.
25. Chen, W.; Huang, H.; Peng, S.; Zhou, C.; Zhang, C. YOLO-face: A real-time face detector. Vis. Comput. 2021, 37, 805–813.
[CrossRef]
26. Al-Masni,M.A.;Al-Antari,M.A.; Park, J.M.; Gi, G.; Kim, T.Y.; Rivera, P.; Valarezo, E.; Choi, M.T.; Han, S.M.; Kim, T.S. Simultaneous
detection and classification of breast masses in digital mammograms via a deep learning YOLO-based CAD system. Comput.
Methods Programs Biomed. 2018, 157, 85–94. [CrossRef] [PubMed]
27. Nie, Y.; Sommella, P.; O’Nils, M.; Liguori, C.; Lundgren, J. Automatic detection of melanoma with yolo deep convolutional neural
networks. In Proceedings of the 2019 E-Health and Bioengineering Conference (EHB), Iasi, Romania, 21–23 November 2019;
pp. 1–4.
28. Ünver, H.M.; Ayan, E. Skin lesion segmentation in dermoscopic images with combination of YOLO and grabcut algorithm.
Diagnostics 2019, 9, 72. [CrossRef] [PubMed]
29. Tan, L.; Huangfu, T.; Wu, L.; Chen, W. Comparison of RetinaNet, SSD, and YOLO v3 for real-time pill identification. BMC Med.
Inform. Decis. Mak. 2021, 21, 1–11. [CrossRef]
30. Cheng,L.; Li, J.; Duan, P.; Wang, M. A small attentional YOLO model for landslide detection from satellite remote sensing images.
Landslides 2021, 18, 2751–2765. [CrossRef]
31. Pham,M.T.; Courtrai, L.; Friguet, C.; Lefèvre, S.; Baussard, A. YOLO-Fine: One-stage detector of small objects under various
backgrounds in remote sensing images. Remote Sens. 2020, 12, 2501. [CrossRef]
32. Qing, Y.; Liu, W.; Feng, L.; Gao, W. Improved Yolo network for free-angle remote sensing target detection. Remote Sens. 2021,
13, 2171. [CrossRef]
33. Zakria, Z.; Deng, J.; Kumar, R.; Khokhar, M.S.; Cai, J.; Kumar, J. Multiscale and direction target detecting in remote sensing
images via modified YOLO-v4. IEEE J. Sel. Top. Appl. Earth Obs. Remote Sens. 2022, 15, 1039–1048. [CrossRef]
34. Kumar, P.; Narasimha Swamy, S.; Kumar, P.; Purohit, G.; Raju, K.S. Real-Time, YOLO-Based Intelligent Surveillance and
Monitoring System Using Jetson TX2. In Data Analytics and Management: Proceedings of ICDAM; Springer: Berlin/Heidelberg,
Germany, 2021; pp. 461–471.
35. Bhambani, K.; Jain, T.; Sultanpure, K.A. Real-time face mask and social distancing violation detection system using Yolo. In
Proceedings of the 2020 IEEE Bangalore Humanitarian Technology Conference (B-HTC), Vijiyapur, India, 8–10 October 2020;
pp. 1–6.
36. Li, J.; Su, Z.; Geng, J.; Yin, Y. Real-time detection of steel strip surface defects based on improved yolo detection network.
IFAC-PapersOnLine 2018, 51, 76–81. [CrossRef]
37. Ukhwah,E.N.; Yuniarno, E.M.; Suprapto, Y.K. Asphalt pavement pothole detection using deep learning method based on YOLO
neural network. In Proceedings of the 2019 International Seminar on Intelligent Technology and Its Applications (ISITIA),
Surabaya, Indonesia, 28–29 August 2019; pp. 35–40.
38. Du,Y.; Pan, N.; Xu, Z.; Deng, F.; Shen, Y.; Kang, H. Pavement distress detection and classification based on YOLO network. Int. J.
Pavement Eng. 2021, 22, 1659–1672. [CrossRef]
39. Chen, R.C. Automatic License Plate Recognition via sliding-window darknet-YOLO deep learning. Image Vis. Comput. 2019,
87, 47–56.
40. Dewi,C.; Chen, R.C.; Jiang, X.; Yu, H. Deep convolutional neural network for enhancing traffic sign recognition developed on
Yolo V4. Multimed. Tools Appl. 2022, 81, 37821–37845. [CrossRef]
41. Roy, A.M.; Bhaduri, J.; Kumar, T.; Raj, K. WilDect-YOLO: An efficient and robust computer vision-based accurate object
localization model for automated endangered wildlife detection. Ecol. Inform. 2023, 75, 101919. [CrossRef]
42. Kulik, S.; Shtanko, A. Experiments with neural net object detection system YOLO on small training datasets for intelligent
robotics. In Advanced Technologies in Robotics and Intelligent Systems: Proceedings of ITR 2019; Springer: Berlin/Heidelberg, Germany,
2020; pp. 157–162.
43. DosReis, D.H.; Welfer, D.; De Souza Leite Cuadros, M.A.; Gamarra, D.F.T. Mobile robot navigation using an object recognition
software with RGBD images and the YOLO algorithm. Appl. Artif. Intell. 2019, 33, 1290–1305. [CrossRef]
Mach. Learn. Knowl. Extr. 2023, 5
1713
44. Sahin, O.; Ozer, S. Yolodrone: Improved Yolo architecture for object detection in drone images. In Proceedings of the 2021
44th International Conference on Telecommunications and Signal Processing (TSP), Brno, Czech Republic, 26–28 July 2021;
pp. 361–365.
45. Chen,C.; Zheng, Z.; Xu, T.; Guo, S.; Feng, S.; Yao, W.; Lan, Y. YOLO-Based UAV Technology: A Review of the Research and Its
Applications. Drones 2023, 7, 190. [CrossRef]
46. VOSviewer. VOSviewer: Visualizing Scientific Landscapes. 2023. Available online: https://www.vosviewer.com/ (accessed on
11 November 2023).
47. Everingham, M.; Van Gool, L.; Williams, C.K.; Winn, J.; Zisserman, A. The Pascal visual object classes (VOC) challenge. Int. J.
Comput. Vis. 2010, 88, 303–338. [CrossRef]
48. Lin, T.Y.; Maire, M.; Belongie, S.; Hays, J.; Perona, P.; Ramanan, D.; Dollár, P.; Zitnick, C.L. Microsoft coco: Common objects in
context. In Proceedings of the European Conference on Computer Vision, Zurich, Switzerland, 6–12 September 2014; pp. 740–755.
49. Redmon,J.; Divvala, S.; Girshick, R.; Farhadi, A. You only look once: Unified, real-time object detection. In Proceedings of the
IEEE Conference on Computer Vision and Pattern Recognition, Las Vegas, NV, USA, 27–30 June 2016; pp. 779–788.
50. Maas,A.L.; Hannun, A.Y.; Ng, A.Y. Rectifier nonlinearities improve neural network acoustic models. In Proceedings of the 30th
International Conference on Machine Learning, Atlanta, GA, USA, 16 June 2013; Volume 30, p. 3.
51. Szegedy, C.; Liu, W.; Jia, Y.; Sermanet, P.; Reed, S.; Anguelov, D.; Erhan, D.; Vanhoucke, V.; Rabinovich, A. Going deeper with
convolutions. In Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition, Boston, MA, USA, 7–12 June
2015; pp. 1–9.
52. Lin, M.; Chen, Q.; Yan, S. Network in network. arXiv 2013, arXiv:1312.4400.
53. Russakovsky, O.; Deng, J.; Su, H.; Krause, J.; Satheesh, S.; Ma, S.; Huang, Z.; Karpathy, A.; Khosla, A.; Bernstein, M.; et al.
Imagenet large-scale visual recognition challenge. Int. J. Comput. Vis. 2015, 115, 211–252. [CrossRef]
54. Redmon, J.; Farhadi, A. YOLO9000: Better, faster, stronger. In Proceedings of the IEEE Conference on Computer Vision and
Pattern Recognition, Honolulu, HI, USA, 21–26 July 2017; pp. 7263–7271.
55. Redmon,J.; Farhadi, A. Yolov3: An incremental improvement. arXiv 2018, arXiv:1804.02767.
56. Krasin, I.; Duerig, T.; Alldrin, N.; Ferrari, V.; Abu-El-Haija, S.; Kuznetsova, A.; Rom, H.; Uijlings, J.; Popov, S.; Veit, A.; et al.
Openimages: A Public Dataset for Large-Scale Multi-Label and Multi-Class Image Classification. 2017; Volume 2, p. 18. Available
online: https://github.com/openimages (accessed on 1 January 2023).
57. He,K.; Zhang, X.; Ren, S.; Sun, J. Spatial pyramid pooling in deep convolutional networks for visual recognition. IEEE Trans.
Pattern Anal. Mach. Intell. 2015, 37, 1904–1916. [CrossRef] [PubMed]
58. Lin, T.Y.; Dollár, P.; Girshick, R.; He, K.; Hariharan, B.; Belongie, S. Feature pyramid networks for object detection. In Proceedings
of the IEEE Conference on Computer Vision and Pattern Recognition, Honolulu, HI, USA, 21–26 July 2017; pp. 2117–2125.
59. Bochkovskiy, A.; Wang, C.Y.; Liao, H.Y.M. Yolov4: Optimal speed and accuracy of object detection. arXiv 2020, arXiv:2004.10934.
60. Chen,L.C.;Papandreou,G.; Kokkinos, I.; Murphy, K.; Yuille, A.L. Deeplab: Semanticimagesegmentationwithdeepconvolutional
nets, atrous convolution, and fully connected crfs. IEEE Trans. Pattern Anal. Mach. Intell. 2017, 40, 834–848. [CrossRef] [PubMed]
61. Liu, S.; Huang, D. Receptive field block net for accurate and fast object detection. In Proceedings of the European Conference on
Computer Vision (ECCV), Munich, Germany, 8–14 September 2018; pp. 385–400.
62. He, K.; Zhang, X.; Ren, S.; Sun, J. Deep residual learning for image recognition. In Proceedings of the IEEE Conference on
Computer Vision and Pattern Recognition, Las Vegas, NV, USA, 27–30 June 2016; pp. 770–778.
63. Hariharan, B.; Arbeláez, P.; Girshick, R.; Malik, J. Hypercolumns for object segmentation and fine-grained localization. In
Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition, Boston, MA, USA, 7–12 June 2015; pp. 447–456.
64. Zhao, Q.; Sheng, T.; Wang, Y.; Tang, Z.; Chen, Y.; Cai, L.; Ling, H. M2det: A single-shot object detector based on multi-level
feature pyramid network. In Proceedings of the AAAI Conference on Artificial Intelligence, Honolulu, HI, USA, 27 January–1
February 2019; Volume 33, pp. 9259–9266.
65. He,K.; Zhang, X.; Ren, S.; Sun, J. Delving deep into rectifiers: Surpassing human-level performance on imagenet classification. In
Proceedings of the IEEE International Conference on Computer Vision, Santiago, Chile, 7–13 December 2015; pp. 1026–1034.
66. Misra, D. Mish: A self-regularized non-monotonic neural activation function. arXiv 2019, arXiv:1908.08681.
67. Bodla, N.; Singh, B.; Chellappa, R.; Davis, L.S. Soft-NMS–improving object detection with one line of code. In Proceedings of the
IEEE International Conference on Computer Vision, Venice, Italy, 22–29 October 2017; pp. 5561–5569.
68. Xie, S.; Girshick, R.; Dollár, P.; Tu, Z.; He, K. Aggregated residual transformations for deep neural networks. In Proceedings of
the IEEE Conference on Computer Vision and Pattern Recognition, Honolulu, HI, USA, 21–26 July 2017; pp. 1492–1500.
69. Tan, M.; Le, Q. Efficientnet: Rethinking model scaling for convolutional neural networks. In Proceedings of the International
Conference on Machine Learning. PMLR, Long Beach, CA, USA, 9–15 June 2019; pp. 6105–6114.
70. Wang, C.Y.; Liao, H.Y.M.; Wu, Y.H.; Chen, P.Y.; Hsieh, J.W.; Yeh, I.H. CSPNet: A new backbone that can enhance learning
capability of CNN. In Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition Workshops, Seattle,
WA,USA,14–19 June 2020; pp. 390–391.
71. Liu, S.; Qi, L.; Qin, H.; Shi, J.; Jia, J. Path aggregation network for instance segmentation. In Proceedings of the IEEE Conference
on Computer Vision and Pattern Recognition, Salt Lake City, UT, USA, 18–23 June 2018; pp. 8759–8768.
72. Woo,S.; Park, J.; Lee, J.Y.; Kweon, I.S. Cbam: Convolutional block attention module. In Proceedings of the European Conference
on Computer Vision (ECCV), Munich, Germany, 8–14 September 2018; pp. 3–19.
Mach. Learn. Knowl. Extr. 2023, 5
1714
73. Ghiasi, G.; Lin, T.Y.; Le, Q.V. Dropblock: A regularization method for convolutional networks. In Proceedings of the 32nd
International Conference on Neural Information Processing Systems, NIPS’18, Red Hook, NY, USA, 3 December 2018; Curran
Associates Inc.: Red Hook, NY, USA, 2018; pp. 10750–10760.
74. Srivastava, N.; Hinton, G.; Krizhevsky, A.; Sutskever, I.; Salakhutdinov, R. Dropout: A simple way to prevent neural networks
from overfitting. J. Mach. Learn. Res. 2014, 15, 1929–1958.
75. Szegedy,C.; Vanhoucke, V.; Ioffe, S.; Shlens, J.; Wojna, Z. Rethinking the inception architecture for computer vision. In Proceedings
of the IEEE Conference on Computer Vision and Pattern Recognition, Las Vegas, NV, USA, 27–30 June 2016; pp. 2818–2826.
76. Islam, M.A.; Naha, S.; Rochan, M.; Bruce, N.; Wang, Y. Label refinement network for coarse-to-fine semantic segmentation. arXiv
2017, arXiv:1703.00551.
77. Zheng, Z.; Wang, P.; Liu, W.; Li, J.; Ye, R.; Ren, D. Distance-IoU loss: Faster and better learning for bounding box regres
sion. In Proceedings of the AAAI Conference on Artificial Intelligence, New York, NY, USA, 7–12 February 2020; Volume 34,
pp. 12993–13000.
78. Ioffe, S.; Szegedy, C. Batch normalization: Accelerating deep network training by reducing internal covariate shift. In Proceedings
of the International Conference on Machine Learning, PMLR, Lille, France, 7–9 July 2015; pp. 448–456.
79. Loshchilov, I.; Hutter, F. Sgdr: Stochastic gradient descent with warm restarts. arXiv 2016, arXiv:1608.03983.
80. Wang, S.; Zhao, J.; Ta, N.; Zhao, X.; Xiao, M.; Wei, H. A real-time deep learning forest fire monitoring algorithm based on an
improved Pruned+ KD model. J.-Real-Time Image Process. 2021, 18, 2319–2329. [CrossRef]
81. Jocher, G. YOLOv5 by Ultralytics. 2020. Available online: https://github.com/ultralytics/yolov5 (accessed on 28 February 2023).
82. Contributors, M. YOLOv5 by MMYOLO. 2023. Available online: https://github.com/open-mmlab/mmyolo/tree/main/
configs/yolov5 (accessed on 13 May 2023).
83. Ultralytics. Model Structure. 2023. Available online: https://docs.ultralytics.com/yolov5/tutorials/architecture_description/#1-model-structure (accessed on 14 May 2023).
84. Hendrycks, D.; Gimpel, K. Gaussian error linear units (gelus). arXiv 2016, arXiv:1606.08415.
85. Ghiasi, G.; Cui, Y.; Srinivas, A.; Qian, R.; Lin, T.Y.; Cubuk, E.D.; Le, Q.V.; Zoph, B. Simple copy-paste is a strong data augmentation
method for instance segmentation. In Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition,
Nashville, TN, USA, 20–25 June 2021; pp. 2918–2928.
86. Zhang, H.; Cisse, M.; Dauphin, Y.N.; Lopez-Paz, D. mixup: Beyond empirical risk minimization. arXiv 2017, arXiv:1710.09412.
87. Buslaev, A.; Iglovikov, V.I.; Khvedchenya, E.; Parinov, A.; Druzhinin, M.; Kalinin, A.A. Albumentations: Fast and Flexible Image
Augmentations. Information 2020, 11, 125. [CrossRef]
88. Wang,C.Y.; Bochkovskiy, A.; Liao, H.Y.M. Scaled-yolov4: Scaling cross-stage partial network. In Proceedings of the IEEE/CVF
Conference on Computer Vision and Pattern Recognition, Nashville, TN, USA, 20–25 June 2021; pp. 13029–13038.
89. Long, X.; Deng, K.; Wang, G.; Zhang, Y.; Dang, Q.; Gao, Y.; Shen, H.; Ren, J.; Han, S.; Ding, E.; et al. PP-YOLO: An effective and
efficient implementation of object detector. arXiv 2020, arXiv:2007.12099.
90. Wang, C.Y.; Yeh, I.H.; Liao, H.Y.M. You only learn one representation: Unified network for multiple tasks. arXiv 2021,
arXiv:2105.04206.
91. Ge,Z.; Liu, S.; Wang, F.; Li, Z.; Sun, J. Yolox: Exceeding Yolo series in 2021. arXiv 2021, arXiv:2107.08430.
92. Law,H.; Deng, J. Cornernet: Detecting objects as paired keypoints. In Proceedings of the European Conference on Computer
Vision (ECCV), Munich, Germany, 8–14 September 2018; pp. 734–750.
93. Duan, K.; Bai, S.; Xie, L.; Qi, H.; Huang, Q.; Tian, Q. Centernet: Keypoint triplets for object detection. In Proceedings of the
IEEE/CVF International Conference on Computer Vision, Seoul, Republic of Korea, 27 October–2 November 2019; pp. 6569–6578.
94. Tian, Z.; Shen, C.; Chen, H.; He, T. Fcos: Fully convolutional one-stage object detection. In Proceedings of the IEEE/CVF
International Conference on Computer Vision, Seoul, Republic of Korea, 27 October–2 November 2019; pp. 9627–9636.
95. Song, G.; Liu, Y.; Wang, X. Revisiting the sibling head in object detector. In Proceedings of the IEEE/CVF Conference on
Computer Vision and Pattern Recognition, Seattle, WA, USA, 13–19 June 2020; pp. 11563–11572.
96. Wu, Y.; Chen, Y.; Yuan, L.; Liu, Z.; Wang, L.; Li, H.; Fu, Y. Rethinking classification and localization for object detection. In
Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition, Seattle, WA, USA, 13–19 June 2020;
pp. 10186–10195.
97. Ge,Z.; Liu, S.; Li, Z.; Yoshie, O.; Sun, J. Ota: Optimal transport assignment for object detection. In Proceedings of the IEEE/CVF
Conference on Computer Vision and Pattern Recognition, Nashville, TN, USA, 20–25 June 2021; pp. 303–312.
98. Li, C.; Li, L.; Jiang, H.; Weng, K.; Geng, Y.; Li, L.; Ke, Z.; Li, Q.; Cheng, M.; Nie, W.; et al. Yolov6: A single-stage object detection
framework for industrial applications. arXiv 2022, arXiv:2209.02976.
99. Ding, X.; Zhang, X.; Ma, N.; Han, J.; Ding, G.; Sun, J. Repvgg: Making vgg-style convnets great again. In Proceedings of the
IEEE/CVF Conference on Computer Vision and Pattern Recognition, Nashville, TN, USA, 20–25 June 2021; pp. 13733–13742.
100. Contributors, M. YOLOv6 by MMYOLO. 2023. Available online: https://github.com/open-mmlab/mmyolo/tree/main/
configs/yolov6 (accessed on 13 May 2023).
101. Feng, C.; Zhong, Y.; Gao, Y.; Scott, M.R.; Huang, W. Tood: Task-aligned one-stage object detection. In Proceedings of the 2021
IEEE/CVF International Conference on Computer Vision (ICCV), Montreal, BC, Canada, 11–17 October 2021; pp. 3490–3499.
102. Zhang, H.; Wang, Y.; Dayoub, F.; Sunderhauf, N. Varifocalnet: An iou-aware dense object detector. In Proceedings of the
IEEE/CVF Conference on Computer Vision and Pattern Recognition, Nashville, TN, USA, 20–25 June 2021; pp. 8514–8523.
Mach. Learn. Knowl. Extr. 2023, 5
1715
103. Gevorgyan, Z. SIoU loss: More powerful learning for bounding box regression. arXiv 2022, arXiv:2205.12740.
104. Rezatofighi, H.; Tsoi, N.; Gwak, J.; Sadeghian, A.; Reid, I.; Savarese, S. Generalized intersection over union: A metric and a loss
for bounding box regression. In Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition, Seoul,
Republic of Korea, 27 October–2 November 2019; pp. 658–666.
105. Ding, X.; Chen, H.; Zhang, X.; Huang, K.; Han, J.; Ding, G. Re-parameterizing Your Optimizers rather than Architectures. arXiv
2022, arXiv:2205.15242.
106. Shu, C.; Liu, Y.; Gao, J.; Yan, Z.; Shen, C. Channel-wise knowledge distillation for dense prediction. In Proceedings of the
IEEE/CVF International Conference on Computer Vision, Montreal, BC, Canada, 10–17 October 2021; pp. 5311–5320.
107. Wang, C.Y.; Bochkovskiy, A.; Liao, H.Y.M. YOLOv7: Trainable bag-of-freebies sets new state-of-the-art for real-time object
detectors. arXiv 2022, arXiv:2207.02696.
108. Contributors, M. YOLOv7 by MMYOLO. 2023. Available online: https://github.com/open-mmlab/mmyolo/tree/main/
configs/yolov7 (accessed on 13 May 2023).
109. Wang, C.Y.; Liao, H.Y.M.; Yeh, I.H. Designing Network Design Strategies Through Gradient Path Analysis. arXiv 2022,
arXiv:2211.04800.
110. Huang, G.; Liu, Z.; Van Der Maaten, L.; Weinberger, K.Q. Densely connected convolutional networks. In Proceedings of the IEEE
Conference on Computer Vision and Pattern Recognition, Honolulu, HI, USA, 21–26 July 2017; pp. 4700–4708.
111. Xu, X.; Jiang, Y.; Chen, W.; Huang, Y.; Zhang, Y.; Sun, X. DAMO-YOLO: A Report on Real-Time Object Detection Design. arXiv
2022, arXiv:2211.15444.
112. Alibaba. TinyNAS. 2023. Available online: https://github.com/alibaba/lightweight-neural-architecture-search (accessed on 18
May2023).
113. Tan, Z.; Wang, J.; Sun, X.; Lin, M.; Li, H. Giraffedet: A heavy-neck paradigm for object detection. In Proceedings of the
International Conference on Learning Representations, Vienna, Austria, 4 May 2021.
114. Jocher, G.; Chaurasia, A.; Qiu, J. YOLO by Ultralytics. 2023. Available online: https://github.com/ultralytics/ultralytics
(accessed on 28 February 2023).
115. Li, X.; Wang, W.; Wu, L.; Chen, S.; Hu, X.; Li, J.; Tang, J.; Yang, J. Generalized focal loss: Learning qualified and distributed
bounding boxes for dense object detection. Adv. Neural Inf. Process. Syst. 2020, 33, 21002–21012.
116. Contributors, M. YOLOv8 by MMYOLO. 2023. Available online: https://github.com/open-mmlab/mmyolo/tree/main/
configs/yolov8 (accessed on 13 May 2023).
117. Ma, Y.; Yu, D.; Wu, T.; Wang, H. PaddlePaddle: An open-source deep learning platform from industrial practice. Front. Data
Domputing 2019, 1, 105–115.
118. Dai, J.; Qi, H.; Xiong, Y.; Li, Y.; Zhang, G.; Hu, H.; Wei, Y. Deformable convolutional networks. In Proceedings of the IEEE
International Conference on Computer Vision, Venice, Italy, 22–29 October 2017; pp. 764–773.
119. Wang, X.; Zhang, R.; Kong, T.; Li, L.; Shen, C. Solov2: Dynamic, faster and stronger. In Proceedings of the Thirty-Fourth
Conference on Neural Information Processing Systems (NeurIPS 2020), Vancouver, BC, Canada, 6–12 December 2020.
120. Liu, R.; Lehman, J.; Molino, P.; Petroski Such, F.; Frank, E.; Sergeev, A.; Yosinski, J. An intriguing failing of convolutional
neural networks and the coordconv solution. In Proceedings of the 32nd Conference on Neural Information Processing Systems
(NeurIPS 2018), Montréal, QC, Canada, 3–8 December 2018; pp. 9628–9639.
121. Huang, X.; Wang, X.; Lv, W.; Bai, X.; Long, X.; Deng, K.; Dang, Q.; Han, S.; Liu, Q.; Hu, X.; et al. PP-YOLOv2: A practical object
detector. arXiv 2021, arXiv:2104.10419.
122. Xu, S.; Wang, X.; Lv, W.; Chang, Q.; Cui, C.; Deng, K.; Wang, G.; Dang, Q.; Wei, S.; Du, Y.; et al. PP-YOLOE: An evolved version of
YOLO. arXiv 2022, arXiv:2203.16250.
123. Rao, L. TreeNet: A lightweight One-Shot Aggregation Convolutional Network. arXiv 2021, arXiv:2109.12342.
124. Contributors, M. PP-YOLOE by MMYOLO. 2023. Available online: https://github.com/open-mmlab/mmyolo/tree/main/
configs/ppyoloe (accessed on 13 May 2023).
125. Research Team. YOLO-NAS by Deci Achieves State-of-the-Art Performance on Object Detection Using Neural Architecture
Search. 2023. Available online: https://deci.ai/blog/yolo-nas-object-detection-foundation-model/ (accessed on 12 May 2023).
126. Chu, X.; Li, L.; Zhang, B. Make RepVGG Greater Again: A Quantization-aware Approach. arXiv 2022, arXiv:2212.01593.
127. Shao, S.; Li, Z.; Zhang, T.; Peng, C.; Yu, G.; Zhang, X.; Li, J.; Sun, J. Objects365: A large-scale, high-quality dataset for object
detection. In Proceedings of the IEEE/CVF International Conference on Computer Vision, Seoul, Republic of Korea, 27 October–2
November 2019; pp. 8430–8439.
128. Vaswani, A.; Shazeer, N.; Parmar, N.; Uszkoreit, J.; Jones, L.; Gomez, A.N.; Kaiser, Ł.; Polosukhin, I. Attention is all you need. In
Advances in Neural Information Processing Systems; MIT Press: Cambridge, MA, USA, 2017; pp. 5998–6008.
129. Fang, Y.; Liao, B.; Wang, X.; Fang, J.; Qi, J.; Wu, R.; Niu, J.; Liu, W. You only look at one sequence: Rethinking transformer in
vision through object detection. Adv. Neural Inf. Process. Syst. 2021, 34, 26183–26197.
130. Dosovitskiy, A.; Beyer, L.; Kolesnikov, A.; Weissenborn, D.; Zhai, X.; Unterthiner, T.; Dehghani, M.; Minderer, M.; Heigold, G.;
Gelly, S.; et al. An image is worth 16x16 words: Transformers for image recognition at scale. arXiv 2020, arXiv:2010.11929.
131. Carion, N.; Massa, F.; Synnaeve, G.; Usunier, N.; Kirillov, A.; Zagoruyko, S. End-to-end object detection with transformers. In
Proceedings of the European Conference on Computer Vision, Glasgow, UK, 23–28 August 2020; pp. 213–229.
Mach. Learn. Knowl. Extr. 2023, 5
1716
132. Zhang, Z.; Lu, X.; Cao, G.; Yang, Y.; Jiao, L.; Liu, F. ViT-YOLO: Transformer-based YOLO for object detection. In Proceedings of
the IEEE/CVF International Conference on Computer Vision, Montreal, BC, Canada, 11–17 October 2021; pp. 2799–2808.
133. Guo, Z.; Wang, C.; Yang, G.; Huang, Z.; Li, G. Msft-yolo: Improved yolov5 based on transformer for detecting defects of steel
surface. Sensors 2022, 22, 3467. [CrossRef]
134. Liu, Y.; He, G.; Wang, Z.; Li, W.; Huang, H. NRT-YOLO: Improved YOLOv5 based on nested residual transformer for tiny remote
sensing object detection. Sensors 2022, 22, 4953. [CrossRef]
135. Xia, G.S.; Bai, X.; Ding, J.; Zhu, Z.; Belongie, S.; Luo, J.; Datcu, M.; Pelillo, M.; Zhang, L. DOTA: A large-scale dataset for object
detection in aerial images. In Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition, Salt Lake City,
UT, USA, 18–22 June 2018; pp. 3974–3983.
136. Wang, S.; Gao, S.; Zhou, L.; Liu, R.; Zhang, H.; Liu, J.; Jia, Y.; Qian, J. YOLO-SD: Small Ship Detection in SAR Images by
Multi-Scale Convolution and Feature Transformer Module. Remote Sens. 2022, 14, 5268. [CrossRef]
137. Wei, S.; Zeng, X.; Qu, Q.; Wang, M.; Su, H.; Shi, J. HRSID: A high-resolution SAR images dataset for ship detection and instance
segmentation. IEEE Access 2020, 8, 120234–120254. [CrossRef]
138. Ouyang, H. DEYO: DETRwith YOLOforStep-by-Step Object Detection. arXiv 2022, arXiv:2211.06588.
139. Ultralytics. YOLOv8—Ultralytics YOLOv8 Documentation. 2023. Available online: https://docs.ultralytics.com/models/yolov8
/ (accessed on 11 November 2023).
Disclaimer/Publisher’s Note: The statements, opinions and data contained in all publications are solely those of the individual
author(s) and contributor(s) and not of MDPI and/or the editor(s). MDPI and/or the editor(s) disclaim responsibility for any injury to
people or property resulting from any ideas, methods, instructions or products referred to in the content.