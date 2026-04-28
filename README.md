# NLP Workshop: Text EDA, Classification & Beyond

A hands-on group workshop on Natural Language Processing — text EDA, preprocessing, classification, similarity, topic modelling, sentiment, and quantification — with integrated Git collaboration practice.

## Prerequisites

- Python 3.9+
- Required packages:
  ```bash
  pip install pandas numpy matplotlib seaborn scikit-learn scipy jupyter \
              nltk textstat wordcloud joblib nbdime
  ```
- Optional (Bonus Track on Swedish text):
  ```bash
  pip install datasets langdetect
  ```
- One-time NLTK downloads (run once in Python):
  ```python
  import nltk
  nltk.download('stopwords'); nltk.download('wordnet'); nltk.download('vader_lexicon')
  ```

## Git workflow for students

This workshop integrates Git collaboration. You work in **groups of 3**.

1. **One person forks** this repository on GitHub.
2. **Add groupmates as collaborators** (Settings → Collaborators).
3. **Everyone clones** the same fork:
   ```bash
   git clone https://github.com/<FORK-OWNER>/Workshop-NLP.git
   cd Workshop-NLP
   ```
4. **Parts 0–3:** Work together on `main` — load data, EDA, preprocessing.
5. **Part 3.5:** Configure `nbdime` so notebook merge conflicts are readable.
6. **Part 4:** Each member creates a branch for one classifier:
   ```bash
   git checkout -b experiment/countvec-nb        # member 1
   git checkout -b experiment/tfidf-logreg       # member 2
   git checkout -b experiment/tfidf-svm          # member 3
   ```
7. **Commit and push** your experiment branch:
   ```bash
   git add nlp_workshop.ipynb
   git commit -m "Complete experiment: <classifier>"
   git push -u origin experiment/<classifier>
   ```
8. **Open Pull Requests** from each branch to `main`.
9. **Review, resolve any merge conflicts with `nbdime`, and merge.**
10. **Parts 5–8:** Synthesize as a group on `main` — topics, sentiment, pipeline, deployment hand-off.

## Workshop structure

| Part | Topic | Time | Who |
|------|-------|------|-----|
| 0 | Repository & Group Setup | ~10 min | Group |
| 1 | First Contact with Text | ~15 min | Group, on `main` |
| 2 | Text EDA | ~25 min | Group, on `main` |
| 3 | Pre-processing | ~20 min | Group, on `main` |
| 3.5 | Resolving notebook merge conflicts | ~10 min | Group exercise |
| 4 | Vectorize & Classify | ~30 min | Individual (one classifier per branch) |
| 5 | Pull Requests & Comparison | ~15 min | Group |
| 6 | Topic Modelling & Similarity | ~15 min | Group, on `main` |
| 7 | Sentiment & Quantification | ~15 min | Group, on `main` |
| 8 | Synthesis & Pipeline Hand-off | ~10 min | Group, on `main` |
| Bonus | Swedish Text Track | optional | Anyone |

Total: ~2 hours hands-on (plus optional bonus).

## Difficulty levels

- ⭐ Basic — everyone should complete these
- ⭐⭐ Intermediate — aim for these if you are comfortable with scikit-learn
- ⭐⭐⭐ Challenge — stretch goals for experienced students

## Datasets

**Default:** `20newsgroups` — built into scikit-learn, two categories (`sci.space`, `sci.med`). No download needed.

**Bonus track:** [`timpal0l/swedish_reviews`](https://huggingface.co/datasets/timpal0l/swedish_reviews) — ~100k Swedish product reviews with sentiment labels, loaded via `datasets.load_dataset()`. Use this if your group project deals with Swedish text.

You can also bring your own text dataset (any CSV with a text column and a label column).

## Files

```
Workshop-NLP/
├── README.md                       ← you are here
├── .gitignore
├── nlp_workshop.ipynb              ← student notebook
├── 20260428 Workshop NLP.pptx      ← presentation slides
└── data/                           ← (optional, for your own datasets)
```

## License

Free to use for teaching purposes.
