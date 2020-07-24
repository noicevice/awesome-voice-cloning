# Scripp says...

I'm going to start archiving everything I learn about dataset creation; by necessity this will not apply to all models, but will likely apply to most. I'll update this as we gain more information.

1. The ideal dataset for a single speaker is at least 20 hours (consistent with LJspeech). Shorter sequences will still train (and even train well), but expect decreases in quality, especially below the five hour mark.
2. The audio should have clear and consistent prosody. In an ideal world the entire dataset would be recorded by the same person, in the same room, under identical conditions for each clip. This is extremely unlikely to happen 
3. The audio should be free of noise other than the speaker in question (background, other speakers), or as much as possible.
4. The audio should contain no hard silences (E.G. don't hard silence, or reduce gain to 0 for any portion of the clip -- this can result in strange learning behavior and NANs)

#### Training from an LJSpeech model: 

Your dataset should adhere to the following format: 22050khz, 16-bit PCM wav files (signed, little endian for the ubernerds out there), each utterance between 1 and 15 seconds. 1-10 is ideal.

#### Training from a LibriVox model: 

Pending

#### Audio Troubleshooting

Babbling: If your audio has successfully picked up the tone of the speaker but can't produce intelligible language, you likely have inconsistencies in your dataset. Ensure that your dataset is a consistent format (all 16-bit or 32-bit, and not a mix of the two). If everything is normal, check your dataset for bad prosody, poor audio normalization, and other aural outliers.