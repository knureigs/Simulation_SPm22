## Комп'ютерні системи імітаційного моделювання
## СПм-22-3, **Іванов Іван Іванович**
### Лабораторна робота №**1**. Опис імітаційних моделей та проведення обчислювальних експериментів

<br>

### Варіант -1, модель у середовищі NetLogo:
[Traffic Basic](http://www.netlogoweb.org/launch#http://www.netlogoweb.org/assets/modelslib/Sample%20Models/Social%20Science/Traffic%20Basic.nlogo)

<br>

### Вербальний опис моделі:
Симуляція руху автомобілів по шосе. Кожен автомобіль дотримується простого набору правил: він уповільнюється (гальмує), якщо бачить автомобіль, до якого наближається, і прискорюється (збільшує швідкість руху), якщо попереду не бачить перешкоди (автомобіля). Модель показує, як можуть утворюватися пробки навіть без ДТП та перехресть.

### Керуючі параметри:
- **number-of-cars** визначає кількість агентів у середовищі моделювання, тобто, в даній моделі, кількість машин на замкнутому шосе.
- **deceleration** визначає зменшення швидкості агента на кожному ігровому такті у разі присутності перешкоди перед ним.
- **acceleration** визначає збільшення швидкості агента на кожному ігровому такті за відсутності перешкод перед агентом.

### Внутрішні параметри:
- **speed**. Швидкість агента (переміщення машини трасою). Може відрізнятись у кожної машини в різні моменти модельного часу.
- **speed-limit**. Верхнє обмеження швидкості. Це загальний параметр для всіх агентів.
- **speed-min**. Мінімальне значення швидкості агентів. Це загальний параметр для всіх агентів.

### Показники роботи системи:
- максимальна швидкість на поточному такті симуляції, тобто, швидкість найшвидшої на даний момент машини на трасі. Не може бути більше значення speed-limit.
- найменша швидкість на поточному такті, тобто, швидкість найповільнішої в даний момент машини.
- поточна швидкість машини, що відстежується (червона машина).

### Примітки:
При налаштуваннях за замовчуванням автомобілі уповільнюються набагато швидше, ніж прискорюються.

### Недоліки моделі:
Відстеження агентом простору тільки безпосередньо перед собою, хоча доцільно враховувати наявність перешкод на більшій відстані та скидати швидкість поступово по мірі наближення, використовуючи вказане користувачем значення deceleration.

<br>

## Обчислювальні експерименти

### 1. Вплив завантаженості дороги на середню швидкість переміщення нею.
Досліджується залежність середньої швидкості червоної (обраної) машини протягом заданого числа тактів (100) від числа машин на трасі, зазначеного на початку симуляції. 
Експерименти проводяться при 5-40 машинах, з кроком 5, усього 8 симуляцій. 
Інші параметри мають значення за замовчуванням:
- **deceleration**: 0.026
- **acceleration**: 0.0045

<table>
<thead>
<tr><th>Кількість автомобілів</th><th>Середня швидкість</th></tr>
</thead>
<tbody>
<tr><td>5</td><td>0,47</td></tr>
<tr><td>10</td><td>0,38</td></tr>
<tr><td>15</td><td>0,46</td></tr>
<tr><td>20</td><td>0,44</td></tr>
<tr><td>25</td><td>0,30</td></tr>
<tr><td>30</td><td>0,14</td></tr>
<tr><td>35</td><td>0,16</td></tr>
<tr><td>40</td><td>0,14</td></tr>
</tbody>
</table>

Графік наочно показує, що досягнення та утримання максимальної швидкості на більшій частині дороги можливе лише за її низької завантаженості, до 15 машин.
