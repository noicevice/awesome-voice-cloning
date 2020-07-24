# Cam's Dataset Creation Workflow

I think this could be perfected with the underlying libraries in this first script. 

I'd take my full audio file of voice and run it through autosub (https://github.com/BingLingGroup/autosub) that would use auditok to split the file into several based on silences (I set a minimum time and max time too, so it can be 10s max or 3s min if you wanted), it creates an srt file that matches the original long file but with all of the in/outs of the silence detection it found. 

Then it sends every all of the clips to Google's Cloud Speech (has other options too), and what it gets back is a new subtitle file with all of the times and transcriptions. 

With that subtitle file and your original long audio file, run it through https://github.com/cubrink/srt-parse (I modified it for lossless wav https://github.com/camjac251/srt-parse, the main repo uses mp3, make sure you add your csv seperator to | instead of a comma, better for sentences with commas), and then it creates a new folder called out and inside will be all of your clips numbered (although not padded, which could help) and a csv file that is in LJSpeech format. 

Finally I just run that through https://github.com/cubrink/LJNormalize


# Future Improvements

One problem with the workflow tho is that audiotok sometimes cuts off the end sounds to words, so instead of cars you'd have ca or sometimes car. kind of broken atm