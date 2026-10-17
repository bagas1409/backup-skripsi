OPEN ACCESS
TYPE Original Research
PUBLISHED 15 May 2023
DOI 10.3389/fpls.2023.1079366
A mobile-based system for
maize plant leaf disease
EDITED BY
Yuzhen Lu,
Michigan State University, United States
REVIEWED BY
Jiajun Xu,
Gachon University, Republic of Korea
Bimlesh Kumar,
Indian Institute of Technology Guwahati,
India
Anil Bhujel,
Ministry of Culture, Tourism and Civil
Aviation, Nepal
*CORRESPONDENCE
Muhammad Naveed Tahir
naveed@uaar.edu.pk
Muhammad Aqib
Aqib.qazi@uaar.edu.pk
SPECIALTY SECTION
This article was submitted to
Sustainable and Intelligent Phytoprotection,
a section of the journal
Frontiers in Plant Science
RECEIVED 25 October 2022
ACCEPTED 24 March 2023
PUBLISHED 15 May 2023
CITATION
Khan F, Zafar N, Tahir MN, Aqib M,
Waheed H and Haroon Z (2023) A mobile
based system for maize plant leaf
disease detection and classification
using deep learning.
Front. Plant Sci. 14:1079366.
doi: 10.3389/fpls.2023.1079366
COPYRIGHT
©2023 Khan, Zafar, Tahir, Aqib, Waheed and
Haroon. This is an open-access article
distributed under the terms of the Creative
Commons Attribution License (CC BY). The
use, distribution or reproduction in other
forums is permitted, provided the original
author(s) and the copyright owner(s) are
credited and that the original publication in
this journal is cited, in accordance with
accepted academic practice. No use,
distribution or reproduction is permitted
which does not comply with these terms.
detection and classification using
deep learning
Faiza Khan1,2, Noureen Zafar1,2, Muhammad Naveed Tahir2,3*,
Muhammad Aqib1,4*, Hamna Waheed1 and Zainab Haroon2,5
1University Institute of Information Technology, Pir Meh Ali Shah (PMAS)-Arid Agriculture University,
Rawalpindi, Pakistan, 2Data Driven Smart Decision Platform for Increased Agriculture Productivity, Pir
Meh Ali Shah (PMAS)-Arid Agriculture University, Rawalpindi, Pakistan, 3Department of Agronomy, Pir
Meh Ali Shah (PMAS)-Arid Agriculture University, Rawalpindi, Pakistan, 4National Center of Industrial
Biotechnology, Pir Meh Ali Shah (PMAS)-Arid Agriculture University, Rawalpindi, Pakistan, 5Department
of Land and Water Conservation Engineering, Faculty of Agricultural Engineering and Technology, Pir
Meh Ali Shah (PMAS)-Arid Agriculture University, Rawalpindi, Pakistan
Artificial Intelligence has been used for many applications such as medical,
communication, object detection, and object tracking. Maize crop, which is
the major crop in the world, is affected by several types of diseases which lower
its yield and affect the quality. This paper focuses on this issue and provides an
application for the detection and classification of diseases in maize crop using
deep learning models. In addition to this, the developed application also returns
the segmented images of affected leaves and thus enables us to track the disease
spots on each leaf. For this purpose, a dataset of three maize crop diseases
named Blight, Sugarcane Mosaic virus, and Leaf Spot is collected from the
University Research Farm Koont, PMAS-AAUR at different growth stages on
contrasting weather conditions. This data was used for training different
prediction models including YOLOv3-tiny, YOLOv4, YOLOv5s, YOLOv7s, and
YOLOv8n and the reported prediction accuracy was 69.40%, 97.50%, 88.23%,
93.30%, and 99.04% respectively. Results demonstrate that the prediction
accuracy of the YOLOv8n model is higher than the other applied models. This
model has shown excellent results while localizing the affected area of the leaf
accurately with a higher confidence score. YOLOv8n is the latest model used for
the detection of diseases as compared to the other approaches in the available
literature. Also, worked on sugarcane mosaic virus using deep learning models
has also been reported for the first time. Further, the models with high accuracy
have been embedded in a mobile application to provide a real-time disease
detection facility for end users within a few seconds.
KEYWORDS
deep learning, object detection, YOLO, transfer learning, disease classification
frontiersin.org
Frontiers in Plant Science
01
Khan et al.
10.3389/fpls.2023.1079366
GRAPHICAL ABSTRACT
1 Introduction
Agriculture is considered the backbone of Pakistan’s economy,
which is reliant on key crops such as wheat, rice, and maize (Shar
et al., 2021). It is considered the primary source of income for the
large population in Pakistan. One of the major causes of low yield is
diseases, which reduce the quality, quantity, and nutritional value of
fruits, vegetables, cereals, and legumes (Saleem et al., 2019;
Turkoglu et al., 2019). Nearly 32% of the losses are observed due
to diseases in cereal crops (Tudi et al., 2021). Maize is very essential
crop all around the world, especially in Pakistan. It is used for
different purposes i.e., poultry, cattle feed, food, beverages, etc. It
contributes 19% (Abdullah et al., 2021) to the Gross Domestic
Product (GDP) but unfortunately, it is prone to various diseases
which results in low production. Some major maize plant diseases
are Blight (Sun et al., 2020), Sugarcane Mosaic virus (Liu and Wang,
2021), and Leaf Spot (Krawczyk et al., 2021). The diseases look the
same in their emerging stages, hence difficult to differentiate from
the human eye and are also time-consuming. Therefore, Artificial
Intelligence (AI) technologies have become one of the current
research hotspots based on the above problem.
AI and deep learning-based methods are progressively being
utilized in agricultural research, because of their ability to
automatically learn the deep features from the image dataset, also
their accuracy and speed levels are higher than the traditional
algorithms (Chen et al., 2022). The most popular architecture of
deep learning is Convolutional Neural Network (CNN).
Specifically, it was intended to work with images, video
recognition, medical image analysis, object detection, flow
prediction (Miglani and Kumar, 2019), traffic control (Jindal and
Bedi, 2018), recommendation systems for healthcare (Shaikh et al.,
2022), anomaly detection (Garg et al., 2019), recognition of diseases
(Astani et al., 2022), weed detection (Khan et al., 2022), soil
monitoring (Chen S. et al., 2022), and pest identification (Cheng
et al., 2021; Huang et al., 2022), etc.
Nowadays, deep learning-based approaches, including Single Shot
Detector (SSD) (Sinan, 2020), You Only Look Once (YOLO)
(Ponnusamy et al., 2020; Ganesan and Chinnappan, 2022)models,
etc. are being used for leaf disease classification and recognition.
(Cheng et al., 2022) have proposed the improved YOLOv4 which is
based on lightweight CNN and was developed for weed detection and
seedling of maize crop. They have trained their model on the 1800
images. First, they decrease the number of parameters and increase the
speed of feature extraction, also MobileNetv3 is used for building the
lightweight feature extraction backbone network to replace
the CSPDarkNet53 network in +YOLOv4. Secondly, they applied the
transfer learning technique which is used for increasing the training
speed. The model gives the Mean Average Precision (mAP) of 89.98%,
the detection speed is 69.76 FPS, and the number of parameters was
8.17x106. However, the accuracy of the model could be improved also
the dataset should be larger. According to Shill and Rahman, 2021,the
detection results for plant disease by using the YOLOv3 and YOLOv4
were obtained as 53%, 52% mAP, and 55%, 56% F1-score, respectively.
The overall mAP of YOLOv4 is better than that of the YOLOv3 model,
however, the dataset was collected in the lab setting from PlantDoc
repository for model training.
Roy and Bhaduri (2021) have developed a real-time object
detection framework that is based on an improved YOLOv4
algorithm, and they applied this algorithm to detect apple plant
diseases. They acquired the dataset from Kaggle which consists of two
diseases of apple plant total of 600 images of each class. The proposed
model was modified to enhance accuracy and then it was verified in
the orchard with complex background. The algorithm obtained a
mAP value of 91.2% with 56.9 FPS and F1-score value is 95.9%. The
modified model compared with the original YOLOv4 model showed
that the developed model gives a 9.05% increase in mAP and 7.6% in
02
Frontiers in Plant Science
frontiersin.org
Khan et al.
10.3389/fpls.2023.1079366
F1-score. Gokulnath and Usha Devi (2020) have developed the
BOOSTED-DEPICT model that can do clustering of maize images
and many other techniques called k-means clustering, deeply
embedded clustering, and regularized deep clustering and has
achieved the accuracies of 97.73% and 91.25% on Plant Village
(PV) and PDD dataset, respectively. Nayar et al. (2022) have used
the YOLOv7 model for the detection of different plant diseases that
were collected from the Plant Village dataset and achieved 65% mAP,
the results reported in their study don’t meet the real-time detection
system. Chen et al. (2022) have proposed an improved YOLOv5
model to detect the rubber tree disease (powdery mildew) with 2375
images and the model obtained 70% mAP. The improved version of
YOLOv5 gained 5.4% higher results than the original YOLOv5.
While considering the above discussion, to the best of our
knowledge there are fewer attempts in the real-time classification,
detection, segmentation, and tracking system of maize crop
diseases, also the sugarcane mosaic virus disease is neglected in
the literature. The real-field dataset is not publicly available for
training and testing of the model, also image dataset used by
different authors in the literature is limited to a lab environment
which is not suitable for real-time scenarios. Therefore, we have
collected the dataset from the real field with a heterogenous
background, on contrasting weather, and different lighting
conditions. Moreover, we have developed smartphone application
for the quick assessment of maize crop. The primary contributions
of this paper are as follows:
• Areal disease data repository is built containing images of
maize crop, collected from the university research farm,
located in the Potohar region of Punjab province, Pakistan.
• This repository contains images of three distinct types of
diseases acquired in different weather conditions and
timestamp values. It also includes the data of sugarcane
mosaic virus disease which is not reported in any deep
learning-based detection work in the past.
• The state-of-the-art YOLOv8n model for maize plant
disease detection and classification is used.
• The best-trained model is integrated with the user-friendly
smartphone application for the real-time detection of maize
disease to facilitate the end user.
The rest of the paper is organized as follows. The background is
presented in section 2. Materials and methods are discussed in
section 3. Section 4 elaborates the proposed system’s results and
discussion, and section 5 concluded the discussion.
2 Background
YOLO is a SOTA algorithm that is used for real-time object
detection, classification, segmentation, and tracking (Jiang et al., 2021).
It is the most popular algorithm for speed and accuracy aspects. In our
research, maize foliar diseases are trained on YOLOv3-tiny (Malta et
al., 2021), YOLOv4, YOLOv5s, YOLOv7s, andYOLOv8nbecause they
are fast, accurate, and real-time object detection algorithms.
2.1 YOLOv3-tiny
The YOLOv3-tiny model is a simplified version of YOLOv3. It
has a smaller number of CNN layers and utilizes less memory. In
YOLOv3, Darknet-53 is used as a deeper architecture for feature
extraction. It means 53 CNN layers have been used, and each CNN
layer is followed by the Leaky Rectified Linear Unit (Relu) activation
function Equation (1), where x represents the input (Agarwal et al.,
2021). It is based on the ReLU activation function but with a small
slope or negative values rather than a flat slope. Also, it gives the
benefit of fast training. The hyperparameters used for training the
YOLOv3-tiny are given in Table 1. The architecture diagram of
YOLOv3-tiny is illustrated in Figure 1.
(
Leaky − ReLU(x) = max(ax,x) = 
ax,if x>0
x, if x ≥ 0
Where a ϵ [ 0,1]
TABLE 1 Hyperparameters configuration for YOLOv3-tiny, YOLOv4,
YOLOv5s, YOLOv7s, YOLOv8n.
Model
YOLOv3-tiny
YOLOv4
YOLOv5s
YOLOv7s
YOLOv8n
Hyperparameters
alpha
batch size
Subdivisions
Activation function
max batches
alpha
batch size
Subdivisions
Activation function
Optimizer
Momentum
alpha
batch size
Activation function
Weight decay
Alpha
Momentum
Optimizer
Weight decay
Activation function
Batch size
Warmup epochs
Warmup bias lr
(learning rate)
Value
0.001
64
16
Leaky-ReLU
6000
0.001
64
16
Mish
Stochastic Gradient Descent
0.937
0.01
64
Mish
0.005
0.01
0.937
Stochastic Gradient Descent
0.0005
leaky ReLU
64
3.0
0.1
(1)
alpha
momentum
weight decay
warmup epochs
warmup momentum
Warmup bias lr
Optimizer
Batch size
Activation function
03
0.01
0.937
0.0005
3.0
0.8
0.1
Adam
64
SiLU
Frontiers in Plant Science
frontiersin.org
2.2YOLOv4model
YOLOv4istheadvancementoftheYOLOv3model inthemAP
byasmuchas10%andframespersecond(FPS)by12%.Itisaone
stageobjectdetectionmodelcomposedofthreeparts; thefirstisthe
backbone, thesecondpart istheneck,andthelastpart isthehead.
Thebackbone ispre-trainedCNNonCenterandScalePrediction
(CSPDarknet53).TheCSPDarket53meansthatthemodelconsistsof
53CNNlayersandthisstageisresponsibleforextractingthefeatures
andcomputingfeaturemapsfromtheinputimages.Thenecksection
is responsible for concatenating thebackbonewiththehead.The
necksectioniscomposedofaspatialpyramidpooling(SPP)anda
PathAggregationNetwork(PAN).Theneckcollectsthefeaturemaps
fromthebackboneandfeedsthemintotheheadasinput.Inthelast
section,theheadisresponsibleforprocessingtheaggregatedfeatures
andpredictingtheboundingbox,predictionscoreclassifiesintothe
relevantclass.Inourstudy,theimagesizeisfixedto416×416,forthe
trainingandtestingprocess.ThearchitectureoftheYOLOv4model
is shown inFigure2. Thehyperparametersused inYOLOv4 for
trainingpurposesareshowninTable1.Theactivationfunctionused
herewasMishas showninEquation(2).Amongotheractivation
functions,Mishis thebest choicebecause it is smooth, andnon
monotonic (Mathayo andKang, 2022). It has various properties
whichmadeitpopularfromSwishandRectifiedLinearUnit(ReLU),
likeunboundedaboveandboundedbelowimprovesitsperformance
anditislowcost.
FIGURE2
ArchitecturediagramofYOLOv4.
FIGURE1
ArchitecturediagramofYOLOv3-tiny.
Khanetal. 10.3389/fpls.2023.1079366
FrontiersinPlantScience frontiersin.org 04
 f(x) = xtanh(softplus(x)) (2)
Wheresoftplus(x)=In(1+ex)
2.3YOLOv5smodel
TheYOLOv5smodel isdividedintothreemaincomponents:
backbone, head, anddetection. Thebackbone is responsible for
collecting the shape image featuresatdifferentneuronsand it is
basedonCNN.Tocreateimagefeatures,theYoloV5susestheCSP
Bottleneck. Layersmake up the head, which combines image
features to forward themto a predictionprocess. For feature
aggregation, theYolov5sadditionallyusesthePAN.Thedetection
procedureincludesphasesforboxandclasspredictioninaddition
tousing features fromthehead.Thearchitecturediagramof the
YOLOv5smodel is shown inFigure3and thehyperparameters
usedforthetrainingofYOLOv5smodelarepresentedinTable1.
TheYOLOv5shastwomappingsinthepost-processingandthe
operationprocesswasasdescribedinEquations3-6.
bx=2 s(tx)−0:5+cx (3)
by=2 s(ty)−0:5+cy (4)
bw=pw(2 (tw))2 (5)
bh=ph(2 (th))2 (6)
Where“b”isthesizeofthepredictionbox, includingbx,by,bw,
andbh representing the x-coordinate, y-coordinate, width, and
height of the center box, respectively. Cx andCy are the side
lengths of the cell, pw andph are thewidthandheight of the
priorbox.s isthesigactivationfunctionasshowninFigure4.
2.4YOLOv7s
Yolov7s is the smaller version of YOLOv7. It is the
advancement of theYOLOv6 intermsofmAP, detectionspeed,
andinferencing.TheEfficientLayerAggregationNetwork(ELAN)
isextendedintheYOLOv7,whichiscalledtheextendedELAN(E
ELAN).Different fundamentalsareusedtoenhance the learning
abilityofthenetworknamedasexpand,shuffle,andmergewithout
demolishing thegradientpath. It alsofocusedonsomemethods
such as trainable “bag-of-freebies” and optimizationmodules.
Various computational blocks are used to learnmore distinct
features.After beingdivided intogroups of size “s”, the feature
FIGURE3
ArchitecturediagramofYOLOv5s.
FIGURE4
Theschematicdiagramforcalculatingthesizeofthepredictionbox.
Khanetal. 10.3389/fpls.2023.1079366
FrontiersinPlantScience frontiersin.org 05
maps fromeachcomputational blockwill be concatenated. The
finalstepwillmergecardinalityusingashuffledgroupfeaturemap.
ThearchitecturediagramoftheYOLOv7isshowninFigure5and
thehyperparametersusedtotraintheYOLOv7modelinthisstudy
arereportedinTable1.
2.5YOLOv8n
TheYOLOv8nmodelisthenanoversionoftheYOLOv8family
becauseit issmallandfastwithhigherdetectionresults. Itcanbe
utilizedforobjectdetectionandclassificationinconjunctionwith
instancesegmentationandobjecttrackingwhichmakesitSOTA.It
wascreatedbyUltralytics,whoalsodevelopedtheYOLOv5model
whichisapowerfulmodel. Ithasseveralarchitecturalupdatesand
enhancements. It isananchor-freemodelwhichmeansthemodel
directlypredicts thecenterpointof anobject inanimagerather
thantheoffset fromaknownanchorboxillustratedinFigure6.
The architecture diagramof the YOLOv8 is depicted in
Figure 7. The SOTAYOLOv8 augments the images at each
epoch. The technique used ismosaic augmentation, which
stitches the four imagesandforces themodel to learnthenew
locations.ThechangeinthestructureofYOLOv8isthat thec3
moduleisreplacedwiththec2fmodule. Inmodulec2f,outputs
fromBottleneckareconcatenated,althoughtheoutputofthelast
Bottleneckwas used in the c3module. Also, the first 6×6
convolutional layers are replacedwith a 3×3 convolutional
blockintheBackbonemodule.Themainthoughtbehindusing
theYOLOv8modelwas theperformance andaccuracyboosts
during trainingand inferencing. It is better than theprevious
versions of YOLO in all aspects (mAP, latency, speed, FPS,
andsize).
3Materialsandmethods
The quality dataset is the fundamental requirement for
buildingthe foundationof thedeeplearningmodelbecause the
performanceof thedeeplearningmodel ishighlydependenton
thequality,quantity,andrelevancyofthedataset.So,thefirstand
crucialstepofanydeeplearningstartswithimageacquisition.The
completepipeline fromimage acquisition tomodel training to
FIGURE5
ArchitecturediagramoftheYOLOv7s.
FIGURE6
VisualizationofananchorboxinYOLOv8n.
Khanetal. 10.3389/fpls.2023.1079366
FrontiersinPlantScience frontiersin.org 06
smartphoneapplicationtesting is showninFigure8.Theother
activitiesofthesystemarelistedbelowandexplainedindetail in
thebelowsections.
1.ThemaizecropfoliardiseasesarecollectedfromUniversity
ResearchFarmKoont (URF), PirMehrAli ShahArid
AgricultureUniversity Rawalpindi (PMAS-AAUR), at
different growth stages (initial, middle, andmature),
different days of themonthwith contrastingweather
conditions.
2. After data collection, thenext step is toperformimage
preprocessing, includingresizing.
3. After that, data augmentationnamedflipping, rotating,
scaling,andcroppingwasapplied.
4. Indataannotation, imageswereannotated/labeledafterthe
experts’knowledge.
FIGURE7
ArchitecturediagramofYOLOv8n.
Khanetal. 10.3389/fpls.2023.1079366
FrontiersinPlantScience frontiersin.org 07
5. The annotateddatawas then fed into thedeep learning
model fortraining.
6. Finally, the aimof our studywas achievedbydetecting,
classifying,segmenting,andtrackingofmaizecropdiseases
i.e.,blight,leafspot,andsugarcanemosaicvirusinthereal
timeenvironment.
7. In the end, results are compared, a suitablemodelwas
selected forourproblemstatement andembedded into
themobile application for real-time detection and
tracking.
3.1Datasetcollectionanddescription
Adetaileddescriptionof howwe collected the dataset and
applieddifferentpreprocessingandaugmentationtechniques are
discussedbelow.
3.2Studyarea
This studywas conducted at URF, Koont PMAS-AAUR,
locatedinPunjabprovince,Pakistan(33.1166°N, 73.0111°E)as
showninFigure9.ThemaizevarietywasPakAfghoiandplanting
wasdoneinJune.Itwassownonaboutoneacrewithnoapplication
of pesticides and fungicides, the line-to-line distancewas 50cm
(about1.64ft).Theseedquantitywas40kgperacre,andonebagof
urea-based fertilizer and one bag of DiammoniumPhosphate
(DAP)wereappliedaftersowing.Thedrill sowingtechniquewas
usedforsowingtheseeds.
3.3Experimentalsetup
Alltheexperimentsfromtrainingtovalidationwereperformed
usingaGraphicsProcessingUnit (GPU:NvidiaRTXA4000)on
Ubuntu20.04LTSoperatingsystem.Thesoftwareandhardware
FIGURE8
ProposedpipelineofmaizediseasedetectionbyYOLOdetectors.
Khanetal. 10.3389/fpls.2023.1079366
FrontiersinPlantScience frontiersin.org 08
used formodel training/testing and their details are presented
inTable2.
3.4Imageacquisition
Ateverystageofobjectrecognitionresearch, fromthetraining
phase toassessing the effectiveness of recognitionalgorithms, a
suitabledataset isnecessary,becausetheperformanceof thedeep
learningmodels is highly dependent on the input images. To
achieve this, 2675 images ofmaize diseaseswere collected at
various development stages, in contrastingweather conditions,
andondifferent days of themonth (June toSeptember) under
thenaturallydiseased environment. The first twomonths after
sowing(June, andJuly) therewerenodiseasesmonitoredinthe
field, sothedatawas collectedafter July.The imagedatasetwas
capturedthroughthesmartphonecamera(SAMSUNGGalaxyA7)
bymaintainingaspecificheightof33cmfromtheleafsurface.The
specifications of the smartphone include 16megapixels (MP)
camera, 3GBRandomAccessMemory (RAM), anda 3.77MB
sizeofeachimage.Afterthecollectionofimages,theywereassessed
several timesbypathologists.Thedatasetsizeofmaizediseases is
illustratedinFigure10,wherethex-axisrepresentsthedateswhen
FIGURE9
StudyAreaofMaizeCrop.
FIGURE10
Datasetdescription.
TABLE2 Implementationdetails.
Features Details
Software Linux64-bitOS
Python3.8
OpenCV4.2
CUDA11.3
cuDNN8.2
Hardware NVIDIARTXA4000
RAM32GB
Khanetal. 10.3389/fpls.2023.1079366
FrontiersinPlantScience frontiersin.org 09
thedatawascollected, andthey-axisdepicts thetotalnumberof
images. Thebluehorizontal, orangevertical, andgreendiagonal
linesexhibitedblight,sugarcanemosaicvirus,andleafspotdisease,
respectively.Thesample imagescollectedfromthestudyareaare
showninFigure11.
3.5Imagepreprocessing
ImagePreprocessingreferstoactivitiesperformedonimagesat
themostfundamentallevel(Sarkietal.,2021).Deeplearning-based
modelstrainfasterif thesizeof theimagesaresmaller.Moreover,
thecollectedrawimagesvaryinsizeandmanyarchitecturesofdeep
learningmodelsrequirethesameimagesize(Sharmaetal.,2020).
Also, if there is adifferencebetweenthe training imageandthe
recognitionimage,theYOLOshowspoorperformance(Jeongetal.,
2018).Hence,forthatpurpose,thecapturedrawimagesareresized
to416×416dimensionswhichisanidealsizefortrainingtheYOLO
models.Whentheresizingisappliedonanimageitspixelvalues
reducedinsizeandtheunwantedregionof interest isdiscarded.
Thispreprocessingmethodisperformedbyusingapythonscript
withthehelpofOpenCvlibrarybeforetrainingtheobjectdetection
and trackingmodel (YOLO). Figure 12depicted the rawimage
A B C
FIGURE11
Maizediseases. (A)sugarcane_mosaicvirus, (B) leafspot, (C)blight.
FIGURE12
Imageresizing.
Khanetal. 10.3389/fpls.2023.1079366
FrontiersinPlantScience frontiersin.org 10
collectedfromtherealfieldwhichis899×1599dimensionsandthe
reduced/resizedimage.
3.6Dataaugmentation
Programmers canenhance thediversity and the size of the
dataset to train themodels using different data augmentation
techniques (Waheedet al., 2020). It is aknown fact thatCNN
canhandlevariationsinimagesandclassifyitemsevenwhenthey
arepositionedindistinctorientations (Buslaevetal., 2020;Umer
et al., 2022). To trainCNN, a considerable amount of data is
requiredsothat it candiscoverandretrievemore features.Deep
learningmodelsperformedbestwhenthesizeofthedatasetislarge
enough hence for this purpose, we enlarged our dataset by
artificially generating samples fromour collected dataset to
maximize the performance of deep learningmodels. Themost
widely used techniques for augmentationwere implemented in
thisresearchnamedrotating(70°and90°),flipping, scaling, and
croppingbyusingpythonscript.
3.7Imageannotation
Image annotation is the process of labeling the data into
different formatssuchas images,videos,ortextfilesformachines
tounderstandtheinputdata.Theannotated/labeleddataset isthe
mostimportantpartofsupervisedMachineLearning(ML)because
modelsaretrainedonthe inputdata,machinesprocess thatdata
andproduceaccurateresults.Differentannotationtoolshavebeen
usedinthe literaturesuchas labelImg, roboflow, yolo_mark, and
manyothers.ForYOLOv3,YOLOv4,YOLOv5,andYOLOv7data
annotation, we have used the yolo_mark tool, which is freely
availableat theAlexeyABrepository.Whereas roboflowwhichis
thecomputervisionplatformthatallowsusers tobuildcomputer
visionmodelsandimageannotations inconjunctionwithadata
augmentationfacilitywasused forYOLOv8nsegmentation. The
annotated images inboth formats, rectangle and segmentedare
depictedinFigures13A,Brespectively.
3.8Modelperformanceevaluators
Allthemodelsaretestedonimagesthatarenotpartofthetraining
processtochecktheireffectiveness.AlltheYOLOvariantsclassifythe
maizediseases very efficientlybutYOLOv8nperforms best of all.
Precision, mAP, Loss, andRecall have beenused as evaluation
indicators in this study for comparative analysis.Gai et al. (2021)
havealsousedtheseperformanceevaluationmethods forobtaining
andcomparing theperformanceof thedifferentmodels. Precision
refers tothemodel’sability torecognizeonly thepertinentobjects.
A B
FIGURE13
ImageannotationforYOLOmodel training, (A)YOLO_marktool,and(B)Roboflow.
Khanetal. 10.3389/fpls.2023.1079366
FrontiersinPlantScience frontiersin.org 11
Khan et al.
10.3389/fpls.2023.1079366
Where True Positive (TP) means our model correctly predicts the
correct diseased class and FalseNegative (FN)means themodel
correctly predicts the incorrect diseased class. The precision is
calculated as shown in Equation (7).
Precision = 
TP
TP + FN
(7)
Recall (4) refers to the model’s ability to recognize all the
pertinent objects. The model can recognize all the detected
bounding boxes from the validation set. The false positive (FP)
means that the model incorrectly predicts the correct class. The
recall is calculated as shown in Equation (8).
Recall =
TP
TP + FP
(8)
The mAP is the mean of the AP of each class. The mAP
encompasses the trade-off between precision and recall as well as
considering both FN and FP and it is calculated as shown in
Equation (10), where N is the number of classes.
N
mAP =1=No
i=1
AP
(9)
The loss function of the YOLO model is calculated by Equation
(10), where cls represents the classification loss, conf represents the
loss of confidence, and reg represents the regression loss. These
losses are calculated by the formulas given in Equations 11 to 13. Ji
et al. (2021) have used the loss formula for calculating the loss of the
YOLO model. The lower the loss value of the model the higher the
performance of the model. Where represents the predicted and true
probability, Ap and Ad exhibits the predicted and true bounding
box while the Ac, C, and I are the desired area, the overlapping area,
and the real area respectively.
LOSS = LOSScls + LOSSconf + LOSSreg
LOSScls = ok2
i=0li oc
c=1E(^pi(c), pi(c)) 
LOSSconf = Sk2
i=0Sm
j=0li,j E(^ci, Ci)
− lnoobjSk2
i=0Sm
j=0li,j E(1:Ii,j)E(^ci, Ci)
LOSSreg = 1 − IOU(Ap, Ad)+
AC −Ap −Ad +I
AC
3.9 Model training and
hyperparameters setup
(10)
(11)
(12)
(13)
In the original data set, 80%, and 20% of images from each
class were selected to form the training set, and validation set,
12
respectively. The image size was set to 416×416 for both training
and validation purposes. In the YOLOv8n model proposed in this
study, the training process uses the trained weight file of the
original YOLOv8n as the initialization parameter. Because
different network structures need to be trained in the
comparative experiment, and the number of iterations to
achieve the optimal detection performance, this study monitors
dynamically during training and saves theweight file of the
network at every epoch for the selection of the best train model
to prevent overfitting. The hyperparameters used for training the
YOLOv3-tiny, YOLOv4, YOLOv5s, YOLOv7s, and YOLOv8n are
depicted in Table 1.
The training process was visualized by configuring the weights and
biases (Wandb) in this study. It isusedtodynamically observe the
training status and performance of the model on different iterations.
The results of the YOLOv8n model are shown in Figure 14.During
model iteration, 0-50, the parameters of the model oscillated
significantly. When the number of iterations increased, the
performance of the model continuously improved. After the 50th
iteration, the model index became stable, and the value of Precision
reached 0.89 and progressively stabilized. Therefore, the model gets
stable and achieved 99.0% mAP between 50 to 99 iterations.
The performance of the YOLOv8n predictor for classifying,
detecting, segmenting, and tracking the blight, leafspot, and
sugarcane mosaic virus diseases in a maize dataset was calculated
by the loss function (Figure 14). It is used to evaluate the correlation
between the given data and the expected outcomes. The lower the
loss, the better the performance of the model, and vice versa. There
are two types of loss, one represents the training segmentation loss
and the other shows the validation segmentation loss of each object.
During each epoch, training loss was assessed, and after each epoch
testing loss was determined.
4 Results and discussion
This section presents the results generated by the applied
models, their comparison, and discussion.
4.1 Maize disease detection results
The results of the adopted model shown in Figure 15 were
performed to view the detected maize diseases i.e., blight, leaf spot,
and sugarcane mosaic virus after training the YOLOv8n model. The
unseen images were used for testing to check the feasibility of the
model, and the adopted YOLOv8n model predicted the diseases
correctly and efficiently with a higher confidence score among other
applied models in this study. The threshold value was set to 0.3,
which means if the confidence score is greater or equal to 30% then
the model categorizes it into the relevant class. It is shown that blight
Frontiers in Plant Science
frontiersin.org
Khan et al.
10.3389/fpls.2023.1079366
FIGURE 14
Visualization of model performance evaluators during training of the YOLOv8n model.
disease is detected by the model with a confidence score of 0.9%, leaf
spot disease by 1.0%, and sugarcane mosaic virus disease with 1.0%.
4.2 Performance evaluation of
detection models
Figure 16 shows the Precision curve of each class. Among all
three classes (blight, leafspot, sugarcane_mosaic) of the maize plant
diseases, the blight class achieves the highest 0.91% AP, and leafspot
gains the lowest 0.84% AP, whereas sugarcane_mosaic obtained the
0.89% AP which is in between blight and leafspot class.
Furthermore, it is seen that the precision values of all classes are
non significantly different from each other. After the 90th iteration,
the model gets stable and achieved above 80% results.
Figure 17 demonstrates the Recall curve of every single class.
The value obtained for blight, leafspot, and sugarcane_mosaic is
0.96%, 0.73%, and 0.94% respectively. It is clearly shown that the
blight and sugarcane_mosaic get stable after 50 epochs and obtain
the highest Recall value, while the performance of the leafspot class
fluctuates till 55 epochs and then gets stable, and achieves
satisfactory results.
1 https://www.tensorflow.org/lite/models/convert
2 https://www.oracle.com/java/
3 https://docs.oracle.com/javase/8/docs/
Frontiers in Plant Science
4.3 Mobile application
The best-trained model was embedded into a mobile application
for real-time detection, segmentation, and tracking which helps the
user to timely detect the diseases of the maize crop efficiently. First,
the model’sresultfile is converted to .tflite using the TensorFlow lite
converter library1 and deployed into the mobile application. The
mobile app was designed using java language2 on Android Studio
using the Android Java Development Kit3 (JDK). Finally, the diseases
are detected/recognized by the TensorFlow lite interpreter library4
The interface of the mobile application is illustrated in Figure 18 and
the full working of the application is depicted in Figure 19. There are
different modules/activities in the mobile application. The first
activity obtained the user login detail just for keeping the record of
the user for next time. For this purpose, a user must select a valid
username and a valid email address as well for account verification.
Based on the provided information, the user account will be created,
and this information could be updated anytime in the future. For
real-time disease detection of maize crop, the user can either select the
image from the mobile already saved in the mobile gallery, or he/she
could capture the new image in real-time from the field for disease
detection. Once the image is selected or captured, then it is forwarded
to the detection model. After that, the next activity is opened which
will show the detected disease of the maize crop.
4 https://www.tensorflow.org/lite/guide/inference
frontiersin.org
13
4.4Comparativeanalysisbetween
appliedmodels
The experimental results of the YOLOv3-tiny, YOLOv4,
YOLOv5s, YOLOv7s, andYOLOv8n are presented inTable 3
where 0, 1, and2 represent the blight, leafspot, and sugarcane
mosaic virus disease class respectively. It is reported that the
YOLOv5sachievedthebest resultsonblight (class0)with99.50%
AP, YOLOv8nperformedbest on leafspot (class 1) disease, and
sugarcane_mosaicdisease(class2)withAPof99.01%and99.07%
respectively. It is investigated that theYOLOv8nobtainedbetter
results thanotherappliedversionsofYOLOintermsof accuracy,
segmentation,andtracking.Moreover,thisstudyalsoinvestigatesthe
otherperformanceevaluatorsincludingprecision, recall,andloss. It
FIGURE15
Examplesofsuccessful recognitionofmaizeplantdiseasesusingtheYOLOv8nmodel.
Khanetal. 10.3389/fpls.2023.1079366
FrontiersinPlantScience frontiersin.org 14
isreportedinthetablethattheprecisionvalueoftheYOLOv7smodel
achieveshigherandthe lossvalue itachieves issmaller thanother
YOLOvariants.ThehigherrecallscorewasgainedbytheYOLOv4.
Theresults(mAP)ofeachmodelappliedinthisstudyaredepicted
inFigure20, theredcolorvertical lines,greencolorhorizontal lines,
yellowcolordiagonal lines, purplecolorhorizontal strips, andaqua
color diamondgrids showtheYOLOv3-tiny, YOLOv4, YOLOv5,
YOLOv7s, andYOLOv8n respectively. The comparative results
illustratethattheYOLOv8noutperformsall.
Theresultsof thecomparativeanalysisofdeeplearning-based
diseasedetectionalgorithmsofourstudywiththeotherstudiesare
expoundedinTable4.Theauthors(Austriaetal.,2022;Li etal.,
2022b)haveusedtheYOLOv5algorithmforthedetectionofapple
andcornrespectively,andtheyhaveachieved90%and97%results.
FIGURE17
RecallcurveoftheYOLOv8nmodel.
A B D C
FIGURE18
Screenshotsofthemaizediseasedetectionapplication(A) login/register(B) Imageselection(C)detectedleafspotdisease(D)detectedsugarcane
mosaicvirusdisease.
FIGURE16
AprecisioncurveoftheYOLOv8model.
Khanetal. 10.3389/fpls.2023.1079366
FrontiersinPlantScience frontiersin.org 15
Lietal.(2022b)usedYOLOv5s,whichisthesmallerversionofthe
YOLOmodel, andtheyobtained93.10%accuracy.LiuandWang
(2021)haveworkedonthediseasedetectionof the tomatoplant
andobtained92.39%mAP.Inthisstudy,wehaveappliedYOLOv3,
YOLOv4, YOLOv5, YOLOv7s, andYOLOv8n for thedetection,
segmentation,andtrackingofmaizeplantdiseasesinthereal-time
environment andachieved69.40%, 97.50%, 88.23%, 93.30%, and
99.04%resultsrespectively.
5Conclusion
Plantdiseaseshave longbeenamajor issue inagriculture.
Early disease detection through deep learningmodels can
overcomethespreadofdiseasesatanearlystageandminimize
the losses. Inthiswork,wellknowndeeplearning-basedobject
detectionmodelYOLOisusedfor thedetectionofdiseases in
maizecrop.FivedifferentversionsofYOLOincludingYOLOv3
tiny,YOLOv4,YOLOv5s,YOLOv7s,andYOLOv8nareusedand
thedatasetforthispurposeiscollectedfromarealenvironment
wherecropwasgrowninauniversityresearchfarmKoont.Data
collectedinthisworkcontainsthreedifferentdiseasesincluding
blight, leaf spot, and sugarcanemosaic virus, and is pre
processed using different data augmentation techniques.
Models trained for disease detectionwere able to accurately
detect, classify, segment, and track the diseases with a high
confidence score.Acomparisonbetweendifferent versions of
YOLOmodelsconfirms that theYOLOv8nmodel achieves the
bestdetectionresultsamongall andmeets therequirementsof
real-timedetection.ThemAPvalueachievedbythismodelwas
99.04%.Toincreasethesystem’susabilitythebest-trainedmodel
withhigherdetectionaccuracywas embedded intothemobile
FIGURE19
Flowchartofthesmartphoneapplication.
FIGURE20
Comparisonbetweenappliedmodelsinthisstudy.
TABLE3 AcomparativeanalysisbetweenYOLOversionsusedinthisstudy.
YoloVariants Ap mAP
(%)
Precision
(%)
Recall
(%)
Loss
(%)
0 1 2
YOLOv3-tiny 78.11 72.43 57.71 69.40 0.81 0.43 1.09
YOLOv4 98.71 97.11 96.57 97.50 0.89 0.98 2.13
YOLOv5s 99.40 91.70 73.60 88.23 0.95 0.89 0.01
YOLOv7s 98.70 92.20 89.00 93.30 1.0 0.95 0.005
YOLOv8n 99.05 99.01 99.07 99.04 0.88 87.66 0.78
Khanetal. 10.3389/fpls.2023.1079366
FrontiersinPlantScience frontiersin.org 16
Khan et al.
10.3389/fpls.2023.1079366
TABLE 4 Comparative analysis of real-time detection systems.
State
of-the
art
(Liu and
Wang,
2020)
Plant
Tomato
Algorithm
YOLOv3
Accuracy (%)
92.39
(Li et al.,
2022b)
(Li et al.,
2022b)
(Austria
et al.,
2022)
Our study
Vegetables
Apple
Corn
Maize
YOLOv5s
YOLOv5
YOLOv5
YOLOv3-tiny, YOLOv4,
YOLOV5s, YOLOv7s,
YOLOv8n
93.10
90.00
97.00
69.40%, 97.50%,
88.23%, 93.30%,
99.04%
application for real-time disease detection and classification. In
the future, these kinds of models could be integrated with the
Unmanned Ariel Vehicles (UAV) for real-time crop monitoring
and management.
Data availability statement
The raw data supporting the conclusions of this article will be
made available by the authors, without undue reservation.
Author contributions
All authors listed have made a substantial, direct, and intellectual
contribution to the work, and approved it for publication.
References
Abdullah, M., Shah, S. A., Saddozai, K. N., Khan, J., Fayaz, M., Ullah, I., et al. (2021).
Analysis of agricultural land price determinants and policy implications for controlling
residential and commercial encroachments: Facts from district swabi (Pakistan).
Sarhad J. Agric. 37, 14–23. doi: 10.17582/journal.sja/2021/37.1.14.23
Agarwal, M., Gupta, S., and Biswas, K. K. (2021). A new Conv2D model with modified
ReLUactivation function for identification of disease type and severity in cucumber plant.
Sustain. Computing: Inf. Syst. 30, 100473. doi: 10.1016/j.suscom.2020.100473
Astani, M., Hasheminejad, M., and Vaghefi, M. (2022). ). a diverse ensemble classifier for tomato
disease recognition. Comput. Electron. Agric. 198, 107054. doi: 10.1016/j.compag.2022.107054
Austria,Y.C.,Mirabueno,M.C.A.,Lopez,D.J.D.,Cuaresma,D.J.L.,Macalisang,J.R.,
and Casuat, C. D. (2022). “EZM-AI: A Yolov5 machine vision inference approach of the
philippine corn leaf diseases detection system,” in 2022 IEEE International Conference on
Artificial Intelligence in Engineering and Technology (IICAIET). (IEEE), 1–6.
Buslaev, A., Iglovikov, V. I., Khvedchenya, E., Parinov, A., Druzhinin, M., and
Kalinin, A. A. (2020). Albumentations: fast and flexible image augmentations.
Information 11 (2), 125. doi: 10.3390/info11020125
Chen, S., Arrouays, D., Leatitia Mulder, V., Poggio, L., and Minasny, B. (2022).
Digital mapping of GlobalSoilMap soil properties at a broad scale: A review. Geoderma
409, 115567. doi: 10.1016/j.geoderma.2021.115567
Funding
The authors are thankful to the Higher Education Commission
(HEC), Islamabad, Pakistan to provide financial support for this
study under the project No 332 Pilot Project for Data Driven Smart
Decision Platform for Increased Agriculture Productivity.
Acknowledgments
The authors gratefully acknowledge PSDP funded project No
321 “Establishment of National Center of Industrial Biotechnology
for Pilot Manufacturing of Bioproducts Using Synthetic Biology
and Metabolic Engineering Technologies at PMAS-Arid
Agriculture University Rawalpindi”, executed through Higher
Education Commission Islamabad, Pakistan.
Conflict of interest
The authors declare that the research was conducted in the
absence of any commercial or financial relationships that could be
construed as a potential conflict of interest.
Publisher’s note
All claims expressed in this article are solely those of the authors
and do not necessarily represent those of their affiliated
organizations, or those of the publisher, the editors and the
reviewers. Any product that may be evaluated in this article, or
claim that may be made by its manufacturer, is not guaranteed or
endorsed by the publisher.
Chen, Z., Wu, R., Lin, Y., Li, C., Chen, S., Yuan, Z., et al. (2022). Plant disease
recognition model based on improved YOLOv5. Agronomy 12 (2), 365. doi: 10.3390/
.agronomy12020365
Cheng, L., Shi-Quan, S., and Wei, G. (2022). Maize seedling and weed detection based
on MobileNetv3-YOLOv4 Vol. 5679– (Institute of Electrical and Electronics Engineers
(IEEE), 5683. doi: 10.1109/cac53003.2021.9727999
Cheng, L., Shi-Quan, S., and Wei, G. (2021). “Maize seedling and weed detection
based on MobileNetv3-YOLOv4,” in 2021 China Automation Congress (CAC). (China:
IEEE), 5679–5683.
Gai, R., Chen, N., and Yuan, H. (2021). A detection algorithm for cherry fruits based
on the improved YOLO-v4model. Neural Computing Appl. 1–12. doi: 10.1007/S00521
021-06029-Z
Ganesan, G., and Chinnappan, J. (2022). Hybridization of ResNet with YOLO
classifier for automated paddy leaf disease recognition: An optimized model. J. Field
Robotics 39 (7), 1085–1109. doi: 10.1002/rob.22089
Garg, S., Kaur, K., Kumar, N., and Rodrigues, , J. J. P. C. (2019). Hybrid deep
learning-based anomaly detection scheme for suspicious flow detection in SDN: A
social multimedia perspective. IEEE Trans. Multimedia 21, 566–578. doi: 10.1109/
TMM.2019.2893549
17
Frontiers in Plant Science
frontiersin.org
Khan et al.
10.3389/fpls.2023.1079366
Gokulnath, B. V., and Usha Devi, G. (2020). Boosted-DEPICT: an effective maize
disease categorization framework using deep clustering. Neural Computing Appl. 1–10.
doi: 10.1007/s00521-020-05303-w
Huang, M. L., Chuang, T. C., and Liao, Y. C. (2022). Application of transfer learning
and image augmentation technology for tomato pest identification. Sustain.
Computing: Inf. Syst. 33, 100646. doi: 10.1016/j.suscom.2021.100646
Jeong, H. J., Park, K. S., and Ha, Y. G. (2018). “Image preprocessing for efficient
training of YOLO deep learning networks,” in 2018 IEEE International Conference on
Big Data and Smart Computing (BigComp). (IEEE), 635–637.
Jiang, P., Ergu,D., Liu, F.,Cai,Y., andMa, B. (2022). “A review of yolo algorithm
developments,” in Procedia computer science,vol.199.(Beijing,China:Elsevier),1066–1073.
Jiang, P., Ergu, D., Liu, F., Cai, Y., and Ma, B. (2021). “A review of yolo algorithm
developments,” in Procedia computer science (Elsevier B.V), 1066–1073. doi: 10.1016/
j.procs.2022.01.135
Ji, W., Gao, X., Xu, B., Pan, Y., Zhang, Z., and Zhao, D. (2021). Apple target
recognition method in complex environment based on improved YOLOv4. J. Food
Process Eng. 44 (11), e13866.
Jindal, V., and Bedi, P. (2018). High performance adaptive traffic control for efficient
response in vehicular ad hoc networks. Int. J. Comput. Sci. Eng. 16 (4), 390–400.
Khan, F., Zafar, N., Tahir, M. N., Aqib, M., Saleem, S., and Haroon, Z. (2022). Deep
learning- based approach for weed detection in potato crops. Environ. Sci. Proc. 23 (1),
6. doi: 10.3390/environsciproc2022023006
Krawczyk, K., Foryś, J., Nakonieczny, M., Tarnawska, M. , and Bereś, P. K. (2021).
Transmission of pantoea ananatis, the causal agent of leaf spot disease of maize (Zea
mays), by western corn rootworm (Diabrotica virgifera virgifera LeConte). Crop Prot.
141, 105431. doi: 10.1016/j.cropro.2020.105431
Li, J., Qiao, Y., Liu, S., Zhang, J., Yang, Z. , and Wang, M. (2022a). An improved
YOLOv5- based vegetable disease detection method. Comput. Electron. Agric. 202,
107345. doi: 10.1016/j.compag.2022.107345
Li, J., Zhu, X., Jia, R., Liu, B., and Yu, C. (2022b). “Apple-YOLO: A novel mobile
terminal detector based on YOLOv5 for early apple leaf diseases,” in In 2022 IEEE 46th
Annual Computers, Software, and Applications Conference (COMPSAC). (IEEE), 352–361.
Liu, J., and Wang, X. (2020). Tomato diseases and pests detection based on improved
yolo V3 convolutional neural network. Front. Plant Sci. 11, 898.
Liu, J., and Wang, X. (2021). Plant diseases and pests detection based on deep
learning: a review, Vol. 17. 22. doi: 10.1186/s13007-021-00722-9
Malta, A., Mendes, M., and Farinha, T. (2021). Augmented reality maintenance
assistant using yolov5. Appl. Sci. 11 (11), 4758. doi: 10.3390/app11114758
Mathayo, P. B., and Kang, D.-K. (2022). Beta and alpha regularizers of mish
activation functions for machine learning applications in deep neural networks. Int.
J. Internet Broadcasting Communication 14, 136–141. doi: 10.7236/IJIBC.2022.14.1.136
Miglani, A., and Kumar, N. (2019). Deep learning models for traffic flow prediction in
autonomous vehicles: A review, solutions, andchallenges. Vehicular Commun. 20, 100184.
Nayar, P., Chhibber, S., and Dubey, A. K. (2022). “An efficient algorithm for plant
disease detection using deep convolutional networks,” in 2022 14th International
Conference on Computational Intelligence and Communication Networks (CICN).
(Lima, Peru: IEEE), 156– 160. doi: 10.1109/CICN56167.2022.10008235
Ponnusamy, V., Coumaran, A., Shunmugam, A. S., Rajaram, K., and Senthilvelavan,
S. (2020). “Smart glass: real-time leaf disease detection using YOLO transfer learning,”
in 2020 International Conference on Communication and Signal Processing (ICCSP).
(Shanghai, China: IEEE), 1150– 1154. doi: 10.1109/ICCSP48568.2020.9182146
Roy, A. M., and Bhaduri, J. (2021). A deep learning enabled multi-class plant disease
detection model based on computer vision. Ai 2 (3), 413–428. doi: 10.3390/ai2030026
Saleem, M. H., Potgieter, J., and Arif, K. M. (2019). Plant disease detection and
classification by deep learning. Plants 8 (11), 468. doi: 10.3390/plants8110468
Sarki, R., Ahmed, K., Wang, H., Zhang, Y., Ma, J., and Wang, K. (2021). Image
preprocessing in classification and identification of diabetic eye diseases. Data Sci. Eng.
6, 455–471. doi: 10.1007/s41019-021-00167-z
Shaikh, S. G., Suresh Kumar, B., and Narang, G. (2022). Recommender system for
health care analysis using machine learning technique: A review. Theor. Issues
Ergonomics Sci. 23 (5), 613–642.
Shar, R. U., Jiskani, A. M., and Qi, Y. (2021). Economic outlook offood crops in pakistan: An
empirical study. Economics Manage. Sustainability 6, 72–86. doi: 10.14254/jems.2021.6-2.6
Sharma, P., Hans, P., and Gupta, S. C. (2020). “Classification of plant leaf diseases
using machine learning and image preprocessing techniques,” in 2020 10th
international conference on cloud computing, data science & engineering
(Confluence). (IEEE), 480–484. doi: 10.1109/Confluence47617.2020.9057889
Shill,A.,andRahman,M.A.(2021).“Plant disease detection based on YOLOv3 and YOLOv4,”
in 2021 International Conference on Automation, Control and Mechatronics for Industry 4.0
(ACMI). (Rajshahi, Bangladesh: IEEE), 1–6. doi: 10.1109/ACMI53878.2021.9528179
Sinan, UĞ .U.Z. (2020). Automatic olive peacock spot disease recognition system
development by using single shot detector. Sakarya Univ. J. Comput. Inf. Sci. 3 (3), 158
168. doi: 10.35377/saucis.03.03.755269
Sun, J., Yang, Y., He, X., and Wu, X. (2020). Northern maize leaf blight detection
under complex field environment based on deep learning. IEEE Access 8, 33679–33688.
doi: 10.1109/ACCESS.2020.2973658
Tudi, M., Daniel Ruan, H., Wang, L., Lyu, J., Sadler, R., Connell, D., et al. (2021).
Agriculture development, pesticide application and its impact on the environment. Int.
J. Environ. Res. Public Health 18 (3), 1112.
Turkoglu, M., Hanbay, D., and Sengur, A. (2019). Multi-model LSTM-based
convolutional neural networks for detection of apple diseases and pests. J. Ambient
Intell. Humanized Computing,1–11. doi: 10.1007/s12652-019-01591-w
Umer, S., Rout, R. K., Pero, C., and Nappi, M. (2022). Facial expression recognition
with trade-offs between data augmentation and deep learning features. J. Ambient
Intell. Humanized Computing 13, 721–735. doi: 10.1007/s12652-020-02845-8
Waheed, A., Goyal, M., Gupta, D., Khanna, A., Hassanien, A. E., and Pandey, H. M.
(2020). An optimized dense convolutional neural network model for disease
recognition and classification in corn leaf. Comput. Electron. Agric. 175, 105456.
doi: 10.1016/j.compag.2020.105456
18
Frontiers in Plant Science
frontiersin.org