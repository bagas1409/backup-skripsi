Review
Disease Detection on Cocoa Crops Based on Computer-Vision
Techniques: A Systematic Literature Review
Joan Alvarado 1,* , Juan Felipe Restrepo-Arias 1
1
, David Velásquez 1 andMikelMaiza2
Escuela de Ciencias Aplicadas e Ingeniería, Universidad EAFIT, Medellín 050022, Colombia;
jfrestrep3@eafit.edu.co (J.F.R.-A.); dvelas25@eafit.edu.co (D.V.)
2
*
Fundación Vicomtech, Basque Research and Technology Alliance (BRTA), Mikeletegi 57,
20009 Donostia-San Sebastián, Spain; mmaiza@vicomtech.org
Correspondence: jfalvaradm@eafit.edu.co
Abstract: Computer vision in the agriculture field aims to find solutions to guarantee and
assure farmers the quality of their products. Therefore, studies to diagnose diseases and detect
anomalies in crops, through computer vision, have been growing in recent years. However,
crops such as cocoa required further attention to drive advances in computer vision to the
detection of diseases. As a result, this paper aims to explore the computer vision methods used
to diagnose diseases in crops, especially in cocoa. Therefore, the purpose of this paper is to
provide answers to the following research questions: (Q1) What are the diseases affecting cocoa
crop production? (Q2) What are the main Machine Learning algorithms and techniques used
to detect and classify diseases in cocoa? (Q3) What are the types of imaging technologies (e.g.,
RGB,hyperspectral, or multispectral cameras) commonly used in these applications? (Q4) What
are the main Machine Learning algorithms used in mobile applications and other platforms
for cocoa disease detection? This paper carries out a Systematic Literature Review approach.
The Scopus Digital, Science Direct Digital, Springer Link, and IEEE Explore databases were
explored from January 2019 to August 2024. These questions have identified the main diseases
that affect cocoa crops and their production. From this, it was identified that mostly Machine
Learning algorithms based on computer vision are employed to detect anomalies in cocoa. In
AcademicEditor: JunLi
Received: 1April2025
Revised: 28April2025
Accepted: 6May2025
Published: 10 May2025
Citation: Alvarado,J.; Restrepo
Arias, J.F.; Velásquez, D.; Maiza, M.
Disease Detection on Cocoa Crops
BasedonComputer-Vision
Techniques: ASystematicLiterature
Review. Agriculture 2025, 15, 1032.
https://doi.org/10.3390/
agriculture15101032
Copyright: ©2025bytheauthors.
Licensee MDPI,Basel,Switzerland.
This article is an open access article
distributed under the terms and
conditions of the Creative Commons
Attribution (CC BY)license
(https://creativecommons.org/
licenses/by/4.0/).
addition, the main sensors were explored, such as RGB and hyperspectral cameras, used for the
creation of datasets and as a tool to diagnose or detect diseases. Finally, this paper allowed us
to explore a Machine Learning algorithm to detect disease deployed in mobile and Internet of
Things applications for detecting diseases in cocoa crops.
Keywords: machine learning; computer vision; plant diseases; cocoa diseases
1. Introduction
Theobroma cocoa is a plant native to the tropical regions of Central and South America.
It thrives in equatorial climates and is cultivated in tropical regions across West and Central
Africa, Latin America, and Southeast Asia [1]. Theobroma cocoa produces cocoa pods which
have an oval-shaped fruit of which the bark is about 80% and the rest, 20%, is made up
of seeds known as cocoa beans and white pulp known as mucilage [2]. Cocoa beans are
processed into chocolate, cocoa powder, cocoa drinks, and other related products in the
food industry, as well as products for the pharmaceutical and cosmetic industries [3].
The African region is the world’s largest producer of cocoa, accounting for approxi
mately 68% of production, followed by Asia/Oceania and Latin America with 14% and
18%[4], respectively; also, approximately 80% of the world’s cocoa comes from smallholder
Agriculture 2025, 15, 1032
https://doi.org/10.3390/agriculture15101032
Agriculture 2025, 15, 1032
2 of 27
farmers [4,5]. In Africa, Ivory Coast is the world’s leading producer of cocoa beans, fol
lowed by Ghana [4]. In the Asia/Oceania region, Indonesia is the third largest producer
of cocoa beans in the world [4]. On the other hand, in Latin America, Ecuador is the sixth
country in the world ranking, ahead of Brazil in 5th place, Peru in 8th place, and Colombia
in 9th place [4].
The production of cocoa and its products have a great demand in the food market,
but the quality of cocoa cultivation depends on favorable climatic conditions and low
incidence of pests and diseases [6,7]. Climate variations, such as changes in temperature
or precipitation, can influence the cocoa pathogens, increasing the incidence of diseases
that threaten their production [7]. However, the environment in which cocoa plants grow
is prone to various diseases that can cause damage to the fruit, resulting in losses in cocoa
crop production [8]. Witches’ broom caused by Moniliophthora perniciosa, frosty pod caused
by Moniliphthora roreri, and black pod caused by Phytophtora are the most common diseases
in cocoa crops [8,9]. Frosty pod directly attacks the cocoa fruit and the losses can exceed
60%ofits production; on the other hand, the losses due to black pod can exceed 40% [10,11].
Visual inspection, a task carried out by farmers, is the most common practice to
control diseases in cocoa crops. Although the farmers have experience in this kind of
task, visual inspection does not provide standardized results when diagnosing the health
condition of cocoa pod [12]. Other methods such as fungicides, pesticides, and other
biological methods to control diseases in cocoa crops are costly and complex to apply [13].
However, in the agricultural field, computer vision (CV) has surged to improve, facilitate,
and reduce the complex tasks related to the evaluation of crops. Based in Machine Learning
algorithms (MLA) and Deep Learning algorithms (DLA), CV has become a tool that allows
farmers to make better decisions and is also used to identify and classify plant diseases
automatically [12,13]. Thus, CV application is a technology that offers in a quick and
accurate way the identification of plant diseases in agriculture.
To perform MLA, a large amount of image data are required to be trained and learn
the patterns of data to perform a particular function. MLA are classified into supervised
and unsupervised learning. In supervised learning, the training data include the output
desire or the target, called labels. For example, in [14], an open-source Kaggle dataset
was used to identify healthy and damaged cocoa fruits affected by Moniliophthora and
Phytophthora diseases. Thus, MLA was developed to detect healthy and unhealthy stages
of cocoa fruits. Classification is a common task in supervised learning algorithms. On the
other hand, in unsupervised learning, the data are not labeled and the system tries to learn
to acquire patterns without prior knowledge [15]. However, DLA uses an Artificial Neural
Network (ANN) composed of multiples layers of neurons and weights connected between
them trying to mimic how the human brain works [16]. For example, for the DLA in [17],
an autoencoder network was implemented for unsupervised disease detection in cucumber
leaf by means of clustering of features and anomaly detection.
Computer vision systems (CVS) is the integration between software and hardware,
which is made up of three elements, the input (captured image), the camera or sensor
device that captures the image, and the microcontroller with its embedded algorithm to
process the input data; then, the system provides an output where an object is classified or
identified [18]. Figure 1 shows the above-mentioned CVS process.
The incorporation of CV technologies, in farm applications, enables farmers to have
a tool that allows them to make diagnoses that cannot be perceived with the naked eye;
thus, the level of precision and accuracy provided by these applications helps to prevent
production losses caused by unhealthy crops. Therefore, given the growth of Machine
Learning (ML) in the farm field based on the detection and classification of plant diseases,
the main objective of this document is to carry out a Systematic Literature Review (SLR)
Agriculture 2025, 15, 1032
3 of 27
to explore the state of the art based on ML application to CV, mainly in cocoa crops. This
study also covers the exploration of CV applications applied to the early detection of
diseases in agriculture especially in Theobroma cacao (TC). Moreover, this paper includes
different methods and algorithms used to detect and identify diseases in the agricultural
field. Therefore, the present SLR has considered the following questions:
• Q1Whatarethemaindiseasesaffecting cocoa crop production?
• Q2WhatarethemainMachineLearning algorithms and techniques used to detect
and classify diseases in cocoa?
• Q3Whatarethetypesofimagingtechnologies (e.g., RGB, hyperspectral, or multispec
tral cameras) commonly used in these applications?
• Q4WhatarethemainMachineLearningalgorithms used in mobile applications and
other platforms for cocoa disease detection?
Figure 1. Computer vision system.
The present paper is organized as follows: Section 2 explains the methodology used
for this SLR. Section 3 presents the related works based on CV techniques implemented
to detect disease in crops other than cocoa. Section 4 presents the answer to the research
questions. Section 5 discusses the limitations in this SLR, and finally, Section 6 presents the
conclusions and future work.
2. Methodology
In order to ensure the quality of the papers in the SLR, the articles that were selected
to be part of the review process must meet the following criteria:
• Publication type: Studies published in peer-reviewed journals.
• Language: Studies written and published in English.
• Researchfocus: Studies that directly address the research questions related to cocoa
disease detection and plant disease detection based on images, as well as the early
detection of cocoa diseases using computer-vision techniques.
• Publication date: Studies published between 2019 and 2024 were considered.
To address the research questions, studies were considered according to their titles
and keywords. The first selection included papers that aimed to address the problem of
cocoa disease detection based on images and computer-vision techniques for early disease
detection in cocoa. Finally, studies that did not include methods based on images and
computer-vision techniques for cocoa and plant disease detection were excluded from this
SLR from further analysis.
2.1. Information Sources
An initial search was conducted in the most recognized scientific databases to identify
those that recovered the largest amount of articles with the most relevance for this study.
After this approach, the digital databases selected for this SLR are listed in Table 1.
Agriculture 2025, 15, 1032
4 of 27
Table 1. Information sources used for the search phase.
Source
Type
URL
Scopus
Science Direct
Springer Link
IEEE Explore
Digital
Digital
Digital
Digital
https://www.scopus.com (accessed on 1 September 2024)
https://www.sciencedirect.com (accessed on 1 September 2024)
https://link.springer.com (accessed on 1 September 2024)
https://ieeexplore.ieee.org (accessed on 1 September 2024)
2.2. Search Strategy
To ensure a structured search strategy, the search terms were selected and categorized
into three specialized domains. The first domain refers to cocoa diseases, crop diseases, and
plant disease detection. The second refers to CV and ML in the field of agriculture. Finally,
the last domain refers to technologies used to detect diseases in the agriculture field. The
keywords used for the search query are detailed in Table 2.
The search query was performed by combining keywords from the groups mentioned
in the Table 2. Then, Boolean operators, such as AND, OR, and NOT were implemented
to maximize the retrieval of relevant articles. Lastly, the search query structure, shown in
Table 3, was applied to the information source.
In addition, after applying the search query to each scientific database, the search
results were delimited by year (2019–2024), review articles, research articles, and conference
papers. Also, the selection of some subject areas, such as Engineering, Computer Science,
Agricultural and Biological Science, Artificial Intelligence in Agriculture, Sensors, Smart
Agriculture Technology, and Computers and Electronics in Agriculture, helps to delimit
and improve the search. Finally, to cover the search, Artificial and Computer Intelligence
were subdisciplines included in Group 2 to focus on the specific topics within a larger field.
Table 2. Keywords groups used for the search query.
Group
Keywords
Group 1
Agriculture plant disease detection, cocoa plant disease, cocoa disease
detection, cocoa pod, and Theobroma cocoa.
Artificial intelligence, Machine Learning, computer vision, image classifi
Group 2
cation, Deep Learning, Convolutional Neural Networks, and technology
digital agriculture
2.3. Selection and Collection Process
The selection process was implemented to ensure the inclusion of relevant studies.
The search was performed using a combination of keywords from the thematic groups. The
initial search was conducted by one researcher using digital databases and the retrieved
articles were reviewed by two researchers. In this first phase, the titles, abstracts, and
keywords were analyzed to figure out the relevance to the research objectives.
To fit the selection, researchers assessed whether the studies are related to the field
of agricultural precision, specifically in the use of computer-vision techniques to detect
disease in cocoa using MLA. Also, to extend this SLR, the studies based on plant disease
detection (PDD) and plant disease classification (PDC) were included in this paper, and the
use of MLA to detect disease through mobile applications.
The PRISMA 2020 protocol [19] was carried out to ensure traceability, allowing for
the selection of the papers in a methodological way. Therefore, the final selection resulted
in 88 studies, which were subsequently analyzed to identify research trends depicted in
Figure 2.
Agriculture 2025, 15, 1032
5 of 27
Table 3. Search query algorithm.
Digital Libraries
Search Algorithm
(“Agriculture” AND “Plant disease detection”) OR “Cacao
disease” OR “Cocoa disease” OR “Theobroma cacao disease”
OR“monilia” OR “Cacao pod” OR“Cacao pod rot” OR “Co
Scopus, Science Direct,
Springer Link and
IEEE Explorer
coa frosty pod rot” AND (LIMIT-TO (SUBJAREA, “COMP”)
OR LIMIT-TO (SUBJAREA, “ENGI”) OR LIMIT-TO (SUB
JAREA, “AGRI”)) AND (LIMIT-TO (EXACTKEYWORD, “Ma
chine Learning”) OR LIMIT-TO (EXACTKEYWORD, “Con
volutional Neural Networks”) OR LIMIT-TO (EXACTKEY
WORD,“Convolutional Neural Network”) OR LIMIT-TO (EX
ACTKEYWORD,“Plant Disease”) OR LIMIT-TO (EXACTKEY
WORD,“DeepLearning”) OR LIMIT-TO (EXACTKEYWORD,
“Computer Vision”))
Figure 2. Trend of distribution papers by publication year.
According to the PRISMA 2020 protocol [19], Figure 3 shows that most articles selected
were developed in India, with a significant difference compared to other countries. This
difference may be attributed to the fact that India, being one of the most populated countries
in the world, has shown interest in applied research in agriculture. Additionally, India is
among the countries with extensive agricultural activity [4], and the corresponding demand
for technological solutions to enhance crop health and productivity likely contributes to
this trend [20].
Finally, the titles and abstracts of the papers were identified and categorized to identify
the approach in CV applications in the agriculture. The categories, depicted in Figure 4a,
were separated by crops, the use of hyperspectral images in agriculture, PDC, PDD and
plant-leaf disease detection (PLDD) applications. On the other hand, Figure 4b provides a
detailed breakdown of papers focusing on individual crops.
Asshown in Figure4b, mostoftheretrieved studies categorized by crop was the cocoa.
However, it is important to clarify that due to the limited number of studies published in
peer-reviewed journals, the majority of studies related to CV techniques to detect disease
on cocoa crops were retrieved from conference proceedings. On the other hand, Figure 4b
indicates in this SLR greater interest in apple, tomato, rice, and strawberry crops compared
to plantain, mango, and corn crops. This approach to the selection process ensures papers
with the most relevant studies associated in plant disease detection, with a special emphasis
on research addressing cocoa disease through MLA.
Agriculture 2025, 15, 1032
6 of 27
Figure 3. Trend of the most relevant papers by country.
(a)
(b)
Figure 4. (a) Studied retrieved categorized by CV applications in agriculture. Plant Leaf Disease
Detection (PLDD): CV on Plant Leaf Disease Detection. Plant disease detection (PDD): CV on plant
disease detection. Plant disease classification (PDC): CV on plant disease classification. Hyperspectral
(Hyp): CV based on hyperspectral images. Crop: CV techniques in crops. (b) Retrieved studies
categorized by crop.
3. Related Works
Systematic Literature Review and review documents, listed in Table 4, were identified
in this SLR. Eleven of the retrieved review articles explore MLA and DLA to detect diseases
in crops and plants using CV techniques. However, review articles based on CV techniques
to detect and classify diseases in cocoa were not found in this SLR. Furthermore, Systematic
Literature Review and review papers based on mobile applications (MA) and Internet of
Things (IoT), as portable solutions to detect and classify diseases in cocoa, were not found
in this SLR.
Table 4. A comparison of the Systematic Literature Review (SLR) with other works.
Main Topic
A B C D E Reference
Artificial intelligence (AI) for agriculture
Machine Learning (ML) for plant disease classification (PDC)
Convolutional Neural Network (CNNs) for crop disease recognition
[18]
[21]
[20]
Agriculture 2025, 15, 1032
7 of 27
Table 4. Cont.
Main Topic
A B C D E Reference
Image processing techniques
Image processing for pest and disease recognition
Imaging techniques for plant disease
SLR on plant disease detection (PDD) and PDC
Deep Learning (DL) for plant-leaf disease detection (PLDD) and PDC
Deep Learning (DL) on PDD and PDC
Disease Diagnosis using CNNs
Disease Detection on cocoa crops based on computer-vision (CV)
techniques
[22]
[23]
[24]
[25]
[26]
[27]
[28]
This
work
A: SLRandreview papers based on plant disease classification. B: SLR and review papers based on plant disease
detection. C: SLR and review papers based on plant disease classification and mobile applications. D: SLR and
review papers based on plant disease detection and mobile applications. E: SLR and review papers based in
cocoa crops.
4. Results
This phase presents the results of the SLR to address the research questions based on
the information extracted from the selected primary studies. Initially, 1869 records were
identified from the selected electronic databases, distributed as follows: 334 records from
IEEE Explore, 561 from Scopus, 413 from SpringerLink, and 561 from ScienceDirect. In the
first place, duplicate records were excluded, reducing the dataset to 1674 unique records.
Subsequently, a screening was performed based on keywords and titles such as disease and
detection, PDD, PDC, image processing, detection, and classifications were then performed,
and 572 studies were considered relevant at this stage. A second screening, conducted on
180 studies, was carried out based on their applications looking at the title and the abstract
tools and computer vision algorithms (CVA) used to detect or diagnose disease crops. In
this phase, diseases in cocoa were explored, as well as MLA and DLA methods to detect
and classify diseases in cocoa. After fully screening 180 studies, 92 articles were excluded,
resulting in 88 articles that were given a full reading for this SLR. See Figure 5.
According to Figure 5, out of the 88 studies retrieved in this SLR, a total of 14 studies
are focused on the applications of computer vision (CV) techniques in cocoa. The remaining
documents are retrieved to analyze these applications in other agricultural contexts which
could be of support for transferring them in the cocoa context.
4.1. Answer to the First Research Question
What are the main diseases that affect the production of cocoa crops?
In the context of CV, the most common reported cocoa diseases in this SLR, which
researchers aim to detect are Moniliophthora pod rot or frosty pod rot (Moniliophthora roreri),
black pod disease (Phytophthora palmivora), and witches’ broom disease (Moniliophthora
perniciosa) [29,30].
4.1.1. Frosty Pod Rot (Moniliophthora roreri)
Frosty pod rot (FPR) or Moniliasis is a fungal disease caused by Moniliophthora roreri, and
it is the most common disease in Central and Latin America, causing economic losses of
between 30% and 40% [31]. This disease thrives in highly warm and humid environments,
which creates an environment conducive to its propagation; in addition, farmers and
growers can suffer crop losses of 40% to 80% of total annual production, and the Moniliasis
affects not only the crop but also the raw material [31,32].
Agriculture 2025, 15, 1032
8 of 27
Figure 5. PRISMA flowchart of literature review.
Figure 6 shows the Moniliasis disease in four cycles. First, it starts as yellowish-green
spots on the surface of the cocoa fruit. Within three months, a hump light in color appears
on the surface of the fruit. The second symptom, which appears after three months, is
the appearance of oily spots [6,33]. One month later, the color of the surface turns brown,
and as the infection progresses, the brown spot becomes more intense. By the end of the
infection and after 8–10 days, the brown spot turns into a white powder known as spores,
which are visible on the surface of the cocoa fruit [33].
The cycle of the FPR, depicted in Figure 6, is developed in four cycles. When the
spores are visible on the surface, they spread to other fruits. The FPR attacks the cocoa
fruit directly and therefore, is more dangerous and difficult to control compared to other
diseases [31,34].
In Latin America, cocoa-producing countries such as Colombia and Ecuador report
significant losses of up to 60% of cocoa production due to FPR diseases; by contrast, Peru
reports lower losses of up to 16% [32,33].
Agriculture 2025, 15, 1032
9 of 27
Figure 6. Monilia disease cycle: (a) Humps; (b) oily spots; (c) brown spots, and (d) white powder and
sporulation.
4.1.2. Black Pod Disease (Phytophthora palmivora)
Black pod disease (BPD), caused by the Phytophthora palmivora, is a similar fungal
disease that can affect the cocoa fruit. Like FPR, BPD causes losses of up to 20–30% of the
annual cocoa production in regions such as Latin America, Africa, and Asia [7,32,33]. BPD
thrives in tropical regions where the humidity is up to 100% and the temperature is up to
25 ◦C. See Table 5. However, unlike FPR, BPD not only affects the cocoa fruit but also other
parts of the tree such as leaves, branches, stems, and roots.
The disease starts with a small wound on the surface of the fruit, which gradually
spreads throughout the fruit, turning it brown [32,35]. Figure 7 shows two examples of
BPD. Example one shows the disease spreading from the stem. In contrast, example two
shows the disease spreading from the apex.
Table 5. Losses due to BPD by country.
Country
Yield Loss (%)
Reference
Côte d’Ivoire
Ghana
Nigeria
Cameroon
Brazil
Indonesia
Ecuador
Mexico
40%
40%
40%
40%
20%
20%
20%
20%
[32,33]
[7,32]
[36]
[32,36]
[33]
[33]
[32,33]
[33]
BPD: black pod disease caused by the Phytophthora palmivora.
On the leaves, it causes a reduction in photosynthesis, thus weakening the plant [31].
The infections in the branches cause cankers, further weakening the plant. Additionally,
BPD affects the stems, which impact the nutrients and cause the lack of water to feed
the tree. Finally, Phytophthora palmivora infects the roots of the cocoa tree, causing health
problems throughout the plant [31].
4.1.3. Witches’ Broom Disease (Moniliophthora perniciosa)
Witches’ broom, a disease caused by the fungus Moniliophthora perniciosa, is considered
the second most threat to cocoa production after BPD. Witches’ broom disease (WBD)
attacks the crops at different stages, causing significant yield and economic losses in cocoa
production [12,31,33]. South America, particularly Brazil, is the region most affected by
WBD due to the production of cocoa; ten years after the appearance of the disease, the
production dropped by 70% [6]. The disease produces a series of broom-like sprouts, from
which the name “Witches’ Broom” originated. When the broom forming on the tree is alive
and green, it dies after the short time, leaving dry residues in the tree. The dry residues,
WBD, adhere to the cocoa tree [6,35]. Moniliophthora perniciosa grows on the stem of the
Agriculture 2025, 15, 1032
10 of 27
cocoa tree. Figure 8 illustrates witches’ broom disease developed on the stem of the tree (1),
and the example highlighting the disease area (2).
Figure 7. Phytophthora palmivora infection on cocoa pods. (a) Black pod disease spreading from the
stem; (b) black pod disease spreading from the apex.
Figure 8. Witches’ broom disease developed on the stem of cocoa tree. (a) The disease developed on
the stem of cocoa tree; (b) Example one, highlighting the disease area.
Cocoa production takes place in tropical areas, where the temperature and humidity
levels range from 24 ◦C–30 ◦C and 70–90%, respectively, which assists in better produc
tion [6]. However, these conditions allow the faster spread of diseases. Frosty pot rot, black
pod disease and witches’ broom are fungal diseases that impact the cocoa production. An
other disease that impacts the cocoa production is the Cocoa Swollen Shoot Virus Disease
(CSSVD), which caused losses by 15% to 50% [6,31,33]. This disease is transmitted to the
cocoa tree by mealybugs, an insect that thrives in warm environments [31].
There are regions where the cocoa diseases have a major impact according to Figure 9.
This figure shows the leading TC diseases and their impact by region. The FPR is a disease
that takes precedence in Caribean, Central, and South America; BPD has a major impact in
the West of Africa, Asia, Latin America, and Caribbean, WBD shows relevance in South
America; and CSSVD in the West of Africa [31].
Agriculture 2025, 15, 1032
11 of 27
Figure 9. Disease distribution by region [31]. (FPR) Frosty pod rot caused by Moniliophthora roreri;
(BPD) black pod disease caused by Phytophthora palmivora; (CSSVD) witches’ broom disease caused
by Moniliophthora perniciosa, (WBD) Cocoa Swollen Shot Virus transmitted by mealybugs.
4.2. Answer to the Second Research Question
What are the main Machine Learning algorithms and techniques used to detect and
classify diseases in cocoa?
The application of MLAs for disease detection in crops has emerged as a valuable
tool that provides solutions for precision agriculture and crop management. Neverthe
less, research specifically focused on ML-based disease detection in cocoa remains limited.
According to this SLR, 14 studies in the context of CV on cocoa were identified, of which
only 10 are addressed in the detection of disease. In this context, MLA has been applied to
disease identification, anomaly detection, ripeness assessment, and pod counting. To ad
dress Q2, the retrieved studies were separated by algorithms employed in CV to detect and
classify diseases in cocoa. The studies were grouped into three categories corresponding to
(1) classical ML, (2) DL based on classification and (3) DL based on object detection. These
categories are illustrated in Figure 10. As shown in Figure 10, DL based on classification is
the predominant approach for disease detection in cocoa pods, followed by DL based on
object detection and, finally, classical ML. This trend indicates a strong preference for deep
neural networks in cocoa disease detection.
Disease Detection in Cocoa Crops with CV Techniques
DL based on classification in cocoa crops: DL architectures, such as EfficientNetB0,
SMulti-Layer Perceptron (MLP), Extreme Learning Machine (ELM), MobileNet and ResNet
havebeenemployed to classify anddiagnose disease cocoa pods[37–41]. Asaresult,several
studies have explored Convolutional Neural Networks (CNNs) for cocoa classification
tasks. Villamonte et al. [37] used DL frameworks such as VGG16 and MobileNet to
classify defects in cocoa beans. On the other hand, Godmalin et al. [39] demonstrated
the effectiveness of a MobileNet-based CNN architecture for classifying infection levels in
cocoa pods. Similarly, Godmalin et al. [38] applied EfficientNet to categorize cocoa pods
into three states: healthy, pest-infested, and affected by BPD. In another study, Achmad et
al. [42] employed ELM and MLP to identify pest attacks in cocoa pods. To assess ripeness
in cocoa, Ayikpa et al. [43] incorporated a Convolutional Block Attention Module (CBAM)
integrated into CNN. Additionally, Ayikpa et al. [43] and Galindo et al. [30] combined
image-processing techniques, specifically the Gray-Level Co-occurrence Matrix (GLCM) for
Agriculture 2025, 15, 1032
12 of 27
feature extraction with CNN for classification. Furthermore, Ayikpa et al. [43] and Galindo
et al. [30] incorporated Support Vector Machine (SVM) for ripeness assessment.
Figure 10. Computer-vision-based algorithms employed in disease detection in cocoa and other crops
grouped into three categories: (1) classical ML; (2) DL based on classification; and (3) DL based on
object detection.
DL based on object detection in cocoa crops: Beyond classification tasks, object
detection frameworks have been employed to detect and classify cocoa diseases. Object
detection algorithms such as You Only Look Once (YOLO) and Single-Shot MultiBox
Detector (SSD) have been used to identify diseases in cocoa [14,41]. Ferraris et al. [14]
developed an automatic object detection method using YOLO for detecting cacao disease,
including FPR and BPD. Similarly, Ayubi et al. [44] developed an efficient YOLO-based
model for detecting cocoa ripeness. Kumi et al. [41] developed a smartphone application
to support farmers in detecting BPD and Swollen Shoot diseases in cocoa pods. Their
approach utilized SSD MobileNetV2, which integrates SSD (Single-Shot Multibox Detector)
for object detection with MobileNetV2 for classification.
Classical ML in cocoa crops: Traditional ML classifiers, such as SVM, Random Forest
(RF), and K-nearest neighbor (KNN), have also been employed in cacao disease classifica
tion, evaluation of cocoa bean quality and ripeness assessment. Nasution et al. [29] intro
duced an automatic approach for classifying BPD using RF. Similarly, Acharya et al. [42]
used Local Binary Pattern (LBP) for feature extraction, followed by SVM for the early
detection of pest-induced damage in cocoa pods. Likewise, Jintawatsakoon et al. [45]
and Appiah et al. [46] have proposed methods to classify and assess cocoa beans using
traditional classifiers such as SVM, RF, and KNN. Moreover, Zainuddin et al. [40] and
Ekawaty et al. [47] employed an Unmanned Aerial Vehicle (UAV) to recognize and count
cocoa pods on trees using image processing. However, their study did not include methods
to detect or classify cocoa diseases.
Table 6 presents a summary of the traditional ML and DL architectures employed
for detecting diseases in cocoa pods. According to the evidence retrieved in this SLR, DL
Agriculture 2025, 15, 1032
13 of 27
models are primarily used to classify BPD. Additionally, Table 6 highlights the implemen
tation of DL methods to classify pest-induced damage. On the other hand, traditional
ML classifiers have been applied to detect different diseases than previously mentioned.
However, retrieved documents based on ML and DL approaches to detect or classify FPR
or Moniliasis were not found in this SLR, indicating that research in this area remains scarce
and requires further exploration to leverage the potential of ML and DL to detect FPR
or Moniliasis.
Table 6. Algorithms based on classification to detect diseases in cocoa.
Reference Disease
Algorithm
Metric [Acc]
[38]
[39]
[41]
[42]
[29]
[48]
[49]
Pest Attack and BPD
BPD
BPD and CSSVD
Pest Attack
EfficientNetB0 2
94%
MobileNetV3S 2 91%
EfficientDet D0 2 81.0%
MLP2
BPD, Cocoa Pod Borer, and Dark Spot RF 1
Other diseases
BPD
SVM1
ResNet18 2
66%
94.4%
80.95%
83.14%
1 Classical Machine Learning (ML); 2 Deep Learning (DL) based on classification.
The studies retrieved on object detection architectures are listed in Table 7, indicating
that research based on object detection remains limited. As shown in Table 7, YOLO
architectures have been utilized to classify cocoa ripeness classification and have also been
applied to detect diseases in cocoa pods. Similarly, Single-Shot Multibox Detector (SSD)
has also been employed to detect black pod disease (BPD) and Cocoa Swollen Shoot Virus
Disease (CSSVD). Although cocoa ripeness is not the main focus of this SLR, it has been
considered as a complementary method for trait detection, as a complementary approach
for disease detection, and as an approach to assess disease across different ripening stages.
Table 7. Algorithms based on object detection to detect diseases in cocoa.
Reference Disease
Algorithm
Metric [mAP]
[14]
[41]
[44]
Moniliophthora roreri, and Phytophthora
palmivora
BPD and CSSVD
Classification of cocoa ripeness
YOLOv5m1
SSD 1
YOLOv5s 1
29–31
95
1 Deep Learning algorithms (DLAs) based on object detection.
Studies employing CV techniques to address Q2 have been analyzed in this SLR. These
studies were categorized into three groups: (1) classical ML; (2) DL based on classification;
and (3) DL based on object detection. Among these, DL architectures based on classifi
cation and object detection are the most employed to identify BPD. Additionally, these
architectures mentioned have been utilized in research to classify and identify BPD as well
as pest-induced damages (pest attack and CSSVD). However, within these categories, meth
ods to detect and identify Moniliasis disease remain scarce. According to this SLR, further
research is needed to leverage the potential of ML and DL to detect Moniliasis disease.
Studies based on disease detection in cocoa crops using CV techniques remain limited
in the literature. However, to obtain a background on how these solutions have been
applied in other crops, this SLR also explores CV techniques in different agricultural
contexts. The objective is to harness the potential of classical ML and DL approaches for
detecting disease in crops other than cocoa. These crops include apples, tomatoes, rice,
strawberries, and potatoes, among others. As shown in Figure 10, the use of DL algorithms
to detect diseases in crops other than cocoa outperformed classical ML algorithms.
Agriculture 2025, 15, 1032
14 of 27
4.3. Disease Detection Based on CV Techniques in Other Types of Crops
4.3.1. Disease Detection in Apple Crops
According to this SLR, there is significant interest in the implementation of CV tech
niques to diagnose disease in apple crops. However, in apple crops, disease diagnosis is
primarily based on the condition of their leaves.
DL based on classification of apple crops: According to this SLR, There is significant
interest in the use of DL architectures to disease classification in apple crops [50–52]. Apples
are among the most widely cultivated crops globally and represent an important source of
income for many farmers around the world. However, in this crop, disease diagnosis is
primarily based on the condition of the leaves.
DL based on object detection in apple crops: This SLR has identified the use
of DL architectures based on object detection to detect apple-leaf disease in real time.
Khan et al. [53] and Liu et al. [54] employed object detection models such as YOLOV4,
Faster R-CNN, and RetinaNet to develop applications for detecting apple-leaf diseases.
These studies evidence the importance of these architectures in real environments.
Classical ML to classify disease in apple crops: According to the evidence found in
this SLR, Random Forest (RF) is the most commonly used traditional ML classifier to detect
diseases in apple leaves [55,56].
The studies retrieved on disease detection in apple crops provide evidence solutions
through ML and DL techniques for image classification. However, it is worth mentioning
that most of the studies were focused on apple leaves [50,51,53–56], with no evidence
found in this SLR especially addressing disease detection in apple fruits. In addition,
most of the data used to carry out these algorithms are based on RBG images, which are
often unbalanced. To solve these problems, data augmentation techniques are commonly
applied to enhance the performance of the models. On the other hand, two of the studies
retrieved were based on hyperspectral images (HSI), demonstrating that some diseases can
be detected at an early stage in a spectral range different from RGB [52,55].
4.3.2. Disease Detection in Tomato and Rice Crops
Among the studies retrieved, this SLR highlights a strong interest in the use of CV
techniques to detect disease in tomato and rice crops [57–64]. However, no studies using
classical ML or DL architectures based on object detection to identify diseases in tomato
and rice crops were found in this SLR [57–59]. Like apple crops, tomato crops are not only
a key source of income for farmers worldwide but also one of the most widely cultivated
crops, occupying an essential place in cuisines worldwide. On the other hand, rice is
another important crop. Researchers consider it a vital food source, as it is a staple food for
a significant part of the world’s population [60–64]. However, similar to tomato crops, no
studies using classical ML or DL approach based on object detection to identify diseases in
this crop were found in this SLR. As shown in Figure 10.
DL based on classification in tomato and rice crops: According to Figure 10, Deep
Learning (DL) architectures based on classification have been widely used to detect disease
in tomato crops [57,65,66]. Similarly, DL approaches based on image classification have
been extensively employed to identify diseases in rice crops [60–64].
The retrieved studies in tomato and rice crops indicate that the input images used to
train these architectures were obtained from public image datasets, suggesting that most
of these studies were conducted in controlled environments rather than under real-world
conditions. Also, the input data used to carry out these algorithms primarily consist of RBG
images. Finally, it is worth highlighting that most of the approaches have been focused on
tomato and rice leaves [57–59,62–64].
Agriculture 2025, 15, 1032
15 of 27
4.3.3. Disease Detection in Strawberry and Potato Crops
Among the studies retrieved, this SLR highlights research efforts focused on disease
detection in strawberry and potato crops using CV techniques [67–72]. As shown in
Figure 10, most of the studies employ DL based on classification, while studies that explore
classical ML or DL architectures based on object detection are still scarce. This suggests that
disease detection in these crops is relatively underexplored compared to other crops such
as tomato, rice, and apple. The impact of diseases on strawberry quality and yield is of
considerable importance, which has led researchers to explore effective CV methodologies
to detect diseases in strawberry. On the other hand, potatoes, a staple vegetable essential
for daily nutrition, play an important role for human beings.
DL based on classification in strawberry and potato crops: In both crops, acResNet
architecture based on classification is the most frequently used approach to detect dis
ease [67–69,71]. In contrast to the studies reported in previous sections, strawberry diseases
can affect both the fruit and the leaves [67], whereas potato diseases primarily appear in
their leaves [71,73].
DL based on object detection in strawberry crops: In the context of DL architectures
based on object detection, Faster R-CNNs is the architecture used to detect disease in
strawberry leaves and fruits [69]. This research highlights the uses of hyperspectral images
for this approach. In addition, the deployment of the model was conducted in both under
controlled environments and real-world conditions [69].
Classical ML in potato crops: Studies retrieved in this SLR demonstrate that classical
ML approaches have been used to detect and classify diseases in potato crops [70]. Partial
Least-Squares Discriminant Analysis (PLS-DA) and Support Vector Machines (SVM) based
on Principal Component Analysis (PCA) scores are supervised classification algorithms em
ployed to detect disease in potato leaves [70]. This approach also highlights the application
of these methods under real-world conditions, as well as the incorporation of hyperspectral
cameras to detect diseases.
According to this Systematic Literature Review (SLR), the evidence indicates that
studies employing DL architectures based on object detection and Machine Learning (ML)
classifiers in strawberry and potato crops were conducted under real-world conditions
[69,70]. In addition, these studies suggest that input images used to train these algorithms
were not obtained from a public dataset due to the use of hyperspectral imaging (HSI). In
contrast to studies in DL based on classification studies, the findings indicate that these
architectures were trained using public image datasets, suggesting that most of these
studies were not conducted under real-world conditions.
Finally, Table 8 presents the most common machine learning algorithms (MLA) used
to classify diseases in the crops mentioned above. As evidenced in Table 8, there is a clear
predominance of Deep Learning (DL) models, particularly on Convolutional Neural Net
works (CNN)-based architectures, through crops other than cocoa. According to Table 8,
models such as ResNet, custom CNN, and more advanced frameworks like Fully Con
volutional–Switchable Normalization Dual-Path Networks (FCSNDPN) and Multi-head
Attention Mechanism Depthwise Separable Convolution Inception Reduction (MDSCIR
Net) have evidenced strong performance, achieving accuracies above 95%. These results
highlight the powerful capabilities of deep convolutional networks in learning hierarchical
features from images, which are fundamentals for disease classification.
Despite the higher predominance of DL models, classical machine learning (ML) al
gorithms, such as Random Forest (RF) and Principal Component Analysis (PCA)-SVM
combined with Partial Least-Squares Discriminant Analysis (PLS-DA) have achieved per
formance levels comparable to those of more complex DL models. In particular, the studies
to detect disease on apples [55,56] report a 98.6% accuracy using Random Forest, slightly
Agriculture2025,15,1032 16of27
outperformingotherscomplexDLmodelswithinthesamedomain. Likewise, theuse
ofhybridmethodssuchasPCA-SVM+PLS-DAhasevidencedanaccuracyof92%,indi
catinganacceptableperformancetodetectdiseaseinpotatoes.Ontheotherhand,DL
algorithmsbasedonobjectdetection,suchasYOLOandRetinaNet,havebeenapplied
inreal-worldfarmingfordetectingdiseaseinappleleaves,demonstratingdistinctive
performancemetrics[53,54].Khanetal. [53]employedYOLOforreal-timediseasede
tection,achievingmeanAveragePrecision(mAP)of41.1andahighdetectionspeedof
approximately47framespersecond(FPS),makingtheirapproachsuitableforreal-world
andreal-timeapplications[53].Similarly,Liuetal. [54]achievedameanAveragePrecision
(mAP)of79.6,demonstratingthecapacityofRetinaNetformoreaccuratedetectionunder
realconditions.Thesefindingsprobablyevidencethechallengesrelatedtoobjectdetection
tasksinagriculture. InthecontextofresearchquestionQ2, itshouldbenotedthatthe
numberofstudiesbasedonCVtechniquesappliedtococoaremainslimitedcomparedto
othercrops.However,thealgorithmsshowninTable8demonstratedtheeffectivenessof
DLarchitecturesandMLA,whichprovideanopportunitytobeprobablyappliedtococoa
crops.Giventhatthesearchitecturescanextractfeaturessuchasleafsport,deformation,
anddiscoloration,thesearchitecturesmaybesuitablyadaptedtoidentifycharacteristic
symptomsincocoapods.
Table8.Classificationalgorithmsinagriculture.
Reference Crop Disease Algorithm Metric[Acc]
[55,56] Apple AppleScab,BlackRotandCedarAppleRust RandomForesta 98.63%
[50] Apple AppleScab,BlackRotandCedarAppleRust DeepCNNsb 98%
[51] Apple AppleScab,BlackRotandCedarAppleRust CapsNetb1 98%
[52] Apple AppleValsaCanker DC-CNNb2 90%
[53] Apple AppleScab,AlternariaandPowderyMildew Xceptionb 81.09%
[54] Apple Grayspot,Brownspot,Alternaria,MosaicandRust MCDCNetc3 66.8mAP
[53] Apple AppleScab,AlternariaandPowderyMildew YOLOc 41.1mAP
[54] Apple Grayspot,Brownspot,Alternaria,MosaicandRust RetinaNetc 79.6mAP
[58] Tomato Earlyblight,Lateblight,andLeafmold EmbededCNNsd 98%
[57,59,65] Tomato Earlyblight,LeafMold,Brownspot,Alternaria,Mosaic
Virus,TargetSpot,YellowLeafCurlVirus CustomCNNsb 91–99%
[66] Tomato Earlyblight,LeafMold,Brownspot,Alternaria,Mosaic
Virus,TargetSpot,YellowLeafCurlVirus FCSNDPNb4 99.83%
[61,62,64] rice BrownSpot,Healthy,RiceHispaandLeafBlast LightweightCNNsb 99%
[60] rice BacterialLeafBlight,Blast,BrownSpot MPW-DCNNb5 97.5%
[63] rice BacterialLeafBlight,BlastandBrownSpot MobileNetV2b 97.56%
[67,74] strawberry Anthracnose,Powderymildew,andGraymold ResNet-50b 94–98.11%
[70] Potato Alternariasolani(EarlyBlight) PCA-SVM+PLS-DAa7 92%
[71] Potato Blight,Septoria,LateBlight,andBlack-leg ResNetb 99.62%
[72] Potato EarlyBlightandLateBlight MDSCIRNetb6 99.65%
[73] Potato Blight,Septoria,LateBlight,andBlack-leg CNN+DNN+
CNN-SVMd 99.98%
[75] Plantain BlackandYellowSigatoka GRecConNNb8 92%
[76] Corn RustandBlightdisease DeepCNNsb 98.40%
[77] Mango PowderyMildewandSootyMould CNNsb 98%
aClassicalMachineLearning(ML).bDeepLearning(DL)basedonclassification. cDeepLearningalgorithms
(DLAs)basedonobjectdetection. dHybridEnsembleMethods(DLA)basedonobjectdetection+classical
MachineLearning(ML). 1CapsuleNetwork(CapsNet). 2Dual-ChannelCNN. 3Multi-scaleConstrainedDe
formableConvolutionNetwork(MCDCNet). 4FCSNDPN.5Moore–Penrosepseudo-inverseweight-baseddeep
ConvolutionNeuralNetwork. 6Multi-headAttentionMechanismDepthwiseSeparableConvolutionInception
ReductionNetwork(MDSCIRNet). 7PartialLeast-SquaresDiscriminantAnalysis(PLS-DA)andSupportVec
torMachines(SVM)basedonPrincipalComponentAnalysis(PCA).8Gated-RecurrentConvolutionalNeural
NetworkNetwork.
Agriculture 2025, 15, 1032
17 of 27
4.4. Answer to the Third Research Question
What are the types of imaging technologies (e.g., RGB, hyperspectral, or multispectral
cameras) commonly used in these applications?
To address Q3 in this Systematic Literature Review (SLR), the retrieved studies were
grouped by technology into three categories corresponding to (1) technologies based on
RGB cameras, (2) technologies based on hyperspectral cameras, and (3) multispectral
cameras. Based on this SLR, RGB cameras (n = 6) are the most commonly used technology
in agriculture for dataset creation or as sensors to capture plant information (6 studies),
followed by hyperspectral (4 studies) and multispectral cameras (1 study).
RGB technologies: According to this SLR, RGB cameras in agriculture are the most
widely used technological tool for CV due to its portability, accessibility, and cost effec
tiveness [74,77]. The images generated by these technologies are fundamental for creating
datasets used to train ML models. Additionally, the integration of RGB cameras into mobile
devices has facilitated and driven the development of computer-vision applications [63].
Singh et al. [77] employed a Sony HDR PJ540 RGB camera with a lens of 26.8 mm
to generate a dataset with healthy leaves. Also, Shin et al. [74] and Singh et al. [77] have
employed DSLR (Digital Single Lens Reflex) cameras such as EOS 1300D Canon and Nikon
DSLRD5600 with an 18–55 mm lens to obtain information based on images of infected
and healthy leaves. On the other hand, mobile devices equipped with advanced camera
technology have also been used for dataset creation. Then, Nayak et al. [63] used mobile
devices such as the iPhone X (12 MP) and Xiaomi Redmi Note 8 (48 MP) to build a dataset
of images with healthy and unhealthy rice leaves.
Most of the images used for training ML models have been created using RGB tech
nologies, providing detailed visual information that supports large-scale analysis and
has proven suitable for general disease classification and diagnosis in real applications.
Table 9 lists the RGB technologies identified in this SLR. According to the retrieved studies,
the limited use of RGB technologies suggests that most of these studies rely on public
datasets. However, the creation of our own datasets enables the training models with
images captured under real-world conditions.
Hyperspectral and multispectral technologies: Unlike RGB cameras, hyperspectral
cameras provide enhanced imaging capabilities by capturing data across multiple bands of
the electromagnetic spectrum, extending beyond the visible range detected by RGB cameras.
These bands include ultraviolet (UV), near-infrared (NIR), and other bands not visible to
the human eye. As a result, the integration of hyperspectral cameras is complex because
these technologies are more expensive than RGB technologies [52,54,55]. Based on this
SLR, the use of hyperspectral cameras in agriculture remains scarce; however, some studies
have used these technologies to create image datasets and diagnose plant diseases in more
detail. Cameras such as SOC 710VP, Corning MicroHSI 410 camera, Gaiasky mini2-VN,
and Specim FX 10 were hyperspectral technologies employed for disease identification
using wavelengths outside the visible RGB spectrum, covering a range between 700 nm
and 1000 nm, relating to the near-infrared (NIR) [52,54,55]. Another technology identified
in this SLR is a multispectral MAPIR Survey3 used to detect disease in coffee crops [16].
Although the use of hyperspectral cameras requires a greater investment due to their
advanced technology, studies retrieved in this SLR have demonstrated that these cameras
can identify patterns that RGB cameras are unable to detect due to their broad spectrum of
information. Table 9 lists the technologies identified in this SLR based on hyperspectral and
multispectral cameras, which were employed to create datasets for training ML models,
enabling the development of the models with hyperspectral images (HSI) captured under
real-world conditions.
Agriculture 2025, 15, 1032
18 of 27
Table 9. Imaging technologies used for dataset construction and diseases detection.
Reference Paper
Technology
Imagen
[24]
[57]
[63]
[67]
[69]
[70]
[78]
[52,55,79]
[16]
Nikon DSLRD5600 with 18–55 mm lens for infected leaves, Sony HDR PJ540
with 26.8 mm wide-angle lens for healthy leaves
RGB camera Logitech C920
12MP iPhone X camera, 48 MP Xiaomi Redmi Note 8 camera
Reflex DSLR camera EOS 1300D Canon
Sony digital camera
Imspector V9 with spectral range of 430–900 nm and resolution of 7 nm.
Hyperspectral camera ISpecim FX 10
SOC-710VP hyperspectral, 400–1000 nm.
MAPIR Survey3 multispectral
RGB
RGB
RGB
RGB
RGB
Hyperspectral
Hyperspectral
Hypespectral
Multispectral
Finally, Table 10 summarizes the main advantages and disadvantages of using RGB
and hyperspectral cameras in crop diseasedetection. This comparisonshowsthedifferences
such as spectral sensitivity, cost and applicability.
Table 10. Comparison between RGB and hyperspectral cameras.
Criteria
RGB Cameras
Hyperspectral Cameras
Cost and availability
Low cost and widely available
Costly and less accessible
Spectral resolution
Three bands (red, green, blue)
High spectral resolution (tens to hundreds of bands)
Early detection of dis
eases
Lower detection capacity in asymptomatic
stages
High sensitivity to biochemical changes before visible
symptoms appear.
Sensitivity to environ
mental condition
High sensitivity to light and shadows.
More robust to environmental variability.
Data processing
Fast, supports low computing power.
Processing intensive, requires advanced algorithms and
computational resources
Real-world applicabil
ity.
High applicability in field and uncontrolled
environments
Remains under exploration for autonomous use in the
field, mainly used in research.
Dataset availability
Public datasets such as PlantVillage and
Kaggle
Limited availability of hyperspectral datasets.
Datasets Used for Training ML Models
Asmentionedabove,thegenerationofimagedatasetstofeedMachineLearningalgorithms
(MLAs)dependsentirely on the technologies discussed above. However, several MLAs were
developed using public datasets available in PlantVillage [50,56–59,65,66]. To extend Q3 in this
SLR, the retrieved studies related to plant disease detection (PLDD), plant disease detection
(PDD), and plant disease classification (PDC) were analyzed to identify the dataset used for
trainingMLmodels. Figure11illustratesthepapersbasedonthetypeofdatasetusedfortraining
MLA.AccordingtotheevidencecollectedinthisSLR,Figure 11indicatesthatPlantVillage is the
most commonlyuseddataset for training classification models. However, PlantVillage datasets
cover various crops and diseases without a specific focus on particular crops [50,56–59,65,80–93].
In contrast, the use of proprietary datasets for training classification models is less. However,
these datasets are focused on particular crops and specific diseases [52–55,74]. Other datasets
represent the smaller portion, with fewer than five studies. Nonetheless, these studies also
employed public datasets from Kaggle [62–64].
Agriculture 2025, 15, 1032
19 of 27
Figure 11. Dataset identified for training MLA in disease detection and classification.
Table 11 presents the datasets used for training MLA in disease detection and classifi
cation, highlighting the data augmentation and image-processing techniques applied. As
shown in Table 11, PlantVillage is the most used dataset and is also the most frequently
referenced in the studies retrieved in this SLR.
Table 11. Imaging technologies used for dataset construction and disease detection.
Reference Paper
DataSet
Techniques
Imagen
Links
[50,56–59,63,65,66,80–93]
[51]
[62,64]
[67,69]
[94]
[53,54,74]
[55]
[52]
PlantVillage
Plant Pathology
2020-FGVC7
Kaggle
Jeonbuk
National
University
Afzaal
Field Plan and
PlantDoc
Own dataset
Own dataset
Own dataset
Data augmentation, rotation, shifting and
flipping
Rotations between 0◦ and 360◦, Random
horizontal and vertical shifts, Random zoom
between 0.8× and 1.2×
HSV(Hue, Saturation, Value), CLAHE
(Contrast Limited Adaptive, Histogram
Equalization)
Pyramid attention network and data
augmentation
Bounding boxes
Data augmentation, normalization and
resizing
Superpixel Segmentation (SLIC) 3D Gabor
filter
Standard Normal Transform (SNV),
Savitzky-Golay (S-G) Convolution Smoothing
(SGCS) and Multivariate Scattering
Correction (MSC)
RGB
RGB
RGB
RGB
RGB
RGB
a
b
c
d
e
Hyperspectral
Hyperspectral
a URL: https://arxiv.org/abs/1511.08060 (accessed on 14 December 2024). b URL: https://arxiv.org/abs/20
04.11958 (accessed on 14 December 2024). c URL: https://archive.ics.uci.edu/dataset/486/rice+leaf+diseases
(accessed on 14 December 2024). d URL: https://datasetninja.com/strawberry-disease-detection (accessed on
14 December 2024). e URL: https://universe.roboflow.com/plant-disease-detection/fieldplant (accessed on 14
December 2024).– Dataset is not publically available.
Agriculture 2025, 15, 1032
20 of 27
4.5. Answer to the Fourth Research Question
What are the main Machine Learning algorithms used in mobile applications and
other platforms for cocoa disease detection?
Based on the studies found in this SLR, the execution of ML models has been carried
out through processing units such as NVIDIA Tesla V100 GPU, NVIDIA RTX A4000 GPU,
NVIDIATesla V100 GPU, Intel Core i5-7500 CPU y AMD Radeon R7 430 GPU and (Intel
Core i5-7200U [68,73,75,77]. As shown in Table 8, column four presents some ML models
based on DL architectures, which are trained and deployed on this kind of unit. However,
several ML models, listed in Table 12, have been developed with optimized architectures
and computational constraints, enabling their implementation on mobile applications and
low-cost devices suitable for resource-restricted environments. It should be emphasized
that, to address Question Q4 in this SLR, additional studies exploring MLA in mobile
applications for crops other than cocoa were included. This inclusion was made due
to the limited number of studies retrieved that focused on cocoa crops, with just two
studies identified.
As presented in Table 12, non-traditional MLA are employed to be deployed in mobile
and edge devices in the agriculture field. As previously mentioned, there are processing
units used to train and run ML models. However, there are other low-cost processing units
that can perform the same solutions while providing a portable alternative. Therefore,
the Raspberry Pi is the most common edge device to deploy and test MLA. Based on the
Raspberry Pi device, Maurya et al. [95] implemented a lightweight framework combining
MLP and Long Short-Term Memory (LSTM), to reduce the computational overhead for
disease detection in cotton and maize crops. Thus, Gonzalez et al. [57], through CNNs
architectures such as MobileNet, NasNetMobile, and Xception, developed a low-cost
embedded system using a Raspberry Pi with a webcam to detect anomalies in tomato
crops in an early way. In addition, Mishra et al. [76] developed and deployed a custom
Dual-Channel Convolutional Neural Network (DC-CNN) on a Raspberry Pi device to
detect corn disease in real time.
On the other hand, smartphones are equipped with architectures specifically designed
to run MLA. Optimized architectures have been developed to adapt to the computational
and power constraints of this device to deploy these algorithms. Therefore, based on
mobile application algorithms, Ayubi et al. [44] developed an efficient model for cocoa
ripeness detection using YOLO model, an object detection algorithms, that can work on
mobile devices. Moreover, Godmalin et al. [39] proposed a CNN architecture based on
MobileNetV3Small that can run on mobile devices to classify cocoa pod-level infections.
Finally, Kumi et al. [41] developed a smartphoneapplication to support farmers in detecting
BPD and Swollen Shoot diseases in cocoa fruits using SSD MobileNet V2, which combines
features from SSD (Single-Shot Multibox Detector) for object detection with MobileNet V2
for its classification.
Table 12. DL architectures for mobile and embedded applications used for disease detection.
Reference Paper
Algorithm
Application
[38]
[39]
[41]
[94]
[95]
[63,96]
[57,90,94]
EfficientNetB0
MobileNetV3Small
SSD MobileNet V2
MobileNet
LSTM1
MobileNetVx
MobileNet CNNs
Detect cocoa diseases
Detect cocoa diseases
Detect and classify cocoa diseases
Detect disease in corn leaves
Detect disease tomato leaves
Detect disease on leaves
Detect leaves disease
1 Long Short-Term Memory (LSTM).
Agriculture 2025, 15, 1032
21 of 27
The Systematic Literature Review (SLR) highlights specific models that are adaptable
to the field of agriculture. However, the retrieved studies demonstrate a limited use of these
models for crop disease detection. Moreover, although this SLR reports the use of these
architectures, not all studies indicate that they have been implemented through mobile
applications. Notably, among the studies retrieved in this SLR, MobileNet and its variants
(MobileNetVx, MobileNetV3Small, and SSD MobileNet V2) are the most frequently used
architectures for detecting disease in crops, as evidenced in Table 12. The preference of these
architectures suggests a focus on lightweight and computationally efficient Deep Learning
models, which are especially suited for deployment in mobile or embedded systems.
Although the use of architectures designed for mobile devices is less frequent com
pared to those mentioned above in question Q2, these architectures offer significant advan
tages related to computational efficiency. The use of DL models for mobile applications
is still under exploration in the context of cocoa compared with other crops. However,
according to Table 12, the use of lightweight models in mobile applications in agriculture
demonstrates that it is possible to develop portable and cost-effective solutions for disease
detection that can be transferred to the cocoa context.
5. Limitations of This Study
Despite the efforts made to ensure studies based on cocoa disease, this SLR may
have some limitations that should be taken into account. First, the search was limited
to specific databases such as Scopus, Science Direct, Springer Link, and IEEE Explorer,
which may have excluded research available in other databases such as Web of Science.
Secondly, the protocol used in this SLR may have weaknesses in the evaluation of studies.
Another weakness is related to the bias introduced by the selection of keywords and the
search query algorithm. Third, the studies available focused on MLA to detect disease in
cocoa were limited. Finally, this SLR was focused on research published between 2019 and
2024, leaving out recent work that could provide additional information. In addition, the
literature search was conducted until 31 August 2024, which means that studies published
after this date were not considered in the analysis.
6. Conclusions and Future Work
This work has carried out a SLR focused on the detection of diseases in cocoa crops
using computer-vision techniques (CV). The protocol used was PRISMA 2020, which
allowed a careful selection of the literature published to date (31 August 2024). According
to each research question, this SLR provides insights that may contribute to future research
works. The questions proposed in this SLR aim to identify the needs currently facing cocoa
production and to explore how the use of ML and CV tools can contribute to providing
solutions to these challenges. Therefore, according to the question Q1, the production of
cocoa faces challenges due to the incidence of diseases caused by Phytophthora palmivora and
Moniliophthora roreri, which can affect more than half of the production, bringing significant
losses to farmers. Furthermore, it should be noted that there are diseases that have a great
impact on specific regions due to environmental conditions. In the case of FPR caused by
Moniliophthora roreri, it mainly affects Latin American countries. According to question Q2,
the application of ML algorithms to detect and classify diseases in cocoa remains limited
and require further development. Most of the CV techniques to date have focused on
detecting BPD, caused by Phytophthora palmivora. Furthermore, existing approaches usually
only distinguish between healthy and unhealthy cocoa pods, without providing more
detailed insights into the specific stage of the Monilia disease cycle. Regarding research
question Q3, it has been observed that RGB cameras are the most commonly used sensors
in computer vision (CV) systems, while the use of hyperspectral and multispectral cameras
Agriculture 2025, 15, 1032
22 of 27
remains limited, indicating that these technologies are still in the exploration phase. This
predominance of RGB cameras is likely due to their portability and accessibility, particularly
in devices such as smartphones, as well as the widespread availability of RGB image-based
datasets, which are commonly used to train machine learning algorithms (MLA). However,
a relevant finding of this SLR is the limited presence of proprietary datasets. Many of the
retrieved papers rely on public datasets, such as PlantVillage and Kaggle. Although these
datasets offer a large number of images, most of them have been focused on leaves and
have been created in controlled environments, which limits their applicability in real field
scenarios. In addition, there is a noticeable limitation of datasets related to cocoa pods
especially in the Monilia disease cycle. On the other hand, multispectral and hyperspectral
technologies have not been applied to the detection of diseases in cocoa crops, particularly
in the context of Monilia. Finally, regarding research question Q4, the lack of mobile
application development makes the limited implementation of these tools in uncontrolled
environments clear, which limits their practical use in the diagnosis of diseases in the
real world. For future work, it is recommended that the SLR be updated to include more
scientific databases. Also, a SLR should be performed on each domain identified in this
study; this will allow for a more detailed examination of the strategies used to address the
problems focused on detecting disease in the agricultural field.
AuthorContributions: Conceptualization, J.A. and J.F.R.-A.; methodology, J.A., J.F.R.-A. and D.V.; val
idation, J.F.R.-A., D.V. and J.A.; formal analysis, J.A., J.F.R.-A. and D.V.; investigation, J.A.; resources,
J.A.; data curation, J.A., J.F.R.-A. and D.V.; writing—original draft preparation, J.A.; writing—review
and editing, J.F.R.-A., J.A., D.V. and M.M.; visualization and supervision, J.F.R.-A., D.V. and M.M. All
authors have read and agreed to the published version of the manuscript.
Funding: This research and the APC were funded by Universidad EAFIT under grant number 819430.
Data Availability Statement: Not applicable.
Acknowledgments: The authors would like to thank Universidad EAFIT for supporting and funding
this research project.
Conflicts of Interest: The authors declare no conflicts of interest.
Abbreviations
The following abbreviations are used in this manuscript:
ML
MLA
DLA
CV
ANN
CVS
TC
SLR
PLDD
PDD
PDC
MA
IoT
DL
CNNs
AI
CVA
FPR
Machine Learning
Machine Learning Algorithms
Deep Learning Algorithms
Computer Vision
Artificial Neural Network
Computer Vision Systems
Theobroma cacao
Systematic Literature Review
Plant-Leaf Disease Detection
Plant Disease Detection
Plant Disease Classification
Mobile Applications
Internet of Things
Deep Learning
Convolutional Neural Network
Artificial Intelligence
Computer-Vision Algorithms
Frosty Pod Rot
Agriculture 2025, 15, 1032
23 of 27
BPD
WBD
CSSVD
SVM
KNN
ANN
RF
YOLO
SSD
MLP
ELM
HSI
Hyp
SGCS
CapsNet
SNV
MSC
MCDCNet
Black Pod Disease
Witches’ Broom Disease
Cocoa Swollen Shoot Virus Disease
Support Vector Machine
K-nearest neighbor
Artificial Neural Network
Random Forest
You Only Look Once
Single-Shot MultiBox Detector
SMulti-Layer Perceptron
Extreme Learning Machine
Hyperspectral Images
Hyperspectral
Savitzky–Golay (S-G) Convolution Smoothing
Capsule Network
Standard Normal Transform
Multivariate Scattering Correction
Multi-scale Constrained Deformable Convolution Network
MDSCIRNet Multi-head Attention Mechanism Depthwise Separable Convolution
Inception Reduction
FCSNDPN
PLS-DA
PCA
CNN
DC-CNN
UAV
LSTM
DC-CNN
References
1.
Fully Convolutional–Switchable Normalization Dual Path Networks
Partial Least-Squares Discriminant Analysis
Principal Component Analysis
Convolutional Neural Networks
Dual-Channel Convolutional Neural Network
Unmanned Aerial Vehicle
Long Short-Term Memory
Dual-Channel Convolutional Neural Network
Tosto, A.; Morales, A.; Rahn, E.; Evers, J.; Zuidema, P.; Anten, N. Simulating cocoa production: A review of modelling approaches
and gaps. Agric. Syst. 2023, 206, 103614. [CrossRef]
2.
3.
4.
5.
6.
7.
8.
9.
DeSouza, P.; Moreira, L.; Sarmento, D.; Da Costa, F. Cacao—Theobroma cacao. Exotic Fruits 2018, 2018, 69–76.
Beg, M.; Ahmad, S.; Jan, K.; Bashir, K. Status, supply chain and processing of cocoa—A review. Trends Food Sci. Technol. 2017, 66,
108–116. [CrossRef]
Food and Agriculture Organization of the United Nations FAOSTAT: Crops and Livestock Products. 2025. Available online:
https://www.fao.org/faostat/en/#data/QCL/visualize (accessed on 20 April 2025).
Duguma, B.; Gockowski, J.; Bakala, J. Smallholder cacao (Theobroma cacao Linn.) cultivation in agroforestry systems of West and
Central Africa: Challenges and opportunities. Agrofor. Syst. 2001, 51, 177–188. [CrossRef]
Reyes, B.; Fonseca, P.; Heming, N.; Conceição, L.; Nascimento, K.; Gramacho, K.; Arevalo-Gardini, E.; Pirovani, C.; Aguiar, E.
Characterization of the microbiota dynamics associated with Moniliophthora roreri, causal agent of cocoa frosty pod rot disease,
reveals new viral species. Front. Microbiol. 2023, 13, 1053562. [CrossRef] [PubMed]
Delgado-Ospina, J.; Molina-Hernandez, J.; Chaves-Lopez, C.; Romanazzi, G.; Paparella, A. The role of fungi in the cocoa
production chain and the challenge of climate change. J. Fungi 2021, 7, 202. [CrossRef] [PubMed]
Cilas, C.; Bastide, P. Challenges to cocoa production in the face of climate change and the spread of pests and diseases. Agronomy
2020, 10, 1232. [CrossRef]
Cubillos, G. Frosty pod rot, disease that affects the cocoa (Theobroma cacao) crops in Colombia. Crop Prot. 2017, 96, 77–82.
[CrossRef]
10. Phillips-Mora, W.; Wilkinson, M. Frosty pod of cacao: A disease with a limited geographic range but unlimited potential for
damage. Phytopathology 2007, 97, 1644–1647. [CrossRef]
11. Guest, D. Black pod: Diverse pathogens with a global impact on cocoa yield. Phytopathology 2007, 97, 1650–1653. [CrossRef]
12. Lopes, J.; Costa, V.; Barbin, D.; Cruz-Tirado, L.; Baeten, V.; Barbon Junior, S. Deep computer vision system for cocoa classification.
Multimed. Tools Appl. 2022, 81, 41059–41077. [CrossRef]
Agriculture 2025, 15, 1032
24 of 27
13. Mamadou,D.; Kacoutchy, J.; Ballo, A.; Kouassi, B. Cocoa pods diseases detection by MobileNet confluence and classification
algorithms. Int. J. Adv. Comput. Sci. Appl. 2023, 14, 344–352. [CrossRef]
14. Ferraris, S.; Meo, R.; Pinardi, S.; Salis, M.; Sartor, G. Machine learning as a strategic tool for helping cocoa farmers in Côte D’Ivoire.
Sensors 2023, 23, 7632. [CrossRef]
15. Géron, A. Hands-on Machine Learning with Scikit-Learn, Keras, and TensorFlow: Concepts, Tools, and Techniques to Build Intelligent
Systems; O’Reilly Media, Inc.: Sebastopol, CA, USA, 2022.
16. Velásquez, D.; Sánchez, A.; Sarmiento, S.; Toro, M.; Maiza, M.; Sierra, B. A method for detecting coffee leaf rust through wireless
sensor networks, remote sensing, and deep learning: Case study of the Caturra variety in Colombia. Appl. Sci. 2020, 10, 697.
[CrossRef]
17. Benfenati, A.; Causin, P.; Oberti, R.; Stefanello, G. Unsupervised deep learning techniques for automatic detection of plant
diseases: Reducing the need of manual labelling of plant images. J. Math. Ind. 2023, 13, 5. [CrossRef]
18. Javidan, S.; Banakar, A.; Rahnama, K.; Vakilian, K.; Ampatzidis, Y. Feature engineering to identify plant diseases using image
processing and artificial intelligence: A comprehensive review. Smart Agric. Technol. 2024, 8, 100480 [CrossRef]
19. Page, M.; McKenzie, J.; Bossuyt, P.; Boutron, I.; Hoffmann, T.; Mulrow, C.; Shamseer, L.; Tetzlaff, J.; Akl, E.; Brennan, S.; et al.
Declaración PRISMA 2020: Una guía actualizada para la publicación de revisiones sistemáticas. Rev. Esp. De Cardiol. 2021, 74,
790–799. [CrossRef]
20. Abade, A.; Ferreira, P.; Barros Vidal, F. Plant diseases recognition on images using convolutional neural networks: A systematic
review. Comput. Electron. Agric. 2021, 185, 106125. [CrossRef]
21. Sajitha, P.; Andrushia, A.; Anand, N.; Naser, M. A review on machine learning and deep learning image-based plant disease
classification for industrial farming systems. J. Ind. Inf. Integr. 2024, 38, 100572 [CrossRef]
22. Teet, S.; Hashim, N. Recent advances of application of optical imaging techniques for disease detection in fruits and vegetables: A
review. Food Control 2023, 152, 109849. [CrossRef]
23. Ngugi, L.; Abelwahab, M.; Abo-Zahhad, M. Recent advances in image processing techniques for automated leaf pest and disease
recognition—A review. Inf. Process. Agric. 2021, 8, 27–51. [CrossRef]
24. Singh, V.; Sharma, N.; Singh, S. A review of imaging techniques for plant disease detection. Artif. Intell. Agric. 2020, 4, 229–242.
[CrossRef]
25. Shafik, W.; Tufail, A.; Namoun, A.; De Silva, L.; Apong, R. A systematic literature review on plant disease detection: Motivations,
classification techniques, datasets, challenges, and future trends. IEEE Access 2023, 11, 59174–59203. [CrossRef]
26. Doutoum, A.; Tugrul, B. A review of leaf diseases detection and classification by deep learning. IEEE Access 2023, 11,
119219–119230. [CrossRef]
27. Li, L.; Zhang, S.; Wang, B. Plant disease detection and classification by deep learning—A review. IEEE Access 2021, 9 56683–56698.
[CrossRef]
28. Joseph, D.; Pawar, P.; Pramanik, R. Intelligent plant disease diagnosis using convolutional neural network: A review. Multimed.
Tools Appl. 2023, 82, 21415–21481. [CrossRef]
29. Nasution, U.; Nababan, A.; Malik, J.; Budiarto, R.; Nainggolan, P.; Rahmat, R. Random Forest Classification in Cocoa Pods
Desease. In Proceedings of the 2023 7th International Conference on Electrical, Telecommunication and Computer Engineering
(ELTICOM), Medan, Indonesia, 13–14 December 2023; pp. 60–66.
30. Galindo, J.; Rosal, J.; Villaverde, J. Ripeness Classification of Cacao Using Cepstral-Based Statistical Features and Support Vector
Machine. In Proceedings of the 2022 IEEE International Conference on Artificial Intelligence In Engineering and Technology
(IICAIET), Kinabalu, Malaysia, 13–15 September 2022; pp. 1–5.
31. Kongor, J.; Owusu, M.; Oduro-Yeboah, C. Cocoa production in the 2020s: Challenges and solutions. CABI Agric. Biosci. 2024,
5, 102. [CrossRef]
32. Marelli, J.; Guest, D.; Bailey, B.; Evans, H.; Brown, J.; Junaid, M.; Barreto, R.; Lisboa, D.; Puig, A. Chocolate under threat from old
and new cacao diseases. Phytopathology 2019, 109, 1331–1343. [CrossRef]
33. Jiménez, D.; Alvarez, J.; Mosquera, S. Frosty pod rot: A major threat to cacao plantations on the move. Trop. Plant Pathol. 2021, 47,
187–200. [CrossRef]
34. Chocolates, C. La Moniliasis del Cacao: DañOs, Sintomas, EpidemiologíA Y Manejo. 2019. Available online: https://chocolates.
com.co/wp-content/uploads/2024/02/Cartilla_Monilia_CNCH_2019.pdf (accessed on 26 November 2024).
35. Decloquement, J.; Ramos-Sobrinho, R.; Elias, S.; Britto, D.; Puig, A.; Reis, A.; Da Silva, R.; Honorato-Júnior, J.; Luz, E.; Pinho, D.; et
al. Phytophthora theobromicola sp. nov.: A new species causing black pod disease on cacao in Brazil. Front. Microbiol. 2021, 12,
537399. [CrossRef] [PubMed]
36. Adeniyi, D. Diversity of cacao pathogens and impact on yield and global production. In Theobroma Cacao-Deploying Science for
Sustainability of Global Cocoa Economy; IntechOpen: London, UK, 2019; pp. 43–59.
Agriculture 2025, 15, 1032
25 of 27
37. Villamonte, A.; Silva, P.; Ronquillo, D.; Rosales, M.; Bandala, A.; Dadios, E. Python based defect classification of theobroma cacao
bean using fine-tuned visual geometry group16. In Proceedings of the 2021 IEEE 13th International Conference on Humanoid,
Nanotechnology, Information Technology, Communication and Control, Environment, and Management (HNICEM), Manila,
Philippines, 28–30 November 2021; pp. 1–6.
38. Godmalin, R.; Aliac, C.; Feliscuzo, L. Classification of cacao pod if healthy or attack by pest or black pod disease using deep
learning algorithm. In Proceedings of the 2022 IEEE International Conference on Artificial Intelligence in Engineering and
Technology (IICAIET), Kota Kinabalu, Malaysia, 13–15 September 2022; pp. 1–5.
39. Godmalin, R.; Aliac, C.; Feliscuzo, L. Cacao Pod Infection Level Classification Using Transfer Learning. In Proceedings of the 2023
IEEE Open Conference of Electrical, Electronic and Information Sciences (eStream), Vilnius, Lithuania, 27 April 2023; pp. 1–6.
40. Justam; Indrabayu; Zainuddin, Z.; Basri. Detection and Counting of the Number of Cocoa Fruits on Trees Using UAV. In
Proceedings of the 2023 IEEE International Conference on Industry 4.0, Artificial Intelligence, and Communications Technology
(IAICT), Bali, Indonesia, 13–15 July 2023; pp. 257–263.
41. Kumi,S.; Kelly, D.; Woodstuff, J.; Lomotey, R.; Orji, R.; Deters, R. Cocoa companion: Deep learning-based smartphone application
for cocoa disease detection. Procedia Comput. Sci. 2022, 203, 87–94. [CrossRef]
42. Achmad,A.; Areni, I.; Basri; Indrabayu. Classification Model Evaluation with Feature Extraction for Pest Attacks Identification
on Cocoa Pods. In Proceedings of the 2023 7th International Conference on New Media Studies (CONMEDIA), Bali, Indonesia,
6–8 December 2023; pp. 150–155.
43. Ayikpa,K.; Mamadou,D.; Gouton,P.; Adou, K.Classification of Cocoa Pod Maturity Using Similarity Tools on an Image Database:
Comparison of Feature Extractors and Color Spaces. Data 2023, 8, 99. [CrossRef]
44. Ayubi, A.; Faiz, M.; Situmorang, G.; Ramadhani, K.; Utama, N. A Cocoa Ripeness Detection and Classification Model Based on
Improved YOLOv5s. In Proceedings of the 2023 10th International Conference on Advanced Informatics: Concept, Theory and
Application (ICAICTA), Lombok, Indonesia, 7–9 October 2023; pp. 1–6.
45. Jintawatsakoon,S.; Inthachot, M.Classification of cocoabeancut-test imageusingstackedmachinelearningmodel. InProceedings
of the 2021 25th International Computer Science and Engineering Conference (ICSEC), Chiang Rai, Thailand, 18–20 November
2021; pp. 234–239.
46. Appiah, O.; Martey, E.; Ninfaakanga, C.; Agangiba, M. Content-Based Image Retrieval Framework for Classification of Cocoa
Beans. In Proceedings of the 2021 IEEE 8th International Conference on Adaptive Science and Technology (ICAST), Accra, Ghana,
25–26 November 2021; pp. 1–6.
47. Ekawaty, Y.; Indrabayu; Areni, I. Automatic cacao pod detection under outdoor condition using computer vision. In Proceedings
of the 2019 4th International Conference on Information Technology, Information Systems and Electrical Engineering (ICITISEE),
Yogyakarta, Indonesia, 20–21 November 2019; pp. 31–34.
48. Achmad,A.; Areni, I.; Basri; Indrabayu. Comparison of image extraction model for cocoa disease fruits attack in support vector
machine classification. In Proceedings of the 2022 International Conference on Electrical and Information Technology (IEIT),
Malang, Indonesia, 15–16 September 2022; pp. 46–51.
49. Montesino, R.; Rosales-Huamani, J.; Castillo-Sequera, J. Detection of phytophthora palmivora in cocoa fruit with deep learning.
In Proceedings of the 2021 16th Iberian Conference on Information Systems and Technologies (CISTI), Chaves, Portugal, 23–26
June 2021; pp. 1–4.
50. Vishnoi, V.; Kumar, K.; Kumar, B.; Mohan, S.; Khan, A. Detection of apple plant diseases using leaf images through convolutional
neural network. IEEE Access 2022, 11, 6594–6609. [CrossRef]
51. Acharya, V.; Ravi, V. Apple foliar leaf disease detection through improved capsule neural network architecture. Multimed. Tools
Appl. 2024, 83, 48585–48605.
52. Cui,R.; Li, J.; Wang, Y.; Fang, S.; Yu, K.; Zhao, Y. Hyperspectral imaging coupled with Dual-channel convolutional neural network
for early detection of apple valsa canker. Comput. Electron. Agric. 2022, 202, 107411. [CrossRef]
53. Khan,A.; Quadri, S.; Banday, S.; Shah, J. Deep diagnosis: A real-time apple leaf disease detection system based on deep learning.
Comput. Electron. Agric. 2022, 198, 107093. [CrossRef]
54. Liu, B.; Huang, X.; Sun, L.; Wei, X.; Ji, Z.; Zhang, H. MCDCNet: Multi-scale constrained deformable convolution network for
apple leaf disease detection. Comput. Electron. Agric. 2024, 222, 109028. [CrossRef]
55. Liu, Y.; Zhao, X.; Song, Z.; Yu, J.; Jiang, D.; Zhang, Y.; Chang, Q. Detection of apple mosaic based on hyperspectral imaging and
three-dimensional Gabor. Comput. Electron. Agric. 2024, 222, 109051. [CrossRef]
56. Hasan, S.; Jahan, S.; Islam, M. Disease detection of apple leaf with combination of color segmentation and modified DWT. J. King
Saud-Univ.-Comput. Inf. Sci. 2022, 34, 7212–7224. [CrossRef]
57. Gonzalez-Huitron, V.; León-Borges, J.; Rodriguez-Mata, A.; Amabilis-Sosa, L.; Rami´rez-Pereda, B.; Rodriguez, H. Disease
detection in tomato leaves via CNN with lightweight architectures implemented in Raspberry Pi 4. Comput. Electron. Agric. 2021,
181, 105951. [CrossRef]
Agriculture 2025, 15, 1032
26 of 27
58. Karthik, R.; Hariharan, M.; Anand, S.; Mathikshara, P.; Johnson, A.; Menaka, R. Attention embedded residual CNN for disease
detection in tomato leaves. Appl. Soft Comput. 2020, 86, 105933.
59. Aishwarya, N.; Praveena, N.; Priyanka, S.; Pramod, J. Smart farming for detection and identification of tomato plant diseases
using light weight deep neural network. Multimed. Tools Appl. 2023, 82, 18799–18810. [CrossRef]
60. Daniya,T.; Vigneshwari, S. A novel Moore-Penrose pseudo-inverse weight-based Deep Convolution Neural Network for bacterial
leaf blight disease detection system in rice plant. Adv. Eng. Softw. 2022, 174, 103336. [CrossRef]
61. Singh, S.; Pritamdas, K.; Devi, K.; Devi, S. Custom convolutional neural network for detection and classification of rice plant
diseases. Procedia Comput. Sci. 2023, 218, 2026–2040. [CrossRef]
62. Tyagi, S.; Reddy, S.; Anand, R.; Sabharwal, A. Enhancing rice crop health: A light weighted CNN-based disease detection system
with mobile application integration. Multimed. Tools Appl. 2024, 83, 48799–48829. [CrossRef]
63. Nayak,A.; Chakraborty, S.; Swain, D. Application of smartphone-image processing and transfer learning for rice disease and
nutrient deficiency detection. Smart Agric. Technol. 2023, 2023, 4. [CrossRef]
64. Bijoy, M.; Hasan, N.; Biswas, M.; Mazumdar, S.; Jimenez, A.; Ahmed, F.; Rasheduzzaman, M.; Momen, S. Towards Sustainable
Agriculture: A Novel Approach for Rice Leaf Disease Detection Using dCNN and Enhanced Dataset. IEEE Access 2024, 12,
34174–34191. [CrossRef]
65. Agarwal, M.; Singh, A.; Arjaria, S.; Sinha, A.; Gupta, S. ToLeD: Tomato leaf disease detection using convolution neural network.
Procedia Comput. Sci. 2020, 167, 293–301. [CrossRef]
66. Huang,X.; Chen, A.; Zhou, G.; Zhang, X.; Wang, J.; Peng, N.; Yan, N.; Jiang, C. Tomato leaf disease detection system based on
FC-SNDPN. Multimed. Tools Appl. 2023, 82, 2121–2144. [CrossRef]
67. Karki, S.; Basak, J.; Tamrakar, N.; Deb, N.; Paudel, B.; Kook, J.; Kang, M.; Kang, D.; Kim, H. Strawberry disease detection using
transfer learning of deep convolutional neural networks. Sci. Hortic. 2024, 332, 113241. [CrossRef]
68. Mahmud,M.;Zaman,Q.;Esau, T.; Price, G.; Prithiviraj, B. Development of an artificial cloud lighting condition system using
machine vision for strawberry powdery mildew disease detection. Comput. Electron. Agric. 2019, 158, 219–225. [CrossRef]
69. Zhao, S.; Liu, J.; Wu, S. Multiple disease detection method for greenhouse-cultivated strawberry based on multiscale feature
fusion Faster R_CNN. Comput. Electron. Agric. 2022, 199, 107176. [CrossRef]
70. VanDeVijver, R.; Mertens, K.; Heungens, K.; Somers, B.; Nuyttens, D.; Borra-Serrano, I.; Lootens, P.; Roldán-Ruiz, I.; Vangeyte, J.;
Saeys, W. In-field detection of Alternaria solani in potato crops using hyperspectral imaging. Comput. Electron. Agric. 2020, 168,
105106. [CrossRef]
71. Singh, G.; Yogi, K. Comparison of RSNET model with existing models for potato leaf disease detection. Biocatal. Agric. Biotechnol.
2023, 50, 102726. [CrossRef]
72. Reis, H.; Turk, V. Potato leaf disease detection with a novel deep learning model based on depthwise separable convolution and
transformer networks. Eng. Appl. Artif. Intell. 2024, 133, 108307. [CrossRef]
73. Paul, H.; Ghatak, S.; Chakraborty, S.; Pandey, S.; Dey, L.; Show, D.; Maity, S. A study and comparison of deep learning based
potato leaf disease detection and classification techniques using explainable AI. Multimed. Tools Appl. 2024, 83, 42485–42518.
[CrossRef]
74. Shin, J.; Chang, Y.; Heung, B.; Nguyen-Quang, T.; Price, G.; Al-Mallahi, A. A deep learning approach for RGB image-based
powdery mildew disease detection on strawberry leaves. Comput. Electron. Agric. 2021, 183, 106042. [CrossRef]
75. Nandhini, M.; Kala, K.; Thangadarshini, M.; Verma, S. Deep Learning model of sequential image classifier for crop disease
detection in plantain tree cultivation. Comput. Electron. Agric. 2022, 197, 106915. [CrossRef]
76. Mishra, S.; Sachan, R.; Rajpal, D. Deep convolutional neural network based detection system for real-time corn plant disease
recognition. Procedia Comput. Sci. 2020, 167, 2003–2010. [CrossRef]
77. Singh, P.; Kumar, D.; Srivastava, A.; Basumatary, M.; Prasad, S. A CNN Model Based Approach for Disease Detection in Mango
Plant Leaves. In International Conference on Soft Computing For Problem-Solving; Springer Nature: Singapore, 2023; pp. 389–399.
78. Almoujahed, M.; Rangarajan, A.; Whetton, R.; Vincke, D.; Eylenbosch, D.; Vermeulen, P.; Mouazen, A. Detection of fusarium head
blight in wheat under field conditions using a hyperspectral camera and machine learning. Comput. Electron. Agric. 2022, 203,
107456. [CrossRef]
79. Weng,S.; Han, K.; Chu, Z.; Zhu, G.; Liu, C.; Zhu, Z.; Zhang, Z.; Zheng, L.; Huang, L. Reflectance images of effective wavelengths
from hyperspectral imaging for identification of Fusarium head blight-infected wheat kernels combined with a residual attention
convolution neural network. Comput. Electron. Agric. 2021, 190, 106483. [CrossRef]
80. Macdonald, W.; Sari, Y.; Pahlevani, M. Grow-light smart monitoring system leveraging lightweight deep learning for plant
disease classification. Artif. Intell. Agric. 2024, 12, 44–56. [CrossRef]
81. Tanwar, S.; Singh, J. ResNext50 based convolution neural network-long short term memory model for plant disease classification.
Multimed. Tools Appl. 2023, 82, 29527–29545. [CrossRef]
82. Argüeso, D.; Picon, A.; Irusta, U.; Medela, A.; San-Emeterio, M.; Bereciartua, A.; Alvarez-Gila, A. Few-Shot Learning approach for
plant disease classification using images taken in the field. Comput. Electron. Agric. 2020, 175, 105542. [CrossRef]
Agriculture 2025, 15, 1032
27 of 27
83. Bouacida, I.; Farou, B.; Djakhdjakha, L.; Seridi, H.; Kurulay, M. Innovative deep learning approach for cross-crop plant disease
detection: A generalized method for identifying unhealthy leaves. Inf. Process. Agric. 2024, 12, 54–67. [CrossRef]
84. Hernández, S.; López, J. Uncertainty quantification for plant disease detection using Bayesian deep learning. Appl. Soft Comput.
2020, 96, 106597. [CrossRef]
85. Zhao, Y.; Sun, C.; Xu, X.; Chen, J. RIC-Net: A plant disease classification model based on the fusion of Inception and residual
structure and embedded attention mechanism. Comput. Electron. Agric. 2022, 193, 106644. [CrossRef]
86. Adnan,F.; Awan, M.; Mahmoud, A.; Nobanee, H.; Yasin, A.; Zain, A. EfficientNetB3-adaptive augmented deep learning (AADL)
for multi-class plant disease classification. IEEE Access 2023, 11, 85426–85440. [CrossRef]
87. Balafas, V.; Karantoumanis, E.; Louta, M.; Ploskas, N. Machine learning and deep learning for plant disease classification and
detection. IEEE Access 2023, 11, 114352–114377. [CrossRef]
88. Tabbakh, A.; Barpanda, S. A deep features extraction model based on the transfer learning model and vision transformer “tlmvit”
for plant disease classification. IEEE Access 2023, 11, 45377–45392. [CrossRef]
89. Srivastava, M.; Meena, J. Plant leaf disease detection and classification using modified transfer learning models. Multimed. Tools
Appl. 2024, 83, 38411–38441. [CrossRef]
90. Kamal,K.; Yin, Z.; Wu, M.; Wu, Z. Depthwise separable convolution architectures for plant disease classification. Comput. Electron.
Agric. 2019, 165, 104948.
91. Ahmad,W.; Adnan, S.; Irtaza, A. Local triangular-ternary pattern: A novel feature descriptor for plant leaf disease detection.
Multimed. Tools Appl. 2024, 83, 20215–20241. [CrossRef]
92. Sharma, V.; Tripathi, A.; Mittal, H. DLMC-Net: Deeper lightweight multi-class classification model for plant leaf disease detection.
Ecol. Inform. 2023, 75, 102025. [CrossRef]
93. HameedAl-bayati, J.; Üstünda˘g, B. Evolutionary feature optimization for plant leaf disease detection by deep neural networks.
Int. J. Comput. Intell. Syst. 2020, 13, 12–23. [CrossRef]
94. Moupojou, E.; Tagne, A.; Retraint, F.; Tadonkemwa, A.; Wilfried, D.; Tapamo, H.; Nkenlifack, M. FieldPlant: A dataset of field
plant images for plant disease detection and classification with deep learning. IEEE Access 2023, 11, 35398–35410. [CrossRef]
95. Maurya, R.; Mahapatra, S.; Rajput, L. A lightweight meta-ensemble approach for plant disease detection suitable for IOT-based
environments. IEEE Access 2024, 12, 28096–28108. [CrossRef]
96. Ahmad,M.;Abdullah, M.; Moon, H.; Han, D. Plant disease detection in imbalanced datasets using efficient convolutional neural
networks with stepwise transfer learning. IEEE Access 2021, 9, 140565–140580. [CrossRef]
Disclaimer/Publisher’s Note: The statements, opinions and data contained in all publications are solely those of the individual
author(s) and contributor(s) and not of MDPI and/or the editor(s). MDPI and/or the editor(s) disclaim responsibility for any injury to
people or property resulting from any ideas, methods, instructions or products referred to in the content.