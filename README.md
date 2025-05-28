## Репозиторій створений для демонстрації технік створення візуалізацій у Power BI.

## 1. Інтерактивна карта густоти населення регіонів України
1. Імпорт даних у Power BI та карти України у форматі JSON.
2.  Здійснено налаштування дизайну карти.
3.  Для кожного регіону створено окрему measure з використанням мови DAX та картку. Формула визначає для цього регіону відповідне значення з даних.
Формула DAX:

$$ 
Київ lbl = 
VAR CurrentRegion = "Київ"
VAR CurrentValue = FORMAT(CALCULATE(SUM(region_tbl[Value]), region_tbl[Region] = CurrentRegion), "#,##0")
VAR RegionExists = COUNTROWS(FILTER(region_tbl, region_tbl[Region] = CurrentRegion)) > 0
RETURN
    IF(RegionExists, IF(ISBLANK(CurrentValue) || CurrentValue = "0", CurrentRegion & ": 0", CurrentRegion & ": " & CurrentValue), CurrentRegion & ": No Data") 
$$

![image](https://github.com/user-attachments/assets/325b31cf-741c-464a-bd17-91b825bddc93)
