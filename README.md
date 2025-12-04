# ASR Evaluation and Signal Processing Analysis

## 1. Overview

This project evaluates the performance of two Automatic Speech
Recognition (ASR) systems using standard error metrics and analyzes the
corresponding audio signal using time-frequency and energy-based
visualizations.

The evaluation includes: - Word Error Rate (WER) - Character Error Rate
(CER) - Waveform Visualization - STFT Magnitude Spectrogram - RMS Energy
Plot

------------------------------------------------------------------------

## 2. Input Data

The following files were used: - `single_s1_22032_11908_asr1.tsv` -- ASR
System 1 output - `single_s1_22032_11908_asr2.tsv` -- ASR System 2
output - `single_s1_22032_11908.wav` -- Audio signal - Each TSV
contains: - Start Time (s) - End Time (s) - ASR Hypothesis - Reference
Transcript

------------------------------------------------------------------------

## 3. Evaluation Metrics

### Word Error Rate (WER)

WER measures the number of word-level errors: WER = (Substitutions +
Insertions + Deletions) / Total Reference Words

### Character Error Rate (CER)

CER measures transcription errors at the character level: CER =
(Character Edits) / Total Reference Characters

------------------------------------------------------------------------

## 4. Results

  System   WER      CER
  -------- -------- --------
  ASR1     0.3197   0.1513
  ASR2     0.9827   0.8294

### Performance Comparison

-   Based on **WER**, the better-performing system is: **ASR1**
-   Based on **CER**, the better-performing system is: **ASR1**

Overall, the system with consistently lower error rates demonstrates
superior transcription accuracy.

------------------------------------------------------------------------

## 5. Signal Processing Analysis

### 5.1 Waveform

-   Displays the raw audio signal.
-   Segment boundaries from the TSV files are overlaid as shaded
    regions.
-   Helps visualize speech distribution across time.

### 5.2 STFT Spectrogram (dB)

-   Shows frequency content of speech over time.
-   Higher intensity regions represent dominant speech frequencies.
-   Helps identify voiced vs unvoiced segments.

### 5.3 RMS Energy (dB)

-   Shows short-term energy variations.
-   Peaks correspond to active speech regions.
-   Valleys indicate silence or low-energy sounds.

------------------------------------------------------------------------

## 6. Inferences from Graphs

-   Speech segments align well with waveform and RMS peaks.
-   The spectrogram shows consistent speech energy in lower and
    mid-frequency bands.
-   Silence regions exhibit lower RMS energy and reduced spectral
    strength.

------------------------------------------------------------------------

## 7. How to Run the Code

### Requirements

-   Python 3.x
-   numpy
-   pandas
-   matplotlib
-   scipy
-   pypandoc

### Run Command

``` bash
python asr_evaluation.py
```

### Output Files

-   `asr_metrics.csv`
-   `waveform.png`
-   `spectrogram.png`
-   `rms_energy.png`

------------------------------------------------------------------------

## 8. Conclusion

This project successfully evaluates two ASR systems using both
word-level and character-level metrics. Based on the computed WER and
CER values, **ASR1** demonstrates better overall transcription
performance. The signal processing visualizations further confirm
accurate segmentation and speech activity.

------------------------------------------------------------------------

## 9. Submission

All scripts, results, and this README should be uploaded to a GitHub
repository and the repository link submitted as the final deliverable.
