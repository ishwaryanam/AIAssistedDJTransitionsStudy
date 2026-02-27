This is a repo for the paper An Empirical Study of AI-Assisted DJ-Style Transitions Between Music Excerpts by Karen Severson, Ishwarya Namburu, and Dr. Fahim Khan

Abstract: Many music listeners want playlists that blend tracks seamlessly, but common crossfade features provide limited control over what portions of each track are used and how transitions are formed. We explored an AI-assisted mixing pipeline that lets a user select short excerpts from two songs and attempts to generate DJ-like transitions between them. We evaluated audio similarity using embedding models (CLAP and MERT) and curated a small benchmarking dataset of song pairs labeled \emph{good}, \emph{okay}, and \emph{bad} to stress-test transition quality. We then experimented with Meta's MusicGen in audio-to-audio mode by splicing the tail of the first excerpt with the head of the second and prompting the model to produce a smooth blend. In our tests, MusicGen did not reliably generate seamless transitions and often introduced unrelated continuation. As a baseline, we implemented tempo-aware crossfading with librosa, which produced improved results for compatible song pairs. Future work will explore Magenta-based audio injection and representation blending approaches to combine generative models with reliable signal-processing transitions.

crossFadeTransitions has the transitions created by beatMatchingTransition.py.

musicGenTransitions_AtoA has the audio to audio transitions created by musicGen

musicGenTrasnitions_TtoA has the text to audio transitions.

Prompt 1: Upbeat pop song with trumpets and guitar and a funky vibe

Prompt 2: Classical music with a gloomy sad mood with violin and piano

for beatMatchingTransition.py
Usage:
    python beatMatchingTransition.py <song1> <song1_secs> <song2> <song2_secs> <output_file>

Example:
    python beatMatchingTransition.py ./songPairs/pair1a.mp3 10 ./songPairs/pair1b.mp3 10 test.mp3

music_generation_musicgen.ipynb has all the code relating to the MusicGen model.

songPairs has the specific pairs we used for the transitions in crossFadeTransitions and musicGenTransitions, but the dataset contains more songs.

scoringModels with scoringModels.ipynb has the CLAP and MERT model.

