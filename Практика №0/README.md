# Практика 0
```
@startuml
left to right direction
actor Студент
actor Преподователь
rectangle Практика {
Студент -- (Получить оценку)
(Убедиться что оценка стоит в ведомости)
(Проверка исправленных недочетов)
Студент -- (исправление)
(Получить оценку) .> (Убедиться что оценка стоит в ведомости) : include
(исправление) .> (Проверка исправленных недочетов) : include
Преподователь -- (Проверка практики)
}
@enduml

```
![screen](https://github.com/SKulLHelL/programming-technologies-and-methods/blob/main/%D0%9F%D1%80%D0%B0%D0%BA%D1%82%D0%B8%D0%BA%D0%B0%20%E2%84%960/screenshots/screen1.png)
