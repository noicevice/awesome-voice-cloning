# awesome-voice-cloning

#### What is this?

A place for all things voice cloning. Make a PR!

# TacoTron 2

[TACOTRON 2](https://github.com/NVIDIA/tacotron2)

#### CookiePPP Tacotron 2 Colabs

[This is the main Synthesis Colab](https://colab.research.google.com/drive/19_S4oUc11S2N2FG-ybrwN455A74bbb85)

[This is the simplified Synthesis Colab](https://colab.research.google.com/drive/1p5Y6cqVAd9NTnFqQ7M11i4hG7M0DwvU2)

[This is supposedly a newer version of the simplified Synthesis Colab](https://colab.research.google.com/drive/1qEwv6sHkmjD6GFflDxBXbefHXph2kJJv)

[For the sake of completeness, this is the training colab](https://colab.research.google.com/drive/1d1a4d7riehUOTofchlwo8N79n3Q7W4SK)

It's worth noting that the cookiePPP training colab has (what I believe is) a major improvement over mine: an integrated grapheme-to-phoneme system, so that the model can learn on syllabes instead of stupid nonstandard English spellings. I believe this will only work with English transcrips.

#### Scripp's Training Colabs

And another link: this is my fully functional Colab notebook for tacotron2 training and synthesis, with explanatory notes. No hardware required--it'll train your model on google's free GPUs and save the output to your google drive. The most complicated part is prepping your dataset before upload. Currently set up to train from the LJspeech-trained model, on 22050hz wav files with 16-bit PCM encoding. (See the dataset section for help on this)

[Training](https://colab.research.google.com/drive/1hiFHCyS_YNJVMnsvzrJq8XYjshRg1c5D?usp=sharing)

You can use this tensorboard to interact in parallel with the Tacotron2 for Dummies notebook to check the progress of your model. You will have to use "Factory Reset Runtime" every time you want to update the tensorboard to check progress.  This is a GREAT way to visualize what's going on with your model.  Much more useful than the alignment charts that the training colab spits out.

[Tensorboard](https://colab.research.google.com/drive/1V8Dr48J-FMVy39Xe1p8QMyCWqH0_XO4t?usp=sharing)

#### Converting graphemes to phonemes

Below is a hastily coded python script to convert graphemes to phonemes in files already prepped for tt2 learning. Basically it takes each line of <filename.wav|transcription> and converts the transcription segment into IPA characters. What this means is that the model shouldn't get confused about words that don't sound the way they are written, and in general they should learn better.

[Script in Colab Form](https://colab.research.google.com/drive/1HKpCTAbirNV10UmbKDh-eTkvbiXhTeM7?usp=sharing)

# Waveglow

[On training Waveglow - Scripp](waveglow/readme.md)

# Dataset Resources

#### Tools

[Noice's Watson Speech To Text Tool](https://github.com/noicevice/watson-speech-to-text)

[ASSFAP](https://colab.research.google.com/drive/18lBRBWOs4uV1DjhoW_fVzoydYUw400PW#scrollTo=ZfO2MFo2qrMi)

[Scripp's Guide](datasets/scripps-thoughts.md)

Use ffmpeg to convert your wav files to the right format:

    ffmpeg -y -i $filename -ac 1 -acodec pcm_s16le -ar 22050 -sample_fmt s16 converted/$filename

Or, on a whole directory:

    #!/bin/bash

    for filename in *.wav; do
        echo "Converting $filename"
        ffmpeg -y -i $filename -ac 1 -acodec pcm_s16le -ar 22050 -sample_fmt s16 converted/$filename    
    done

# Datasets

[Kanye West](datasets/kanye-west.md)

[LJSpeech Dataset: Old Reliable](https://keithito.com/LJ-Speech-Dataset/)

[Common Voice: Broad voice dataset sample with demographic metadata. Includes valid-invalid identifier as an indication of transcript quality.](https://www.kaggle.com/mozillaorg/common-voice?select=cv-valid-test.csv)

[VoxCeleb: 2000+ hours of celebrity utterances, with 7000+ speakers. Audio is captured as "in the wild," including background noise.](http://www.robots.ox.ac.uk/~vgg/data/)voxceleb/vox1.html

[TED-LIUM: 452 hours of audio and aligned trascripts from TED talks.](https://www.openslr.org/51)

[LibriSpeech: 1000+ hour dataset of read English speech based on public domain audiobooks.](https://www.openslr.org/12)

# Creating a Dataset

[Some Scripts for recording voices](texts/readme.md)

[SRT Splitting](https://github.com/camjac251/srt-parse)

[AutoSub](https://github.com/BingLingGroup/autosub)

[Cam's Workflow](workflows/cam.md)

# Glossary of Terms

[Glossary](datasets/glossary.md)
