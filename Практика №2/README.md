# Практическая №2

Вариант №3

Информационная система поликлиники

Обзор: информационная система поликлиники позволяет ставить и снимать больных с учета, записывать больных на прием к врачам, учитывать факт приема, а также позволяет вести историю болезни (медицинскую карту) больного.

```
@startuml
title Запись пациента на прием к врачу

actor Пациент as Пациент
participant "Модуль управления расписанием врачей" as Schedule
database База_данных as Database

activate Пациент
Пациент -> Schedule: Открыть расписание врачей
activate Schedule
Schedule -> Database: Загрузить расписание врачей
activate Database
Database --> Schedule: Расписание врачей

Schedule -> Пациент: Отобразить список доступных врачей и время приема
deactivate Schedule

Пациент -> Schedule: Выбрать врача и время приема
activate Schedule

Schedule -> Database: Проверить наличие свободного времени у врача
Database --> Schedule: Свободное время есть

Schedule -> Database: Создать новый прием в расписании врача
Database --> Schedule: Новый прием создан

Schedule -> Пациент: Уведомление о записи на прием
deactivate Schedule

Пациент -> Database: Добавить информацию о приеме в медицинскую карту пациента
activate Database
Database --> Пациент: Информация добавлена в медицинскую карту

Пациент -> Schedule: Закрыть расписание врачей
deactivate Schedule

deactivate Database
deactivate Пациент
@enduml
```
![screen](https://github.com/SKulLHelL/programming-technologies-and-methods/blob/main/%D0%9F%D1%80%D0%B0%D0%BA%D1%82%D0%B8%D0%BA%D0%B0%20%E2%84%962/screenshots/screen1.png)

```
@startuml
skinparam nodesep 80

node "Web-сервер" {
    component "Веб-сайт-поликлиники"
}

node "Сервер\nприложений" {
    component "Сервис управления\nмедкартами"
    component "Сервис записи\nна прием"
    component "Сервис учета\nприема"
}

node "База данных поликлиники" {
    database Данные 
}

"Веб-сайт-поликлиники" --> "Сервис управления\nмедкартами"  
"Веб-сайт-поликлиники" --> "Сервис записи\nна прием" 
"Веб-сайт-поликлиники" --> "Сервис учета\nприема" 
"Сервис управления\nмедкартами" --> Данные 
"Сервис записи\nна прием" --> Данные 
"Сервис учета\nприема" --> Данные 

@enduml
```
![screen](https://github.com/SKulLHelL/programming-technologies-and-methods/blob/main/%D0%9F%D1%80%D0%B0%D0%BA%D1%82%D0%B8%D0%BA%D0%B0%20%E2%84%962/screenshots/screen2.png)
