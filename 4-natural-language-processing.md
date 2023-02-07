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


Definition: Speech translation translates languages either directly (speech-to-speech) or using text as an intermediate step.

Literal and semantic translation: AI systems should take into account the context for proper tanslations, not only literal because it might provide insufficient or incorrect meaning.

Text translation is used for documents like emails, PDFs, and websites.

Speech translattion is used for spoken languages, either directly (speech-to-speech) or indirectly with speech-to-text.

### Translator Service

Definition: Analyzes _semantic_ context of text for text-to-text translations. 60 languages supported.

Requires specifying the source language to one or more destination languages for translations (one-to-many). It is possible to use cultural variants like Spanish from Spain or from Mexico.

Additional configurations:

- Profanity filtering
- Selective translation: Useful when trying to avoid a literal translation of something that doesn't make sense to translate like a name, or brand.

### Speech Service

Definition: Analyzes speech or spoken audio to text, and can create spoken audio from text. Both can also get translated.

Provides the following services via APIs:

- **Speech-to-text**
- **Text-to-speech**
- **Speech-translation**

Example usage: real-time closed-captioning of spoken audio (e.g. via video)

## Create a language model with Conversational Language Understanding

[Learning Module](https://learn.microsoft.com/training/modules/create-language-model-with-language-understanding/?WT.mc_id=academic-0000-alfredodeza)

The main service in Azure is the **Language Service**

Three main concepts:

- **Utterance**: A sentence or phrase a user might say for a system to react, like "turn the lights on"
- **Entity**: A specific item within an utterance. For example in "what is the weather today?", the "weather" is the entity. Sometimes there is no entity.
- **Intent**: The goal or objective in an utterance. "WeatherStatus" might be the intent for many different utterances

Note: There is a `None` intent is a _fallback_ when no other intents are matched, and is helpful to handle utterances that don't map anything else. It is always created in Conversational Language Understanding app, but left empty. It can't be deleted.

### Conversational Language Understanding

Definition: A service to help build application without having much ML experience or knowledge.

Service requires two main tasks:

1. Definte entities, intents, and utterances for training the model (a.k.a. authoring a model)
1. Publish the model so that client applications can use it for intent and entity prediction based on input

Resources possible:

- **Language Service**: A resource to build apps, use it if only requiring this service exclusively.
- **Cognitive Services**: Includes the Conversational Language Understanding service along with other cognitive services

### Authoring

Use pre-built _domains_ that includes pre-defined intents and entities for common uses that you can build on.

Note: order of entities/intents do not matter

Add the intents with the Portal (although you can write code for it). Use the portal for authoring, but SDK for predictions


### Intents

There are 4 types:

1. **Machine Learned**: Model learns from sample utterances you provide
1. **List**: Allows a hierarchy of lists/sublists. Like _device_ might be a light -> lamp -> night stand
1. **RegEx**: Entities as a regular expression that describes a pattern
1. **Pattern.any**: Entities with patterns to solve complex scenarios that are hard to extract from utterances


### Training

After entities and utterances are defined, use the service to train and test the model. Use sample utterances to see if intents and entities are recognized correctly.

## Predicting

After verification of training predictions you publish the application to a _preduction resource for consumption_

Clients can use the prediction to take actions based on predicted intent.

## Build a bot with the Language Service and Azure Bot Service

[Learning Module](https://learn.microsoft.com/training/modules/build-faq-chatbot-qna-maker-azure-bot-service/?WT.mc_id=academic-0000-alfredodeza)

Conversations can happen in different channels including email and text messages. It requires a **knowledge base** and a a **bot service** to provide an interface.

In Azure it requires two core services:

1. **Language Service**: Includes question answering to create a knowledge base for querying later
1. **Azure Bot Service**: The framework for creating, publishing, and managing bots on Azure

### Custom Knowledge base

Must create a **Language Service** resource.

Define Q&A. Use the _Language Studio_ custom Q&A to create a knowledge base. Enter them manually or with an existing FAQ document or website (or a combination of both).

**Test** the knowledge base using the Language Studio and reviewing the answers after the model has been processed.

**Use the knowledge base**: Over an API (REST interface) that requires an ID, the endpoint, and the Authorization key

### Azure Bot Service

Build it using the Bot Framework SDK to write code for conversation flow control.

Easier with the _automatic bot creation_ functionality using the knowledge base automatically.

**Extend and configure**

* Extend by adding custom code
* Test the bot in an interactive test
* Configure logging and analytics

**Connect channels**

Bots can use more than one channel. Including Microsoft Teams, web chat, and email.
