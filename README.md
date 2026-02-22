# HematoVision-Advanced-Blood-Cell-Classification-Using-Transfer-Learning
HematoVision is an intelligent blood cell classification system that uses transfer learning with deep neural networks to accurately identify and categorize different types of blood cells from microscopic images. By leveraging pretrained models, it improves diagnostic efficiency, reduces manual effort, and aids in faster detection.


HematoVision
1️⃣ What Problem Are We Solving?

In hospitals, doctors examine blood samples to check for diseases like:

Infections

Leukemia

Immune disorders

Inflammation

To do this, they look at blood cells under a microscope and identify different types of white blood cells.

This process:

Takes a lot of time

Requires skilled professionals

Can sometimes lead to human errors

So, we created HematoVision, an AI-based system that automatically identifies blood cells from images.

2️⃣ What Does HematoVision Do?

HematoVision:

Takes a blood cell image as input

Processes the image

Uses a trained deep learning model

Predicts the type of blood cell

Displays the result

It classifies the image into one of four types:

Eosinophil

Lymphocyte

Monocyte

Neutrophil

3️⃣ How Does It Work?
Step 1: Dataset

We used around 12,000 labeled blood cell images.
Each image belongs to one of the four classes.

Step 2: Transfer Learning

Instead of building a model from zero, we used a pre-trained CNN model (like MobileNet, VGG, etc.).

These models:

Already know how to detect shapes, edges, textures

Are trained on millions of images

We just fine-tuned it to recognize blood cells.

This is called Transfer Learning.

It helps:
✔ Improve accuracy
✔ Reduce training time
✔ Reduce computational cost

Step 3: Training the Model

During training:

The model learns patterns of each blood cell type

Adjusts its weights

Improves prediction accuracy

After training, we saved the model as:

blood_cell_model.h5
Step 4: Building the Web Application

We used Flask to build a simple web application.

The user:

Uploads a blood cell image

The image is processed

The model predicts the class

The result is displayed on the webpage

blood_cell_model.h5


4️⃣ Why Is This Project Important?

✔ Speeds up diagnosis
✔ Reduces manual workload
✔ Improves accuracy
✔ Useful for telemedicine
✔ Helpful for medical training

5️⃣ Real-World Use

In hospitals:

A lab technician uploads a blood sample image

HematoVision instantly predicts the cell type

Doctors use the result for diagnosis

In rural areas:

Images can be uploaded remotely

Doctors can give faster treatment decisions


🛠 Technologies Used in HematoVision
1️⃣ Programming Language
🐍 Python

Main language used to build the project

Used for model training and backend development

2️⃣ Deep Learning & AI
🔹 TensorFlow

Used to build and train the deep learning model

Handles neural network operations

🔹 Keras

High-level API of TensorFlow

Used to create CNN models easily

🔹 Convolutional Neural Networks (CNN)

Used for image classification

Extracts features from blood cell images

🔹 Transfer Learning

Uses pre-trained models like:

MobileNet

VGG16

ResNet

Reduces training time and improves accuracy

3️⃣ Image Processing
🔹 NumPy

Used for handling image arrays and numerical operations

🔹 Image Preprocessing (Keras)

Resizing images (224x224)

Normalizing pixel values

4️⃣ Web Development
🔹 Flask

Backend framework

Connects the trained model to the webpage

🔹 HTML

Frontend user interface

Used for uploading images and displaying results

🔹 CSS (Optional)

Styling the webpage

5️⃣ Development Tools

VS Code (for coding)

Jupyter Notebook (for training model)

GitHub (for project hosting)

Team ID : LTVIP2026TMIDS42950

Team Size : 4

Team Leader : B Asma Sania

Team member : Golla Akhila

Team member : Lahari Kandukuri

Team member : Chadalavada Ramya Sree


