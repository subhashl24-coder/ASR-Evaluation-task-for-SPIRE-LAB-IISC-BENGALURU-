# ASR Evaluation and Signal Processing Analysis
ASR Evaluation and Audio Analysis – SPIRE Lab
This repository contains Python programs, evaluation outputs, signal-processing visualisations, and a detailed written report comparing two Automatic Speech Recognition (ASR) systems using the Word Error Rate (WER) and Character Error Rate (CER). It also includes analyses such as spectrograms, waveforms, and RMS energy plots for the speech audio.

1. How the Code Functions
1.1 ASR Evaluation Script (evaluate_asr.py)
This script measures the transcription accuracy of two ASR systems.
Processing steps:
Loads the input TSV files that include:
start time of each segment
end time of each segment
ASR system output
human-annotated reference transcript
Normalises text by converting it to lowercase and removing unnecessary spaces.
Uses the jiwer alignment toolkit to compute:
sentence-level WER
sentence-level CER
Concatenates the full transcript and calculates:
overall WER for the corpus
overall CER for the corpus
Stores all results in CSV files and prints the evaluation summary.
This script enables straightforward comparison between the two ASR systems.
1.2 Audio Analysis Script (audio_visualize.py)
This script carries out basic signal-processing operations on the input audio file.
Processing steps:
Loads the waveform using librosa
Generates visualisations including:

waveform
spectrogram (time–frequency representation)
RMS energy curve

These plots reveal pauses, changes in loudness, speaking rate, and parts of the audio that may influence ASR accuracy.

2. How to Run the Code
2.1 Installing Dependencies
pip install pandas jiwer librosa matplotlib numpy

2.2 Running ASR Evaluation
python evaluate_asr.py

This will:


Read both ASR TSV inputs


Compute sentence-level and corpus-level WER/CER


Produce:


asr1_results.csv


asr2_results.csv




Display summary performance scores in the terminal


2.3 Running Audio Analysis
python audio_visualize.py

This command will show the following plots one after another:


waveform


spectrogram


RMS energy


These visualisations can be saved and added to the final report.

3. Understanding WER and CER
Word Error Rate (WER)
WER measures transcription accuracy at the word level and is calculated using:
WER=S+D+INWER = \frac{S + D + I}{N}WER=NS+D+I​
Where:


S = Substitutions


D = Deletions


I = Insertions


N = Total reference words


Lower WER values indicate better ASR accuracy.
Character Error Rate (CER)
CER works similarly to WER but evaluates errors at the character level.
It helps identify spelling-level and fine-grained recognition mistakes.
Both metrics are computed through jiwer, which aligns ASR outputs with reference transcripts.

4. Results and System Comparison
After running the evaluation:
ASR SystemWER (approx.)CER (approx.)ASR10.270.13ASR20.470.22
Interpretation


ASR1 demonstrates fewer errors across both word-level and character-level metrics.


ASR2 exhibits higher substitution, deletion, and insertion counts.


ASR1 aligns more closely with the human transcript and maintains sentence structure better.


Conclusion
ASR1 clearly outperforms ASR2 based on WER and CER.
Thus, ASR1 is the preferred system for this dataset.

5. Audio Signal-Processing Interpretation
5.1 Waveform Analysis
The waveform displays several spoken segments separated by noticeable silent gaps.
High-amplitude portions represent active speech, while flat regions reflect pauses.
The segmented speaking style influences ASR segmentation and alignment.
5.2 Spectrogram Analysis
The spectrogram shows that most speech energy lies under ~6 kHz, consistent with natural speech.
Voiced areas exhibit harmonic and formant patterns, while silence areas show minimal activity.
Spectral variations correspond to differences in articulation clarity, which can influence ASR performance.
5.3 RMS Energy Curve
The RMS energy curve mirrors the waveform—peaks correspond to voiced speech and low levels represent silence.
Stronger energy sections generally help ASR recognition, while softer regions may cause transcription errors.
Combined Observations


All three plots highlight clear voiced and silent segments.


The spectral characteristics indicate typical conversational speech.


Higher-energy regions correlate with better ASR accuracy, supporting the observation that ASR1 performs more reliably than ASR2.


Screenshots of the plots are included in the PDF report and saved in the repository.

6. Repository Contents
The project folder contains:

evaluate_asr.py – script for computing WER/CER

audio_visualize.py – script for waveform/spectrogram/RMS plotting

single_s1_22032_11908_asr1.tsv – ASR1 output with timestamps and references

single_s1_22032_11908_asr2.tsv – ASR2 output with timestamps and references

asr1_results.csv, asr2_results.csv – generated evaluation files

final report PDF with analysis and figures

7. Acknowledgment
Dataset and task instructions were provided by SPIRE Lab, Indian Institute of Science (IISc), Bengaluru.

8. Author
Subhash
