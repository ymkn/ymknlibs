# SMTSO2010CTJ / C2916319 — provisional reference

The provisional footprint and simplified nominal STEP model were carried over from GS2. Geometry has not been modified during the library migration. The STEP file is a dimensional reference envelope, not a certified manufacturer model.

GS2's source record identifies the JLCEDA/EasyEDA Official Library as a dimensional reference:

- https://lceda.cn/
- https://easyeda.com/
- https://easyeda.com/api/components/3403fcac404e4e89b580a9d68b37acef
- Manufacturer drawing reference: https://file.huaqiu.com/web2/M00/A8/08/pYYBAGRu-3qALyOPAALOTHXtjNw513.pdf

Copyright and related rights in the official library belong to JLCEDA/EasyEDA. Its official source polygons and official 3D model are not redistributed here. GS2's footprint was independently generated from observed dimensions; its pad inner diameter was increased to provide nominal hole clearance, rather than copying the original reference land unchanged.

The footprint keeps the `PROVISIONAL` suffix and `board_only` attribute. It is not assembler-approved. Assembly-process suitability, paste design, solder-joint strength, tolerances and actual component fit remain unverified. The geometry must be reviewed before use in any project; do not treat library inclusion as a manufacturing qualification.

## Verification note 2026-11-08

The model was checked against the manufacturer drawing (SINHOO
SMTSO2010CTJ, Rev.A, 2017-05-26, "M2*5.56*L1.0+1.53", based on
PEMSMTSO): barrel Ø5.56 × 1.0 plus a Ø3.60 × 1.53 pilot that enters
the PCB hole. The original envelope above matches the drawing; only
the barrel protrudes below the PCB back face. (A revision replacing
the pilot with a Ø7.14 flange — a dimension from the SMTSO3640CTJ
drawing, a different part — was pushed and reverted the same day.)
