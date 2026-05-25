# Naive Bayes Classifier — Play Tennis

A from-scratch implementation of the **Naive Bayes (Maximum A Posteriori)** classifier applied to the classic Play Tennis dataset. Built manually using probability lookup tables — no sklearn, no magic.

---

## Dataset

**`play_tennis.csv`** — 14 labeled training examples with 4 categorical features:

| Feature | Values |
|---|---|
| `outlook` | Sunny, Overcast, Rain |
| `temp` | Hot, Mild, Cool |
| `humidity` | High, Normal |
| `wind` | Weak, Strong |
| `play` (label) | Yes (9), No (5) |

---

## How It Works

### Naive Bayes (MAP Rule)

For a new instance, the classifier computes the posterior probability for each class and picks the maximum:

```
P(Yes | outlook, temp, humidity, wind)
  = P(Yes) × P(outlook|Yes) × P(temp|Yes) × P(humidity|Yes) × P(wind|Yes)

P(No  | outlook, temp, humidity, wind)
  = P(No)  × P(outlook|No)  × P(temp|No)  × P(humidity|No)  × P(wind|No)
```

Whichever is larger → predicted class.

### Training

Probabilities are computed manually using `pd.crosstab()` to build a lookup table for each feature:

- **Class priors:** `P(Yes) = 9/14`, `P(No) = 5/14`
- **Likelihoods:** counted per feature value per class (e.g., `P(Sunny|Yes) = 2/9`)

---

## Example Predictions

### Problem 1 — `Sunny, Hot, High humidity, Weak wind`

```
P(Yes | ...) = (9/14) × (2/9) × (2/9) × (3/9) × (6/9) ≈ 0.0053
P(No  | ...) = (5/14) × (3/5) × (2/5) × (4/5) × (2/5) ≈ 0.0274
→ Prediction: NO PLAY
```

### Problem 2 — `Overcast, Cold, Low humidity, Weak wind`

```
P(Yes | ...) = (9/14) × (4/9) × (3/9) × (6/9) × (6/9)
P(No  | ...) = (5/14) × (0/5) × ...
→ Prediction: PLAY (P(No) = 0 due to zero probability)
```

---

## Files

```
├── naive_bayes.ipynb   # Main notebook with step-by-step implementation
└── play_tennis.csv     # Training dataset (14 samples)
```

---

## Requirements

```bash
pip install numpy pandas
```

---

## Run

```bash
jupyter notebook naive_bayes.ipynb
```

---

## Key Concepts Covered

- Conditional probability and Bayes' theorem
- Class prior and likelihood estimation from data
- Maximum A Posteriori (MAP) classification rule
- Zero-probability problem (when a feature value never appears in a class)
- Manual probability tables using `pd.crosstab()`
