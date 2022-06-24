Инструкция по работе модуля Lnhog_change
Модуль Lnhog_change предназначен для создания/удаления объектов Lnhog и корректировки параметров внутри объекта Lnhog.
Модуль Lnhog имеет два параметра, которые указываются в ini (см. рис.1) 
•	Email_alarm_changes – емейл адрес для рассылки ошибок модуля.
•	Max_num_changes_to_push= максимально допопустимое количество изменений.
 ![image](https://user-images.githubusercontent.com/107686063/175474857-3097c888-1c5d-4ad7-8f85-8400668bc4db.png)


Для корректировки параметров необходимо использовать шаблон, в таком виде см Рисунок 2. Обратите внимание на параметры b2Threshold1GERANQci1, b2Threshold1GERAN их значение необходимо вносить именно в виде словаря!
 
![image](https://user-images.githubusercontent.com/107686063/175474878-b97ed68a-9a8b-4db2-8396-7ad600a14fea.png)

Алгоритм работы с модулем Lnhog:
1.	Проверить, что в шаблоне (см. Рис.2) .
2.	Выбрать нужные кластер секторов LTE.
3.	Запустить модуль в режиме Open Loop, проверить какие изменения он предлагает
4.	Запустить модуль в режиме Close Loop



Алгоритм работы модуля:
 
1.	Считывает соседей 4г-2г  у таргетной соты 4г
2.	Считывает BCCH  у всех соседей, формирует из них список.
3.	Если на секторе нету LNHOG:
Создает объект с указанным списком параметров:
Если LNHOG есть: 
проверяет корректность параметров, если есть отличия корректирует
Проверяет корректно ли создан LNHOG если создан не корректно(кем-то не соном) удаляет


Форма отчета и для чего нужна каждая вкладка
Отчет имеет три вкладке create, update, delete
Create - показываются все созданные объекты и параметры
Update- показывает все измененные параметры.
Delete – все удаленные объекты.
 ![image](https://user-images.githubusercontent.com/107686063/175474917-05e92c31-b684-490c-835c-a8ca023e87f7.png)
![image](https://user-images.githubusercontent.com/107686063/175474931-36a417d7-9990-4034-ab22-b9382f3383b0.png)
![image](https://user-images.githubusercontent.com/107686063/175474946-3ab2173b-55ec-4368-803b-b0f895ce8e9f.png)

Описание названий столбцов.
Object – dn на котором произошли изменение.
Parameter – название параметра.
Value - значение парамтера.
Result – успешность применения параметра, если там стоит не «ок» значит параметр не установил свое значение, необходимо смотреть лог, что бы узнать по какой причине
