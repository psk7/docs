---
editable: false
---

# LN

_Математические функции_

#### Синтаксис


```
LN( number )
```

#### Описание
Возвращает натуральный логарифм числа `number`. Возвращает `NULL`, если число меньше или равно 0.

**Типы аргументов:**
- `number` — `Число`


**Возвращаемый тип**: `Дробное число`

#### Примеры

```
LN(1) = 0.0
```

```
LN(EXP(2)) = 2.0
```


#### Поддержка источников данных

`Материализованный датасет`, `ClickHouse 1.1`, `Microsoft SQL Server 2017 (14.0)`, `MySQL 5.6`, `PostgreSQL 9.3`.
