# Morocco Administrative Divisions / المغرب



## Overview

| Item | Details |
|------|---------|
| Region | 10 |
| Province | 69 |
| Locality | 1,735 |
| Coordinates | ✅ Included (all levels) |
| Postal Codes | ✅ Included (locality level) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-05-29 |
| Website | [openadmindata.org/ma](https://openadmindata.org/ma/) |
| API | [openadmindata.org/api/ma](https://openadmindata.org/api/ma/) |

## Browse by Region

| # | Region | Provinces | Localitys | Link |
|---|----|----|----|------|
| 1 | بني ملال - خنيفرة (Beni Mellal Khenifra) | 5 | 161 | [Browse](divisions/beni-mellal-khenifra-ma001/) |
| 2 | الدار البيضاء - سطات (Casablanca Settat) | 9 | 180 | [Browse](divisions/casablanca-settat-ma002/) |
| 3 | درعة - تافيلالت (Draa Tafilalet) | 5 | 167 | [Browse](divisions/draa-tafilalet-ma003/) |
| 4 | فاس - مكناس (Fez Meknes) | 9 | 255 | [Browse](divisions/fez-meknes-ma004/) |
| 5 | كلميم - واد نون (Guelmim Oued Noun) | 4 | 59 | [Browse](divisions/guelmim-oued-noun-ma005/) |
| 6 | مراكش - آسفي (Marrakech Safi) | 8 | 271 | [Browse](divisions/marrakech-safi-ma006/) |
| 7 | الجهة الشرقية (Oriental) | 8 | 142 | [Browse](divisions/oriental-ma007/) |
| 8 | الرباط - سلا -القنيطرة (Rabat Sale Kenitra) | 7 | 115 | [Browse](divisions/rabat-sale-kenitra-ma008/) |
| 9 | سوس - ماسة (Souss Massa) | 6 | 216 | [Browse](divisions/souss-massa-ma009/) |
| 10 | طنجة - تطوان - الحسيمة (Tangier Tetouan Al Hoceima) | 8 | 169 | [Browse](divisions/tangier-tetouan-al-hoceima-ma010/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-region.json](data/all-region.json) | JSON | All 10 region records |
| [all-province.json](data/all-province.json) | JSON | All 69 province records |
| [all-localite.json](data/all-localite.json) | JSON | All 1,735 locality records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-2 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-region.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['province']} provinces")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-region.json", "utf-8"));
console.log(`Total: ${data.length} regions`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=region, 2=province, 3=locality |
| `level_name` | object | Level label (local + English) |
| `name.local` | string | Name in local script |
| `name.en` | string | English name |
| `name.slug` | string | URL-safe slug |
| `parent` | object/null | Parent division reference |
| `ancestors` | array | Full ancestor chain |
| `children_count` | object | Count of children per level |
| `zip_codes` | array | Postal codes (where available) |
| `geo.lat` | string | Latitude (WGS84) |
| `geo.lon` | string | Longitude (WGS84) |

Full schema: [data/schema.json](data/schema.json)

## Hierarchy Browse

```
divisions/{region-slug}/
divisions/{region-slug}/{province-slug}/
```

Localitys are listed inline in each province's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-region links
- [Per-region data](docs/llms-full/) — Full data by region

## Citation

```
Morocco Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/morocco-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
