# Sundanese Speech Corpus

A Sundanese monologue speech corpus, built for IF4071 Speech Processing
(Major Assignment Phase 1, Semester 1 2026/2027). It will be used to train and
evaluate a Sundanese speech recognition system in Phase 2.

| | |
|---|---|
| Language | Sundanese |
| Speech type | Monologue, one recording per topic |
| Speakers | 10 (5 male, 5 female), from different regions |
| Topics | Introduction, Daily, Family, Food, Work/Education, Travel, Culture (at least 4 per speaker) |
| Duration | 117.4 minutes in 51 files (about 10-15 minutes per speaker) |
| Audio | WAV, 16 kHz, 16-bit, mono |
| Annotation | 480 segments with transcripts, speaker, topic and event tags |

## Structure

```
audio/S01..S10/              audio files per speaker (SXX_TYY_NNN.wav)
metadata/metadata.csv        one row per audio file
annotation/annotation.csv    one row per speech segment
consent/consent_form/        signed consent forms (personal details redacted)
documentation/README.txt     full corpus documentation
documentation/qc_report.csv  quality control results
documentation/G06_Laporan_01.pdf  project report
```

See [documentation/README.txt](documentation/README.txt) for file naming, column
descriptions, annotation tags, quality control and known limitations. Note that
transcripts of S01-S08 are uncorrected ASR output.

## License

CC BY-NC 4.0. For education and non-commercial research only.
