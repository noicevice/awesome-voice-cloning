# On Training Waveglow - Scripp

A custom waveglow model can significantly increase the quality of your trained Tacotron2 vocalizations. NVIDIA's pretrained model (256 channel Waveglow V5) was trained on the LJ speech dataset, which has a number of issues including a general lack of low-end vocalizations and a moderate to strong bias towards sibilance. It will perform relatively well when synthesizing female voices or in initial model evaluations, but if you find its quality lacking you may want to consider training your own. Training a custom waveglow model takes significantly longer than training a Tacotron2 model; you can expect to train it up to 300,000 steps.

Below is an example courtesy of AI Clone Voices; the first is a sample of his Argonian Male tacotron2 model synthesized with NVIDIA's default waveglow model. The second is the same text synthesized with a custom, from-scratch trained waveglow model, at 270,000 iterations, which trained for approximately 220 hours on p100 GPU via Google Colab. The dataset is 53 minutes in length, and was trained using the Tacotron-2 For Dummies colab, with default settings.

Male Argonian on 256 Channel WaveGlow V5:
https://drive.google.com/file/d/17Fequd5ZP6IlqsFyzY0Siz3_FIdC_eF0/view

Male Argonian running the custom trained wave glow using the same training data:
https://drive.google.com/file/d/1tRH_BI-UPELmzvMAHoj9q8whWK2lNCIy/view


Credit to AI Clone Voices for testing, samples, and information on this process.