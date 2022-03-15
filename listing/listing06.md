Что выведет программа? Объяснить вывод программы. Рассказать про внутреннее устройство слайсов и что происходит при передачи их в качестве аргументов функции.

```go
package main

import (
	"fmt"
)

func main() {
	var s = []string{"1", "2", "3"}
	modifySlice(s)
	fmt.Println(s)
}

func modifySlice(i []string) {
	i[0] = "3"
	i = append(i, "4")
	i[1] = "5"
	i = append(i, "6")
}
```

Ответ:
```
Вывод программы: [3 2 3]
на строке i[0] = "3" мы изменяем один массив, так как,
что s в main, что i указывают на один и тот же массив 
При вызове append мы уже получаем указатель на новый массив

слайс представляет собой три поля:
длина
емкость
ссылка на массив

Вот и получается, что при передаче слайса в функцию, мы можем изменять
значения слайса из main, ссылка на массив то одна 
```