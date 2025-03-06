# Computer-Vision: License-Plate-Detection

## Overview
This project automates license plate detection, text extraction, and QR code integration using OpenCV and EasyOCR computer vision techniques. It demonstrates an end-to-end pipeline that processes vehicle images, detects license plates, and extracts textual information using Optical Character Recognition (OCR). This project is well-suited for applications such as automated toll systems, parking management, and vehicle identification.

## Workflow

**1. Environment Setup**

-  **Installed dependencies:** **easyocr** for OCR, **opencv-python** for image processing, and **qrcode** for QR generation.

-  Configured OpenCV with the correct version to avoid compatibility issues.

**2.  Image Loading and Preprocessing**

-  Loaded vehicle images (**car1.jpg to car4.jpg**).

-  Converted images to grayscale to simplify feature detection.

-  Applied Gaussian blur to reduce noise and improve detection accuracy.

**3.  License Plate Detection**

-  Utilised OpenCV’s Haar Cascade classifier (**haarcascade_russian_plate_number.xml**) for plate localization.

-  **Parameters:** **scaleFactor=1.1**, **minSize=(30,30)**, **minNeighbors=5** to balance sensitivity and precision.

-  Drew bounding boxes around detected plates using **cv2.rectangle**.

**4.  License Plate Extraction & OCR**

-  Cropped detected plate regions from the original image.

-  Preprocessed cropped images: grayscale conversion and Otsu’s thresholding for binarisation.

-  Used EasyOCR with the English language model (**reader = easyocr.Reader(["en"])**) to extract plate text.

**5.  QR Code Integration**

-  Generated QR codes from extracted plate text using qrcode library.

-  Customized QR code appearance (colors, border size).

-  Validated QR codes using OpenCV’s **QRCodeDetector** to ensure readability.

## Methodologies

-  **Haar Cascade Classifier:** A pre-trained object detection model that detects license plates in images. Uses a cascade of classifiers to identify features at different scales. Leveraged pre-trained models for real-time object detection, optimized for European/Russian plate formats.

-  **Grayscale Conversion:** Converts images to grayscale to reduce computational complexity and improve edge detection.

-  **EasyOCR for Text Recognition:** A deep learning-based OCR model used to extract text from the detected license plate. Chosen for its robustness in reading distorted or low-resolution text.

-  **Preprocessing Techniques:** Gaussian blur and Otsu’s thresholding enhanced OCR accuracy by improving contrast and reducing noise.

-  **QR Code Workflow:** Demonstrated data encoding/decoding capabilities, linking physical plates to digital records.

## Results & Findings

-  Successfully detected license plates from vehicle images.

-  OCR extracted readable text from the detected plates.

-  The detection pipeline is effective for automated vehicle identification applications.

### Performance Observations

-  Haar Cascade performs well under good lighting conditions, but may require fine-tuning for varying angles and blurriness.

-  EasyOCR provides highly accurate character recognition, making it suitable for real-world applications.

## Conclusion

This project showcases a functional pipeline for license plate recognition, emphasising practicality and modularity. By combining detection, OCR, and QR technologies, it provides a foundation for applications in security, parking systems, and automated toll collection. Future work could focus on real-time processing and expanding regional plate compatibility.
