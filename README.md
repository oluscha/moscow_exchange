# moscow_exchange
analysis of MOEX rate
1.	Автоматически (запросом Python)  получить данные по Индексу Московской Биржи за ретроспективный 5-летний период, считая текущую дату начальной точкой отсчета
https://www.moex.com/ru/index/IMOEX/archive/?from=2022-05-01&till=2022-05-16&sort=TRADEDATE&order=desc;

2.	Архивный файл формата zip сохранить на диск, распаковать и прочитать распакованное содержимое (csv-файл);

3.	Данные п.2 сохранить в базу данных формата SQLite3;

Дальнейшие операции необходимо осуществлять с данными, хранящимися в БД.
4.	Выполнить аналитику - 1

4.1	Определить месяц и год (таковых может быть несколько), при котором средние показатели отклонений цен закрытия (CLOSE) от их средних значений превышают 100 единиц;
4.2	Данные округлить до 2 знаков после запятой;
4.3	Сгенерировать картинку в matplotlib с полученными данными, по оси асбцисс – дата, по оси ординат – показатель п.4.2;

5.	Выполнить аналитику – 2 (Определить даты точек старта трендов(резких движений) цены закрытия бумаги за 5 летний период).
5.1	Абсолютное изменение цены между текущим и предшествующим торговыми днями должно быть не менее 20% от разницы между максимальным и минимальным значением в календарном торговом месяце.
5.2	Определить даты и направления изменения тренда.
5.3	Финальную таблицу представить в виде: 
o	Имя периода (в формате `месяц.год`)
o	Цена закрытия
o	Максимальная цена в периоде
o	Минимальная цена в периоде
o	Тип локального минимума (local_min, local_max)
