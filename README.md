# Web Data Integration: Video Games Project

## 🚀 Project Summary
This project focuses on the end-to-end integration of heterogeneous video game datasets. By leveraging data integration techniques—specifically using the **PyDI** library—this repository demonstrates a complete pipeline for unifying data from multiple sources. The goal is to produce a single, high-quality "Golden" dataset through a rigorous process of schema matching, blocking, entity resolution (matching), and data fusion.

Whether using machine learning pipelines or rule-based approaches, this project evaluates different strategies to resolve conflicts and identify duplicate records across disparate data sources like Metacritic, Playtime, and Video Game Sales.

---

## 📂 Datasets

The project utilizes three primary source datasets and several derived datasets for training and evaluation.

### Source Data (`/parquet`)
These are the raw input datasets converted to Parquet format for efficient processing:
*   **`df_metacritic.parquet`**: Metadata and review scores from Metacritic.
*   **`df_playtime.parquet`**: User playtime data and game attributes.
*   **`df_videogamesales.parquet`**: Sales figures and global ranking data.

### Machine Learning & Evaluation Data (`/ml-datasets`)
Datasets used for training the matching models and evaluating performance:
*   **`golden_dataset.csv`** & **`Golden_Fusion_Dataset.csv`**: The ground truth datasets used to verify the accuracy of the integration process.
*   **`train_PM.parquet` / `test_PM.parquet`**: Training and testing sets for the **Playtime-Metacritic** matching pairs.
*   **`train_PS.parquet` / `test_PS.parquet`**: Training and testing sets for the **Playtime-Sales** matching pairs.


## 🗺 Roadmap

The project follows a structured pipeline approach. Below is the current status and future goals of the integration process:

- [x] **Data Preprocessing**: Conversion of raw CSV/JSON data into optimized Parquet format.
- [x] **Schema Matching**: Aligning attributes across Metacritic, Playtime, and Sales datasets.
- [x] **Blocking**:
    - [x] Implementation of Embedding-based Blockers (`ML-EmbeddingBlocker-Pipeline.ipynb`).
    - [x] Implementation of Rule-based Blockers (`RB-EmbeddingBlocker-Pipeline.ipynb`).
- [x] **Matching**:
    - [x] Training ML models on labeled pairs (`train_PM`, `train_PS`).
    - [x] Evaluation of matchers against the Golden Dataset (`Blockers&Matchers_Evaluation.ipynb`).
- [ ] **Fusion**:
    - [ ] Conflict resolution strategies (Voting, Trusted Source).
    - [ ] Final generation of the unified Golden Record.
- [ ] **Visualization**: Dashboard for exploring the integrated video game data.

---

## 📊 Project Structure

| File / Directory | Description |
| :--- | :--- |
| `Blockers&Matchers_Evaluation.ipynb` | Main notebook for evaluating the performance of different blocking and matching strategies. |
| `ML-EmbeddingBlocker-Pipeline.ipynb` | Pipeline using Machine Learning embeddings to block potential matches. |
| `RB-EmbeddingBlocker-Pipeline.ipynb` | Pipeline using Rule-Based methods for blocking. |
| `ml-datasets/` | Contains Ground Truth (Golden) datasets and Train/Test splits. |
| `parquet/` | Contains the source datasets optimized for reading. |
| `preprocessing/` | Scripts or notebooks used for initial data cleaning. |
| `output/` | Directory where final integrated results are stored. |
