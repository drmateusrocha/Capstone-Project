# Capstone-Project
Rocha's Capstone Project - Berkeley

### AI/ML models to predict the final color of leucite-reinforced ceramic veneer restorations

**Mateus Rocha**
Center for Dental Biomaterials, College of Dentistry of University of Florida.
mrocha@dental.ufl.edu
www.biomaterials.dental.ufl.edu

#### Executive summary

This is Capstone Project to complete the requirements for the Certificate in AI/ML at UC Berkeley. 

The study aims to develop an algorithm that can eliminate the necessity of visual inspection for shade selection and shade matching of any esthetic and restorative procedure using glass-based ceramic restorations. Recently, the Ivoclar Vivadent e.max shade navigation app was a considerable advance in the field to assist dentists in selecting the appropriate ceramic shade, translucence, and thickness. Still, there are several limitations as the app relies on the dentist's color perceptibility and acceptability. This study shows the algorithm developed and clinical spectrophotometric analysis aid using artificial intelligence to assist the dentist in selecting shade, type, thickness, and translucency of the ceramic restorations. 


#### Rationale

Dental ceramics are in constant development and they are an essential material for restorative dental treatments. For conventional feldspathic ceramics, the dental technician constructs a ceramic restoration by condensation and sintering of layers of ceramic powder with different shades and opacities to mimic the natural tooth structure.2,3 However, this approach is becoming obsolete since computer-aid design and computer-aid manufacturing (CAD/CAM) can produce monolithic ceramic restorations with similar optical properties but higher mechanical strength.
IPS Empress® CAD (Ivoclar ­Vivadent, Schaan, Liechtenstein) is a leucite-reinforced ceramic that presents a higher leucite volume as its crystalline phase, resulting in improved mechanical properties. The material is processed utilizing the hot-pressing technique or the CAD/CAM technique. The mechanical strength combined with excellent optical properties makes leucite-reinforced ceramics suitable for veneers and anterior crowns.
The chairside CAD/CAM dentistry is an extraordinary achievement that brings the dentist the opportunity for selecting and handling the ceramic materials. Consequently, the final results depend on the dentist skills with these particular materials. Considerable research attention has been devoted to color matching of CAD/CAM ceramic materials. However, the majority of the laboratory studies are hard to clinically translate due to the vast number of clinical variables
Shade guide is the traditional and most common method used for shade evaluation in dentistry but still presents many limitations. Instrumental color measurement has increased in popularity over the years. Different types of spectrophotometers, colorimeters, and imaging systems have been used in dentistry for shade evaluation.
Instrumental measurement provides objective and quantitative data, which reduces the subjectivity of the visual method. However, there is no method to combine the CIELab coordinates (L*, a* and b*) obtained from the tooth substrate and ceramic to predict the best ceramic type, shade, and thickness. The understanding of these interactions would extend the use of spectrophotometers in dentistry and it can lead to development of an algorithm for spectrophotometric software-assisted shade selection.

#### Research Question
Which regression model is the most accurate in the test data set, using their default parameters?

#### Research Question
The specific aims of the study are: 1 - Evaluate the L*, a* and b* of monolithic ceramics with different thicknesses, shades, and translucencies, cemented on white, black, A1, and A3 substrates with translucent resin cement. 2 - Create an algorithm based on the regression analysis of the color coordinate parameters (L*, a* and b*) to predict the final color of the ceramic restoration and the color change (ΔE00) from the initial substrate color. The hypotheses tested in this study are: H1 - There are significant differences in the L*, a* and b* color coordinates of monolithic ceramics with different thicknesses, shades, and translucencies cemented on white, black, A1, and A3 substrates with translucent resin cement. H2 - The algorithm created using the color coordinate parameters (L*, a* and b*) predicts the final color of the ceramic restoration and the color change (ΔE00) from the initial substrate color.


#### Data Sources
The data source can be found in this GitHub depository. The data collection was obtained by the author research group according to the following protocol:

Leucite-reinforced glass-ceramics blocks (IPS Empress® CAD, C14, Ivoclar Vivadent, Schaan Liechtenstein) (Figure 1) in 4 different shades (HT - A1, A3; LT - A1, A3) were used in this study. The blocks were bonded to dressing sticks (Buehler®, Lake Bluff, IL) to allow precise cuts without chipping of the specimens during the section. The assembly was mounted in a precision diamond saw machine (Isomet, Buehler®, Lake Bluff, IL with the Buehler's® Isomet diamond blade 15 LC, dimensions: four inches (102 mm), thickness: 0.012 in (0.3 mm) Buehler®, Lake Bluff, IL) and the blocks were sectioned under water cooling at 400 rpm. Specimens (n = 5) perpendicular to the long axis of the block were obtained with thicknesses of 0.3, 0.5, 0.7 and 1.2 mm. The accuracy of the final thickness was determined with a digital caliper (Mitutoyo Corp®, Kawasaki, Japan) with an accuracy of ± 0.05 mm. The glaze was not applied to avoid high reflection luster that could affect shade measurement. A pilot study showed that samples prepared following this protocol present similar superficial rugosity to the samples milled in the CEREC® MC XL milling machine (according to the ISO 25178 - Geometric Product Specifications – Surface texture, Sa = 18.56 ± 1.7 µm for the Isomet 15LC Diamond Saw and Sa = 17.57 ± 1.8 µm for the CEREC® MCXL milling machine, p = 0.832).
An experimental translucent resin-based cement with a refractive index of 1.5229 and without photoinitiators was produced to simulate the cementation of the ceramic veneer on the substrate. This simulation mimicked the refractive index changes and the light propagation through the interfaces between the ceramic-cement and cement substrate. 
Four different substrates were used: white background; black background; IPS Empress® LT A1 CAD/CAM block; IPS Empress® LT A3 CAD/CAM block. For reference, the CIELab coordinates of backgrounds were black (L*= 22.06, a*= 0.33, b*= 0.30), white (L*= 97.29, a*= -0.06, b*= 2.39), IPS Empress® LT A1 (L*= 71.29, a*= 0.99, b*= 10.87), and IPS Empress® LT A3 (L*= 64.30, a*= 2.13, b*= 14.82).

The color parameters of each specimen were obtained with a D65 illuminant over the different backgrounds interposed with the translucent resin cement using a calibrated spectrophotometer (CM-700d, Konica Minolta®, Tokyo, Japan) with a target mask with a sensor-opening diameter of 3 mm (SAV). The CIE 1931 2° Standard Colorimetric Observer was used to calculate color coordinate values for each specimen. The sensor opening of the spectrophotometer was placed in the center of each specimen and three measurements were collected in both SCI (specular component included) and SCE (specular component excluded) modes. The CIELab coordinates (L*, a* and b*) from the specimens were used to evaluate color change (ΔE00) from the substrate to the surface of the veneer according to the CIEDE2000 formula: ∆E00 = [(∆L/KL.SL)2 + (∆C/KC.SC)2 + (∆H/KH.SH)2 + RT.( ∆C/KC.SC).( ∆H/KH.SH)]0.5 , where ΔL, ΔC and ΔH are the differences in lightness, chroma and hue, and Rt is a function (the so-called rotation function) that accounts for the interaction between chroma and hue differences in the blue region. Weighting functions, SL, SC, and SH adjust the total color difference for variation in the location of the color difference pair in L*, a* and b* coordinates, and the parametric factors KL, KC, and KH are correction terms for the experimental conditions, which were set to 1. Differences in each inherent color parameter were also determined as ΔL*, Δa*, and Δb* by subtracting each specimen from the substrate color coordinate parameter value (+a* = red, −a* = green; +b* = yellow, −b* = blue; +L* = white, -L* = black).

The data set containing all variable were organized into:

    #Final CIELAB Result
    Lfinal = L* value of the final restoration; 
    afinal = a* value of the final restoration; 
    bfinal = b* value of the final restoration; 
    
    #Substrate Parameters
    Lsub= L* value of the substrate; 
    asub = a* value of the substrate; 
    bsub = b* value of the substrate;
    
    #Ceramic Parameters
    Lcer= L* value of the ceramic block; 
    acer = a* value of the ceramic block; 
    bcer = b* value of the ceramic block; 
    T = thickness of the ceramic restoration; 
    

#### Methodology
I am using the Jupyter Notebooks with scikit-learn libraries. The method was to first check the data for missing values. We use the one-hot encoder to treat the data. Then we used only the following bank information:
	
	# bank client data:
	 - 1 - age (numeric)
	 - 2 - job : type of job (categorical: 'admin.','blue-collar','entrepreneur','housemaid','management','retired','self-employed','services','student','technician','unemployed','unknown')
	 - 3 - marital : marital status (categorical: 'divorced','married','single','unknown'; note: 'divorced' means divorced or widowed)
	 - 4 - education (categorical: 'basic.4y','basic.6y','basic.9y','high.school','illiterate','professional.course','university.degree','unknown')
	 - 5 - default: has credit in default? (categorical: 'no','yes','unknown')
	 - 6 - housing: has housing loan? (categorical: 'no','yes','unknown')
	 - 7 - loan: has personal loan? (categorical: 'no','yes','unknown')
     
     
     
After this I tested the default method of common classifiers; I selected the two best; and I optimize their parameters


#### Results
The results show that by default the logistic regression and the SVM model has the highest accuracy in the test data (0.8865); Both of them have the lowest accuracy in the training data, but still a high accuracy (0.8876). However, the train time for the logistic regression is only 0.3145 while the SVM is 13.37. Thus, by default, the logistic regression is the best model.

According to the logistic regression the highest coefficient to determine the model are: if the job is student and if the default_unknown.

Nevertheless, when the models are optimize, the results are completely different.
The Decision Tree when optimized (max_depth=3, min_samples_leaf=20, random_state=42) shows a highest train and test accuracy (0.8880 and 0.8872) , respectively.

Also the feature importance shows that the most important features to determine if the client will subscribe are
	> age = 0.60
	> job_student = 0.20
	> default_no = 0.19
	> education_basic.9y = 0.01

The decision tree model can be found in the link

<img src="https://github.com/drmateusrocha/Capstone-Project/blob/8b77156b7e4899b83990cce20da017619bb41c70/images/fig1-L_by_ceramic.jpeg" width="1000">
#### Outline of project

- Notebook > https://github.com/drmateusrocha/Practical-Aplication-3/blob/main/rocha_prompt_III.ipynb
