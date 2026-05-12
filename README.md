# Early Success Prediction of Indian Movies using Subtitles

A two-stage machine learning pipeline that predicts whether an Indian film will be commercially successful — before it releases — using only its subtitle text. Instead of relying on star power or budget, this approach treats screenplays as documents and extracts semantic features using custom document embeddings.

Published in the **International Journal of Image and Graphics** (World Scientific, Vol. 23, No. 4, 2023).

📄 [Read the Paper](https://www.worldscientific.com/doi/abs/10.1142/S0219467823500304)

---

## How It Works

The pipeline has two stages:

**Stage 1 — ROI Prediction (Regression)**  
Takes a subtitle file, converts it into a fixed-length vector using Doc2Vec (Paragraph Vector), and predicts the film's Return on Investment.

**Stage 2 — Success Classification**  
Uses the predicted ROI to classify the film as successful or unsuccessful.

```
Subtitle (.srt) → Preprocessing → Doc2Vec Embedding → Regressor (ROI) → Classifier (Hit/Flop)
```

The custom embedding model (**Sub2Vec**) was trained on 2700+ subtitle files to learn semantic representations of screenplay content — capturing narrative structure, dialogue patterns, and thematic elements as 50/100-dimensional vectors.

---

## Dataset

| Detail | Value |
|--------|-------|
| Total films | 2700+ |
| Industries covered | Bollywood, Kollywood, Tollywood, Mollywood, Sandalwood |
| Languages | Hindi, Tamil, Telugu, Malayalam, Kannada |
| Features | Subtitle-derived Doc2Vec vectors + metadata |
| Target variable | ROI (Stage 1), Success/Failure (Stage 2) |

---

## Results

Multiple regressor-classifier combinations were evaluated. Best performing:

| Model Combination | F1-Score | Cohen's Kappa |
|-------------------|----------|---------------|
| **XGBoost Regressor + AdaBoost Classifier** | **0.77** | **0.48** |

Other combinations tested include Random Forest, Gradient Boosting, SVR, and Lasso as regressors, paired with SVM, Logistic Regression, and Decision Tree classifiers.

---

## Tech Stack

| Component | Technology |
|-----------|------------|
| Embeddings | Doc2Vec (Paragraph Vector / Sub2Vec) |
| Regression | XGBoost, Random Forest, SVR, Lasso, Gradient Boosting |
| Classification | AdaBoost, SVM, Logistic Regression, Decision Tree |
| Language | Python |
| Libraries | Gensim, Scikit-learn, XGBoost, Pandas, NumPy, Matplotlib |

---

## Project Structure

```
├── codes/            # Training, embedding generation, and evaluation scripts
├── dataset/          # Subtitle files and metadata
├── project-report/   # Final year project report
├── LICENSE           # MIT License
└── README.md
```

---

## Citation

If you use this work, please cite:

```bibtex
@article{tejas2023subtitle,
  title={Early Success Prediction of Indian Movies using Subtitles: A Document Vector Approach},
  author={Tejas Manoj and Vaddadi Sai Rahul and Narayanan Prasanth, N. and Raja, S. P.},
  journal={International Journal of Image and Graphics},
  volume={23},
  number={04},
  year={2023},
  publisher={World Scientific}
}
```

---

## Authors

- **Tejas Manoj** — [GitHub](https://github.com/iam-teju) · [LinkedIn](https://www.linkedin.com/in/iamteju/)
- Vaddadi Sai Rahul
- N. Narayanan Prasanth
- S. P. Raja

Supervised by **Dr. Jothi K.R.**, VIT Vellore
