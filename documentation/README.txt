SUNDANESE SPEECH CORPUS
Narrative monologue speech in Sundanese
IF4071 Speech Processing - Major Assignment Phase 1 - Semester 1 2026/2027

1. OVERVIEW
-----------
Purpose      : training and evaluation data for a Sundanese automatic speech
               recognition (ASR) system (Phase 2)
Language     : Sundanese
Speech type  : monologue. Each speaker talks about themselves on assigned
               topics (one recording per topic). There is no interviewer.
Speakers     : 10 (5 male: S01-S05, 5 female: S06-S10)
Topics       : T01 Introduction       T05 Work/Education
               T02 Daily              T06 Travel
               T03 Family             T07 Culture
               T04 Food
               Every speaker covers at least 4 topics.
Duration     : 117.4 minutes in 51 files, 9.8-14.9 minutes per speaker
Audio        : WAV PCM, 16 kHz, 16-bit, mono
Environment  : indoor, relatively quiet room

2. SPEAKERS
-----------
  ID  Sex Age    Origin                 Files Minutes
  S01   M   18-22  Malang, Jawa Timur      4     12.8
  S02   M   18-22  Blitar, Jawa Timur      5     13.5
  S03   M   18-22  Malang, Jawa Timur      5     10.1
  S04   M   18-22  Jakarta                 7     11.1
  S05   M   18-22  Buah Batu, Bandung      4     14.9
  S06   F   18-22  Malang, Jawa Timur      4     12.9
  S07   F   18-22  Malang, Jawa Timur      7      9.8
  S08   F   18-22  Bandung                 6     11.6
  S09   F   18-22  Bekasi, Jawa Barat      5     10.7
  S10   F   50-59  Karawang, Jawa Barat    4     10.2

Speakers come from different regions (see Origin), and their everyday use of
Sundanese varies. Real names are not stored in this repository.

Minutes per topic:
  Daily            26.6 min
  Introduction     22.6 min
  Food             18.8 min
  Culture          17.9 min
  Work/Education   15.8 min
  Travel            9.8 min
  Family            5.9 min

3. FOLDER STRUCTURE
-------------------
audio/S01..S10/             audio files per speaker
metadata/metadata.csv       one row per audio file
annotation/annotation.csv   one row per speech segment
consent/consent_form/       signed consent forms (personal details redacted)
documentation/README.txt    this file
documentation/qc_report.csv quality control results
documentation/IF4071-...pdf assignment specification
documentation/G06_Laporan_01.pdf  project report (group 6)

File naming: SXX_TYY_NNN.wav
  SXX = speaker, TYY = topic, NNN = file number for that speaker and topic
  Example: S04_T05_001.wav = speaker S04, topic Work/Education, first file

4. HOW THE AUDIO WAS PREPARED
-----------------------------
- Recorded with smartphones indoors. For S01-S04 and S06-S08 each session was recorded
  with two phones at the same time; the cleaner recording (higher estimated
  SNR) was kept and the other was not used.
- Original files (AAC .m4a, 48 kHz) were converted once with ffmpeg to
  16 kHz, 16-bit, mono WAV. S05 was delivered as 48 kHz WAV and resampled the
  same way; S10 was delivered as 16 kHz WAV. No noise reduction,
  normalisation or other processing was applied.
- Long sessions were cut into one file per topic at the quietest point near
  each topic change. Cut points are approximate (a few seconds). Parts of S01
  beyond the 10-15 minute target and a closing chat at the end were left out.

5. METADATA (metadata/metadata.csv)
-----------------------------------
File, Speaker, Gender (M/F), Age (range), Language/Dialect, Origin (home
region), Language_Background, Topic, Duration (minutes), Sample_Rate,
Bit_Depth, Channels, Environment, Quality (Good/Acceptable/Reject)

Language/Dialect is "Sundanese" for all files; no regional dialect was
assigned. Language_Background is left empty.

6. ANNOTATION (annotation/annotation.csv)
-----------------------------------------
Each row is one segment of about 15 seconds, cut at pauses.

segment_id, file, speaker, gender, language_dialect, topic, start, end
(seconds), transcript, transcript_norm, events, code_switch (Y/N)

transcript       text with tags
transcript_norm  lowercase, no tags or punctuation (ready for ASR training)

Tags used:
  [NAME]     a personal name (masked)
  [laugh]    laughter
  [unclear]  words that could not be recovered
Tags defined but not observed: [noise] [cough] [overlap] [pause], and
<id>...</id> / <en>...</en> for code-switching (code_switch is N everywhere).

How the transcripts were made:
- Automatic speech recognition (Whisper medium fine-tuned for Sundanese) on
  windows of about 15 s cut at pauses.
- S09 and S10: the ASR output was refined with text alignment, giving cleaner
  transcripts.
- S01-S08: ASR output only. Personal names were masked, but the text has NOT
  been fully corrected, so it contains recognition errors (misheard or
  misspelled words). Use with care, for example by filtering or by manual
  correction before training.

7. QUALITY CONTROL (documentation/qc_report.csv)
------------------------------------------------
Every file was checked for format, duration, clipping, speech level and
estimated SNR (90th minus 10th percentile of 25 ms frame energy).

  Good        no clipping, SNR >= 20 dB
  Acceptable  light clipping or SNR 10-20 dB or very quiet
  Reject      heavy clipping, SNR < 10 dB or wrong format

Result: all 51 files are Good (SNR 20.6-40.4 dB, median 37.9 dB; no
clipping). The final label of each file is in the final_label column.
S09 has the lowest SNR (20.6-22.2 dB); it was recorded at a lower bitrate.

8. KNOWN LIMITATIONS
--------------------
- Transcripts of S01-S08 are uncorrected ASR output (see section 6).
- Segment boundaries are about 15 s windows, not exact utterances.
- S07 has 9.8 minutes, slightly below the 10 minute target.
- Topics are not evenly covered (Family 5.9 min, Travel 9.8 min).
- Age is given as a range. Speaker S10 is the only speaker outside 18-22.

9. ETHICS
---------
All speakers gave informed consent before recording, including consent to
store the data in this repository. Speakers are identified only by ID. Personal
names in the transcripts are replaced by [NAME]. Real names and contact
details are not stored.

10. LICENSE
-----------
CC BY-NC 4.0: for education and non-commercial research only.
