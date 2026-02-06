# Шпаргалка по TypeScript

## Основы TypeScript

> #### Что такое TypeScript?
> TypeScript — это надмножество JavaScript, добавляющее статическую типизацию. Код TypeScript компилируется в обычный JavaScript.
>
> Типы — это возможные значения данных в программе и возможные операции над ними.

## Типы в TypeScript
TypeScript является строго типизированным языком, и каждая переменная и константа в нем имеет определенный тип.
Для установки типа применяется знак двоеточия `:` (аннотация типа), после которого указывается название типа.
``` TypeScript
let x: number = 10;
let hello: string = "hello world";
```

#### В TypeScript имеются следующие базовые типы:

* **boolean: логическое значение true или false**
``` TypeScript
let isTrue: boolean = true;
let isFalse: boolean = false;
```

* **number: числовое значение** <br>
C помощью данного типа можно определять как целые числа, так и числа с плавающей точкой. <br>TS поддерживает двоичную, восьмеричную, десятичную и шестнадцатиричную записи чисел.
``` TypeScript
let age: number = 36;
let height: number = 1.68;
let hex: number = 0xf00d;
let binary: number = 0b1010;
```

* string: строки

* Array: массивы

* Кортежи

* Enum: перечисления

* Any: произвольный тип

* Symbol

* null и undefined: соответствуют значениям null и undefined в javascript

* Never: также представляет отсутствие значения и используется в качестве возвращаемого типа функций, которые генерируют или возвращают ошибку

| Когда использовать **`type`** | Когда использовать **`interface`** |
|-------------------------------|------------------------------------|
| **1. Для примитивных псевдонимов (Alias):**<br>`type UserID = string;`<br>`type JSONString = string;` | **1. Для описания формы объектов и классов:**<br>`interface User { name: string; id: number; }`|
| **2. Для объединений (Union) и пересечений (Intersection):**<br>`type Status = 'success' \| 'error' \|'pending';`<br>`type Coord = [number, number];` | **2. Когда нужно **декларативное слияние** (Declaration Merging):**<br>Можно определить интерфейс в разных частях кода, и TypeScript их объединит.|
| **3. Для сложных преобразований типов** с помощью утилит:<br>`type UserPreview = Pick<User, 'id' \| 'name'>;` | **3. Для ООП-архитектуры** (контракт класса):<br>`interface Serializable { serialize(): string; }`<br>`class MyClass implements Serializable { ... }` |
| **4. Когда нужен неизменяемый тип** <br>(более строгий подход). | **4. Когда важен интуитивный автокомплит** в IDE с иерархией `extends`.|
| **5. Для кортежей (Tuples):**<br>`type Data = [string, number, boolean];`| |
