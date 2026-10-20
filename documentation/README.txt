SUNDANESE SPEECH CORPUS
Spontaneous / conversational speech
IF4071 Speech Processing - Major Assignment Phase 1 - Semester 1 2026/2027

1. OVERVIEW
-----------
Purpose      : training and evaluation data for a Sundanese automatic speech
               recognition (ASR) system (Phase 2)
Language     : Sundanese (main dialect: Priangan; other dialects are noted
               per speaker)
Speech type  : spontaneous speech from semi-structured interviews. Speakers
               answer prompt questions; nothing is read from a script.
Speakers     : 10 native speakers, S01-S05 male, S06-S10 female, aged 18+
Topics       : 4 per speaker (T01 + 3 others), about 3-4 minutes each
                 T01 Introduction       T05 Work/Education
                 T02 Daily              T06 Travel
                 T03 Family             T07 Culture
                 T04 Food
Duration     : about 10-15 minutes per speaker
Audio        : WAV PCM, 16 kHz, 16-bit, mono
Environment  : indoor, relatively quiet room

2. FOLDER STRUCTURE
-------------------
audio/S01..S10/             audio files per speaker
metadata/metadata.csv       one row per audio file
annotation/annotation.csv   one row per speech segment
consent/consent_form/       signed consent forms (personal details redacted)
documentation/README.txt    this file
documentation/qc_report.csv quality control results

3. FILE NAMING
--------------
SXX_TYY_NNN.wav   SXX = speaker, TYY = topic, NNN = file number
Example: S03_T05_001.wav = speaker S03, topic Work/Education, first file

4. METADATA (metadata/metadata.csv)
-----------------------------------
File, Speaker, Gender (M/F), Age, Language/Dialect, Origin (home region),
Language_Background, Topic, Duration (minutes), Sample_Rate, Bit_Depth,
Channels, Environment, Recording_Date, Device, Quality

5. ANNOTATION (annotation/annotation.csv)
-----------------------------------------
Each row is one segment (one speaker turn, about 2-15 seconds).

segment_id, file, speaker (SXX, or INT for the interviewer), gender,
language_dialect, topic, start, end (seconds), transcript, transcript_norm,
events, code_switch (Y/N)

transcript       verbatim, standard Sundanese spelling (e, eu, é), with tags
transcript_norm  lowercase, no tags or punctuation (ready for ASR training)

Tags:
  [noise] [laugh] [cough] [overlap] [unclear] [pause]   special events
  [NAME] [PLACE]                                        anonymized names/places
  <id>...</id>  <en>...</en>                            switch to Indonesian/English

6. QUALITY CONTROL (documentation/qc_report.csv)
------------------------------------------------
Automatic check per file: format, clipping, estimated SNR, speech level.
Manual check by a group member other than the recorder: clear speech, no
other voices, not cut off.

  Good        clear, no clipping, very little background noise
  Acceptable  usable, with minor issues (short noise, slight echo, quiet)
  Reject      unusable; re-recorded where possible, excluded from totals

7. ETHICS
---------
All speakers signed an informed consent form before recording, including
consent to store the data in this repository. Speakers are identified only by
ID. Names and specific places mentioned in speech are replaced with [NAME] or
[PLACE] in transcripts. Real names are not stored in this repository.

8. LICENSE
----------
CC BY-NC 4.0: for education and non-commercial research only.
