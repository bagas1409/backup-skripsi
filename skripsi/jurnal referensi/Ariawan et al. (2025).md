Indonesian Journal of Data and Science 
Volume 6 Issue 1 
ISSN 2715-9936 
https://doi.org/10.56705/ijodas.v6i1.233 
Research Article 
Performance Comparasion of DenseNet-121 and 
MobileNetV2 for Cacao Fruit Disease Image Classification 
Kadek Rizki Ariawan 1,*, Anak Agung Gde Ekayana 2, I Putu Yoga Indrawan 3, Komang Redy 
Winatha 4, I Nyoman Anom Fajaraditya Setiawan 5 
1 Institut Bisnis dan Teknologi Indonesia, Bali 80225, Indonesia, rizkiariawan2203@gmail.com 
2 Institut Bisnis dan Teknologi Indonesia, Bali 80225, Indonesia, gungekayana@instiki.ac.id 
3 Institut Bisnis dan Teknologi Indonesia, Bali 80225, Indonesia, yoga.indrawan@instiki.ac.id 
4 Institut Bisnis dan Teknologi Indonesia, Bali 80225, Indonesia, redwin@instiki.ac.id 
5 Institut Bisnis dan Teknologi Indonesia, Bali 80225, Indonesia, anomkojar@instiki.ac.id 
Correspondence should be addressed to Kadek Rizki Ariawan; rizkiariawan2203@gmail.com 
Received 02 December 2025; Accepted 22 March 2025; Published 31 March 2025 
© Authors 2025. CC BY-NC 4.0 (non-commercial use with attribution, indicate changes).  
License: https://creativecommons.org/licenses/by-nc/4.0/ — Published by Indonesian Journal of Data and Science. 
Abstract: 
Introduction: Cacao fruit diseases significantly impact cocoa yield and quality in Indonesia. Early detection is critical, 
yet traditional methods are often time-consuming and error-prone due to the visual similarity of disease symptoms. 
This study aims to compare the performance of two Convolutional Neural Network (CNN) architectures—DenseNet
121 and MobileNetV2—for automated image classification of cacao fruit diseases. Methods: The dataset comprises 
8000 images augmented from 2000 original photos taken in cocoa plantations in Bali, categorized into four classes: 
fruit rot, fruit-sucking pests, pod borers, and healthy fruits. Both CNN models were trained using the Adam optimizer, 
a learning rate of 0.001, and a dropout rate of 0.4. The input images were resized to 224×224 pixels. Evaluation metrics 
included accuracy, precision, recall, and F1-score. Results: DenseNet-121 outperformed MobileNetV2 across all 
metrics. DenseNet-121 achieved an accuracy of 94.50%, precision of 94.75%, recall of 94.25%, and F1-score of 
94.50%. In comparison, MobileNetV2 reached an accuracy of 93.88%. Although MobileNetV2 offered faster training 
time and lower model complexity, DenseNet-121 demonstrated superior feature extraction and stability, supported by 
its deeper architecture and greater parameter capacity. Conclusions: DenseNet-121 is more effective than 
MobileNetV2 in classifying cacao fruit diseases, providing higher accuracy and robustness. Despite requiring more 
computational resources, it is better suited for developing a web-based cocoa disease detection tool to assist farmers 
in timely and accurate disease identification. 
Keywords: Convolutional Neural Network, DenseNet-121, Image Classification, Kakao Fruit Disease, MobileNetV2. 
1. Introduction 
Cacao is one of the most important plantation commodities for the Indonesian economy. The potential of the 
cacao industry to drive economic growth and income distribution is highly promising, as cacao is a key export 
commodity that significantly contributes to foreign exchange [1]. According to the latest data from the Central 
Bureau of Statistics of Bali Province, cacao ranks as the second most important plantation commodity in Bali after 
coffee, with a production of 4.9 thousand tons in 2023, compared to coffee's 14.6 thousand tons. Cacao plays a 
strategic role in the regional economy, particularly benefiting farmers in Jembrana, Tabanan, and Buleleng. The 
increasing global demand for organic and sustainable cacao presents promising export opportunities for Balinese 
cacao. 
In Indonesia, cocoa is cultivated in various regions, one of which is Bali. Cocoa usually starts to bear fruit at 
the age of 4 years [2]. Despite its economic potential, cacao production is often affected by various plant diseases 
and pests, leading to yield losses of up to 50–80% [3], [4]. One of the most severe diseases affecting cacao 
production is cacao pod disease, which directly reduces crop yield [5]. There are three primary diseases that impact 
cacao pods. The first is fruit rot caused by the Phytophthora palmivora fungus. Additionally, fruit-sucking pests 
29 
30  
Indonesian Journal of Data and Science 
(Helopeltis) and pod borers (Conopomorpha cramerella) also pose significant threats, reducing both the quality 
and quantity of cacao production [6]. 
Currently, many farmers still rely on conventional observation methods to identify cacao diseases. This manual 
approach is time-consuming and labor-intensive, with identification results often varying based on the skill level 
of the observer. Moreover, certain cacao diseases exhibit highly similar symptoms, making differentiation difficult 
[7], [8]. To address these challenges, artificial intelligence (AI) technology presents a reliable solution. AI-based 
approaches enable farmers to accurately detect various types of pests and diseases, improving early identification 
and disease management [9]. The development of an automatic cacao fruit disease identification system requires 
an effective classification model. The accuracy and efficiency of this classification model are crucial to ensuring 
reliable disease detection [10], [11]. One of the most widely used methods for image classification is the 
Convolutional Neural Network (CNN), a deep learning algorithm particularly effective in image processing tasks 
[12], [13].  
While previous studies have explored deep learning models for plant disease classification, research 
specifically comparing CNN architectures for cacao disease classification remains limited. Most prior studies 
focus on general plant disease identification without assessing the suitability of different CNN architectures for 
cacao fruit disease detection. This research aims to fill that gap by comparing the performance of two CNN 
models, MobileNetV2 and DenseNet-121, in classifying cacao fruit diseases. By analysing these models, this 
study provides insights into the most suitable architecture for accurately detecting cacao diseases. 
This study compares the performance of CNN architectures, MobileNetV2 and DenseNet-121, in cacao fruit 
disease classification. The dataset consists of 2000 cacao fruit images categorized into four classes: fruit rot 
(Phytophthora Palmira), fruit-sucking pests (Heliopolis), pod borers (Copromorphid camarilla), and healthy fruit. 
The objective is to develop a model with high classification accuracy for cacao fruit diseases. The best-performing 
model from this research will be implemented in a web-based cacao disease detection system to assist farmers in 
diagnosing and managing cacao diseases effectively. 
2. Method: 
Figure 1. Research flow 
Research was conducted in several stages. First, the dataset is collected. Next, the data pre-processing stage 
aims to improve or prepare the data to be ready for further processing. The flowchart shows the steps that are 
taken to classify cocoa fruit diseases using a deep learning-based method. Next, data augmentation is performed 
to increase the amount and variety of training data. Techniques such as random rotation, vertical flip, horizontal 
flip, and zooming in are used to enhance the image center. After augmentation, the data is divided into data sharing 
stages, which consist of 80 percent, 10 percent, and 10 percent for training and testing, respectively. Modeling is 
the next stage where two popular CNN architectures, MobileNetV2 and DenseNet-121, are used to train the model 
of classification. MobileNetV2 was chosen because it is able to handle devices with limited computing resources, 
while DenseNet-121 offers more complex inter-layer connections, which allows for deeper feature utilization. 
Model training was performed using Adam's optimizer to optimize the model weight. After the Model 
Performance Evaluation stage, the accuracy and reliability of the trained model are evaluated using metrics such 
as precision, accuracy, recall, and F1-Score. The next step is the comparison of evaluation results, where the 
results of the MobileNetV2 and DenseNet-121 models are compared based on the metrics of evaluation. A 
comparison is made to determine which model best performs in classifying cacao fruit diseases. The final step is 
system design. 
31  
Indonesian Journal of Data and Science 
Data Selection 
The primary data used in this study was collected on cocoa plantations in the Penebel region of Tabanan, Bali. The 
images were taken using a Redmi 13C mobile phone camera with a resolution of 50MP taken in a portrait position. The 
images taken were images of ripe and unripe cocoa fruit. Images were taken from various positions, such as from the front, 
back, and side. in the process of taking pictures directly assisted by cocoa farmers in the garden. The results of the data 
collected are image data of diseased cocoa fruit and healthy cocoa fruit images, which consist of 2000 original image data 
and are divided into 4 classes, namely, fruit rot disease (Phytophthora palmivora), fruit sucking pest (Helopeltis), fruit borer 
(Conopomorpha cramerella), and healthy fruit. 
Figure 2. (A) Fruit rot (Phytophthora palmivora), (B) pod borer (Conopomorpha cramerella), (C) fruit-sucking pest 
(Helopeltis), (D) healthy fruit. 
Tools and Technology Used 
This research utilizes technologies and tools to train, build, and evaluate models namely: 
a. Program language: Python 
b. Adam optimizer  
c. Deep Learning Framework: TensorFlow and Keras 
d. Trained Models: DenseNet-121 and MobileNetV2 
e. Augmentation Technique: ImageDataGenerator to provide image variability during the training process. 
f. 
Number of epochs: 25 
g. Batch size: 32 
h. ReLU activation function 
i. 
Dropout :0.4 
Pre-processing Data 
Pre-processing is a process used to process the original image data before further image data processing is 
carried out. The data pre-processing stage aims to prepare the data to fit the needs of the model, reduce noise, 
align the scale, and ensure dimensional consistency. In this study using data pre-processing by applying resizing 
techniques. The data is resized to 224×224 pixels, by using the same dimensions, the transfer learning results 
become more accurate and provide input size consistency, as well as reduce computational load without losing 
important information. 
Data Augmentation 
Augmentation is a technique in machine learning that is used to expand the training dataset by creating new variations 
of existing data [14]. By using augmentation, the model not only learns from the original data  but also from the modified 
data. This helps the model to be more generalist in recognizing patterns so it can perform better when encountering data that 
is different from the trained data. In addition, augmentation also reduces the possibility of overfitting, which is a condition 
when the model is over trained on training data so that it performs poorly on new, unfamiliar data [15], [16], [17]. In this 
research, the augmentation method used is geometric transformation, which provides variations in the position of objects, 
such as rotation, vertical flip, horizontal flip, and zooming in. This technique provides a variety of object positions in the 
32  
Indonesian Journal of Data and Science 
dataset so that the model can be better able to handle differences in viewpoint, size, or object orientation in the actual data. 
From the original data of 2000 images after augmentation to as many as 8000 images. 
Model DenseNet-121 
DenseNet-121 is a CNN (Convolutional Neural Network) architecture intended to improve feature utilization 
and make the flow of information easier through different layers of the network [18], [19], [20]. In this 
architecture, each layer or block uses a feed-forward mechanism to connect with all other layers or blocks. The 
main elements of each DenseNet layer include batch normalization, the ReLU activation function, and a 
convolution operation with 3×3 filters. Batch normalization to speed up the training process and allow higher 
learning rates during model building. Each block receives a matrix representing image pixels as input. This matrix 
is then processed using batch normalization to reduce the possibility of overfitting during the training process 
[21], [22], [23]. 
Figure 3. DenseNet-121 Architecture 
Model MobileNetV2 
MobileNetV2 is a deep neural network architecture called CNN (Convolutional Neural Network) created by 
Google and intended for devices that have limited computing capacity, such as mobile phones, Internet of Things 
devices, and real-time systems [24], [25]. This architecture aims to achieve high efficiency in computation usage, 
memory, and model size while still maintaining optimal accuracy [26]. MobileNetV2 introduces an inverted 
residual block, where the small input channel dimensions are enlarged using 1×1 convolution, then processed 
through depthwise convolution on each channel, and finally returned to small dimensions using 1×1 linear 
convolution. The architecture also uses depthwise separable convolution, which splits the convolution operation 
into two stages: depth wise convolution to process each channel separately and pointwise convolution (1×1) to 
combine the information between channels. Finally, MobileNetV2 applies a linear bottleneck (without ReLU 
activation) to prevent the loss of important information when channels are minimized [27], [28]. With this 
approach, MobileNetV2 becomes highly computationally and memory efficient, making it ideal for applications 
on mobile devices or real-time systems such as computer vision [29], [30], [31]. 
Figure 4. MobileNetV2 Architecture 
33  
Indonesian Journal of Data and Science 
Data Analysis Method 
The evaluation results will compare data using the DenseNet-121 and MobileNetV2 models in cocoa fruit 
disease classification. Model performance evaluation uses the main metrics, namely precision, accuracy, recall, 
and F1-score, using the Adam optimizer. In addition to using confusion matrix evaluation, there are several other 
benchmarks that can be used to determine the weaknesses and strengths of the model, including the loss value to 
measure the error rate of the model during training and validation. Time: This refers to the time required for the 
model to perform the training process. Model complexity (number of parameters) Model complexity is seen from 
the number of parameters that affect efficiency and memory requirements. Size/computation required measures 
the hardware requirements, such as memory and computing power, to run the model optimally. 
System Design 
After evaluating the performance of the two models, the model that produces better accuracy will be used to 
be further developed in the creation of a simple web-based cocoa fruit disease detection system. The system is 
expected to assist farmers in identifying cocoa fruit diseases quickly so as to enable the implementation of more 
timely and efficient control measures. With this system, cocoa fruit disease detection can be done automatically 
and increase productivity and quality of crops 
3. Results and Discussion 
Results 
The following is a table of model evaluation results: 
Table 1. Evaluation Results of DenseNet-121 and MobileNetV2 Models 
Model 
Learning Rate 
Optimizer 
Accuracy 
Precission 
Recall 
F1-Score 
DenseNet-121 
0.001 
Adam 
0.9388 
0.9400 
0.9375 
0.9375 
MobileNetV2 
0.001 
Adam 
0.9450 
0.9475 
0.9425 
0.9450 
The performance comparison between MobileNetV2 and DenseNet-121 shows that DenseNet-121 has better 
performance than MobileNetV2. The accuracy of DenseNet-121 (94.50%) is higher than MobileNetV2 (93.88%), 
indicating that this model makes correct predictions more often. Precision, recall, and F1-score are also higher for 
DenseNet-121, meaning that the model is better at recognizing each class more equally. MobileNetV2 still 
performed well, but slightly lower than DenseNet-121. 
Benchmark the weaknesses and advantages of each model as follows: 
a. 
b. 
c. 
Loss Value Comparison: DenseNet-121 has a training loss of 0.1877, while MobileNetV2 has a training 
loss of 0.2204. This shows that DenseNet-121 is faster at learning from training data than MobileNetV2. 
The validation loss of DenseNet-121 is more stable than MobileNetV2, which experiences larger 
fluctuations, which means that DenseNet-121 is better at generalizing to new data. 
Training Time Comparison: MobileNetV2 requires 895.23 seconds or 14.92 minutes to complete the 
training process. While DenseNet-121 takes 1016.52 seconds, or 16.94 minutes, longer than 
MobileNetV2. MobileNetV2 is about 121.29 seconds or 2.02 minutes faster than DenseNet-121, 
indicating that the MobileNetV2 architecture is more lightweight and computationally efficient. 
Model Complexity Comparison (Number of Parameters): MobileNetV2 has a total of 2.42 million 
parameters, while DenseNet-121 has 7.17 million parameters. MobileNetV2 is much lighter, with about 
3 times fewer parameters than DenseNet-121. 
d. Comparison of Model Size or Computation: MobileNetV2 has a size of 11.1 MB, while DenseNet-121 
has a size of 29.62 MB. MobileNetV2 is much lighter, with about 3 times fewer parameters than 
DenseNet-121. DenseNet-121 is more complex, requiring more memory and computation, but offers 
better accuracy and stability. 
DenseNet-121 performs better because its architecture is more complex and efficient in capturing patterns in 
cocoa disease images. The main advantage of DenseNet-121 is that the connections between layers are dense, so 
each layer receives information from all previous layers. This allows the model to reuse learned features, capture 
patterns better, and maintain learning stability. Its larger number of parameters (7.17 million compared to 2.42 
34  
Indonesian Journal of Data and Science 
million in MobileNetV2) gives the model a higher capacity to understand image details, although it requires more 
computing power. In addition, the structure of DenseNet-121 helps maintain gradient stability, reduces overfitting, 
and results in higher accuracy. With efficient use of features and stability in training, DenseNet-121 is superior in 
cocoa disease classification, although it requires more resources than MobileNetV2. 
Figure 5. Confusion Matrix DenseNet-121 Without (Left) and MobileNetV2 With (Right) 
Figure 6. Accuracy and Loss DenseNet-121 Without (Left) and MobileNetV2 With (Right) 
Figure 7. Number of Parameters DenseNet-121 Without (Left) and MobileNetV2 With (Right) 
Discussion 
According to the results shown in Table 1, DenseNet-121 achieves a higher accuracy of 94.50% than 
MobileNetV2, which only achieves 93.88%. DenseNet-121 has a higher precision value than MobileNetV2, with 
a rating of 94.75 compared to MobileNetV2's 94.00. Finally, the F1-Score value shows that DenseNet-121 is also 
higher at 94.50 and MobileNetV2 is only 93.75, while the recall value shows that DenseNet-121 is also higher at 
94.25 and MobileNet is only 93.75. This demonstrates that MobileNetV2 is not as effective as the DenseNet-121 
model. 
When the benefits and drawbacks of each model are compared, it is evident that the DenseNet-121 model 
performs better during training since it has advantages in contrast to a lesser training loss value. Compared to 
MobileNetV2, which saves time, it has fewer parameters, which reduces computation even though MobileNetV2 
has drawbacks in a higher loss value. However, it has drawbacks in a greater number of parameters, a longer 
training period, and a significant amount of computation. 
35  
Indonesian Journal of Data and Science 
DenseNet-121 is superior to MobileNetV2 because its more complex architecture allows for more efficient 
utilization of information. It utilizes tighter inter-layer connections, thus retaining more information from previous 
data. With a larger number of parameters, DenseNet-121 is able to recognize more complex patterns, resulting in 
higher accuracy. In addition, its structure also helps reduce overfitting, making the model more stable when tested 
with new data. In contrast, MobileNetV2 is lighter and faster, but the sacrifice in the number of parameters makes 
it less accurate than DenseNet-121. 
4. Conclusion 
This study shows that the CNN architecture DenseNet-121 performs better than MobileNetV2 in classifying 
cocoa fruit diseases. Using a dataset of 8000 augmented images divided into four classes, both models were tested 
for performance. The evaluation results show that DenseNet-121 has a testing accuracy of 94.50%, slightly higher 
than MobileNetV2, which reaches 93.88%. In addition, DenseNet-121 also excels in other evaluation metrics such 
as precision, recall, and F1 score, which are higher than MobileNetV2. In terms of learning efficiency, DenseNet
121 has a lower training loss value (0.1877) than MobileNetV2 (0.2204), which indicates that the model 
understands the patterns from the training data faster. However, in terms of training time, MobileNetV2 is faster 
with 14.92 minutes, while DenseNet-121 takes 16.94 minutes. In terms of model complexity, MobileNetV2 has 
2.42 million parameters, much lighter than DenseNet-121, which has 7.17 million parameters. Likewise, in terms 
of model size, MobileNetV2 is only 11.1 MB, while DenseNet-121 reaches 29.62 MB. Despite being larger and 
more complex, DenseNet-121 is able to provide more accurate and stable results. Because DenseNet-121 uses 
information more intelligently than MobileNetV2, it performs better overall. By linking each layer to the one 
before it, it is able to identify patterns more precisely and in more detail. DenseNet-121 is more accurate in 
identifying cocoa disease when it has more parameters because it can extract more characteristics from the image. 
References: 
[1] 
[2] 
[3] 
[4] 
[5] 
[6] 
[7] 
[8] 
[9] 
D. Sihwinarti, A. J. Darmawan, A. Heptariza, I. Made, S. Ramayu, and K. N. Erawati, “Zero Waste Circular 
Economy: Transforming Chocolate Production into Chocolate Jam in Bali,” Jurnal Ekonomi, vol. 13, p. 
2024, doi: 10.54209/ekonomi.v13i02. 
L. Fudjaja, R. Ryadha, Saadah Saadah, N. M. Viantika, M. Ridwan, and R. Darma, “Fostering cocoa 
industry resilience: A collaborative approach to managing farm gate price fluctuations in West Sulawesi, 
Indonesia,” Open Agric, vol. 9, no. 1, Jan. 2024, doi: 10.1515/opag-2022-0312. 
D. S. Arsyad et al., “A one health exploration of the reasons for low cocoa productivity in West Sulawesi,” 
One Health, vol. 8, Dec. 2019, doi: 10.1016/j.onehlt.2019.100107. 
P. M. Etaware, “Some Identifiable Factors Responsible for the Variation in Cocoa Production in Nigeria 
and Other Cocoa Producing Nations, Adjudicated by Their Contributions to the Global Market,” Frontiers 
in Agronomy, vol. 4, Mar. 2022, doi: 10.3389/fagro.2022.731019. 
C. Cilas and P. Bastide, “Challenges to Cocoa Production in the Face of Climate Change and the Spread 
of Pests and Diseases,” Agronomy, vol. 10, no. 9, Sep. 2020, doi: 10.3390/agronomy10091232. 
E. Tovurawa, B. Dlamini, S. E. Moore, V. Marivate, and A. Modupe, “Cacao Plant Disease Detection and 
Classification,” Jan. 07, 2025. doi: 10.21203/rs.3.rs-5763786/v1. 
S. P. M. Reis et al., “Genome-Wide Analysis of Moniliophthora roreri Facilitates the Development of 
Species-Specific Primers for Biomonitoring Frosty Pod Rot of Cacao,” PhytoFrontiersTM, Jan. 2025, doi: 
10.1094/PHYTOFR-03-24-0032-R. 
E. C. S. San Diego, S. G. C. Rodrin, and E. R. Arboleda, “Classification Of Prominent Cacao Pod Diseases 
Using Multi-Feature Visual Analysis And K-Nearest Neighbors Algorithm,” Journal of Engineering and 
Technology for Industrial Applications, vol. 11, no. 51, pp. 28–34, Feb. 2025, doi: 
10.5935/jetia.v11i51.1367. 
E. A. Iñiguez Freites, “Automated Detection of the Main Pests in Cocoa Crops (&lt;em&gt;Theobroma 
cacao&lt;/em&gt; L.) and Potential Natural Enemies Through Computerized Monitoring in the Dominican 
Republic,” Feb. 26, 2025. doi: 10.20944/preprints202502.2119.v1. 
36  
Indonesian Journal of Data and Science 
[10] Z. Gao, Y. Tian, S.-C. Lin, and J. Lin, “A CT Image Classification Network Framework for Lung Tumors 
Based on Pre-trained MobileNetV2 Model and Transfer learning, And Its Application and Market Analysis 
in the Medical field.”, 2025, doi: 10.48550/arXiv.2501.04996. 
[11] R. Archana and P. S. E. Jeevaraj, “Deep learning models for digital image processing: a review,” Artif 
Intell Rev, vol. 57, no. 1, Jan. 2024, doi: 10.1007/s10462-023-10631-z. 
[12] J. Lu, L. Tan, and H. Jiang, “Review on convolutional neural network (CNN) applied to plant leaf disease 
classification,” Aug. 01, 2021, MDPI AG. doi: 10.3390/agriculture11080707. 
[13] A. A. Elngar et al., “Image Classification Based On CNN: A Survey,” Journal of Cybersecurity and 
Information Management (JCIM), vol. 6, no. 1, p. 18, 2021, doi: 10.5281/zenodo.4897990. 
[14] A. A. Khan, O. Chaudhari, and R. Chandra, “A review of ensemble learning and data augmentation models 
for class imbalanced problems: Combination, implementation and evaluation,” Jun. 15, 2024, Elsevier Ltd. 
doi: 10.1016/j.eswa.2023.122778. 
[15] Z. Wang et al., “A Comprehensive Survey on Data Augmentation,” May 2024, doi: 
10.48550/arXiv.2405.09591. 
[16] T. Kumar, A. Mileo, R. Brennan, and M. Bendechache, “Image Data Augmentation Approaches: A 
Comprehensive Survey and Future directions,” Jan. 2023, doi: 10.1109/ACCESS.2024.3470122. 
[17] M. D’incà, C. Tzelepis, I. Patras, and N. Sebe, “Improving Fairness using Vision-Language Driven Image 
Augmentation.”, 2024, doi: 10.48550/arXiv.2311.01573. 
[18] H. P. Hadi, E. H. Rachmawanto, and R. R. Ali, “Comparison of DenseNet-121 and MobileNet for Coral 
Reef Classification,” MATRIK : Jurnal Manajemen, Teknik Informatika dan Rekayasa Komputer, vol. 23, 
no. 2, pp. 333–342, Mar. 2024, doi: 10.30812/matrik.v23i2.3683. 
[19] A. Bello, S. C. Ng, and M. F. Leung, “Skin Cancer Classification Using Fine-Tuned Transfer Learning of 
DENSENET-121,” Applied Sciences (Switzerland), vol. 14, no. 17, Sep. 2024, doi: 10.3390/app14177707. 
[20] S. Chakraborty, A. Roy, P. Pramanik, D. Valenkova, and R. Sarkar, “A Dual Attention-aided DenseNet
121 for Classification of Glaucoma from Fundus Images,” Jun. 2024, doi: 10.48550/arXiv.2406.15113. 
[21] M. A. Mutasodirin and F. M. Falakh, “Efficient Weather Classification Using DenseNet and EfficientNet,” 
Jurnal Informatika: Jurnal Pengembangan IT, vol. 9, no. 2, pp. 173–179, Aug. 2024, doi: 
10.30591/jpit.v9i2.7539. 
[22] J. A. Patel, G. V. Lakhani, R. K. Vaghela, and D. L. Labana, “DenseMobile Net: Deep Ensemble Model 
for Precision and Innovation in Indian Food Recognition,” in ASEC 2024, Basel Switzerland: MDPI, Feb. 
2025, p. 3. doi: 10.3390/engproc2025087003. 
[23] J. Potsangbam and S. Shuleenda Devi, “Classification of Breast Cancer Histopathological Images Using 
Transfer Learning with DenseNet121,” in Procedia Computer Science, Elsevier B.V., 2024, pp. 1990
1997. doi: 10.1016/j.procs.2024.04.188. 
[24] Q. Zhu, H. Zhuang, M. Zhao, S. Xu, and R. Meng, “A study on expression recognition based on improved 
mobilenetV2 network,” Sci Rep, vol. 14, no. 1, Dec. 2024, doi: 10.1038/s41598-024-58736-x. 
[25] T. Barman and S. Susan, “Multi-Label Remote Sensing Image Classification using MobileNetV2,” in 2024 
15th International Conference on Computing Communication and Networking Technologies, ICCCNT 
2024, 
Institute 
of 
Electrical 
10.1109/ICCCNT61001.2024.10725506. 
and 
Electronics 
Engineers 
Inc., 
2024. 
doi: 
[26] S. K. Bharadwaj, R. Jha, J. Kumar, D. K. Mishra, V. Shinde, and V. K. Jadon, “Comparative Study of 
Mobilenetv2, Simple CNN And Vgg19 For Image Classification,” Journal of Data Acquisition and 
Processing, vol. 39, no. 1, p. 152, doi: 10.5281/zenodo.7546488. 
37  
Indonesian Journal of Data and Science 
[27] M. Khoiruddin and S. Tena, “Fruit and Vegetable Classification using Convolutional Neural Network with 
MobileNetV2,” Journal of Applied and Research Computer Science and Information Systems, vol. 2, no. 
2, pp. 203–210, 2024, doi: 10.61098/jarcis.v2i2.197. 
[28] L. Cao, “A MobileNetV2 model of transfer learning is employed for remote sensing image classification.” 
in Advances in Engineering Technology Research, vol. 10, no. 1, 2024, 10.56028/aetr.10.1.596.2024 
[29] E. Shavna Gracia, N. Anisa Sri Winarsih, and D. Nuswantoro, “Comparison of VGG16, MobileNetV2, 
InceptionV3, ResNet50, and Custom CNN Architectures for Furniture Image Classification,” vol. 16, no. 
01, 2025, doi: 10.35970/infotekmesin.v16i1.2500. 
[30] S. Joshi, R. Shah, Y. Chandola, and V. Uniyal, “Classification of Brain MRI Images using End-to-End 
Trained AlexNet & End-to-End Pre-Trained MobileNet,” 2024. 
[31] B. J. Bipin Nair, B. Arjun, S. Abhishek, N. M. Abhinav, and V. Madhavan, “Classification of Indian 
Medicinal Flowers using MobileNetV2,” in Proceedings of the 18th INDIAcom; 2024 11th International 
Conference on Computing for Sustainable Global Development, INDIACom 2024, Institute of Electrical 
and Electronics Engineers Inc., 2024, pp. 1512–1518. doi: 10.23919/INDIACom61295.2024.10498274. 