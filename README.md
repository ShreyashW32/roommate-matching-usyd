# Roommate Matching (USyd)

A Flask web app that matches students with compatible roommates from their
lifestyle survey answers.

## How it works

1. **Preprocessing.** Survey answers such as hobbies, sports and habits are label-encoded and min-max scaled. Missing answers become "No Preference".
2. **Similarity.** Cosine similarity is computed between every pair of students.
3. **Constraints.** Matches respect each student's gender and preferred roommate gender.
4. **Serving.** Results are precomputed into `roommate_results.pkl`. You enter a name and the app returns that student's top matches.

## Run locally

```bash
pip install -r requirements.txt
python app.py
# open http://127.0.0.1:5000
```

To rebuild the matches from new survey data, run `PICKLE.py`, which uses
`roommate_algorithm.py`.

## Tech

Python, Flask, pandas and scikit-learn (cosine similarity), deployed with Gunicorn.
