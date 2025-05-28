## Репозиторій створений для демонстрації технік створення візуалізацій у Power BI.
## ОСНОВНІ ЕТАПИ РОБОТИ З POWER BI
1. Збір і валідація вимог
2. Завантаження даних
3. Підготовка даних до моделювання
4. Розробка звіту та обрахунки
5. Дизайн звіту

## . Звіт по роботі персоналу за місяць
1. Завантаження даних та обробка в Power Query, перевірка якості даних.
2. Створення інтерактивного звіту з метою моніторингу кількості відпрацьованих годин по цехам магазину, співробітникам в розрізі відпрацьованого місяця.

![image](https://github.com/user-attachments/assets/b97198bc-790e-4ad8-8bac-84d57762c13b)



## . Sales_Dashboard
1. Завантажено дані, здійснено перевірку якості даних та обробку в Power Query (змінено тим даних, видалено лишню інформацію для оптимізації звіту, замінено значення, форматування тексту)
2. Створено таблицю календар та створено зв'язок між таблицями
3. Пораховано Profit Ratio за допомогою формули DAX.
4. Додано фільтрацію за категоріями, сегментами та регіонами.

![Sales Dashboard](https://github.com/user-attachments/assets/a04f18e7-70d9-4b50-95ad-43ed4928f400)





## . Інтерактивна карта густоти населення регіонів України
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


