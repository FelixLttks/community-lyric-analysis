# Genius audio features

## Branches
- `main`: Cleaned-up and summarized version of `dev`; may slightly differ.
- `dev`: For development and inspecting Git history or details. Not intended for production use.

## File structure

| File | Description |
|------|-------------|
| [README.md](README.md) | This file |
| [projectsheet.md](projectsheet.md) | Project goals |
| `data/` | Folder to persistently store processed data |
| `notebooks/` | |
| &nbsp;&nbsp;&nbsp;&nbsp;[1.data_acquisition.ipynb](notebooks/1.data_acquisition.ipynb) | Load data and merge datasets |
| &nbsp;&nbsp;&nbsp;&nbsp;[2.data_preprocessing.ipynb](notebooks/2.data_preprocessing.ipynb) | Cleanup dataset |
| &nbsp;&nbsp;&nbsp;&nbsp;[3.statistics.ipynb](notebooks/3.statistics.ipynb) | Statistics |
| &nbsp;&nbsp;&nbsp;&nbsp;[4.ml_1_regression.ipynb](notebooks/4.ml_1_regression.ipynb) | ML-task 1: Regression on audio features |
| &nbsp;&nbsp;&nbsp;&nbsp;[5.ml_2_lyrics_generation.ipynb](notebooks/5.ml_2_lyrics_generation.ipynb) | ML-task 2: Generation of lyrics |


## Dataset naming (.parquet)
| Processing step | Exported after step |
|-----------------|---------------------|
| Merging         | tracks_merged       |
| Normalize       | tracks_norm         |
| Cleanup         | tracks              |

## Additional Files
All model files, embeddings, and supplementary data are available for download at [this link](REMOVED).