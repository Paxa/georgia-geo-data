---
license: odbl
language:
  - ka
  - ru
  - en
task_categories:
  - feature-extraction
  - token-classification
tags:
  - georgia
  - streets
  - districts
  - geocoding
  - openstreetmap
  - napr
pretty_name: Georgia Verified Streets, Districts & Suburbs
configs:
  - config_name: streets
    data_files: "data/streets.parquet"
  - config_name: districts
    data_files: "data/districts.parquet"
  - config_name: suburbs
    data_files: "data/suburbs.parquet"
---

# Georgia Verified Streets, Districts & Suburbs

Curated multilingual (`ka`, `ru`, `en`) dataset of verified streets, urban districts, and suburbs across Georgian cities (`batumi`, `tbilisi`, `kutaisi`, `kobuleti`, `bakuriani`, `gudauri`).

## Origin & Methodology

This dataset is an open extraction from **[Hotyata](https://hotyata.com)** (`georgia-geo-data` on [GitHub](https://github.com/Paxa/georgia-geo-data)). It combines open geographic registries (**OpenStreetMap** & Georgia's **NAPR** `maps.gov.ge`) with real-world multilingual street names, colloquialisms, and transliteration variants extracted from human-generated real estate listings.

- **Interactive Map Demo**: Open [the live map viewer](https://paxa.github.io/georgia-geo-data/) (`index.html`) to browse streets, suburbs, and districts.
- **Hugging Face Dataset**: [`epasha/georgia-geo-data`](https://huggingface.co/datasets/epasha/georgia-geo-data) (with Dataset Viewer & Parquet configs).

## О датасете (RU)

Открытая выгрузка геоданных проекта **[Hotyata](https://hotyata.com)** — верифицированные улицы, районы и пригороды Грузии (`ka`, `ru`, `en` названия, разговорные синонимы и транслитерации из реальных объявлений). Координаты и геометрия основаны исключительно на открытых источниках (**OpenStreetMap** и госреестр **NAPR** `maps.gov.ge`).

## Completeness & Coverage

- **Total geo objects**: **1971** (`1906` streets, `36` districts, `29` suburbs)
- **Verified & published**: **1906 / 1906 (100.0%)** of observed catalog streets (remaining 0 unconfirmed ad mentions/outliers are excluded)
- **Streets with coordinates**: **1553 / 1906**
- **Streets with district**: **1464 / 1906**
- **Streets with NAPR (`maps.gov.ge`)**: **1423 / 1906**
- **Streets with OpenStreetMap**: **342 / 1906**
- **Suburbs with coordinates (OSM)**: **29 / 29**

### Streets by City

| City | Verified (Published) | With Coords | With District | With NAPR | With OSM |
|---|---:|---:|---:|---:|---:|
| `tbilisi` | 1316 / 1316 (100.0%) | 1160 | 1046 | 1120 | 222 |
| `batumi` | 569 / 569 (100.0%) | 375 | 397 | 297 | 119 |
| `bakuriani` | 15 / 15 (100.0%) | 13 | 15 | 4 | 0 |
| `gudauri` | 6 / 6 (100.0%) | 5 | 6 | 2 | 1 |

## Summary

| Subset | Records | Formats |
|---|---:|---|
| `streets` | 1906 | `data/streets.parquet`, `data/streets.jsonl` |
| `districts` | 36 | `data/districts.parquet`, `data/districts.jsonl`, `data/districts.geojson` |
| `suburbs` | 29 | `data/suburbs.parquet`, `data/suburbs.jsonl`, `data/suburbs.geojson` |

## Attribution & License

- **License**: ODbL-1.0
- **Sources**: OpenStreetMap contributors, NAPR (`maps.gov.ge`), and [Hotyata](https://hotyata.com) multilingual alias extraction.

## Usage (Hugging Face `datasets`)

```python
from datasets import load_dataset

streets = load_dataset("epasha/georgia-geo-data", "streets", split="train")
```
