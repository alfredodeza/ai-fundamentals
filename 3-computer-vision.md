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

## Detect and analyze faces with the Face Service

[Learning Module](https://learn.microsoft.com/training/modules/detect-analyze-faces/?WT.mc_id=academic-0000-alfredodeza)

## Read text with the Computer Vision Service

[Learning Module](https://learn.microsoft.com/training/modules/read-text-computer-vision/?WT.mc_id=academic-0000-alfredodeza)

## Analyze receipts with the Form Recognizer Service

[Learning Module](https://learn.microsoft.com/training/modules/analyze-receipts-form-recognizer/?WT.mc_id=academic-0000-alfredodeza)
