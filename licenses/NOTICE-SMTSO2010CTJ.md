# SMTSO2010CTJ / C2916319 — provisional reference

The provisional footprint and simplified nominal STEP model were carried over from GS2. Geometry has not been modified during the library migration. The STEP file is a dimensional reference envelope, not a certified manufacturer model.

GS2's source record identifies the JLCEDA/EasyEDA Official Library as a dimensional reference:

- https://lceda.cn/
- https://easyeda.com/
- https://easyeda.com/api/components/3403fcac404e4e89b580a9d68b37acef
- Manufacturer drawing reference: https://file.huaqiu.com/web2/M00/A8/08/pYYBAGRu-3qALyOPAALOTHXtjNw513.pdf

Copyright and related rights in the official library belong to JLCEDA/EasyEDA. Its official source polygons and official 3D model are not redistributed here. GS2's footprint was independently generated from observed dimensions; its pad inner diameter was increased to provide nominal hole clearance, rather than copying the original reference land unchanged.

The footprint keeps the `PROVISIONAL` suffix and `board_only` attribute. It is not assembler-approved. Assembly-process suitability, paste design, solder-joint strength, tolerances and actual component fit remain unverified. The geometry must be reviewed before use in any project; do not treat library inclusion as a manufacturing qualification.

## Update 2026-11-08

The STEP model was redrawn to the manufacturer's datasheet dimensions
(SINHOO SMTSO2010CTJ, LCSC C2916319): solder flange Ø7.14 × 1.53 plus
boss Ø5.56 × 1.0 (2.53 total below the PCB back face), replacing the
earlier Ø5.56 / Ø3.6-ring envelope. The coordinate convention is
unchanged (boss at z 0..+1.0, flange at z −1.53..0, Ø2.0 hole). It
remains a dimensional reference envelope, not a certified manufacturer
model, and the footprint keeps its `PROVISIONAL` status.
