# Matched-source sample selection

1. Read the ALMA snapshot and keep valid positions and observations dated on/after 2013-01-01 UTC.

2. Find each ALMA position's nearest source in the combined high/low-latitude 4LAC-DR3 catalogs. Accept gamma-center separation strictly less than 0.1 degree.

3. For multiple ALMA positions sharing a Fermi source, require one unique candidate within 1 arcsec of the published 4LAC counterpart position. This identifies J0650-1637, J1300+14 and J1407-2709; reject J0650-1632, J1300+1417 and J1407-2701. These rejected candidates do not become non-matched sources. Localization ellipses are not an additional selection criterion.

4. Prefer finite positive 4LAC redshift; otherwise use finite positive BZCAT redshift matched within 3 arcsec. No valid value means NaN and `Z_ORIGIN=unknown`. This numerical validity check does not independently establish spectroscopic reliability.

5. Exclude nonfinite/nonpositive flux or frequency from flux aggregation, but preserve membership of the source. No upper limit is inferred from a zero flux entry.

6. Band 3: choose maximum valid frequency and median flux within NumPy `isclose` of that frequency (atol=1e6 Hz, rtol=1e-5). Bands 6 and 7: median all valid flux values and median all valid frequencies. Quoted flux errors are median nonnegative finite catalog errors for the SAME contributing rows, not errors on the medians and not including an extra planetary model uncertainty.

7. For ALPHA36, first take the median flux at each exact frequency, then use the highest valid frequency in each of Bands 3 and 6: ALPHA36=log(S6/S3)/log(nu6/nu3). These fluxes can differ from the broadband aggregate S_B3/S_B6. If either required band is unavailable, ALPHA36 is NaN; no fallback index is included in this distribution.

The result contains 949 ALMA sources and 949 distinct Fermi counterparts. No redshift or luminosity cut is applied to catalog membership. This distribution provides matching results and basic source properties only.
