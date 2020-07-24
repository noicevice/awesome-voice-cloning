# awesome-voice-cloning

#### What is this?

A place for all things voice cloning. Make a PR!

# Dataset Resources

#### Tools

[Noice's Watson Speech To Text Tool](https://github.com/noicevice/watson-speech-to-text)

[ASSFAP](https://colab.research.google.com/drive/18lBRBWOs4uV1DjhoW_fVzoydYUw400PW#scrollTo=ZfO2MFo2qrMi)

[Scipp's Guide](datasets/scripps-thoughts.md)

Use ffmpeg to convert your wav files to the right format:

    ffmpeg -y -i $filename -ac 1 -acodec pcm_s16le -ar 22050 -sample_fmt s16 converted/$filename

Or, on a whole directory:

    #!/bin/bash

    for filename in *.wav; do
        echo "Converting $filename"
        ffmpeg -y -i $filename -ac 1 -acodec pcm_s16le -ar 22050 -sample_fmt s16 converted/$filename    
    done

#### Datasets

[Kanye West](datasets/kanye-west.md)

[LJSpeech Dataset: Old Reliable](https://keithito.com/LJ-Speech-Dataset/)

[Common Voice: Broad voice dataset sample with demographic metadata. Includes valid-invalid identifier as an indication of transcript quality.](https://www.kaggle.com/mozillaorg/common-voice?select=cv-valid-test.csv)

[VoxCeleb: 2000+ hours of celebrity utterances, with 7000+ speakers. Audio is captured as "in the wild," including background noise.](http://www.robots.ox.ac.uk/~vgg/data/)voxceleb/vox1.html

[TED-LIUM: 452 hours of audio and aligned trascripts from TED talks.](https://www.openslr.org/51)

[LibriSpeech: 1000+ hour dataset of read English speech based on public domain audiobooks.](https://www.openslr.org/12)