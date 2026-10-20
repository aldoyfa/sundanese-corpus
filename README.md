# Sundanese Speech Corpus

A spontaneous speech corpus of Sundanese, built for IF4071 Speech Processing
(Major Assignment Phase 1, Semester 1 2026/2027). It will be used to train and
evaluate a Sundanese speech recognition system in Phase 2.

| | |
|---|---|
| Language | Sundanese (main dialect: Priangan) |
| Speech type | Spontaneous, semi-structured interviews |
| Speakers | 10 native speakers (5 male, 5 female) |
| Topics | 4 per speaker, from Introduction, Daily, Family, Food, Work/Education, Travel, Culture |
| Duration | About 10–15 minutes per speaker |
| Audio | WAV, 16 kHz, 16-bit, mono |

## Structure

```
audio/S01..S10/              audio files per speaker (SXX_TYY_NNN.wav)
metadata/metadata.csv        one row per audio file
annotation/annotation.csv    one row per speech segment
consent/consent_form/        signed consent forms (personal details redacted)
documentation/README.txt     full corpus documentation
documentation/qc_report.csv  quality control results
```

See [documentation/README.txt](documentation/README.txt) for file naming, column descriptions,
annotation tags, and QC criteria.

## License

CC BY-NC 4.0. For education and non-commercial research only.
