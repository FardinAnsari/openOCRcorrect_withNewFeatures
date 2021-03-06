# openOCRcorrect_withNewFeatures

### kindly add the data folder from the project location in your computer (if you have it) or email me so that I can send it to you as it was too big to upload here. thankyou

## OpenOCRCorrect
A framework for assisting human while correcting the OCR errors in documents, mostly dedicated to Indian Languages.
Tested on Sanskrit, Hindi, Marathi and English.

The interactive features as of now are:-
1. Error detection.
2. Generating Suggestions (will replace this to auto-completion in Future Work).
Please mail to rohitsaluja22@gmail.com or file an issue for any suggestions related to auto-completion.

Following information is updated on the fly, after correction of each page:-
1. A domain specific dictionary which is uploaded on the fly.
2. The domain specific dictionary is also uploaded with OCR words with high confidence as the user starts working on the document.
3. OCR confusions specific to the documents which are uploaded on the fly.

# Video demo

https://tinyurl.com/y7wbpo6m 
1. After laoding the OCR page, as user clicks on Spell Check, the correct words remain black.
2. The purple words are the auto corrections.
3. The incorrect words are colored with blue, green and red strings from Dictionary. This improves readability.
4. The user can type in slp1 format or right click on the word (right click suggestion may be a partially corrected word) to correct the words. "Ctrl+d" converts the slp1 word-under-cursor to Devanagari and removes the color coding from the word-under-cursor.
Right click works after clicking left on the word-under-cursor. Please mail to rohitsaluja22@gmail.com or file an issue for any suggestions to correct this.

# Ubuntu and Qt version

Compiled and Tested on Ubuntu Ubuntu 16.04. with Qt 5

# Installation

1. Add the Shobhika Font to Ubuntu from https://github.com/Sandhi-IITBombay/Shobhika/releases/ for reading Devanagari:
- Download latest version zip.
- Unzip the file.
- Open otf files with Font Viewer.
- Click Install on Top Right Corner.

2. Install qt5:
- $ sudo apt-get install qt5-default

3. Go to folder "FrameWorkCode", compile qpadfinal.pro and make:
- $ cd FrameWorkCode
- $ qmake qpadfinal.pro
- $ make
- Ignore the warnings. Will be removed in the next version.

# How to run the code?

Execute file qpadfinal in folder "FrameWorkCode"
- $ ./qpadfinal

# New feature added
1. bold unbold feature
2. subscript superscript feature.
for reference go to https://github.com/FardinAnsari/TextEditor

# chanllenges
1. To understand the working of OpenOCRcorrect

# How to use the Framework

1) Select the Language out of Sanskrit, Hindi/Marathi or English from top right. Click on the “Open” icon on top left, or press “Ctrl+O”.
2) Open the file “data/Book1Sanskrit/Inds/page-1.txt”. This also link the files and folders in “Book1Sanskrit/”.
3) Click on “Load Data” to load Dictionary, Confusions, Sandhi Rules, GEROCR , IEROCR. Common OCR words in GEROCR and IEROCR will be loaded in Domain Vocabulary. It will take few seconds.
If you forget to “Load Data”, data will be loaded whenever you right click a word.
4) Finally, after loading data, page1.txt will again appear in the text browzer. Left click on the word to change the mouse cursor position and then right click on the colored words to generate suggestions.
5) Type in slp1 format and press “Cntrl+d” to change the text under cursor to Devanagari.
e.g. :-
प्रन्थाङ्कः -> graन्थाङ्कः -> (Cntrl D) -> ग्रन्थाङ्कः
If there are any issues in the format, just right click on the word and select the correct suggestion. Leave the correct colored words as it is.
6) Do not forget to use “Cntrl + S” to save the partially/fully corrected page to folder “Corrected”. Next time you come to the same page, the page will be uploaded from folder “Corrected” automatically.
7) Very Important: Afther the whole page is corrected load the words in Domainvocabulary by clicking “Cntrl + Shift + P”.
8) There is a timer on top left which gets updated on each right click or “Ctrl S”. It resets to 0 on loading the new page. Use “Ctrl+Shift+R” to move to next page and “Ctrl+Shift+L” to move to previous page.
9) As you use “Cntrl + Shift + P” to load domain words, you will observe improvement in suggestions page by page.
10) A useful tip: keep the GEROCR open in an editor as certain correct lines can be directly copied from it.

# Citations

You can read about our papers on: https://www.cse.iitb.ac.in/~rohitsaluja/publication.html
If you use this framework or learn from our publications, please cite our papers:

@article{RohitErrorDetectionNCorrection,
    author="Rohit Saluja and Devaraj Adiga and Parag Chaudhuri and Ganesh Ramakrishnan and Mark Carman",
    title="Error Detection and Corrections in {I}ndic {OCR} using {LSTM}s",
    journal = "International Conference on Document Analysis and Recognition ({ICDAR})",
    location="Kyoto, Japan",
    year="2017"
}

@article{RohitOpenOCRCorrect,
        author="Rohit Saluja and Devaraj Adiga and Parag Chaudhuri and Ganesh Ramakrishnan and Mark Carman",
    title="A Framework for Document Specific Error Detection and Corrections in {I}ndic {OCR}",
    journal="1st International Workshop on Open Services and Tools for Document Analysis (ICDAR- OST)",
    location="Kyoto, Japan",
    year="2017"
}

# References:
1. We started the code (and used icons) from: https://www.youtube.com/watch?v=x858_WCtl_Y
2. We further improved the application via ideas from "QPlainTextEdit With In Line Spell Check". Visit: https://john.nachtimwald.com/2009/08/22/qplaintextedit-with-in-line-spell-check/
3. For generating suggestions and  we used "Algorithm: Edit distance using a trie-tree (Dynamic Programming)" by Author: Murilo Adriano Vasconcelos <muriloufg@gmail.com>.
Visit: https://murilo.wordpress.com/2011/02/01/fast-and-easy-levenshtein-distance-using-a-trie-in-c/
4. For extracting OCR confusions, we used C++ implementation of "A linear space algorithm for computing maximal common subsequences" by D. S. Hirschberg for allignment. Visit  http://portal.acm.org/citation.cfm?id=360861. 
We further developed the code to extract OCR confusions from unalligned OCR text, alligned OCR text and Correct text.
5. Abdulkader, Ahmad, and Mathew R. Casey. "Low cost correction of OCR errors using learning in a multi-engine environment." Document Analysis and Recognition, 2009. ICDAR'09. 10th International Conference on. IEEE, 2009.
