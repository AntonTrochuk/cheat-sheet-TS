# Шпаргалка по TypeScript

## Основы TypeScript

> #### Что такое TypeScript?
> TypeScript — это надмножество JavaScript, добавляющее статическую типизацию. Код TypeScript компилируется в обычный JavaScript.


| Когда использовать **`type`** | Когда использовать **`interface`** |
|-------------------------------|------------------------------------|
| **1. Для примитивных псевдонимов (Alias):**<br>`type UserID = string;`<br>`type JSONString = string;` | **1. Для описания формы объектов и классов:**<br>`interface User { name: string; id: number; }`|
| **2. Для объединений (Union) и пересечений (Intersection):**<br>`type Status = 'success' \| 'error' \| 'pending';`<br>`type Coord = [number, number];` | **Нельзя** создать объединение напрямую. Можно лишь наследовать от других интерфейсов (`extends`). |
| **3. Для сложных преобразований типов** с помощью утилит:<br>`type UserPreview = Pick<User, 'id' \| 'name'>;` | Возможно, но менее идиоматично. Удобнее для декларативного описания формы объекта. |
| **4. Когда нужен неизменяемый тип** (более строгий подход). | |
| **5. Для кортежей (Tuples):**<br>`type Data = [string, number, boolean];` | Можно описать, но менее очевидно:<br>`interface Data extends Array<string \| number> { 0: string; 1: number; }` (не рекомендуется) |
| | **1. Для описания формы объектов и классов:**<br>`interface User { name: string; id: number; }` |
| | **2. Когда нужно **декларативное слияние** (Declaration Merging):**<br>Можно определить интерфейс в разных частях кода, и TypeScript их объединит. |
| | **3. Для ООП-архитектуры** (контракт класса):<br>`interface Serializable { serialize(): string; }`<br>`class MyClass implements Serializable { ... }` |
| | **4. Когда важен интуитивный автокомплит** в IDE с иерархией `extends`. |
