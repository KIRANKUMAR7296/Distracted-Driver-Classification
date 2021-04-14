# Distracted Driver Classification 🚗🚙🚌

### 1. Problem

Predict the **Likelihood** : What the **Driver** is doing in Each Picture?

We need to **Classify** Images into following 10 Classes 

- c0: Safe Driving
- c1: Texting (Right) 
- c2: Talking on the Phone (Right)
- c3: Texting (Left)
- c4: Talking on the Phone (Left)
- c5: Operating the Radio
- c6: Drinking
- c7: Reaching Behind
- c8: Makeup
- c9: Talking to Pessenger

### 2. Data

**[Kaggle's State Farm Distracted Driver Detection](https://www.kaggle.com/c/state-farm-distracted-driver-detection/data)**

### 3. Features

Data consist of Driver Images, each taken in A Car with A Driver doing something in the Car 
- Texting 
- Eating 
- Talking on the Phone
- Makeup
- Reaching Behind (Reaching for some Object on the Back Seat) 

### 4. Files 
1. **imgs.zip** - Zipped Folder of All (Train/Test) Images.
2. **sample_submission.csv** - Sample Submission File in the Correct Format.
3. **driver_imgs_list.csv** - List of Training Images, their subject (Driver) ID, and Class ID.

### 5. Libraries
1. NumPy
2. Pandas
3. Matplotlib
4. Sklearn
5. Keras ( Utils )
6. Tensorflow

### 6. Approach
- Reduced Image Size to 240 x 240
- Total Number of Images : 2242
- **tensorflow.keras.utils.to_categorical** : Converts a **Class Vector** ( **Integers** ) to **Binary Class** `Matrix`. ( Dummy Encoding )

### 7. Parameters of Layers ( **tensorflow.keras.layers**  )

1. **Conv2D** : 2D Convolution Layer    
- Filters : Number of Filters in Convolution.
- kernel_size : Size of Window. 
- Strides : How Far will Pooling Window Move | Steps.
- Padding : valid ( no padding ) or same ( Add Same Padding from all sides )
- Activation Function : Activation Function to Use ( ReLu )   
- input_shape : 

2. **Flatten**
- **Flattens** the Input ( Down Sampling :  e.g ( output = ( 1, 10, 64 ) flattens to output = ( 640 ) i.e 1 x 10 x 64 = 640 )

3. **MaxPooling2D**
- Pool Size : Window Size ( Even if only one Integer is Passed it will be considered for both e.g. If 2 is Passes it is ( 2, 2 ) )
- Strides : How Far will Pooling Window Move | Steps.
- Padding : valid ( no padding ) or same ( Add Same Padding from all sides )

3. **BatchNormalization**
- Applies a **Transformation** | `Mean` = 0 and `Standard Deviation` close to 1 
- Axis : Axis to be Normalized 
- Epsilon : Variance Added to Prevent from Divide by 0 Error.

4. **Activation** 
- Activation : Name of Activation Function to be Applied ( e.g. activation = "relu" ) 
