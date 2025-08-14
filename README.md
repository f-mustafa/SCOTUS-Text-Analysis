# SCOTUS Text Analysis — LIN 127 (UC Davis)

This project analyzes U.S. Supreme Court oral argument transcripts (SCOTUS corpus) to explore how language differs by **gender**, **age**, and **political ideology** of the justices.  
It also tests text classification methods to label speech as “liberal” or “conservative.”

---

## Why this project matters
- **Real-world relevance:** Supreme Court language reflects legal reasoning, institutional norms, and underlying biases.
- **Technical depth:** Combines text processing, corpus linguistics, visualization, and machine learning.
- **Bias awareness:** Shows limitations of classifiers when dealing with ambiguous human language.

---

##  Methods
1. **Data parsing:** Extracted `.cha` transcripts from the 2007 SCOTUS corpus for Justices Ginsburg (liberal) and Roberts (conservative).
2. **Text analysis:**  
   - Tokenized speech  
   - Calculated top-30 most frequent words per justice  
   - POS-tagged words using NLTK
3. **Modeling:**  
   - Trained a `fastText` classifier on labeled utterances from four justices (two liberal, two conservative)  
   - Tested on new and ambiguous sentences  
   - Compared with a zero-shot classifier (`BART-MNLI`)
4. **Visualization:** Matplotlib plots for top-word frequencies.

---

##  Key results
- Roberts spoke **~6,000 more words** than Ginsburg in the 2007 sample.
- Vocabulary differences reflect gender norms and political style (e.g., Roberts uses “mr” frequently; Ginsburg asks more questions).
- **fastText accuracy** improved with higher learning rate & trigram features, but struggled with ambiguous input (~50–70% accuracy).
- Zero-shot classification confirmed model uncertainty for nuanced sentences.

---

##  How to run
1. **Clone the repo**
   ```bash
   git clone https://github.com/f-mustafa/scotus-text-analysis.git
   cd scotus-text-analysis
