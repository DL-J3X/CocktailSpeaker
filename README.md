# CocktailSpeaker

## Introduction
The development of artificial intelligence not only brings convenience to our life but also concerns of privacy exposure. We are able to easily share information using audio and videos. It is important to maintain the privacy of the participants from these media while preserving the original information to be conveyed as much as possible. There are some existing methods that anonymize speech using signal processing or machine learning techniques. However, most of them result in either poor quality of the audio, poorly anonymized, or not obviously anonymized. In this paper, we would like to propose a novel method to convert the speech from one speaker to some other speaker identity through the pipeline: speech --> linguistic units --> speech. With our proposed cocktail speaker decoding (CSD), we can also dynamically change the speaker identity without re-training the network. The model can be applied to many scenarios, such as generating the speech in a standardized speaking style for all the operators in call center services.

## Cocktail Speaker Decoding
The cascaded voice conversion and cocktail speaker decoding is implemented with ESPNet (see https://github.com/DL-J3X/espnet). The model preparation takes the following steps:

- Train an ASR system with https://github.com/DL-J3X/espnet/tree/master/egs2/libritts/asr1
- Train an TTS system with https://github.com/DL-J3X/espnet/tree/master/egs2/libritts/tts1
- Use the Hifi-GAN vocoder from https://github.com/kan-bayashi/ParallelWaveGAN
- Use baseline by using https://github.com/DL-J3X/espnet/blob/master/egs2/libritts/tts1/run.sh
- Use cocktail speaker decoding by using https://github.com/DL-J3X/espnet/blob/master/egs2/libritts/tts1/run_tgt.sh
- Use perturb x-vector method by using https://github.com/DL-J3X/espnet/blob/master/egs2/libritts/tts1/run_direct_perturb.sh

## Evaluation

### Speaker Verification

### ASR Inference


