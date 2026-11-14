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

- **Interactive Map Demo**: Open `index.html` (via GitHub Pages or a local static server) to browse streets, suburbs, and districts on an interactive map.

## О датасете (RU)

Открытая выгрузка геоданных проекта **[Hotyata](https://hotyata.com)** — верифицированные улицы, районы и пригороды Грузии (`ka`, `ru`, `en` названия, разговорные синонимы и транслитерации из реальных объявлений). Координаты и геометрия основаны исключительно на открытых источниках (**OpenStreetMap** и госреестр **NAPR** `maps.gov.ge`).

## Summary

| Subset | Records | Formats |
|---|---:|---|
| `streets` | 1608 | `data/streets.jsonl`, `data/streets.parquet` |
| `districts` | 36 | `data/districts.jsonl`, `data/districts.geojson`, `data/districts.parquet` |
| `suburbs` | 29 | `data/suburbs.jsonl`, `data/suburbs.geojson`, `data/suburbs.parquet` |

## Attribution & License

- **License**: ODbL-1.0
- **Sources**: OpenStreetMap contributors, NAPR (`maps.gov.ge`), and [Hotyata](https://hotyata.com) multilingual alias extraction.

## Usage (Hugging Face `datasets`)

```python
from datasets import load_dataset

streets = load_dataset("json", data_files="data/streets.jsonl", split="train")
```
