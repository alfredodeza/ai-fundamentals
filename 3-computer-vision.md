# Explore Computer Vision

[Learning Path](https://learn.microsoft.com/training/paths/explore-computer-vision-microsoft-azure/?WT.mc_id=academic-0000-alfredodeza)

## Analyze Images with the Computer Vision Service

[Learning Module](https://learn.microsoft.com/training/modules/analyze-images-computer-vision/?WT.mc_id=academic-0000-alfredodeza)

### Azure Computer Vision resources

Computer Vision definition: Specific to only Vision and no other service. Useful for tracking utilization and costs separately.
Cognitive Services definition: General cognitive services that includes Computer Vision

Key difference: Cognitive Service includes Computer Vision. Computer Vision is a smaller (specific) service

Two essential pieces of information are provided for these services:

- **key**: For authentication
- **endpoint**: An HTTP address to communicate with the resource (for Cognitive Services, the endpoint is always the same regardless of the service)

### Analyze images with Computer Vision Service

These tasks are all part of the Computer Vision Service _specifically_

**Describing an image**: Generate human readable description of image contents
**Tagging visual features**: Recognized objects are suggested as tags for metadata to descibe attributes of the image
**Detecting objects**: Similar to tagging, but creates a box surrounding the object along with the type of object
**Detecting brands**: Identifies commercial brands
**Detecting faces**: Detects and analyzses human faces, including age. Note: This is a _subservice_ of Face Service (which has more functionality)
**Categorizing an image**: Uses a parent/child hierarchy of categories from detected objects.
**Detecting domain specific content**:
**Optional Character Recognition (OCR)**: Detects printed and handwritten textt in images.

Other capabilities:

- Detecting image types like line drawings
- Detecting image color schemes like overall and dominant colors
- Thumbnail generation for smaller version of images
- Content moderation like adult content or violoent scenes

## Classify images with the Custom Vision Service

[Learning Module](https://learn.microsoft.com/training/modules/classify-images-custom-vision/?WT.mc_id=academic-0000-alfredodeza)

Useful examples for this service:

- Product identification, like visual searches
- Disaster investigation, like identifying bridges and roads
- Medical diagnosis, like X-ray evaluation

### Classification

Definition: Predict a category (or class) for an item. Uses inputs (features) to find the probability of a class and provide a label for it.

**Image Classification**: Classify an object from an image. Requires data made of features and labels from categorized images.

### Azure Custom Vision Service

Definition: Service that includes common techniques for training image classification models, making it easy to create a software service with minimal knowledge of Convolutional Neural Networks (CNNs) and other deep learning techniques and then deploy them.

### Azure Custom Vision resources

Custom Vision definition: A subservice of Cognitive Services for image classification exclusively enabling people with little to no ML experience to create image classification solutions
Cognitive Services definition: General cognitive services that includes Custom Vision

Requires a **resource** in your Azure subscription which must be one of:

- **Custom Vision** (dedicated only for Custom Vision)
  - Must choose between training, prediction, or both.
  - Creates a separate endpoint for each
- **Cognitive Services** (Includes Custom Vision as well as other services)
  - Does not require to choose between training or prediction
  - Always has a single HTTP endpoint and key

### Model training

Requires uploading images and label them with class labels. This can be done in the portal or with an SDK

Note: As with all ML training, the more images with labels the better the results. Key is to have objects from different angles.

### Model evaluation

Custom Vision holds back some of the training data to evaluate using these metrics:

- **Precision**: Percentage of correct predictions
- **Recall**: Percentage of correct identifications
- **Average Precision (AP)**: Overall metric that uses precision and recall

### Using the model

Requires the following for client applications to consume the model:

- **Project ID**: Unique ID of Custom Vision project that trained the model
- **Model Name**: The assigned model name
- **Endpoint**: The HTTP address that points to the published model
- **Key**: Used to authenticate

## Detect objects in images with the Custom Vision Service

[Learning Module](https://learn.microsoft.com/training/modules/detect-objects-images-custom-vision/?WT.mc_id=academic-0000-alfredodeza)

Object Detection Definition: Recognizes individual object in an image

Useful examples for this type of ML:

- Building safety by detecting extinguishers
- Assisted driving by detecting other cars and driving lanes
- Tumor detection from MRI or x-rays

Object classification vs. Object detection: classification classifies **an image** and detection classifies **individual objects within an image**

### Azure Custom Vision

Definition: Helps create object detection models with minimal deep learning experience and less training images

Consists of three tasks:

1. Upload an tag images
1. Train the model
1. Publish the model

Two types of resources:

- **Custom Vision** (dedicated only for Custom Vision)
  - Must choose between training, prediction, or both.
  - Creates a separate endpoint for each
- **Cognitive Services** (Includes Custom Vision as well as other services)
  - Does not require to choose between training or prediction
  - Always has a single HTTP endpoint and key

### Image Tagging

Training image models requires tagging classes and bounding box coordinates in training images.

* Custom Vision Portal provides a UI for this process to make it easier.
* Ensure you have sufficient images and from different angles

### Model evaluation

Custom Vision holds back some of the training data to evaluate using these metrics:

- **Precision**: Percentage of correct predictions
- **Recall**: Percentage of correct identifications
- **Average Precision (AP)**: Overall metric that uses precision and recall

### Using the model

Requires the following for client applications to consume the model:

- **Project ID**: Unique ID of Custom Vision project that trained the model
- **Model Name**: The assigned model name
- **Endpoint**: The HTTP address that points to the published model
- **Key**: Used to authenticate


## Detect and analyze faces with the Face Service

[Learning Module](https://learn.microsoft.com/training/modules/detect-analyze-faces/?WT.mc_id=academic-0000-alfredodeza)

Definition of Face detection and analysis: Locates and analyzises human faces in images or video, returning bounding box coordinates around a face

Facial analysis: Aside from detection, other information including _facial landmarks_ can be used as features to train a machine learning model
Facial recognition: Identifies individuals given their facial features

Example uses of face detection and analysis:

- Security: For unlocking of devices or areas in a building
- Social media: For tagging of known friends on images
- Missing persons: For finding missing individuals from public camera systems

Services for face analysis on Azure:

- **Computer Vision**
- **Video Indexer**
- **Face**

### Azure Face

Definition: Service that returns the rectangle coordinates for human faces in an image

Includes attributes like:

* Blur
* Exposure
* Glasses
* Head pose (orientation)
* Noise (in image)
* Occlusion (objects blocking)

**Responsible AI**: Azure limits the service unless an intake form is submitted to enable face comparision and ability to identify _named_ indivisuals in an image

Two types of resources for Face service:

- **Face**: Dedicated only for Face
- **Cognitive Services**: Includes Azure Face as well as other services

Both resources alwyas provide a key and an endpoint.

Key difference from other services: **Face** does not make you choose between training, prediction or both which generates more than one endpoint
Note on facial detection: Best results are obtained with frontal facing faces

## Read text with the Computer Vision Service

[Learning Module](https://learn.microsoft.com/training/modules/read-text-computer-vision/?WT.mc_id=academic-0000-alfredodeza)

**OCR** (Optical Character Recognition) allows AI to read text in images.

Vision intersects with Natural Language Processing.

Uses of OCR:

- Note taking
- Digitizing forms like medical records
- Scanning hand writing

### Azure Read API

Definition: Exclusively handled by Computer Vision service which includes image analysis capabilities. Can handle scanned documents with lots of text.

Works asynchronously since it can handle large documents. Process requires:

1. Submitting image(s) which responds with an ID
1. Use the ID to check if processing is complete
1. Retrieve results on completion

Results include:

- **Pages**: Metadata on each page submitted
- **Lines**: Number of lines of text
- **Words**: Words in a line of text with coordinates

Two types of resources for the Read API:

- Computer Vision: Specific to only Vision and no other service. Useful for tracking utilization and costs separately.
- Cognitive Services: General cognitive services that includes Computer Vision

Both resources alwyas provide a key and an endpoint.

Computer Vision provides a single API to read text in images: the **Read** API

## Analyze receipts with the Form Recognizer Service

[Learning Module](https://learn.microsoft.com/training/modules/analyze-receipts-form-recognizer/?WT.mc_id=academic-0000-alfredodeza)

Definition: Provides text from digitized documents using OCR (Optical Character Recognition) as well as structured data from forms including receipts.

Examples:

- Retrieve address and phone number for a merchant from a receipt
- Create structured data that can tell you quantity and price for each item in a receipt

Two types of automated processing:

- **Pre-built receipt model**: Ready-to-use model for parsing data from receipts
- **Custom models**: Extracts key/value pairs from forms by training models using _your own data_

Two resources to use the Form Recognizer service:

- **Form Recognizer**: Only has access to the Form Recognizer Service
- **Cognitive Services**: Includes the Form Recognizer Service

Both resources alwyas provide a key and an endpoint.

Pre-built model works for English receipts with data common to the US. Can extract information like:

- Taxes
- Items with prices and count
- Merchant information
- Dates and times
- All other extra data


## Vision Services chart

**Cognitive Services** is the parent service for all Vision and Text related services which provides a single interface (API)

| Service Name | Part of other Service | Endpoints generated |
| - | - | - |
| Computer Vision | Cognitive Services | 1 |
| Custom Vision | Cognitive Services | 1 of training, prediction, or both  |
| Azure Face  | Cognitive Services  | 1  |
| Cognitive Services | | 1 for all other included services |
