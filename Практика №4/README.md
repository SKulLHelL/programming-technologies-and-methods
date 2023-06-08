# Итератор

```
def alphabets_upto(letter):
    for i in range(65, ord(letter)+1):
            yield chr(i)
 
if __name__ == "__main__":
 
    alphabets_upto_K = alphabets_upto('K')
    alphabets_upto_M = alphabets_upto('M')
 
    for alpha in alphabets_upto_K:
        print(alpha, end=" ")
 
    print()
 
    for alpha in alphabets_upto_M:
        print(alpha, end=" ")

def inBuilt_Iterator1():
     
    alphabets = [chr(i) for i in range(65, 91)]
     
    for alpha in alphabets:
        print(alpha, end = " ")
    print()
 
def inBuilt_Iterator2():
     
    alphabets = [chr(i) for i in range(97, 123)]
     
    for alpha in alphabets:
        print(alpha, end = " ")
    print()
 
if __name__ == "__main__" :
    inBuilt_Iterator1()
    inBuilt_Iterator2()
```

Результат программы:

```
A B C D E F G H I J K 
A B C D E F G H I J K L M A B C D E F G H I J K L M N O P Q R S T U V W X Y Z 
a b c d e f g h i j k l m n o p q r s t u v w x y z
```

## Диаграмма

```
@startuml
interface Iterator.Iterator {
+ boolean hasNext()
+ Object next()
}
interface Iterator.Aggregate {
+ Create Iterator()
+ Iterator()
}
class Iterator.Concrete_Iterator {
+ {static} void hasNext():Next
}
class Iterator.Concrete_Aggregate {
+ {static} void Create Iterator():Iterator
}

Iterator.Iterator <|..|> Iterator.Aggregate
Iterator.Aggregate ..> Iterator.Concrete_Iterator
Iterator.Concrete_Iterator ..> Iterator.Iterator
Iterator.Concrete_Aggregate ..> Iterator.Aggregate
@enduml
```
![](https://github.com/SKulLHelL/programming-technologies-and-methods/blob/main/%D0%9F%D1%80%D0%B0%D0%BA%D1%82%D0%B8%D0%BA%D0%B0%20%E2%84%964/iterator/iterator.jpg)
