
This dataset contains acapella singing of classical Turkish makam recordnigs sung from semi-professional singers  

Annotations of secitons (aranağme, zemin etc.) are taken from https://github.com/MTG/turkish_makam_section_dataset 
Annotations of lyrics words and lyrics phrases are done by georgi.dzhambazov@upf.edu
FORMAT: All annotations in TextGrid (used in Praat) 

-------------------------
-------------------------

!! Please help annotate not annotated audio !!

INSTRUCTIONS  how to assign each segment of the audio to its corresponding word from the lyrics with the software tool Praat:

Songs are divided into sections, so work we with the audio for a given section (chorus/verse).
The corresponding lyrics can be found in .pdf files on the given file lyrics.txt    

We generate files with extension .TextGrid: with tier named *words*

Audio files have name: 
number_compositionNameShort_sectionNumber_sectionName.wav
where sectionNumber comes from the .tsv file

.tsv file has to be number of note on which lyrics for the section start (not note of no lyrics)


-------------------------

Annotation instructions:


Download Praat from http://www.fon.hum.uva.nl/praat/

Check the video:
https://www.youtube.com/watch?v=0zvRrB66zOk


-------------------------
OPTIONAL (if you need score):
Parse score  (to make sure annotatiaon is done on words in score, not on "what is heard")
python https://github.com/georgid/Lyrics2AudioAligner/blob/master/AlignmentStep/MakamScore.py <pathTOScore_indicated_in_lyrics.txt_>
e.g. python /Users/joro/Documents/Phd/UPF/voxforge/myScripts/AlignmentStep/MakamScore.py /Users/joro/Documents/Phd/UPF/turkish-makam-lyrics-2-audio-test-data/nihavent--sarki--aksak--koklasam_saclarini--artaki_candan/


-------------------------
Select PRAAT-> PREFERENCES -> TEXT WRITING PREFERENCES and make sure UTF-8 is selected as encoding

OPEN -> READ FROM FILE   Select the .wav file 

button ANNOTATE -> to TextGrid

All tier names: words

Which of these are point tiers? (leave empty)

Select Sound and TextGrid objects together. Button VIEW AND EDIT


-------------------------

Enter lyrics in top pane

press Tab to play 

press Enter to mark end of a word in audio 

NOTE: you can adjust an existing annotation mark by dragging left or right

-------------------------

FILE -> Save .TextGrid file as text file

send ready files to  georgi.dzhambazov@upf.edu 

Leave long (over 0.2 secs) silent sections empty

--------------
Annotated example: 

open with Praat goekhan/02_Kimseye_Part1_zemin.TextGrid  

open goekhan/02_Kimseye_Part1_zemin.wav 

Select Sound and TextGrid objects together. Button VIEW AND EDIT




-------------------------
some scripts : 
cd <dir_with_wav>;
for i in `ls *.wav`; do sox  $i -b 16 output.wav; mv output.wav $i; done
