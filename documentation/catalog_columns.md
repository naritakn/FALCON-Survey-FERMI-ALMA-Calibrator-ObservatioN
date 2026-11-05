# FALCON catalog columns — v1.1 draft

949 rows and 23 columns. The original 21 column names/order are retained; MATCH_STATUS and COUNTERPART_NAME describe the association. Missing numeric values are NaN in FITS and empty in CSV. No luminosity or analysis-selection columns are included.

| Column | Unit | Description |
|---|---|---|
| SOURCE_ID | — | Stable IAU-style identifier from v1.0 for the retained ALMA position. |
| ALMA_NAME | — | Full ALMA source alias string, separated by /. |
| RA | deg | ALMA right ascension, J2000/ICRS. |
| DEC | deg | ALMA declination, J2000/ICRS. |
| REDSHIFT | — | Finite positive adopted redshift; NaN if unavailable. |
| Z_ORIGIN | — | 4LAC-DR3, Roma-BZCAT or unknown. |
| S_B3 | Jy | Band 3 median flux of contributing rows; see selection rules. |
| E_S_B3 | Jy | Median quoted flux uncertainty over valid errors in the same Band 3 contributing rows; not uncertainty on median. |
| S_B6 | Jy | Band 6 median flux of contributing rows; see selection rules. |
| E_S_B6 | Jy | Median quoted flux uncertainty over valid errors in the same Band 6 contributing rows; not uncertainty on median. |
| S_B7 | Jy | Band 7 median flux of contributing rows; see selection rules. |
| E_S_B7 | Jy | Median quoted flux uncertainty over valid errors in the same Band 7 contributing rows; not uncertainty on median. |
| FGL_NAME | — | Unique associated 4LAC-DR3 source name. |
| GAMMA_FLUX | erg / (s cm2) | 4LAC Energy_Flux100, 0.1–100 GeV energy flux. |
| E_GAMMA_FLUX | erg / (s cm2) | 4LAC Unc_Energy_Flux100. |
| PHOTON_INDEX | — | 4LAC PL_Index. |
| E_PHOTON_INDEX | — | 4LAC Unc_PL_Index. |
| ALPHA36 | — | Measured index for Snu proportional to nu^alpha36; NaN when unavailable. Reproduce with ALPHA_S/NU columns. |
| CLASS | — | Original Fermi class normalized in case; includes BCU, RDG, etc., not just three classes. |
| SED_TYPE | — | Original LSP, ISP, HSP or blank when unavailable. |
| SEP_FERMI | deg | ALMA to gamma-ray catalog center separation, not to counterpart position. |
| MATCH_STATUS | — | accepted or accepted_counterpart for the three resolved multiple matches. |
| COUNTERPART_NAME | — | 4LAC ASSOC1 name. |
