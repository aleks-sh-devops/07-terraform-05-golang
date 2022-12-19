
С `golang` в рамках курса, мы будем работать не много, поэтому можно использовать любой IDE. 
Но рекомендуем ознакомиться с [GoLand](https://www.jetbrains.com/ru-ru/go/).  

## Задача 1. Установите golang.
1. Воспользуйтесь инструкций с официального сайта: [https://golang.org/](https://golang.org/).
2. Так же для тестирования кода можно использовать песочницу: [https://play.golang.org/](https://play.golang.org/).
## Ответ  
```
yum install golang -y

go version

go version go1.18.4 linux/amd64
```
## Задача 2. Знакомство с gotour.
У Golang есть обучающая интерактивная консоль [https://tour.golang.org/](https://tour.golang.org/). 
Рекомендуется изучить максимальное количество примеров. В консоли уже написан необходимый код, 
осталось только с ним ознакомиться и поэкспериментировать как написано в инструкции в левой части экрана.  

## Ответ  
Ознакомился

## Задача 3. Написание кода. 
Цель этого задания закрепить знания о базовом синтаксисе языка. Можно использовать редактор кода 
на своем компьютере, либо использовать песочницу: [https://play.golang.org/](https://play.golang.org/).

1. Напишите программу для перевода метров в футы (1 фут = 0.3048 метр). Можно запросить исходные данные 
у пользователя, а можно статически задать в коде.
    Для взаимодействия с пользователем можно использовать функцию `Scanf`:
    ```
    package main
    
    import "fmt"
    
    func main() {
        fmt.Print("Enter a number: ")
        var input float64
        fmt.Scanf("%f", &input)
    
        output := input * 2
    
        fmt.Println(output)    
    }
    ```
 ## Ответ  
 ```
 package main

import "fmt"

func main() {
    fmt.Print("Enter the number of meters: ")
    var input float64
    fmt.Scanf("%f", &input)

    output := input / 0.3048

    fmt.Print("The number of feet is: ")
    fmt.Println(output)
}
 ```
 
Запуск:  
```
[root@vmtester2 07-terraform-05-golang]# go run converter.go
Enter the number of meters: 2
The number of feet is: 6.561679790026246
```

2. Напишите программу, которая найдет наименьший элемент в любом заданном списке, например:
    ```
    x := []int{48,96,86,68,57,82,63,70,37,34,83,27,19,97,9,17,}
    ```
## Ответ  
```
package main

import "fmt"

func main() {
    x := []int{48,96,86,68,57,82,63,70,37,34,83,5033,27,19,97,9,17,1228} // Наш массив
    max := x[0] // Присваиваем переменной 0-й элемент массива
//    fmt.Println(max) // Для отладки.
    for _, i  := range x {
        if i > max {
           max = i
//           fmt.Println(max)  // Для отладки.
        }
    }
fmt.Println(max)
}
```

Запуск:  
```
[root@vmtester2 07-terraform-05-golang]# go run question2.go
5033
```

3. Напишите программу, которая выводит числа от 1 до 100, которые делятся на 3. То есть `(3, 6, 9, …)`.

В виде решения ссылку на код или сам код. 

## Решение  
```
package main

import "fmt"

func main() {
    i := 3
    end := 100
    for i < end {
        if i >= end {
            break
        }
        fmt.Println(i)
        i += 3
    }
}
```

Запуск:  
```
[root@vmtester2 07-terraform-05-golang]# go run question3.go
3
6
9
12
15
18
21
24
27
30
33
36
39
42
45
48
51
54
57
60
63
66
69
72
75
78
81
84
87
90
93
96
99
```
## Задача 4. Протестировать код (не обязательно).

Создайте тесты для функций из предыдущего задания. 
