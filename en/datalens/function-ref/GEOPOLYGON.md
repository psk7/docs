---
editable: false
---

# GEOPOLYGON

_Type conversion functions_

#### Syntax


```
GEOPOLYGON( value )
```

#### Description
Converts the `value` expression to geopolygon format.

**Argument types:**
- `value` — `Geopolygon | String`


**Return type**: `Geopolygon`

#### Examples

```
GEOPOLYGON("[[[55.79421,37.65046],[55.79594,37.6513],[55.79642,37.65133],[55.7969, 37.65114],[55.79783, 37.65098],[55.78871,37.75101]]]")
```

```
GEOPOLYGON("[[[55.75,37.52],[55.75,37.68],[55.65,37.60]],[[55.79,37.60],[55.76,37.57],[55.76,37.63]]]")
```


#### Data source support

`Materialized Dataset`, `ClickHouse 1.1`, `Microsoft SQL Server 2017 (14.0)`, `MySQL 5.6`, `PostgreSQL 9.3`.
