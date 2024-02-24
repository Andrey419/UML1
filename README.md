@startuml
left to right direction
skinparam packageStyle rectangle

actor DeaneryAdministrator as "Деканат\nадминистратор"
actor Student as "Студент"
actor System as "Информационная\nсистема деканата"

rectangle "Информационная\nсистема деканата" {
    usecase "Принять студента" as UC1
    usecase "Отчислить студента" as UC2
    usecase "Вести учет успеваемости" as UC3
    usecase "Перевести студента" as UC4

    DeaneryAdministrator --> UC1: (1) 
    DeaneryAdministrator --> UC2: (2) 
    DeaneryAdministrator --> UC3: (3) 
    DeaneryAdministrator --> UC4: (4) 

    UC1 --> System: (5) 
    UC2 --> System: (6) 
    UC3 --> System: (7) 
    UC4 --> System: (8) 

    Student --> UC3: (9)
    Student --> UC4: (10)

    UC1 ..> UC2: (11)
}
@enduml
