# seismosonify
1:1 Earthquake Sonifier (Live Web Client coming soon)

This is a 1:1 seismic data sonifier. It takes any seismic data input, such as a station recording from a historical earthquake (or a real-time SeedLink stream) and converts it to audio in the human hearing range while maintaining the 1:1 timescale.

I presented this at the 2026 Las Vegas Curiosity Lab hosted by the Desert Research Institute on 09-16-2026. For those of you who couldn't make it, I will be linking a live web client here where you can use my tool. The application itself is stable-ish (it works), I just need to create a web client for it.

I plan on presenting this at SSA2027, will keep posting updates here.

How it works: Accepts an input of any seismic data in miniseed format (0-20Hz default filter but editable) and upscales each sample to the 2000-4000Hz range using a custom vocoder while preserving the original length of each sample. This differs from most sonification approaches in the sense that it preserves the original 1:1 timescale instead of speeding the entire waveform up by a large factor (typically several hundred times faster), allowing the user to listen to the data at the same timescale it was recorded at. The output frequency map is spread across 2000-4000Hz to make subtle variations in frequency obvious to the human listener. This also has a livestreaming panel where the user can input a SeedLink address for the application to continually play a real-time audio stream from the seismic data as it reads it while accounting for latency on its own. Multiple SeedLink streams are supported and can run in parallel while maintaining a buffer for each, allowing the user to quickly switch between streams. Both the live playback and event playback support a local (0.1-20Hz) filter range and a teleseismic (0.01-0.5Hz) filter range. Within both of these ranges, the top and bottom cutoff frequencies are adjustable. The filter applies to both the seismogram + spectrogram plots and to the audio playback. I built an event selector and station selector into this which pulls from FDSN and USGS, allowing the user to search for any earthquake (USGS) recorded by any station (present on FDSN) and generate a video of its sonification with a custom start / end time. I added in a timescale factor (to speed up the full audio recording) because I found that listening to an hour long teleseism on a 1:1 timescale can sound like an endless drone without much variation. BTW you can also export images and videos of past events (and real-time plots) with plenty of customization options. That's the gist of what I've been working on lately, I'll be cleaning this wall of text a bit later as I get this project a bit more organized.


I will be writing up better documentation for this once I publish the web client. At the moment I'm in the middle of my university semester so I can't promise any exact dates quite yet. This should be up by SSA2027 at the latest.


I will be posting sample videos here in the meantime.


The concept is my Prior Art. The application itself was developed for the 2026 DRI Curiosity Lab.


The web client will be free to use upon release and is intended strictly for non-commercial use. This is completely free to use as long as you link to this repository somewhere visibly (or mention me) and as long as the use is non-commercial.

---THIS PRODUCT AND ITS SONIFICATION APPROACH IS FOR NON-COMMERCIAL USE ONLY---
