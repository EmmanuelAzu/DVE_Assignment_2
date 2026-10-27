# COMS4060A/7056A – Assignment 2: NYC Taxi Trips

Geospatial and time-series analysis of the NYC TLC taxi trips (Kaggle *nyc-taxi-trip-duration*, `train` file only, January–June 2016).

## Contents

| File / folder | What it is |
|---|---|
| `DVE_Assignment_2.ipynb` | The notebook: one section per question (1 cleaning, 2 features, 3 time, 4 location clusters, 5 airports, 6 PCA / t-SNE / UMAP). Outputs are saved, so results can be read without running it. |
| `DVE_Assignment_2_Report.pdf` | The report (NeurIPS style) discussing all answers with the plots. |
| `report/` | LaTeX source of the report (`main.tex`) and the NeurIPS style file. |
| `figures/`, `maps/` | Plots used in the report; interactive hotspot maps (open the `.html` files in a browser). |
| `requirements.txt` | Python packages needed to run the notebook. |
| `nyc-taxi-trip-duration.zip` | The dataset (contains `train.zip`, `test.zip`, `sample_submission.zip`; only the training data is used). |

## How to run the notebook

1. **Python 3.10 or newer**, then install the packages (a virtual environment is recommended):

   ```bash
   python -m venv .venv
   source .venv/bin/activate        # Windows: .venv\Scripts\activate
   pip install -r requirements.txt
   ```

2. **Data.** Nothing to do if `nyc-taxi-trip-duration.zip` is in this folder. Otherwise put the training data next to the notebook (or in a `data/` folder next to it) in any one of these forms: `train.csv`, `train.zip`, or `nyc-taxi-trip-duration.zip`.

3. **Start Jupyter and run everything:**

   ```bash
   jupyter notebook DVE_Assignment_2.ipynb
   ```

   then *Kernel → Restart & Run All* (or open the notebook in VS Code and select the virtual environment).

## Notes

- **Run time:** the first full run takes roughly 15–20 minutes on a 4-core machine, almost all of it t-SNE and UMAP in Section 6. Those embeddings are saved in a `cache/` folder, so later runs take a few minutes. Delete `cache/` to recompute everything.
- **Memory:** the full dataset with the extra columns needs a few GB of RAM (8 GB recommended).
- **Internet:** only the background tiles of the interactive folium maps (Section 4.2) need internet access; all other plots work offline.
- **Reproducibility:** a fixed random seed (42) is used throughout; running the notebook rewrites the files in `figures/` and `maps/`.
- **Rebuilding the report:** `cd report && pdflatex main.tex` (run twice); it reads the plots from `../figures/`.
