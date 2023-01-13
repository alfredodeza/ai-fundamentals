# Explore Natural Language Processing (NLP)

[Learning Path](https://learn.microsoft.com/training/paths/explore-natural-language-processing/?WT.mc_id=academic-0000-alfredodeza)

Definition of NLP: Process of analyzing and evaluating text (from a document or a phrase) to get context, meaning, and insights.

## Analyze text with the Language Service

[Learning Module](https://learn.microsoft.com/training/modules/analyze-text-with-text-analytics-service/?WT.mc_id=academic-0000-alfredodeza)

Definition: Part of Azure Cognitive Services that can perform advanced NLP processing on text

The service can:

- Detect text language
- Provide sentiment analysis
- Extract key phrases
- Identify and categorize entities like dates, places, and people

Resources:

- **Language**: Exclusively for that service, does not have access to any other cognitive service
- **Cognitive Services**: Provides other services including Language

### Language Detection

Definition: Service that detects the language of the text. Allows for multiple documents at a time for analysis

Provides the following for each doc:

- Language name
- ISO 6391 language code (e.g. "es")
- Score of confidence

**Predominant** language is always chosen even on mixed language text. Can provide an **unknown** value if it can't detect the language with a **NaN** for score (Not a Number)

### Sentiment Analysis

Definition: Ability to provide a positive, neutral, or negative sentiment in text.

Useful for:

- Customer reviews
- Discussion forums
- Social media analysis

Provides a score between 0 and 1, where 1 is positive and 0 is negative. 0.5 is considered neutral or **indeterminate**

### Key phrase extraction

Definition: Ability to evaluate text and identify main talking points.

Language Service can parse unstructured text and produce entities like:

| Type | Sub Type | Example |
| - | - | - |
| Quantity | Number |  "fifty" |
| DateTime | Date |  "August 3rd" |
| DateTime | DateRange |  "Monday to Wednesday" |
| Email |  |  "admin@example.com" |

## Recognize and synthesize speech

[Learning Module](https://learn.microsoft.com/training/modules/recognize-synthesize-speech/?WT.mc_id=academic-0000-alfredodeza)

- **Speech Recognition**: Detect and interpret spoken input
- **Speech synthesis**: Generate spoken output

### Speech Recognition

Converts speech (spoken language) into data for processing using multiple models, for example:

- An acoustic model to convert audio signals into phonemes
- A language model to convert phonemes to words or sequence of words

Example usage:

- Closed Captions
- Meeting transcipts
- Note taking (Speech to text)

### Speech synthesis

Definition: Opposite of Recognition: it turns text into speech breaking text down to words and assiging phonetic sounds to each word.

Example usage:

- Responding to commands or input
- Voice menus for telephone systems
- Reading websites or email messages

### Azure Speech

Definition: A service from the Cognitive Services group which includes two APIs: **Speech-to-Text** and **Text-to-Speech**

Resources possible:

- **Speech**: For speech related tasks exclusively
- **Cognitive Services**: Includes the Speech service in addition to other services. Use this when using other services aside from Speech.

## Translate text and speech

[Learning Module](https://learn.microsoft.com/training/modules/translate-text-with-translation-service/?WT.mc_id=academic-0000-alfredodeza)

## Create a language model with Conversational Language Understanding

[Learning Module](https://learn.microsoft.com/training/modules/create-language-model-with-language-understanding/?WT.mc_id=academic-0000-alfredodeza)

## Build a bot with the Language Sercie and Azure Bot Service

[Learning Module](https://learn.microsoft.com/training/modules/build-faq-chatbot-qna-maker-azure-bot-service/?WT.mc_id=academic-0000-alfredodeza)


