# Проект: «Анализ данных об оптовых продажах аудиотехники»
### При работе с проектом нужно собрать данные из различных источников, проанализировать их и сделать выводы, которые помогут руководству компании принимать обоснованные тактические решения.
### Стек: Python, Pandas, Matplotlib
### Выполненные задачи:
+ Сбор данных со всех папок в три датафрейма 
+ Посчитаны количество заказов в каждый день. Определен день с наибольшим числом заказов (2024-03-14, 34 заказа)
+ Построен график с количеством заказов по дням
  ![image](https://github.com/user-attachments/assets/f1b92c0c-2ea0-40ae-89f2-0ef4f907b8bb)
+ Определен  день, когда не было ни одного подтвержденного заказа (9 марта)
+ Построен график с заказами по дням в разбивке по статусу заказа.
  ![image](https://github.com/user-attachments/assets/78188ad3-6b4a-4d50-bfd6-02e73d3b30f1)
+ Из usd_rate.txt создан датафрейм с 2 колонками: date и currency_rate. Расчитано среднее значение курса доллара за месяц (91.7)
+ С учетом курса доллара для каждого дня рассчитаны следующие метрики:
  - Общая выручка в рублях (2038231821.56)
  - Средний чек в месяце в рублях (6596219.49)
+  Построен график выручки, среднего чека и числа заказов на каждый день.
![image](https://github.com/user-attachments/assets/63cefb9a-1118-44f9-bb39-82bed5da38d3)
+ Рассчитано общее число брендов, которыми интересовались клиенты (121). Опредены бренды , принесшие наибольшую выручку.
  | brand | revenue | orders |
  |-------------:|------------:|----------------------|
  |     JBL | 2.665961e+08	 | 264 |
  |     Heco | 2.388163e+08		 | 229 |
  | Yamaha |	1.658651e+08	| 218 |
  | Klipsch |	2.039024e+08	| 205 |
  | Magnat	| 1.141989e+08	| 154 |
  |   ...	| ...	| ... |
+ Определено, у каких брендов доля ни разу не заказанных товаров была больше половины от всех продаваемых товаров этого бренда.
  | brand	| no	| yes	| total_products	| not_ordered_ratio |
  |------:|-------:|------:|------:|--------------|
	| Dali	| 49.0	| 18.0	| 67.0	| 0.731343 |
	| KEF	| 54.0 | 	28.0 | 	82.0	| 0.658537 |
	| Marantz	| 19.0	| 3.0	| 22.0	| 0.863636 |
	|Pioneer	| 70.0 | 33.0	| 103.0 |	0.679612 |
+ Составлен отчет по продажам менеджеров.

### Выводы:
+ Заказов в рабочие дни значительно больше, чем в выходные и праздники
+ 9 марта произошел сбой в работе CRM системы, который не позволил клиентам подтвердить заказ. В результате все созданные в первый день заказы автоматически отменились, поэтому клиентам пришлось оформлять их повторно на следующий день. Почти половина заказов повторяет вчерашние.
+ Число заказов и выручка не каждый день изменяются в одинаковом направлении, так же как средний чек и выручка. В день с наибольшим числом заказов выручка и/или средний чек не показывают максимальное значение
+ Согласно отчету по продажам, лучшим менеджером по % выручки стала Маргарита Камертонова, наихудшие показатели у Сергея Контрабасова.
