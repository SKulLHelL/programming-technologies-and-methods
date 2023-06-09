# Инверсия управления

your_name.py
```
config = {}

def your_name():
    output_function = config["OUTPUT_FUNCTION"]
    output_function("Your name, ")
```

your_name_people.py
```
people = []


def your_name_people():
    for person in people:
        print(f"Hello, {person}.")
```

main.py
```
import your_name

your_name.config["OUTPUT_FUNCTION"] = print

if __name__ == "__main__":
    your_name.your_name()
```

serzh.py
```
import your_name_people

your_name_people.people.append("Serzh")
```

## Диаграмма

```
@startuml Inversion_Of_Control
class YourName.your_name {
- config []
+ def your_name()
}
class YourName.your_name_people {
+ def your_name_people()
}
class YourName.main {
- config []
+ def your_name()
}
class YourName.serzh {
+ people.append()
}


YourName.your_name <|.. YourName.main
YourName.your_name_people <|.. YourName.main
YourName.serzh <|.. YourName.your_name
@enduml
```
![инверсия контроля](https://github.com/SKulLHelL/programming-technologies-and-methods/blob/main/%D0%9F%D1%80%D0%B0%D0%BA%D1%82%D0%B8%D0%BA%D0%B0%20%E2%84%966/screenshots/Inversion_Of_Control.png)
