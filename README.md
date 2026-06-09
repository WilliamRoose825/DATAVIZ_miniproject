# DATAVIZ Mini-Project — French Baby Names (INSEE 1900–2020)

Three interactive visualisations built with **Altair 6** exploring the French baby-names dataset.

| Viz | Question answered |
|-----|-------------------|
| 1 — Time trends | How do baby names evolve over time? |
| 2 — Regional map | Is there a geographic/regional effect? |
| 3 — Gender effects | Does popularity by gender evolve consistently? |

## Setup

### 1. Clone the repository
```bash
git clone https://github.com/WilliamRoose825/DATAVIZ_miniproject.git
cd DATAVIZ_miniproject
```

### 2. Download the data file
The CSV is too large to store in git. Download it from INSEE and place it at:
```
Names hints/dpt2020.csv
```
**Direct link:** https://www.insee.fr/fr/statistiques/fichier/2540004/dpt2020_csv.zip  
(unzip and rename to `dpt2020.csv`)

The GeoJSON files for the department maps are already included in `Names hints/`.

### 3. Install dependencies
```bash
pip install altair geopandas shapely pandas jupyter
```
Or with `uv` (recommended, uses `pyproject.toml`):
```bash
uv sync
```

### 4. Run the notebook
```bash
jupyter notebook Week_2/Designs.ipynb
```
Or open in VS Code with the Jupyter extension.

## Project structure
```
Names hints/
  dpt2020.csv                          ← download separately (see above)
  departements-avec-outre-mer.geojson  ← included
  departements-version-simplifiee.geojson
Week_2/
  Designs.ipynb                        ← main notebook (3 visualisations)
pyproject.toml                         ← Python dependencies
```

## Data notes
- Source: [INSEE — Fichier des prénoms](https://www.insee.fr/fr/statistiques/2540004)
- Rows with `preusuel == "_PRENOMS_RARES"`, `dpt == "XX"` or `annais == "XXXX"` are dropped.
- `sexe`: 1 = male, 2 = female.
- Corsica is coded `"20"` in the CSV and `"2A"/"2B"` in the GeoJSON — handled in the notebook.
