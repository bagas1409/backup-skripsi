ORIGINAL RESEARCH
published: 27 October 2017
doi: 10.3389/fpls.2017.01852
Deep Learning for Image-Based
Cassava Disease Detection
Amanda Ramcharan1, Kelsee Baranowski1, Peter McCloskey2, Babuali Ahmed3,
James Legg3 and David P. Hughes1,4,5*
1 Department of Entomology, College of Agricultural Sciences, Penn State University, State College, PA, United States,
2 Department of Computer Science, Pittsburgh University, Pittsburgh, PA, United States, 3 International Institute of Tropical
Agriculture, Dar el Salaam, Tanzania, 4 Department of Biology, Eberly College of Sciences, Penn State University, State
College, PA, United States, 5 Center for Infectious Disease Dynamics, Huck Institutes of Life Sciences, Penn State University,
State College, PA, United States
Edited by:
Ashraf El-kereamy,
University of California Division of
Agriculture and Natural Resources,
United States
Reviewed by:
Jan Frederik Kreuze,
International Potato Center, Peru
Zhong Yin,
University of Shanghai for Science and
Technology, China
*Correspondence:
David P. Hughes
dph14@psu.edu
Specialty section:
This article was submitted to
Technical Advances in Plant Science,
a section of the journal
Frontiers in Plant Science
Received: 07 July 2017
Accepted: 11 October 2017
Published: 27 October 2017
Citation:
Ramcharan A, Baranowski K,
McCloskey P, Ahmed B, Legg J and
Hughes DP (2017) Deep Learning for
Image-Based Cassava Disease
Detection. Front. Plant Sci. 8:1852.
doi: 10.3389/fpls.2017.01852
Cassava is the third largest source of carbohydrates for human food in the world but is
vulnerable to virus diseases, which threaten to destabilize food security in sub-Saharan
Africa. Novel methods of cassava disease detection are needed to support improved
control which will prevent this crisis. Image recognition offers both a cost effective and
scalable technology for disease detection. New deep learning models offer an avenue
for this technology to be easily deployed on mobile devices. Using a dataset of cassava
disease images taken in the field in Tanzania, we applied transfer learning to train a deep
convolutional neural network to identify three diseases and two types of pest damage
(or lack thereof). The best trained model accuracies were 98% for brown leaf spot (BLS),
96% for red mite damage (RMD), 95% for green mite damage (GMD), 98% for cassava
brown streak disease (CBSD), and 96% for cassava mosaic disease (CMD). The best
model achieved an overall accuracy of 93% for data not used in the training process.
Our results show that the transfer learning approach for image recognition of field images
offers a fast, affordable, and easily deployable strategy for digital plant disease detection.
Keywords: cassava disease detection, deep learning, convolutional neural networks, transfer learning, mobile
epidemiology, Inception v3 model
1. INTRODUCTION
Cassava (Manihot esculenta Crantz) is the most widely grown root crop in the world and a major
source of calories for roughly two out of every five Africans (Nweke et al., 2002). In 2014, over 145
million tonnes of cassava were harvested on 17 million hectares of land on the African continent
(FAOSTAT, 2017). It is considered a food security crop for smallholder farms, especially in low
income, food-deficit areas (Bellotti et al., 1999) as it provides sufficient yields in low soil fertility
conditions and where there are irregular rainfall patterns (De Bruijn and Fresco, 1989).
Smallholder farmers, representing 85% of the world’s farms, face numerous risks to their
agricultural production such as climate change, market shocks, and pest and disease outbreaks
(Nagayet, 2005). Cassava, an exotic species introduced to Africa from South America in the
16th century, initially had few pest and disease constraints on the continent. In the 1970s two
arthropod pests, the cassava mealybug [Phenacoccus manihoti(Matt.-Ferr.)] and the cassava green
mite [Mononychellus tanajoa (Bond.)] were accidentally introduced from the neotropics (Legg,
1999), becoming the most economically threatening pests. Cassava virus diseases, in particular
cassava mosaic disease (CMD) and cassava brown streak disease (CBSD), have a longer history on
Frontiers in Plant Science | www.frontiersin.org
1
October 2017 | Volume 8 | Article 1852
Ramcharan et al.
Image-Based Cassava Disease Detection
the continent. Mosaic disease was the first to be recorded in
Tanzania towards the end of the 19th century (Warburg, 1894).
In East Africa, the outbreak of a severe form of the virus in the
1990s, termed East African cassava mosaic virus (EACMV-UG or
UgV), coupled with the sensitivity of local cultivars, resulted in a
threat to food security in the region as farmers’ only solution was
to abandon cultivation (Thresh et al., 1994). Thresh et al. (1997)
estimated annual yield losses to CMD at 15–24%, or 21.8–34.8
million tons, at 1994 production levels. CBSD was reported in the
1930s (Storey, 1936). With limited success in controlling CMD
and CBSD, the two diseases have become the largest constraints
to cassava production and food security in sub-Saharan Africa
resulting in losses of over US$1 billion every year (Legg et al.,
2006).
In order to manage the detection and spread of cassava
diseases, early identification in the field is a crucial first step.
Traditional disease identification approaches rely on the support
of agricultural extension organizations, but these approaches are
limited in countries with low logistical and human infrastructure
capacity, and are expensive to scale up. In such areas, internet
penetration, smartphone and unmanned aerial vehicle (UAV)
technologies offer new tools for in-field plant disease detection
based on automated image recognition that can aid in early
detection at a large scale. Previous research has demonstrated
automated image recognition of crop diseases in wheat (Gibson
et al., 2015; Siricharoen et al., 2016), apples (Dubey and
Jalal, 2014) and on datasets of healthy and diseased plants
(Mohanty et al., 2016); this technology was also demonstrated
on UAVs (Puig et al., 2015). Cassava disease detection based
on automated image recognition through feature extraction has
shown promisingresults (Aduwoet al., 2010; Abdullakasim et al.,
2011; Mwebaze and Owomugisha, 2016) but extracting features
is computationally intensive and requires expert knowledge
for robust performance. In order to capitalize on smartphone
technology, models must be fast and adapted to limited
processing power. Transfer learning, where a model that hasbeen
trained on a large image dataset is retrained for new classes,
offers a shortcut to training deep learning models because of
lower computational requirements. This would have a distinct
advantage for field settings. Here we investigated the potential for
adapting an already trained deep learning convolutional neural
network model to detect incidence of cassava disease using an in
field dataset of 2,756 images comprising 3 cassava diseases and 2
types of pest damage (or lack thereof).
2. METHODS
2.1. The Cassava Image Datasets
The cassava leaf images were taken with a commonly available
Sony Cybershot 20.2-megapixel digital camera in experimental
fields belonging to the International Institute of Tropical
Agriculture (IITA), outside of Bagamoyo, Tanzania. The entire
cassava leaf roughly centered in the frame was photographed
to build the first dataset (Figure S6). Over a four-week period,
11,670 images were taken. Images of cassava diseases were
taken using several cassava genotypes and stages of maturity
(as described in Table S1) in order to provide the full range of
symptoms for each given disease to the deep learning model.
Each of the diseases or types of pest damage was distinctive and
the variation of symptomexpression between varieties was minor
in comparison to the contrasts between diseases.
Images were then screened for co-infections to limit the
number of images with multiple diseases. This dataset, called the
“original cassava dataset,” comprised 2,756 images. These photos
were then manually cropped into individual leaflets to build the
second dataset. This dataset, called the “leaflet cassava dataset,”
comprised 15,000 images of cassava leaflets (2,500 images per
class). Figure 1 shows an example frombothdatasets: (a) original
cassava dataset and (b) leaflet cassava dataset and Figures S1
S5 show examples from both datasets for each cassava disease.
Both datasets were tested to shed light on model performance
with images of full leaves but fewer images versus cropped
leaves with more images. The underlying assumption was that
the cropped leaf images (leaflet cassava dataset) would improve
model performance to correctly identify a disease as the dataset
was larger. Additionally, we suspected the end users trying to
get a diagnosis for a disease would focus in on leaflets showing
symptoms. Both datasets comprised six class labels assigned
manually based on in-field diagnoses by cassava disease experts
from IITA. For all datasets, we used the images as is, in color,
and with varied backgrounds from the field in order to assess the
model performance (Figure S6).
The six class labels for the datasets included three disease
classes, two mite damage classes, and one healthy class, defined
as a lack of disease or mite damage on the leaf. The disease
classes and the number of images in the original dataset were:
cassava brown streak disease (CBSD) (398 images), cassava
mosaic disease (CMD) (388 images), brown leaf spot (BLS) (386
images), and the mite damage classes were: cassava green mite
damage (GMD) (309 images) and red mite damage (RMD) (415
images). Figure 2 illustrates examples of the class labels for the
original cassava dataset. Within these classes, several cassava
varieties were photographed at different stages of plant maturity
(Table S1).
The five disease and pest class symptoms are as follows:
CBSD is a result of infection with cassava brown streak
ipomoviruses (CBSIs) (family Potyviridae, genus Ipomovirus).
There are two species associated with the disease, Cassava
brown streak virus (CBSV) and Ugandan cassava brown streak
virus (UCBSV) (Mbanzibwa et al., 2011). Both cause the same
symptoms. These two virus species are vectored by whiteflies
[Bemisia tabaci (Genn.)] in a semi-persistent manner. When
infected, cassava leaves show a mottled yellowing pattern
typically beginning from the secondary veins and progressing
to tertiary veins as the infection gets more severe (Nichols,
1950). This yellowish chlorosis spreads along the veins until
severely infected leaves are mostly yellow. Disease symptoms
can vary by variety, age of the plant and weather conditions.
Tolerant varieties and plants at a young age may be infected but
asymptomatic. The two viruses may also cause brown streaks on
stems of infected plants and brown necrotic rotting in tuberous
roots which may render them inedible.
CMD is a result of infection with cassava mosaic
begomoviruses (CMBs) (family Geminiviridae, genus
Frontiers in Plant Science | www.frontiersin.org
2
October 2017 | Volume 8 | Article 1852
Ramcharan et al.
Image-Based Cassava Disease Detection
FIGURE 1 | Healthy cassava leaf images from the (A) original cassava dataset and (B) leaflet dataset.
FIGURE 2 | Examples of images with in field backgrounds from 6 classes in the original cassava dataset. (A) Cassava brown streak disease (CBSD), (B) Healthy,
(C) Green mite damage (GMD), (D) Cassava mosaic disease (CMD), (E) Brown leaf spot (BLS), (F) Red mite damage (RMD).
Begomovirus). There are many species and recombinant strains
associated with this group of viruses, although the common
form in coastal East Africa, where sampling was undertaken, is
East African cassava mosaic virus (EACMV) (Ndunguru et al.,
2005). The virus species are vectored by B. tabaci (Genn.) in a
persistent manner, contrasting to CBSIs. Newly-infected plants
begin to express symptoms from the top, while plants infected
through the planted cutting often show symptoms in all leaves.
SymptomsofCMDareatypicalmosaicinwhichthereisamixof
yellow/pale green chlorotic patches and green areas (Figure 2D).
Unlike CBSD, leaves are usually distorted in shape, and where
symptoms are severe the size of leaves is greatly reduced and
the plant is stunted. Stunting and the damage to chlorophyll
resulting from chlorosis results in the quantitative declines in
yield.
BLS is caused by the fungus [Mycosphaerella henningsii
(Sivan)]. This fungus is distributed worldwide and typically does
not cause great yield loss. The disease manifests in brown circular
leaf spots with some varieties expressing a chlorotic halo around
the spots. Severe infections can cause the leaves to turn yellow or
brown. The circular spots can become dry and crack depending
on the environment.
GMD is caused by cassava green mites [Mononychellus
tanajoa (Bondar)]. This is a widespread pest in Africa and
South America. The mites cause small white, scratch-like spots
where they have fed and in severe cases cause the whole leaf
to be covered with the pattern. There is such a reduction in
chlorophyll that the leaf may become stunted in a manner similar
to that caused by CMD. Depending on variety and environment,
infestations can lead to losses in tuberous root yield of up to 30%
(Skovgård et al., 1993).
RMD is caused by cassava red spider mite [Oligonychus
biharensis (Hirst)], which is widely distributed across Africa.
Their feeding damage also causes small scratch-like spotting on
the leaf but typically produces a distinct reddish-brown rust
color. Feeding is also focused around the main vein but severe
infestations can cause the whole leaf to turn orange.
Although GMD and RMD are not strictly diseases, for
simplicity, we refer to all of the conditions affecting the plants
that were considered in this study as diseases.
Frontiers in Plant Science | www.frontiersin.org
3
October 2017 | Volume 8 | Article 1852
Ramcharan et al.
Image-Based Cassava Disease Detection
FIGURE 3 | Overall accuracy for transfer learning using three machine learning methods.
2.2. Approach
We evaluated the applicability of transfer learning from a deep
convolutional neural network (CNN) model for the cassava
image datasets. Convolutional neural networks are leading the
state-of-the-art in computer vision tasks (Szegedy et al., 2016).
As opposed to traditional approaches of training classifiers with
hand-designed feature extraction, CNNs learn feature hierarchy
from pixels to classifier and train layers jointly. Due to model
complexity CNNs can take weeks to fully train, therefore transfer
learning is applied to shortcut model training by taking a
fully-trained model for a set of classes and retraining the
existing weights for new classes. Our approach retrains the
existing weights of the Inception v3 CNN model to classify
the cassava image datasets by exploiting the large amount of
visual knowledge already learned from the Imagenet database.
Previous research has shown that transfer learning is effective
for diverse applications (Karpathy et al., 2014; Yosinski et al.,
2014; Mohanty et al., 2016) and has much lower computational
requirements than learning from scratch, which is a benefit to
mobile applications.
We analyzed the performance of training the final layer of
the CNN model Inception v3 for the new cassava image datasets
with three different architectures: the original inception softmax
layer, support vector machines (SVM), and knn nearest neighbor
(knn). The latest version of the Inception model (based on
GoogLeNet), Inception v3, was implemented in TensorFlow.
Inception v3 was trained from the ImageNet Large Visual
Recognition Challenge using the data from 2012, where it was
tasked with classifying images into 1,000 classes. The top-5 error
rate of Inception v3 was 3.46%, compared to 6.67 and 4.9%
for Inception (GoogLeNet) and BN-Inception v2 respectively
(Szegedy et al., 2016). Inception v3 is 42 layers deep, but the
computation cost is only 2.5 times higher than that of GoogLeNet
with 22 layers. Beginning with the GoogLeNet model, Inception
v3 implementsseveral design principles to scale up convolutional
networks to improve performance with a modest increase in
computational cost; a significant benefit for scenarios where
memory or computational power is limited, such as mobile or
drone devices. Beginning with the GoogLeNet model, Inception
v3 factorizes the traditional 7 × 7 convolution into three 3 ×
3 convolutions, grid reduction is applied to three traditional
inception modules to reduce to a 17 × 17 grid with 768 filters,
then grid reduction is applied again to five factorized inception
modules to reduce to a 8 ×8×1,280grid. Adetailed description
of the design principles implemented to create the Inception
v3 model from GoogleNet is provided in Szegedy et al. (2016).
The model parameters implemented in this study included the
number of training steps (4,000), the learning rate (0.035), train
batch size (100), test batch size (−1; the entire test set), and the
validation batch size (100).
2.3. Performance Measurements
In order to perform a robust validation and test for any inherent
bias in the datasets, experiments were run for a range of training
testing data splits. During model training, 10% of the dataset
was used to validate training steps, thus 90% of the dataset was
split into different training and testing dataset configurations.
The training-test splits were as follows: 80-10 (80% of dataset
for training, 10% for testing respectively), 60-30 (60% of dataset
for training, 30% for testing respectively), 50-40, (50% of dataset
for training, 40% for testing respectively), 40-50 (40% of dataset
for training, 50% for testing respectively), and 20-70 (20% of
dataset for training, 70% for testing respectively). For each
experiment the overall accuracy is reported as the number of
samples in all classes that were similar.
3. RESULTS
For the original cassava dataset (i.e., the whole leaf), the overall
accuracy in classifying a leaf as belonging to the correct category
Frontiers in Plant Science | www.frontiersin.org
4
October 2017 | Volume 8 | Article 1852
Ramcharan et al.
Image-Based Cassava Disease Detection
FIGURE 4 | Confusion matrices for 10% test dataset using original (A,C,E) and leaflet (B,D,F) datasets.
ranged from 73% (20-70 split, knn) to 91% (80-10 split, SVM).
For the leaflet cassava dataset, the overall accuracy was higher
and ranged from 80% (20-70 split, knn) to 93.0% (80-10 split,
SVM). Figure 3 and Table S2 show the overall accuracies for
the datasets. It is worth noting that all models performed much
better than randomly guessing, even with varied backgrounds in
the images such as human hands, feet, soil or other distracting
features. Results also suggest the models were not overfit to the
datasets as the training-testing data split had a small effect on
the overall accuracies reported. Support vector machines and the
final Inception v3 softmax layer, both based on achieving linear
separability of the classes, had similar model performances for
both original and leaflet datasets, while the knn model (k = 3),
based on similarity with its neighbors, performed the worst.
Frontiers in Plant Science | www.frontiersin.org
5
October 2017 | Volume 8 | Article 1852
Ramcharan et al.
Image-Based Cassava Disease Detection
The confusion matrices from the original and leaflet dataset,
allow a more detailed analysis by shedding light on how model
performance changes with different disease representations in
the images. On the confusion matrix plots for the 80-10 (80%
of dataset for training, 10% for testing respectively) data split,
the rows correspond to the true class, and the columns show the
predicted class. The diagonal cells show the proportion (range
0–1) of the examples the trained network correctly predicts the
classes of observations i.e., this is the proportion of the examples
in which the true and predicted classes match. The off-diagonal
cells show where the network made mistakes.
Using the confusion matrix for the Inception v3 model in
Figure 4A (original dataset, 80-10 data split) as an example,
the Healthy class diagonal cell shows the Inception v3 model
correctly identified 0.78 or 78% of the healthy leaf images. This
increased to 0.83 for the leaflet data set (Figure 4B). Overall the
target and output class predictions were within a similar range for
all classes and datasets suggesting the overall reported accuracy
is indicative of the model performance for all cassava disease
classes.
Comparing proportions in the off-diagonal cells for the
models showed that the proportion of correct predictions
between the leaflet dataset and the original dataset did not
significantly increase even though the leaflet dataset was almost
7 times as large as the original dataset. Looking into specific
diseases in Figure 4, the highest reported prediction accuracy
was 0.98 for CBSD (Inception v3-leaflet) and BLS (SVM- leaflet)
diseases. The Inception v3 model had the highest accuracies
of 0.98 and 0.95 with the leaflet dataset for CBSD and GMD,
respectively. Healthy and BLS classes also had highest accuracies
with the leaflet dataset for the SVM model (0.90 and 0.98
respectively). The slight improvement in accuracies using the
leaflet dataset over the original dataset could be due to the
increase in sample size for the disease classes providing more
images for the models to learn from. Alternatively, the leaflet
dataset could reduce the accuracy of the model as all leaflets
on a cassava leaf may not show signs of a disease, which would
confuse the model. For CMD and RMD, the SVM model with
the original dataset had the highest accuracies of 0.96 and 0.96,
respectively. These results suggest the size of the dataset is not
as important in improving prediction accuracy as previously
assumed.
4. DISCUSSION AND CONCLUSION
The results of this study show that image recognition with
transfer learning from the convolutional neural network
Inception v3 is a powerful method for high accuracy automated
cassava disease detection. This method avoids the complex and
labor-intensive step of feature extraction from images in order
to train models, and the model can be easily trained on a
desktop and deployed on a mobile device. Transfer learning is
also capable of applying common machine learning methods by
retraining the vectors produced by the trained model on new
class data. In this study, three machine learning methods were
used, and results showed the SVM model to be have the highest
prediction accuracies for four out of six disease classes. With
respect to specific cassava diseases, the SVM model had the
highest accuracies for cassava mosaic disease (CMD) (96%) and
red mite damage (RMD) (96%) using the original dataset, and
90% and 98% for healthy and brown leaf spot (BLS) using the
leaflet dataset. The Inception v3 model had the highest accuracies
for the cassava brown streak disease (CBSD) (98%) and 95%
accuracy for green mite damage (GMD) with the leaflet dataset.
In a practical field setting where the goal is smartphone
assisted disease diagnosis, our results show that diagnostic
accuracy improved only slightly when the leaflet was used
rather than the whole leaf for some diseases (CBSD, BLS,
GMD), while whole leaf images gave higher accuracies for other
diseases (CMD and RMD). This was not expected. Rather,
the larger image leaflet dataset was expected to perform better
for all disease classes compared to the original dataset. These
results indicate that datasets needed to build transfer learning
models for plant disease diagnosis do not require very large
training datasets (<500 images per class). The high accuracies
reported suggest that variations in background had little effect
on the prediction accuracies of the model. Portions of images
contained the sky, hands, shoes, and other vegetation, yet
predictions in all image classes were greatly above the probability
of randomly guessing (16.7%). In the field it is also likely
that an extension worker would use more than one picture
to predict the disease, thus improving the diagnostic accuracy
further. This study therefore shows that transfer learning applied
to the Inception v3 deep learning model offers a promising
avenue for in-field disease detection using convolutional neural
networks with relatively small image datasets. Work to validate
the method in the field with mobile devices has begun through
work with TensorFlow Android Inference Interface. Models
developed in this study are available on Android devices,
shown in the youtube link https://www.youtube.com/watch?
v=479p-PEubZk&feature=youtu.be, and are currently being
used by researchers in Tanzania to rapidly monitor disease
prevalence.
AUTHORCONTRIBUTIONS
AR, KB, BA, JL, and DH conceived the study and wrote the
paper. BA, KB, and JL collected and processed data. PM and AR
implemented the algorithms described and prepared results.
FUNDING
We thank the Huck Institutes at Penn State University for
support.
SUPPLEMENTARY MATERIAL
The Supplementary Material for this article can be found
online at: https://www.frontiersin.org/articles/10.3389/fpls.2017.
01852/full#supplementary-material
Frontiers in Plant Science | www.frontiersin.org
6
October 2017 | Volume 8 | Article 1852
Ramcharan et al.
Image-Based Cassava Disease Detection
REFERENCES
Abdullakasim, W., Powbunthorn, K., Unartngam, J., and Takigama, T. (2011). An
images analysis technique for recognition of brown leaf spot disease in cassava.
Tarım. Makinaları. Bilimi. Dergisi. 7, 165–169.
Aduwo, J. R., Mwebaze, E., and Quinn, J. A. (2010). “Automated vision-based
diagnosis of Cassava Mosaic Disease,” in Industrial Conference on Data Mining
Workshops (New York, NY), 114–122.
Bellotti, A. C., Smith, L., and Lapointe, S. L. (1999). Recent advances
in cassava pest management. Ann. Rev. Entomol. 44, 343–370.
doi: 10.1146/annurev.ento.44.1.343
De Bruijn, G., and Fresco, L. (1989). The importance of cassava in world food
production. Netherl. J. Agric. Sci. 37, 21–34.
Dubey, S. R., and Jalal, A. S. (2014). Adapted approach for fruit disease
identification using images. arXiv preprint arXiv:1405.4930.
FAOSTAT(2017). Faostat:Food and Agriculture Data. Rome: FAOSTAT. (Accessed
Jan 04, 2017).
Gibson, D., Burghardt, T., Campbell, N., and Canagarajah, N. (2015). “Towards
automating visual in-field monitoring of crop health,” in IEEE International
Conference on Image Processing (ICIP), 2015 (Quebec City, QC: IEEE), 3906
3910.
Karpathy, A., Toderici, G., Shetty, S., Leung, T., Sukthankar, R., and Fei-Fei, L.
(2014). “Large-scale video classification with convolutional neural networks,” in
Proceedings of the IEEE conference on Computer Vision and Pattern Recognition
(Columbus), 1725–1732.
Legg, J. (1999). Emergence, spread and strategies for controlling the pandemic
of cassava mosaic virus disease in east and central africa. Crop Protect. 18,
627–637. doi: 10.1016/S0261-2194(99)00062-9
Legg, J., Owor, B., Sseruwagi, P., and Ndunguru, J. (2006). Cassava mosaic virus
disease in east and central africa: epidemiology and management of a regional
pandemic. Adv. Virus Res. 67, 355–418. doi: 10.1016/S0065-3527(06)67010-3
Mbanzibwa, D., Tian, Y., Tugume, A., Mukasa, S., Tairo, F., Kyamanywa, S., et
al. (2011). Simultaneous virus-specific detection of the two cassava brown
streak-associated viruses by rt-pcr reveals wide distribution in east africa, mixed
infections, and infections in manihot glaziovii. J. Virol. Methods 171, 394–400.
doi: 10.1016/j.jviromet.2010.09.024
Mohanty, S. P., Hughes, D. P., and Salathé, M. (2016). Using deep learning
for image-based plant disease detection. Front. Plant Sci. 7:1419.
doi: 10.3389/fpls.2016.01419
Mwebaze, E., and Owomugisha, G. (2016). “Machine learning for plant disease
incidence and severity measurements from leaf images,” in Machine Learning
and Applications (ICMLA), 2016 15th IEEE International Conference on (IEEE)
(Anaheim, CA).
Nagayet, O. (2005). “Small farms: current status and key trends,” in The Future of
Small Farms: Proceedings of a Research Workshop (Washington, DC), 355–367.
Ndunguru, J., Legg, J. P., Aveling, T., Thompson, G., and Fauquet, C. M. (2005).
Molecular biodiversity of cassava begomoviruses in tanzania: evolution of
cassava geminiviruses in africa and evidence for east africa being a center of
diversity of cassava geminiviruses. Virol. J. 2:21. doi: 10.1186/1743-422X-2-21
Nichols, R. (1950). The brown streak disease of cassava: distribution,
climatic effects and diagnostic symptoms. East Afr. Agric. J. 15, 154–160.
doi: 10.1080/03670074.1950.11664727
Nweke, F. I., Spencer, D. S., and Lynam, J. K. (2002). The Cassava Transformation:
Africa’s Best-Kept Secret. East Lansing.
Puig, E., Gonzalez, F., Hamilton, G., and Grundy, P. (2015). “Assessment of crop
insect damage using unmanned aerial systems: a machine learning approach,”
in 21st International Congress on Modelling and Simulation (MODSIM2015),
(Gold Coast, QLD). Available online at: https://eprints.qut.edu.au/95241/
Siricharoen, P., Scotney, B., Morrow, P., and Parr, G. (2016). “A lightweight mobile
system for crop disease diagnosis,” in International Conference Image Analysis
and Recognition, (Póvoa de Varzim: Springer), 783–791.
Skovgård, H., Tomkiewicz, J., Nachman, G., and Münster-Swendsen, M. (1993).
The effect of the cassava green mite mononychellus tanajoa on the growth and
yield of cassava manihot esculenta in a seasonally dry area in kenya. Exp. Appl.
Acarol. 17, 41–58.
Storey, H. (1936). Virus diseases of east african plants: V.—streak disease of maize.
East Afr. Agric. J. 1, 471–475.
Szegedy, C., Vanhoucke, V., Ioffe, S., Shlens, J., and Wojna, Z. (2016). “Rethinking
the inception architecture for computer vision,” in Proceedings of the IEEE
Conference on Computer Vision and Pattern Recognition (Las Vegas), 2818
2826.
Thresh, J., Fargette, D., Otim-Nape, G., et al. (1994). Effects of african cassava
mosaic geminivirus on the yield of cassava. Trop. Sci. Lond. 34, 26–26.
Warburg, O. (1894). Die Kulturpflanzen Usambaras. Mitteilungen aus den
Deutschen Schutzgebieten 7, 131.
Yosinski, J., Clune, J., Bengio, Y., and Lipson, H. (2014). “How transferable
are features in deep neural networks?,” in Advances in Neural Information
Processing Systems (Montreal), 3320–3328.
Conflict of Interest Statement: The authors declare that the research was
conducted in the absence of any commercial or financial relationships that could
be construed as a potential conflict of interest.
Copyright © 2017 Ramcharan, Baranowski, McCloskey, Ahmed, Legg and Hughes.
This is an open-access article distributed under the terms of the Creative Commons
Attribution License (CC BY). The use, distribution or reproduction in other forums
is permitted, provided the original author(s) or licensor are credited and that the
original publication in this journal is cited, in accordance with accepted academic
practice. No use, distribution or reproduction is permitted which does not comply
with these terms.
Frontiers in Plant Science | www.frontiersin.org
7
October 2017 | Volume 8 | Article 1852