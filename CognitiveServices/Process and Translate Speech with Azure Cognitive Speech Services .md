# Process and Translate Speech with Azure Cognitive Speech Services

### Speech Service and Synthesize Text Input to Speech
#### Intro
The Speech-to-text provides real-time transcription of audio streams based on machine learning and
artificial intelligence algorithms. The Speech services APIs allow developers to add real-time speech transcription to their applications or services.

Speech-to-text services are exposed through platform-independent REST APIs or the Speech SDK. These APIs allow you to integrate these services into any solution
that requires speech translation. Dependent whether we choose the REST API or the Speech SDK, services will vary. 

Speech-to-text provide using multiple languages. In default the service using universal language model created by Microsoft. When using speech-to-text for recognition and transcription in a unique environment,
you can create and train custom models. It's helpful especially in customized environments, e.g. factories. 

Text-to-speech is sometimes known as voice synthesizing. The text that is used for input, is converting and then passed to the synthesizer to generate the human-spoken words.
Synthesized speech has improved over time and now sound less like a computer-generated representation. The neural voice capabilities are enhanced through deep neural networks and improve on the standard voices by adding the ability to utilize stress and intonation in the spoken language. 
Synthesize voice is support in over 45 languages by about 75 voices.

If you needed to perform audio-to-text for more than 10 minutes, it would use Speech Synthesis Markup Language (SSML). This API works in an asynchronous fashion so don't use it for real time synthesis. The service will perform the necessary work on the audio and then save the content to a file that you can download.

Speech translation is the service by which conversational, spoken phrases are translated to other language immediately. Speech transaltion is mix of all speech services and allow to translate input voice to multiple languages in real time- 
Microsoft's translation engine is powered by two different approaches: statistical machine translation (SMT) and neural machine translation (NMT). SMT uses advanced statistical analysis to estimate the best possible translations given the context of a few words.
With NMT, neural networks are used to provide more accurate, natural-sounding translations by using the full context of sentences to translate words.
User can choose languages and voice types. 

All the functionalities are based on Speech Service. 

_Source: https://docs.microsoft.com/en-us/learn/paths/process-translate-speech-azure-cognitive-speech-services/_

#### Use Cases
- automation, industry, factories
- bot services
- business intelligence
- international events, conferences
- museum, tourism 
- airport announcements 

#### How to

###### Speech Service and Synthesize Speech
Service enables: 
- speech to text
- speech translation
- text to speech

What we need to do is creatine Speech service in Azure platform.
After that we can create app which will provide to-directional conversion records to text. We can use any languages (C#, Python) only if  the language has access to azure.cognitiveservices.speech library. 

The default format is 16 bit, 16khz mono PCM. To customize the format, you can pass an AudioStreamFormat object to CreatePushStream() using the static function AudioStreamFormat.GetWaveFormatPCM(sampleRate, (byte)bitRate, (byte)channels).

The supported languages page shows the languages supported by both the Speech SDK and REST API so you can have support for your preferred method of accessing the services.
You can also perform some customization, for a subset of languages, to help improve accuracy. Customization is offered for a subset of the languages through uploading Audio + Human-labeled Transcripts or Related Text: Sentences. 

To use Synthesize Speech only what we need to add in code is audio configuration parameter.

The service support broaden set of languages and synthesize's voices:
https://docs.microsoft.com/en-us/azure/cognitive-services/speech-service/language-support

###### Speech translation
*Migration*
If you have used Bing Speech or the Translator Speech API and want to migrate to Speech service, your old keys won't be work on new service, which necessitate a migration to the new services.

The speech translation capabilities require working with some key objects:

- A SpeechTranslationConfig object that will accept
    - your subscription key and region information
    - attributes for source and target language
    - a speech output voice name
- A TranslationRecognizer object that will accept
    - the SpeechTranslationConfig object listed above
    - calling the method to start the recognition process
- A TranslationRecognitionResult object is returned for you to evaluate for the result
- A Speech Synthesizer object to play the audio output in the target language

It's possible to translate a few languages in Real-time by adding target language methods of the Speech Config object. The translation is executed in order queue.
The translation engine recognize that an utterance has finished by a break in the audio. Then a content is translating. 

Speech translation languages support:
 https://docs.microsoft.com/en-us/azure/cognitive-services/speech-service/language-support#speech-translation

_Pricing_

We can use Speech services using 2 types of subscription: Free and Standard.
Free version enables:
- 5 audio hours free per month (Speech to Text)
- 5 million characters free per month (Text to Speech)
- 5 audio hours free per month (Speech Translation)

More info:
https://azure.microsoft.com/en-us/pricing/details/cognitive-services/speech-services/
