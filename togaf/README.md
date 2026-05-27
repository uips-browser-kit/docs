# togaf

TOGAF-aligned architecture inventories for uips-browser-kit.

## Layers

| Folder | TOGAF domain | Contents |
|---|---|---|
| `biz/` | Business Architecture | Roles, processes, capabilities |
| `app/` | Application Architecture | Application components and services |
| `dat/` | Data Architecture | Data entities and flows |
| `tec/` | Technology Architecture | Physical technology components |

## File format

Each layer uses CSV inventories.  Column schemas follow the naming convention
established in the source data (e.g. `TA_PTC_` prefix for Technology Architecture
Physical Technology Components).
