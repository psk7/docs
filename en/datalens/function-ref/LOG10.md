---
editable: false
---

# LOG10

_Mathematical functions_

#### Syntax


```
LOG10( number )
```

#### Description
Returns the logarithm of the number `number` to base 10. Returns 'NULL' if the number is less than or equal to 0.

**Argument types:**
- `number` — `Number`


**Return type**: `Number (decimal)`

#### Examples

```
LOG10(1) = 0.0
```

```
LOG10(1000) = 3.0
```

```
LOG10(100) = 2.0
```


#### Data source support

`Materialized Dataset`, `ClickHouse 1.1`, `Microsoft SQL Server 2017 (14.0)`, `MySQL 5.6`, `PostgreSQL 9.3`.
