---
editable: false
---

# COUNT_IF

_Агрегатные функции_

#### Синтаксис


```
COUNT_IF( condition )
```

#### Описание
Возвращает количество элементов в группе, которые удовлетворяют условию `condition`.

**Типы аргументов:**
- `condition` — `Логический`


**Возвращаемый тип**: `Целое число`

#### Примеры

```
COUNT_IF([Profit] > 5)
```


#### Поддержка источников данных

`Материализованный датасет`, `ClickHouse 1.1`, `Microsoft SQL Server 2017 (14.0)`, `MySQL 5.6`, `PostgreSQL 9.3`.
