# FALCON Survey — matched-source catalog

**FERMI–ALMA Calibrator ObservatioN (FALCON), v1.1 draft**

This repository distributes the revised cross-match of the ALMA Calibrator Source Catalogue and Fermi-LAT 4LAC-DR3: **949 ALMA sources with 949 distinct Fermi counterparts**.

## Catalog files

- `catalog/FALCON_catalog.fits`: astronomy table with 949 rows and 23 columns; table extension `FALCON`.
- `catalog/FALCON_catalog.csv`: the same sources and columns in CSV format.

The table includes source identifiers, coordinates, counterpart names, matching status, redshift, flux densities, spectral properties, classifications and angular separations. Missing numeric values are NaN in FITS and empty in CSV. Sources without redshifts remain included.

See [column definitions](documentation/catalog_columns.md) and [sample selection](documentation/sample_selection.md) before interpreting the data.

This distribution contains no luminosity columns, luminosity-sample flags, analysis scripts, notebooks or raw input datasets.

## Read the FITS file

```python
from astropy.table import Table
catalog = Table.read("catalog/FALCON_catalog.fits", hdu="FALCON")
print(len(catalog))  # 949
```

## Citation and license

Please cite Narita et al., *FALCON Survey (FERMI–ALMA Calibrator ObservatioN): Cross-matching ALMA Calibrators with Fermi-LAT Blazars* (under review), and this repository. Author information is provided in `CITATION.cff`. The catalog is licensed under CC BY 4.0; see `LICENSE.md`.
