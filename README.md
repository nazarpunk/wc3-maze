# wc3-maze

[Demo](https://nazarpunk.github.io/wc3-maze)

https://xgm.guru/p/wc3/dungeongenerator

Генерация ячеек:

   Генерация начинается с создания юнитов 1 типа (красные) на месте декораций расположенных на карте.
       1. Создаётся один юнит 2 типа (зелёный) в центральной зоне.
       2. Сначала выбираются 4 красных юнита (сверху, справа, снизу и слева) вокруг зелёного юнита, затем выбирается только один из них. Таким образом выбирается направление генерации.
       3. Выбранный красный юнит удаляется и на его месте создаётся следующий зелёный юнит, от которого продолжится дальнейшая генерация.
       4. Процесс описанный в 3 и 4 пунктах повторяется опр. кол-во раз в зависимости от выбранного размера подземелья.
       5. Если генерация заходит в тупик (вокруг ведущего зелёного юнита нет ни одного красного), то в этой точке создаётся первый портал, затем выбирается случайный красный юнит на месте которого создаётся второй портал и зелёный юнит, от которого продолжается генерация.

Генерация стен:
   После окончания генерации ячеек выбираются по очереди все зелёные юниты.
   Пикаются красные юниты вокруг выбранного зелёного юнита.
   Проверяются углы между красным юнитом и зелёным и в зависимости от угла между юнитами ставится стена.
   Процесс 2 и 3 пункта повторяется для каждого зелёного юнита.

Генерация стен в залах подземелья:
   Выбирается зелёный юнит.
   Выбираются все зелёные юниты вокруг выбранного юнита (он в том числе).
   Если количество юнитов в группе равняется 9 (центрального юнит + 8 юнитов вокруг), то создаётся стена в случайной точке (сверху, справа, снизу, слева от центрального юнита).

Генерация монстров:
   Создаётся группа из всех зелёных юнитов.
   Выбирается 1 случайный юнит из группы и на его месте создаётся монстр.
   Повышает Custom Value зелёного юнита на 1.
   Если Custom Value равен 2 (максимум созданных монстров вокруг одного зелёного юнита), то зелёный юнит удаляется из группы.
   Процесс с 2 по 4 пункт повторяется опр. кол-во раз в зависимости от указанного количества монстров.