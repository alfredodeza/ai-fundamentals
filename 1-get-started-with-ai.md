# Get Started with AI

[Learning Path](https://learn.microsoft.com/training/paths/get-started-with-artificial-intelligence-on-azure/?WT.mc_id=academic-0000-alfredodeza)

## Get Started with AI on Azure

[Learn Module](https://learn.microsoft.com/training/modules/get-started-ai-fundamentals/?WT.mc_id=academic-0000-alfredodeza)

### Introduction to AI

- **Machine Learning**: Foundation of AI. Teaches a machine to learn based on data
- **Anomaly Detection**: Automatic error detection based on anomaly
- **Computer Vision**: Interpretation of images and video
- **Natural Language Processing (NLP)**: Interpret written or spoken language
- **Knowledge mining**: Information extraction from unstructured data

### Machine Learning

Definition: The foundation for most AI solutions

How does it work:

- Machines (computers) learn from data
- Data Scientists use data to train machine learning models to make predicitons based on data.

### Machine Learning on Azure

- **Automated ML (AutoML)**: Create effective ML models with no expertise needed
- **Azure ML Designer**: A GUI for no-code development of ML models
- **Data and Compute**: Cloud-based resources for data scientists tu run experiments
- **Pipelines**: A way to orchestrate tasks like training, validation, and deployment

### Anomaly Detection

Definition: Analyzing data over time to identify unusual changes

**Anomaly Detector**: An Azure service with an API to create anomaly detection solutions

### Computer Vision

Definition: Area of AI for visual processing based on interpretation of images and video

**Models and capabilities**

| Task | Description |
| -    | -           |
| Image Classification | Classify images based on content. For example _is this a car or a bike?_ |
| Object Detection | Classify individual objects and location within an image using a box |
| Semantic Segmentation | Similar to object detection that uses an overlay to color-code distinct objects|
| Image Analysis | Extract information from images including tags for easier cataloging|
| Face detection, analysis, and recognition | Finds human faces in an image. Can be used with facial geometry to recognize individuals|
| Optical Character Recognition (OCR) | Detect and extract text in images, like a road sign or building number|

Azure Services

- **Computer Vision**: Analyse images and videos to extract descriptions, tags, objects and text
- **Custom Vision**: Customized image classification with your own images
- **Face**: Face detection and facial recognition solutions
- **Form Recognizer**: Information extraction from scanned documents

### Natural Language Processing

Definition: Area of AI that understands written and spoken language

Uses:

- Analyze and interpret text in documents
- Interpret spoken language
- Translattion of written and spoken languages
- Interpret commands

Azure Services

- **Language**:  Analyze text or spoken language to build smart applications
- **Translator**: Translation service for more than 60 languages
- **Speech**:  Recognize and synthesize speech and translate to other languages
- **Azure Bot**: Conversational AI with the ability to connect to channels like email, Teams, and web chat


### Knowledge Mining

Definition: Describe solutions about extracting information from unstructured data to create a searchable one

Azure Service: Azure Cognitive Search, and enterprise solution for building searchable indexes from private or public assets including analyzing images.

### Challenges and Risks

Challenges or risks:

- **Bias**: Trained data might rely heavily on specific race, or geography
- **Errors**: Mistakes can cause harm (e.g. autonomus vehicles)
- **Exposing data**: Non-compliant solutions that don't remove Personal Identifiable Information (PII)
- **Accessibility**: A solution might not work with individuals with disabilities
- **Complex systems**: Users must trust how solutions are generated (e.g. from what data)
- **Liability**:  Who/what is liable for decisions?

### Responsible AI

AI development at Microsoft uses 6 principles:

Fairness: AI systems should treat all people fairly

Reliability & Safety: AI systems should work reliably and safely

Privacy & Security: Respect privacy and consider security at all times, even after deployment

Inclusiveness: Empower everyone regardless of ability, gender, and other factors

Transparency: Systems shouold be understandable

Accountability: People should be accountable. Engineers and designers should work with a governance framework
