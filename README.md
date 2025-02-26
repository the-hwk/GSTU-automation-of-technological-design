# Автоматизация технологического проектирования

## Небольшие пояснения к предметной области

А именно про взаимосвязи между сущностями. Есть **изделие**. Оно может состоять из **сборочных единиц** и **деталей**. **Сборочная единица** представляет собой сборку из **деталей**. А для изготовления **детали** необходим **материал** (например, сталь, пластик, медь и т.д.) определенного объема. Этот объем определяется нормой затрат материала на изготовление детали.

Т.е., например, если необходимо сделать болт, то необходима заготовка из углеродистой стали массой 0,06 кг - это и есть норма затрат. Также в результате обработки заготовки (мы из стального параллелепипеда вырезаем болт) некоторая часть **материала** выбрасывается. Это называется "отходы материала".

## По БД

В результате выполнения л.р. №1 у Вас должна получится следующая БД:

![db-schema](https://github.com/the-hwk/GSTU-automation-of-technological-design/blob/main/db-schema.svg)

## По задачам

#### Л.р. №1
- спроектировать реляционную БД
- разработать приложение для работы с этой БД
	- *CRUD*-операции

#### Л.р. №2
- дополнить функционал приложения поиском **изделий** и **сборочных единиц**, в составе которых имеется указанная **деталь**
	- **деталь** вводится или по коду, или по названию
	- вывести названия **изделий** и **сборочных единиц** (они должны как-то помечаться кто есть кто)

#### Л.р. №3
- дополнить функционал приложения:
	- расчет и вывод общего расхода **материалов** на изготовление указанного **изделия**
	- расчет и вывод расхода **материалов** на изготовление указанного **изделия** подетально (т.е. вывести список **деталей** и расход **материалов**)
		- P.S. именно **деталей**, т.е. если в составе **изделия** есть **сборочные единицы**, то вытягиваем из них **детали** и добавляем в список. Детали не должны дублироваться. Считаем общее количество одноименных **деталей** и вычисляем расход **материала**
- добавить в БД таблицу "План выпуска изделий"
	- включает в себя **изделие**, дату (год и месяц) и количество **изделий**, планируемых к выпуску на эту дату
- дополнить функционал приложения: 
	- определение списка **материалов** и вычисление требуемого их объема для изготовления **изделий** на указанную дату

## И внимание!

Заполнить БД адекватными тестовыми данными! В файле с л.р. №1 есть таблицы с данными.
Или реализовать генератор наименований в виде `Деталь-1`, `Деталь-2`, `Деталь-3` и т.д., чтобы было понятно что где и куда.
