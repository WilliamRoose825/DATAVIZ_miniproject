# DATAVIZ Mini-Project — French Baby Names (period 1900–2020)

## Reminder:
In this mini-project, we will be working with a data set of baby names in France. It contains the list of all baby names registered in France, year by year, from 1900 through 2020. There are two data sets: one aggregated to the national level, and another with data by department. Our goal is to create 3 different visualizations around these data, each focussed on answering different kinds of questions about the data:

Visualization 1:
- How do baby names evolve over time?
- Are there names that have consistently remained popular or unpopular?
- Are there some that have were suddenly or briefly popular or unpopular?
- Are there trends in time?

Visualization 2: 
- Is there a regional effect in the data?
- Are some names more popular in some regions?
- Are popular names generally popular across the whole country?

Visualization 3: 
- Are there gender effects in the data?
- Does popularity of names given to both sexes evolve consistently? (Note: this data set treats sex as binary; this is a simplification that carries into this assignment but does not generally hold.)

In this Github project we exhibit the code used during the Week 2. Our notebook Designs.ipynb gathers three interactive designs, each responding to a visualization need. It was built with Altair, a python library used during lab class and rely upon some tools from the 'Names hints' reference folder.


## Setup

### 1. Clone the repository
```bash
git clone https://github.com/WilliamRoose825/DATAVIZ_miniproject.git
cd DATAVIZ_miniproject
```

### 2. Download the data file
The CSV is too large to store in git. Download it from https://perso.telecom-paristech.fr/eagan/class/igr204/data/dpt2020.csv and place it at:
```
Names hints/dpt2020.csv
```

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
  dpt2020.csv                              ← download separately (see above)
  departements-avec-outre-mer.geojson      ← included from the reference folder 'Names hints'
  departements-version-simplifiee.geojson  ← included from the reference folder 'Names hints'
Week_2/
  Screenshots/                             ← folder including interesting cases to investigate (cf forum)
    Screenshot_A
    Screenshot_B
    Screenshot_C
    Screenshot_D
    Screenshot_E
    Screenshot_F
    Screenshot_G
    Screenshot_H
    Screenshot_I
  Designs.ipynb                            ← main notebook (3 visualisations)
pyproject.toml                             ← Python dependencies
```

## Data notes
- Rows with `preusuel == "_PRENOMS_RARES"`, `dpt == "XX"` or `annais == "XXXX"` are dropped.
- `sexe`: 1 = male, 2 = female.
- Corsica is coded `"20"` in the CSV and `"2A"/"2B"` in the GeoJSON — handled in the notebook.
