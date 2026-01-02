Рещенные задачи с SQL-тренажера https://sql-academy.org/ru/trainer

#### [Задание 1](https://sql-academy.org/ru/trainer/tasks/1)
Вывести имена всех людей, которые есть в базе данных авиакомпаний
```sql
SELECT name FROM Passenger;
```
#### [Задание 2](https://sql-academy.org/ru/trainer/tasks/2)
Вывести названия всеx авиакомпаний
```sql
SELECT name FROM Company;
```
#### [Задание 3](https://sql-academy.org/ru/trainer/tasks/3)
Вывести все рейсы, совершенные из Москвы
```sql
SELECT * FROM Trip
WHERE town_from = 'Moscow';
```
#### [Задание 4](https://sql-academy.org/ru/trainer/tasks/4)
Вывести имена людей, которые заканчиваются на "man"
```sql
SELECT name FROM Passenger
WHERE name LIKE '%man';
```
#### [Задание 5](https://sql-academy.org/ru/trainer/tasks/5)
Вывести количество рейсов, совершенных на TU-134
```sql
SELECT COUNT(*) AS 'count' 
FROM Trip
WHERE plane = 'TU-134';
```
#### [Задание 6](https://sql-academy.org/ru/trainer/tasks/6)
Какие компании совершали перелеты на Boeing
```sql
SELECT DISTINCT name 
FROM Company
JOIN Trip ON Company.id = Trip.company
WHERE Trip.plane = "Boeing";
```
#### [Задание 7](https://sql-academy.org/ru/trainer/tasks/7)
Вывести все названия самолётов, на которых можно улететь в Москву (Moscow)
```sql
SELECT DISTINCT plane 
FROM Trip
WHERE town_to = 'Moscow'; 
```
#### [Задание 8](https://sql-academy.org/ru/trainer/tasks/8)
В какие города можно улететь из Парижа (Paris) и сколько времени это займёт?
```sql
SELECT town_to, TIMEDIFF(time_in, time_out) AS flight_time 
FROM Trip 
WHERE town_from = 'Paris';
```
#### [Задание 9](https://sql-academy.org/ru/trainer/tasks/9)
Какие компании организуют перелеты из Владивостока (Vladivostok)?
```sql
SELECT name FROM Company 
JOIN Trip ON Company.id = Trip.company
WHERE town_from = 'Vladivostok';
```
#### [Задание 10](https://sql-academy.org/ru/trainer/tasks/10)
Вывести вылеты, совершенные с 10 ч. по 14 ч. 1 января 1900 г.
```sql
SELECT * FROM Trip
WHERE time_out >= "1900-01-01 10-00-00" AND time_out <= "1900-01-01 14-00-00";
```
#### [Задание 11](https://sql-academy.org/ru/trainer/tasks/11)
Выведите пассажиров с самым длинным ФИО. Пробелы, дефисы и точки считаются частью имени.
```sql
SELECT name FROM Passenger
WHERE LENGTH(name) = (SELECT MAX(LENGTH(name)) FROM Passenger);
```
#### [Задание 12](https://sql-academy.org/ru/trainer/tasks/12)
Выведите идентификаторы всех рейсов и количество пассажиров на них. Обратите внимание, что на каких-то рейсах пассажиров может не быть. В этом случае выведите число "0".
```sql
SELECT Trip.id, COUNT(Pass_in_trip.passenger) AS count 
FROM Trip 
LEFT JOIN Pass_in_trip ON Pass_in_trip.trip = Trip.id
GROUP BY Trip.id;
```
#### [Задание 13](https://sql-academy.org/ru/trainer/tasks/13)
Вывести имена людей, у которых есть полный тёзка среди пассажиров
```sql
SELECT name FROM Passenger
GROUP BY name
HAVING COUNT(*) > 1;
```
#### [Задание 14](https://sql-academy.org/ru/trainer/tasks/14)
В какие города летал Bruce Willis
```sql
SELECT town_to 
FROM Trip 
JOIN Pass_in_trip ON Trip.id = Pass_in_trip.trip
JOIN Passenger ON Pass_in_trip.passenger = Passenger.id
WHERE Passenger.name = "Bruce Willis";
```
#### [Задание 15](https://sql-academy.org/ru/trainer/tasks/15)
Выведите идентификатор пассажира Стив Мартин (Steve Martin) и дату и время его прилёта в Лондон (London)
```sql
SELECT Passenger.id, Trip.time_in 
FROM Passenger
JOIN Pass_in_trip ON Passenger.id = Pass_in_trip.passenger
JOIN Trip ON Pass_in_trip.trip = Trip.id
WHERE Passenger.name = "Steve Martin" AND Trip.town_to = "London";
```
#### [Задание 16](https://sql-academy.org/ru/trainer/tasks/16)
Вывести отсортированный по количеству перелетов (по убыванию) и имени (по возрастанию) список пассажиров, совершивших хотя бы 1 полет.
```sql
SELECT name, COUNT(trip) AS count 
FROM Passenger
JOIN Pass_in_trip ON Passenger.id = Pass_in_trip.passenger
GROUP BY Passenger.name
ORDER BY count DESC, name;
```
#### [Задание 17](https://sql-academy.org/ru/trainer/tasks/17)
Определить, сколько потратил в 2005 году каждый из членов семьи. В результирующей выборке не выводите тех членов семьи, которые ничего не потратили.
```sql
SELECT member_name, status, SUM(amount*unit_price) AS costs 
FROM FamilyMembers
JOIN Payments ON member_id = family_member
WHERE date LIKE '2005%'
GROUP BY family_member;
```
#### [Задание 18](https://sql-academy.org/ru/trainer/tasks/18)
Выведите имя самого старшего человека. Если таких несколько, то выведите их всех.
```sql
SELECT member_name 
FROM FamilyMembers
WHERE birthday = (SELECT MIN(birthday) FROM FamilyMembers);
```
#### [Задание 19](https://sql-academy.org/ru/trainer/tasks/19)
Определить, кто из членов семьи покупал картошку (potato)
```sql
SELECT DISTINCT status
FROM FamilyMembers
JOIN Payments ON FamilyMembers.member_id = Payments.family_member
JOIN Goods ON Payments.good = Goods.good_id
WHERE good_name = 'potato';
```
#### [Задание 20](https://sql-academy.org/ru/trainer/tasks/20)
Сколько и кто из семьи потратил на развлечения (entertainment). Вывести статус в семье, имя, сумму
```sql
SELECT status, member_name, SUM(unit_price * amount) AS costs 
FROM FamilyMembers
JOIN Payments ON Payments.family_member = FamilyMembers.member_id
JOIN Goods ON Payments.good = Goods.good_id
JOIN GoodTypes ON Goods.type = GoodTypes.good_type_id
WHERE GoodTypes.good_type_name = 'entertainment'
GROUP BY family_member;
```
#### [Задание 21](https://sql-academy.org/ru/trainer/tasks/21)
Определить товары, которые покупали более 1 раза
```sql
SELECT DISTINCT good_name 
FROM Goods
JOIN Payments ON good_id = good
GROUP BY good
HAVING COUNT(amount) > 1;
```
#### [Задание 22](https://sql-academy.org/ru/trainer/tasks/22)
Найти имена всех матерей (mother)
```sql
SELECT member_name 
FROM FamilyMembers
WHERE status = 'mother';
```
#### [Задание 23](https://sql-academy.org/ru/trainer/tasks/23)
Найдите самый дорогой деликатес (delicacies) и выведите его цену
```sql
SELECT good_name, unit_price FROM Payments
JOIN Goods ON good_id = good
JOIN GoodTypes ON type = good_type_id
WHERE good_type_name = 'delicacies'
ORDER BY unit_price DESC LIMIT 1;
```
#### [Задание 24](https://sql-academy.org/ru/trainer/tasks/24)
Определить, кто и сколько потратил в июне 2005
```sql
SELECT member_name, SUM(amount*unit_price) AS costs 
FROM FamilyMembers
JOIN Payments ON member_id = family_member
WHERE date LIKE "2005-06%"
GROUP BY family_member;
```
#### [Задание 25](https://sql-academy.org/ru/trainer/tasks/25)
Определить, какие товары не покупались в 2005 году
```sql
SELECT good_name FROM Goods
WHERE good_id NOT IN (SELECT good FROM Payments WHERE YEAR(date) = 2005);
```
#### [Задание 26](https://sql-academy.org/ru/trainer/tasks/26)
Определить группы товаров, которые не приобретались в 2005 году
```sql
SELECT good_type_name
FROM GoodTypes
WHERE good_type_id NOT IN(
		SELECT type
		FROM Goods AS g
		JOIN Payments AS p ON p.good = g.good_id
		WHERE YEAR(date) = 2005);
```
#### [Задание 27](https://sql-academy.org/ru/trainer/tasks/27)
Узнайте, сколько было потрачено на каждую из групп товаров в 2005 году. Выведите название группы и потраченную на неё сумму. Если потраченная сумма равна нулю, т.е. товары из этой группы не покупались в 2005 году, то не выводите её.
```sql
SELECT good_type_name, SUM(amount * unit_price) AS costs 
FROM GoodTypes
JOIN Goods ON good_type_id = type
JOIN Payments ON good_id = good
WHERE YEAR(date) = 2005
GROUP BY good_type_name;
```
#### [Задание 28](https://sql-academy.org/ru/trainer/tasks/28)
Сколько рейсов совершили авиакомпании из Ростова (Rostov) в Москву (Moscow) ?
```sql
SELECT COUNT(*) AS count FROM Trip
WHERE town_from = 'Rostov' AND town_to = 'Moscow';
```
#### [Задание 29](https://sql-academy.org/ru/trainer/tasks/29)
Выведите имена пассажиров, улетевших в Москву (Moscow) на самолете TU-134. В ответе не должно быть дубликатов.
```sql
SELECT DISTINCT name FROM Passenger
WHERE id IN (
    SELECT passenger FROM Pass_in_trip
    JOIN Trip ON trip = Trip.id
    WHERE town_to = 'Moscow' AND plane = 'TU-134');
```
#### [Задание 30](https://sql-academy.org/ru/trainer/tasks/30)
Вывести количество занятых мест по каждому рейсу из таблицы Pass_in_trip, отсортировав результат по убыванию количества занятых мест.
```sql
SELECT trip, COUNT(passenger) AS count FROM Pass_in_trip
GROUP BY trip
ORDER BY count DESC;
```
#### [Задание 31](https://sql-academy.org/ru/trainer/tasks/31)
Вывести всех членов семьи с фамилией Quincey.
```sql
SELECT * FROM FamilyMembers
WHERE member_name LIKE '%Quincey';
```
#### [Задание 32](https://sql-academy.org/ru/trainer/tasks/32)
Вывести средний возраст людей (в годах), хранящихся в базе данных. Результат округлите до целого в меньшую сторону.
```sql
SELECT FLOOR(AVG(TIMESTAMPDIFF(YEAR, birthday, CURDATE()))) AS age 
FROM FamilyMembers;
```
#### [Задание 33](https://sql-academy.org/ru/trainer/tasks/33)
Найдите среднюю цену икры на основе данных, хранящихся в таблице Payments. В базе данных хранятся данные о покупках красной (red caviar) и черной икры (black caviar). В ответе должна быть одна строка со средней ценой всей купленной когда-либо икры.
```sql
SELECT AVG(unit_price) AS cost FROM Payments
JOIN Goods ON good = good_id
WHERE good_name LIKE '% caviar';
```
#### [Задание 34](https://sql-academy.org/ru/trainer/tasks/34)
Сколько всего 10-ых классов
```sql
SELECT COUNT(*) AS count 
FROM Class
WHERE name LIKE '10%';
```
#### [Задание 35](https://sql-academy.org/ru/trainer/tasks/35)
Сколько различных кабинетов школы использовались 2 сентября 2019 года для проведения занятий?
```sql
SELECT COUNT(DISTINCT classroom) AS count 
FROM Schedule
WHERE date = '2019-09-02';
```
#### [Задание 36](https://sql-academy.org/ru/trainer/tasks/36)
Выведите информацию об обучающихся, живущих на улице Пушкина (ul. Pushkina)?
```sql
SELECT * FROM Student
WHERE address LIKE 'ul. Pushkina%';
```
#### [Задание 37](https://sql-academy.org/ru/trainer/tasks/37)
Сколько лет самому молодому обучающемуся?
```sql
SELECT MIN(TIMESTAMPDIFF(YEAR, birthday, NOW())) AS year 
FROM Student;
```
#### [Задание 38](https://sql-academy.org/ru/trainer/tasks/38)
Сколько учениц с именем Анна (Anna) учится в школе?
```sql
SELECT COUNT(*) AS count 
FROM Student
WHERE first_name = 'Anna';
```
#### [Задание 39](https://sql-academy.org/ru/trainer/tasks/39)
Сколько обучающихся в 10 B классе ?
```sql
SELECT COUNT(*) AS count 
FROM Student_in_class
WHERE class = (
    SELECT id FROM Class
    WHERE name = '10 B');
```
#### [Задание 40](https://sql-academy.org/ru/trainer/tasks/40)
Выведите название предметов, которые преподает Ромашкин П.П. (Romashkin P.P.). Обратите внимание, что в базе данных есть несколько учителей с такой фамилией.
```sql
SELECT name AS subjects 
FROM Subject
JOIN Schedule ON Subject.id = Schedule.subject
JOIN Teacher ON Schedule.teacher = Teacher.id
WHERE Teacher.last_name = 'Romashkin' 
	AND Teacher.first_name LIKE 'P%' 
	AND Teacher.middle_name LIKE 'P%';
```
#### [Задание 41](https://sql-academy.org/ru/trainer/tasks/41)
Выясните, во сколько по расписанию начинается четвёртое занятие.
```sql
SELECT start_pair 
FROM Timepair
ORDER BY start_pair LIMIT 3,1;
```
#### [Задание 42](https://sql-academy.org/ru/trainer/tasks/42)
Сколько времени обучающийся будет находиться в школе, учась со 2-го по 4-ый уч. предмет?
```sql
SELECT DISTINCT TIMEDIFF(
    (SELECT end_pair 
    FROM Timepair
    WHERE id = 4),

    (SELECT start_pair 
    FROM Timepair
    WHERE id = 2)) AS time 
FROM Timepair;
```
#### [Задание 43](https://sql-academy.org/ru/trainer/tasks/43)
Выведите фамилии преподавателей, которые ведут физическую культуру (Physical Culture). Отсортируйте преподавателей по фамилии в алфавитном порядке.
```sql
SELECT last_name 
FROM Teacher
JOIN Schedule ON Teacher.id = Schedule.teacher
JOIN Subject ON Schedule.subject = Subject.id
WHERE name = 'Physical Culture'
ORDER BY Teacher.last_name;
```
#### [Задание 44](https://sql-academy.org/ru/trainer/tasks/44)
Найдите максимальный возраст (количество лет) среди обучающихся 10 классов на сегодняшний день. 
```sql
SELECT MAX(TIMESTAMPDIFF(YEAR, birthday, NOW())) AS max_year 
FROM Student
JOIN Student_in_class ON Student.id = Student_in_class.student
JOIN Class ON Student_in_class.class = Class.id
WHERE Class.name LIKE '10%';
```
#### [Задание 45](https://sql-academy.org/ru/trainer/tasks/45)
Какие кабинеты чаще всего использовались для проведения занятий? Выведите те, которые использовались максимальное количество раз.
```sql
SELECT classroom 
FROM Schedule
GROUP BY classroom
HAVING COUNT(classroom) = (
    SELECT COUNT(classroom) AS count 
    FROM Schedule
    GROUP BY classroom
    ORDER BY count DESC LIMIT 1);
```
#### [Задание 46](https://sql-academy.org/ru/trainer/tasks/46)
В каких классах введет занятия преподаватель "Krauze" ?
```sql
SELECT DISTINCT name 
FROM Class
JOIN Schedule ON Class.id = Schedule.class
JOIN Teacher ON Teacher.id = Schedule.teacher
WHERE Teacher.last_name = 'Krauze';

```
#### [Задание 47](https://sql-academy.org/ru/trainer/tasks/47)
Сколько занятий провел Krauze 30 августа 2019 г.?
```sql
SELECT COUNT(*) AS count 
FROM Schedule
WHERE Teacher = (
    SELECT id FROM Teacher
    WHERE Teacher.last_name = 'Krauze')
    AND date = '2019-08-30';
```
#### [Задание 48](https://sql-academy.org/ru/trainer/tasks/48)
Выведите заполненность классов в порядке убывания
```sql
SELECT Class.name, COUNT(Student_in_class.Student) AS count 
FROM Student_in_class
JOIN Class ON Student_in_class.class = Class.id
GROUP BY class
ORDER BY count DESC;
```
#### [Задание 49](https://sql-academy.org/ru/trainer/tasks/49)
Какой процент обучающихся учится в "10 A" классе? Выведите ответ в диапазоне от 0 до 100 с округлением до четырёх знаков после запятой, например, 96.0201
```sql
SELECT COUNT(*)/(
	SELECT COUNT(*) 
	FROM Student_in_class)
	*100 AS percent 
FROM Student_in_class
JOIN Class ON Student_in_class.class = Class.id
WHERE Class.name = '10 A';
```
#### [Задание 50](https://sql-academy.org/ru/trainer/tasks/50)
Какой процент обучающихся родился в 2000 году? Результат округлить до целого в меньшую сторону.
```sql
SELECT FLOOR(
	COUNT(*)/(
		SELECT COUNT(*) 
		FROM Student)
	* 100)
AS percent 
FROM Student
WHERE YEAR(birthday) = 2000;
```
#### [Задание 51](https://sql-academy.org/ru/trainer/tasks/51)
Добавьте товар с именем "Cheese" и типом "food" в список товаров (Goods). В качестве первичного ключа (good_id) укажите количество записей в таблице + 1.
```sql
INSERT INTO Goods (good_id, good_name, type)
SELECT
    (SELECT COUNT(*) + 1 FROM Goods),
    'Cheese',
    (SELECT good_type_id FROM GoodTypes WHERE good_type_name = 'food');
```
#### [Задание 52](https://sql-academy.org/ru/trainer/tasks/52)
Добавьте в список типов товаров (GoodTypes) новый тип "auto". В качестве первичного ключа (good_type_id) укажите количество записей в таблице + 1.
```sql
INSERT INTO GoodTypes
SELECT COUNT(*) + 1, 'auto' FROM GoodTypes;
```
#### [Задание 53](https://sql-academy.org/ru/trainer/tasks/53)
Измените имя "Andie Quincey" на новое "Andie Anthony".
```sql
UPDATE FamilyMembers
SET member_name = 'Andie Anthony'
WHERE member_name = 'Andie Quincey';
```
#### [Задание 54](https://sql-academy.org/ru/trainer/tasks/54)
Удалить всех членов семьи с фамилией "Quincey".
```sql
DELETE FROM FamilyMembers
WHERE member_name LIKE '% Quincey';
```
#### [Задание 55](https://sql-academy.org/ru/trainer/tasks/55)
Удалить компании, совершившие наименьшее количество рейсов
```sql
DELETE FROM Company
WHERE id IN (
    SELECT Trip.company 
    FROM Trip
    GROUP BY company
    HAVING COUNT(*) = (
        SELECT COUNT(*) AS count 
        FROM Trip
        GROUP BY company
        ORDER BY count LIMIT 1)
);
```
#### [Задание 56](https://sql-academy.org/ru/trainer/tasks/56)
Удалить все перелеты, совершенные из Москвы (Moscow).
```sql
DELETE FROM Trip
WHERE town_from = 'Moscow';
```
#### [Задание 57](https://sql-academy.org/ru/trainer/tasks/57)
Перенести расписание всех занятий на 30 мин. вперед.
```sql
UPDATE Timepair
SET start_pair = DATE_ADD(start_pair, INTERVAL 30 MINUTE),
end_pair = DATE_ADD(end_pair, INTERVAL 30 MINUTE);
```
#### [Задание 58](https://sql-academy.org/ru/trainer/tasks/58)
Добавить отзыв с рейтингом 5 на жилье, находящиеся по адресу "11218, Friel Place, New York", от имени "George Clooney". В качестве первичного ключа (id) укажите количество записей в таблице + 1.
```sql
INSERT INTO Reviews
SELECT MAX(Reviews.id) + 1, (
	SELECT Reservations.id 
    FROM Reservations
    JOIN Rooms ON Reservations.room_id = Rooms.id
    JOIN Users ON Reservations.user_id = Users.id
    WHERE Rooms.address = '11218, Friel Place, New York' 
    AND Users.name = 'George Clooney'),
    5 FROM Reviews;
```
#### [Задание 59](https://sql-academy.org/ru/trainer/tasks/59)
Вывести пользователей,указавших Белорусский номер телефона ? Телефонный код Белоруссии +375.
```sql
SELECT * FROM Users
WHERE phone_number LIKE '+375%';
```
#### [Задание 60](https://sql-academy.org/ru/trainer/tasks/60)
Выведите идентификаторы преподавателей, которые хотя бы один раз за всё время преподавали в каждом из одиннадцатых классов.

```sql
SELECT DISTINCT teacher 
FROM Schedule
JOIN Class ON Schedule.class = Class.id
WHERE Class.name = '11 A'

INTERSECT 

SELECT DISTINCT teacher 
FROM Schedule
JOIN Class ON Schedule.class = Class.id
WHERE Class.name = '11 B'
```
#### [Задание 61](https://sql-academy.org/ru/trainer/tasks/61)
Выведите список комнат, которые были зарезервированы хотя бы на одни сутки в 12-ую неделю 2020 года. В данной задаче в качестве одной недели примите период из семи дней, первый из которых начинается 1 января 2020 года. Например, первая неделя года — 1–7 января, а третья — 15–21 января.

```sql
SELECT Rooms.* 
FROM Rooms
JOIN Reservations ON Rooms.id = Reservations.room_id
WHERE YEAR(start_date) = 2020 
	AND DAYOFYEAR(start_date) >= 6 * 12 
	AND DAYOFYEAR(start_date) < 7 * 12;
```

#### [Задание 62](https://sql-academy.org/ru/trainer/tasks/62)
Вывести в порядке убывания популярности доменные имена 2-го уровня, используемые пользователями для электронной почты. Полученный результат необходимо дополнительно отсортировать по возрастанию названий доменных имён.

```sql
SELECT SUBSTRING(email, INSTR(email, '@') + 1) AS domain, 
	COUNT(*) AS count 
FROM Users
GROUP BY domain 
ORDER BY count DESC, domain;
```
#### [Задание 63](https://sql-academy.org/ru/trainer/tasks/63)
Выведите отсортированный список (по возрастанию) фамилий и имен студентов в виде Фамилия.И.

```sql
SELECT CONCAT(last_name, '.', LEFT(first_name, 1), '.') AS name 
FROM Student
ORDER BY name;
```
#### [Задание 64](https://sql-academy.org/ru/trainer/tasks/64)
Вывести количество бронирований по каждому месяцу каждого года, в которых было хотя бы 1 бронирование. Результат отсортируйте в порядке возрастания даты бронирования.

```sql
SELECT YEAR(start_date) AS year, MONTH(start_date) AS month, 
	COUNT(*) AS amount 
FROM Reservations
GROUP BY year, month
ORDER BY year, month;
```
#### [Задание 65](https://sql-academy.org/ru/trainer/tasks/65)
Необходимо вывести рейтинг для комнат, которые хоть раз арендовали, как среднее значение рейтинга отзывов округленное до целого вниз.

```sql
SELECT room_id, FLOOR(AVG(Reviews.rating)) AS rating 
FROM Reservations
JOIN Reviews ON Reservations.id = Reviews.reservation_id
GROUP BY room_id;
```
#### [Задание 66](https://sql-academy.org/ru/trainer/tasks/66)
Вывести список комнат со всеми удобствами (наличие ТВ, интернета, кухни и кондиционера), а также общее количество дней и сумму за все дни аренды каждой из таких комнат.

```sql
SELECT 
    home_type,
    address,
    COALESCE(SUM(TIMESTAMPDIFF(DAY, start_date, end_date)), 0) AS days,
    COALESCE(SUM(Reservations.total), 0) AS total_fee
FROM Rooms 
LEFT JOIN Reservations ON Rooms.id = Reservations.room_id
WHERE Rooms.has_air_con = 1 
    AND Rooms.has_internet = 1 
    AND Rooms.has_kitchen = 1 
    AND Rooms.has_tv = 1
GROUP BY Rooms.id, home_type;
```
#### [Задание 67](https://sql-academy.org/ru/trainer/tasks/67)
Вывести время отлета и время прилета для каждого перелета в формате "ЧЧ:ММ, ДД.ММ - ЧЧ:ММ, ДД.ММ", где часы и минуты с ведущим нулем, а день и месяц без.
```sql
SELECT CONCAT(DATE_FORMAT(time_out, "%H:%i, %e.%c"), " - ", DATE_FORMAT(time_in, "%H:%i, %e.%c")) AS flight_time 
FROM Trip;
```
#### [Задание 68](https://sql-academy.org/ru/trainer/tasks/68)
Для каждой комнаты, которую снимали как минимум 1 раз, найдите имя человека, снимавшего ее последний раз, и дату, когда он выехал

```sql
SELECT room_id, Users.name, end_date
FROM Reservations R1
JOIN Users ON R1.user_id = Users.id
WHERE end_date = (
    SELECT MAX(end_date) 
    FROM Reservations R2
    WHERE R2.room_id = R1.room_id
    );
```
#### [Задание 69](https://sql-academy.org/ru/trainer/tasks/69)
Вывести идентификаторы всех владельцев комнат, что размещены на сервисе бронирования жилья и сумму, которую они заработали

```sql
SELECT Rooms.owner_id AS owner_id, COALESCE(SUM(total), 0) AS total_earn 
FROM Rooms
LEFT JOIN Reservations R1 ON Rooms.id = R1.room_id
GROUP BY owner_id;
```
#### [Задание 70](https://sql-academy.org/ru/trainer/tasks/70)
Необходимо категоризовать жилье на economy, comfort, premium по цене соответственно <= 100, 100 < цена < 200, >= 200. В качестве результата вывести таблицу с названием категории и количеством жилья, попадающего в данную категорию

```sql
SELECT 
CASE 
    WHEN price <= 100 THEN 'economy'
    WHEN price > 100 AND price < 200 THEN 'comfort'
    WHEN price >= 200 THEN 'premium'
END AS category,
COUNT(*) AS count
FROM Rooms  
GROUP BY category;
```

#### [Задание 71](https://sql-academy.org/ru/trainer/tasks/71)
Найдите какой процент пользователей, зарегистрированных на сервисе бронирования, хоть раз арендовали или сдавали в аренду жилье. Результат округлите до сотых.
```sql
SELECT ROUND((
		SELECT COUNT(DISTINCT Users.id)
		FROM Users,
			Rooms,
			Reservations
		WHERE Users.id = Reservations.user_id
			OR (
				Users.id = Rooms.owner_id
				AND Rooms.id = Reservations.room_id
			)) / (
			SELECT COUNT(*)
			FROM Users) * 100,
		2) as percent;
```

#### [Задание 72](https://sql-academy.org/ru/trainer/tasks/72)
Выведите среднюю цену бронирования за сутки для каждой из комнат, которую бронировали хотя бы один раз. Среднюю цену необходимо округлить до целого значения вверх.
```sql
SELECT room_id, CEIL(AVG(Reservations.price)) AS avg_price 
FROM Rooms
JOIN Reservations ON Rooms.id = Reservations.room_id
GROUP BY room_id;
```
#### [Задание 73](https://sql-academy.org/ru/trainer/tasks/73)
Выведите id тех комнат, которые арендовали нечетное количество раз

```sql
SELECT room_id, COUNT(*) AS count 
FROM Rooms
JOIN Reservations ON Rooms.id = Reservations.room_id
GROUP BY Rooms.id
HAVING MOD(count, 2) != 0;
```
#### [Задание 74](https://sql-academy.org/ru/trainer/tasks/74)
Выведите идентификатор и признак наличия интернета в помещении. Если интернет в сдаваемом жилье присутствует, то выведите «YES», иначе «NO».
```sql
SELECT id, IF(has_internet, 'YES', 'NO') AS has_internet 
FROM Rooms
```
#### [Задание 75](https://sql-academy.org/ru/trainer/tasks/75)
Выведите фамилию, имя и дату рождения студентов, кто был рожден в мае.
```sql
SELECT last_name, first_name, birthday
FROM Student
WHERE MONTH(birthday) = 05;
```
#### [Задание 76](https://sql-academy.org/ru/trainer/tasks/76)
Вывести имена всех пользователей сервиса бронирования жилья, а также два признака: является ли пользователь собственником какого-либо жилья (is_owner) и является ли пользователь арендатором (is_tenant). В случае наличия у пользователя признака необходимо вывести в соответствующее поле 1, иначе 0.
```sql
SELECT name, 
        IF(id IN (SELECT owner_id FROM Rooms), 1, 0) AS is_owner,
        IF(id IN (SELECT user_id FROM Reservations), 1, 0) AS is_tenant
FROM Users;
```
#### [Задание 77](https://sql-academy.org/ru/trainer/tasks/77)
Создайте представление с именем "People", которое будет содержать список имен (first_name) и фамилий (last_name) всех студентов (Student) и преподавателей(Teacher)
```sql
CREATE VIEW People AS 
SELECT first_name, last_name FROM Student
UNION ALL 
SELECT first_name, last_name FROM Teacher;
```
#### [Задание 78](https://sql-academy.org/ru/trainer/tasks/78)
Выведите всех пользователей с электронной почтой в «hotmail.com»
```sql
SELECT * FROM Users
WHERE email LIKE '%@hotmail.com';
```

#### [Задание 79](https://sql-academy.org/ru/trainer/tasks/79)
Выведите поля id, home_type, price у всего жилья из таблицы Rooms. Если комната имеет телевизор и интернет одновременно, то в качестве цены в поле price выведите цену, применив скидку 10%.
```sql
SELECT id, 
	home_type, 
	IF(has_internet = 1 AND has_tv = 1, price*0.9, price) AS price 
FROM Rooms;
```
#### [Задание 80](https://sql-academy.org/ru/trainer/tasks/80)
Создайте представление «Verified_Users» с полями id, name и email, которое будет показывает только тех пользователей, у которых подтвержден адрес электронной почты.
```sql
CREATE VIEW Verified_Users AS 
SELECT id, name, email 
FROM Users
WHERE email_verified_at IS NOT NUll;
```
#### [Задание 93](https://sql-academy.org/ru/trainer/tasks/93)
Какой средний возраст клиентов, купивших Smartwatch (использовать наименование товара product.name) в 2024 году?
```sql
SELECT AVG(distinct_customers_age.age) AS average_age 
FROM (SELECT DISTINCT Customer.customer_key, Customer.age 
    FROM Customer
    JOIN Purchase ON Customer.customer_key = Purchase.customer_key
    JOIN Product ON Purchase.product_key = Product.product_key
    WHERE Product.name = 'Smartwatch' AND YEAR(Purchase.date) = 2024) AS distinct_customers_age;
```
#### [Задание 94](https://sql-academy.org/ru/trainer/tasks/94)
Вывести имена покупателей, каждый из которых приобрёл Laptop и Monitor (использовать наименование товара product.name) в марте 2024 года?
```sql
SELECT Customer.name 
FROM Customer
JOIN Purchase ON Customer.customer_key = Purchase.customer_key
JOIN Product ON Purchase.product_key = Product.product_key
WHERE YEAR(date) = 2024 
	AND MONTH(date) = 03 
    AND (Product.name = 'Laptop' OR Product.name = 'Monitor')
GROUP BY Customer.customer_key
HAVING COUNT(DISTINCT Product.name) = 2;
```
#### [Задание 97](https://sql-academy.org/ru/trainer/tasks/97)
Посчитать количество работающих складов на текущую дату по каждому городу. Вывести только те города, у которых количество складов более 80. Данные на выходе - город, количество складов.
```sql
SELECT city, COUNT(*) AS warehouse_count 
FROM Warehouses
WHERE ISNULL(date_close) = 1
GROUP BY city 
HAVING warehouse_count > 80;
```
#### [Задание 99](https://sql-academy.org/ru/trainer/tasks/99)
Посчитай доход с женской аудитории (доход = сумма(price * items)). Обратите внимание, что в таблице женская аудитория имеет поле user_gender «female» или «f».
```sql
SELECT SUM(price*items) AS income_from_female 
FROM Purchases
WHERE user_gender IN ('female', 'f');
```
#### [Задание 101](https://sql-academy.org/ru/trainer/tasks/101)
Выведи для каждого пользователя первое наименование, которое он заказал (первое по времени транзакции).
```sql
SELECT user_id, item
FROM (SELECT user_id, item, transaction_ts,
        ROW_NUMBER() OVER(
            PARTITION BY user_id 
            ORDER BY transaction_ts) AS rn
    FROM Transactions
) AS subquery
WHERE rn = 1;
```
#### [Задание 109](https://sql-academy.org/ru/trainer/tasks/109)
Выведите название страны, где находится город «Salzburg»
```sql
SELECT name AS country_name 
FROM Countries
WHERE id IN (
    SELECT countryid 
    FROM Regions
    JOIN Cities ON Regions.id = Cities.regionid
    WHERE Cities.name = 'Salzburg');
```
#### [Задание 111](https://sql-academy.org/ru/trainer/tasks/111)
Посчитайте население каждого региона. В качестве результата выведите название региона и его численность населения.
```sql
SELECT Regions.name AS region_name,
        (SELECT SUM(population) 
        FROM Cities
        GROUP BY regionid
        HAVING regionid = Regions.id) AS total_population
FROM Regions;
```
#### [Задание 114](https://sql-academy.org/ru/trainer/tasks/114)
Напишите запрос, который выведет имена пилотов, которые в качестве второго пилота (second_pilot_id) в августе 2023 года летали в New York
```sql
SELECT name 
FROM Pilots
JOIN Flights ON Pilots.pilot_id = Flights.second_pilot_id
WHERE MONTH(flight_date) = 8 
	AND YEAR(flight_date) = 2023 
	AND destination = 'New York';
```
#### [Задание 123](https://sql-academy.org/ru/trainer/tasks/123)
Необходимо написать SQL-запрос, который покажет всех сотрудников, у кого в работе менее трех задач. Результат предоставить в виде: имя сотрудника, количество задач в работе.
```sql
SELECT emp_name, COUNT(Tasks.id) AS task_count 
FROM Employee
JOIN Tasks ON Employee.id = Tasks.assignee_id
GROUP BY Employee.id
HAVING task_count < 3;
```
#### [Задание 125](https://sql-academy.org/ru/trainer/tasks/125)
Дана база данных автоматизирующая работу библиотеки. В таблице Books хранится информация о произведениях, в таблице BookEditions - информация об изданиях этих произведений (одно произведение может издаваться много раз в разные годы). Найти произведения, которые издавались более 5 раз. В качестве результата вывести название произведения (title).
```sql
SELECT title 
FROM Books
JOIN BookEditions ON Books.id = BookEditions.book_id
GROUP BY title
HAVING COUNT(*) > 5;
```
#### [Задание 128](https://sql-academy.org/ru/trainer/tasks/128)
Создайте индекс idx_price к столбцу price таблицы Rooms.
```sql
CREATE INDEX idx_price
ON Rooms(price);
```
#### [Задание 129](https://sql-academy.org/ru/trainer/tasks/129)
Дана база данных с информацией о компаниях и их счетах. В таблице Company хранится информация о компаниях, в таблице Contract - информация о счетах, в таблице Company_contract - связи между компаниями и их счетами. Найти номера счетов (contract_number) по компаниям, в названии которых (company_name) встречается 'SBER'.
```sql
SELECT contract_number 
FROM Contract
JOIN Company_contract ON Contract.contract_id = Company_contract.contract_id
WHERE Company_contract.company_id IN (
                    SELECT company_id FROM Company
                    WHERE company_name LIKE '%SBER%');
```
#### [Задание 131](https://sql-academy.org/ru/trainer/tasks/131)
Дана база данных с информацией о покупках и зарегистрированных клиентах. В таблице purchases хранится информация о покупках, в таблице registered_customers - информация о зарегистрированных клиентах. Напишите запрос для определения количества заказов, размещенных каждым зарегистрированным клиентом. Выведите customer_id и общее количество заказов, размещенных каждым клиентом.
```sql
SELECT rs.customer_id, COALESCE(COUNT(purchase_id), 0) AS total_orders 
FROM registered_customers rs 
LEFT JOIN purchases ON rs.customer_id = purchases.customer_id
GROUP BY rs.customer_id;
```
#### [Задание 133](https://sql-academy.org/ru/trainer/tasks/133)
Дана база данных с информацией о разработчиках и проектах. В таблице Developers хранится информация о разработчиках, в таблице Projects - информация о проектах, в таблице ProjectHistory - история работы разработчиков над проектами. Вывести все проекты (name), которые никогда не брались в работу разработчиками.
```sql
SELECT name 
FROM Projects
WHERE id NOT IN (
		SELECT project_id 
		FROM ProjectHistory);
```
#### [Задание 139](https://sql-academy.org/ru/trainer/tasks/139)
Страна считается большой, если:
- её площадь составляет не менее 3 миллионов км² (3000000), или
- её население составляет не менее 25 миллионов человек (25000000).
Напишите запрос для поиска названия (name), населения (population) и площади (area) больших стран.
```sql
SELECT name, population, area 
FROM World
WHERE area >= 3000000 OR population >= 25000000;
```
