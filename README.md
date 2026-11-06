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

## Citation

If you use the FALCON catalog in your research, please cite the following paper and this repository:

Kanako Narita, Yoshiyuki Inoue, Bunyo Hatsukade, and Yasushi Fukazawa (2026). *FALCON (FERMI-ALMA Calibrator ObservatioN): Cross-matching ALMA Calibrators with Fermi-LAT Blazars*. [arXiv:2611.07737 [astro-ph.HE]](https://arxiv.org/abs/2611.07737).

```bibtex
@misc{narita2026falconfermialmacalibratorobservation,
      title={FALCON (FERMI-ALMA Calibrator ObservatioN): Cross-matching ALMA Calibrators with Fermi-LAT Blazars},
      author={Kanako Narita and Yoshiyuki Inoue and Bunyo Hatsukade and Yasushi Fukazawa},
      year={2026},
      eprint={2611.07737},
      archivePrefix={arXiv},
      primaryClass={astro-ph.HE},
      url={https://arxiv.org/abs/2611.07737},
}
```

Machine-readable citation information is provided in `CITATION.cff`.

## License

The catalog is licensed under CC BY 4.0; see `LICENSE.md`.
