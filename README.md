# Car Plate Number Detection and Recognition

This Jupyter notebook demonstrates car plate number detection and recognition using image processing techniques and OCR (Optical Character Recognition). You can follow the steps below to perform car plate number detection and extract text from an image.

## Table of Contents
1. [Installation and Imports](#installation-and-imports)
2. [Reading the Image](#reading-the-image)
3. [Plate Detection](#plate-detection)
4. [Masking](#masking)
5. [Text Extraction Using Tesseract](#text-extraction-using-tesseract)
6. [Text Extraction Using Easy OCR](#text-extraction-using-easy-ocr)
7. [Evaluation and Metrics](#evaluation-and-metrics)

## 1. Installation and Imports <a name="installation-and-imports"></a>

Before getting started, you need to install the required dependencies. This includes the installation of Tesseract OCR, Pytesseract, EasyOCR, OpenCV, and other libraries. You can run the following code to install the necessary packages:

```python
!sudo apt install tesseract-ocr
!pip install pytesseract
!pip install easyocr
!pip install imutils
```

## 2. Reading the Image <a name="reading-the-image"></a>

After installing the required libraries, the next step is to read the image. You can specify the path to the image you want to process. In this notebook, we use an example image located at `/content/drive/MyDrive/car_plates_dataset/car10.jpg`. Ensure that you replace this with the actual file path to your image.

The following code reads the image:

```python
image_path = '/content/drive/MyDrive/car_plates_dataset/car10.jpg'
original_image = cv2.imread(image_path)

if original_image is not None:
    print("Image read successfully.")
else:
    print("Failed to read the image. Please check the file path.")
```

## 3. Plate Detection <a name="plate-detection"></a>

Car plate detection is performed in the following steps:

- Applying a bilateral filter for noise reduction and edge detection
- Finding contours in the image
- Identifying the plate location
- Masking the plate area

The code for plate detection is provided in the notebook. You can visualize the results to ensure the detection is accurate.

## 4. Masking <a name="masking"></a>

Once the plate is detected, the next step is to apply masking to focus on the plate area. This masking process helps in better text extraction. The code for masking the plate area is included in the notebook.

## 5. Text Extraction Using Tesseract <a name="text-extraction-using-tesseract"></a>

After masking, text extraction is performed using Tesseract OCR. The extracted text is printed to the console. This step allows you to recognize and read the car plate number.

## 6. Text Extraction Using Easy OCR <a name="text-extraction-using-easy-ocr"></a>

In addition to Tesseract, the notebook demonstrates text extraction using Easy OCR. Easy OCR provides another method for reading text from the car plate. The extracted text is compared with the ground truth to calculate accuracy, precision, recall, and F1-score.

## 7. Evaluation and Metrics <a name="evaluation-and-metrics"></a>

The notebook includes code to calculate and display evaluation metrics such as accuracy, precision, recall, F1-score, precision-recall curves, and confusion matrices for both Tesseract OCR and Easy OCR.

This notebook serves as a guide for car plate number detection and recognition. You can apply these techniques to your own car plate images and further refine the process for your specific use case.
