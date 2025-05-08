# js-questions

<details>
  <summary><b>Задача №1</b></summary>
  
  ```js

// Вы работаете с массивом чисел и решили сделать его более организованным.
// Ваша задача — написать функцию, которая принимает массив чисел и возвращает новый массив,
// где все нечетные числа идут в порядке возрастания в начале, а четные — в убывающем порядке в конце.

const inputArray = [7, 2, 5, 3, 4, 8, 1];

// Ожидаемый вывод
// [1, 5, 3, 7, 8, 4, 2]
  ```

  <hr>
  <details>
	<summary><span><b>Ответ</b></span></summary>
	  
  ```js
function sortArray(arr) {
  const result = [];

  for (let num of arr) {
    if (num % 2 !== 0) result.unshift(num);
    else result.push(num);
  }
  return result;
}

console.log(sortArray(inputArray));
  ```

  </details>
  <hr>

</details>

<details>
  <summary><b>Задача №2</b></summary>
  
  ```js
// Основные требования:
// 1. Напишите функцию isMagicString(s), где s — это строка, состоящая только из символов a, b и c.
// 2. Функция должна возвращать true, если строка «нужная», и false в противном случае.

// Результат выполнения функции:

console.log(isMagicString("aabbcc")); // true
console.log(isMagicString("aabbc")); // false
console.log(isMagicString("abcabc")); // true
console.log(isMagicString("abcdef")); // false (невалидные символы)
  ```

  <hr>
  <details>
	<summary><span><b>Ответ</b></span></summary>
	  
  ```js
	// Решение 1 – "наследование контекста"
	getFilteredUsers: function () {
	    return this.users.filter(((user) => {
	        return user.status === this.currentFilter;
	    }))
	}
	
	// Решение 2 – "объявление контекста"
	getFilteredUsers: function () {
	    const self = this
	    return this.users.filter((function (user) {
	        return user.status === self.currentFilter;
	    }))
	}
  ```

  </details>
  <hr>

</details>
<details>
  <summary><b>Задача №3</b></summary>
  
  ```js
// Цель: Напишите функцию на JavaScript, которая анализирует массив чисел
// и возвращает объект с тремя свойствами: максимальное число, минимальное число,
// и среднее арифметическое всех чисел в массиве.

// Описание задачи:
// Вам нужно реализовать функцию analyzeArray, которая принимает на вход массив чисел и возвращает объект с тремя свойствами:
// - max: максимальное число в массиве,
// - min: минимальное число в массиве,
// - average: среднее арифметическое
// всех чисел в массиве.
  ```

  <hr>
  <details>
	<summary><span><b>Ответ</b></span></summary>
	  
  ```js
function analyzeArray(arr) {
    const obj = {
        max: 0,
        avg: 0,
        min: 0,
    };

    obj.min = Math.min(...arr);
    obj.avg = arr.reduce((acc, item) => acc + item) / arr.length;
    obj.max = Math.max(...arr);

    return obj;
}

const numbers = [4, 8, 15, 16, 23, 42];
const result = analyzeArray(numbers);
console.log(result);
// { max: 42, min: 4, average: 18 }

const moreNumbers = [10, -10, 0, 20, -20];
const anotherResult = analyzeArray(moreNumbers);
console.log(anotherResult);
// { max: 20, min: -20, average: 0 }

  ```

  </details>
  <hr>

</details>
<details>
  <summary><b>Задача №4</b></summary>
  
  ```js
// Что выведется при запуске?

let x = 5;
function addFive(num) {
    return num + 5;
}
x = (x++, (x = addFive(x)), (x *= 2), (x -= 5), (x += 10));

console.log(x);

  ```

  <hr>
  <details>
	<summary><span><b>Ответ</b></span></summary>
	  
  27

  </details>
  <hr>

</details>
<details>
  <summary><b>Задача №5</b></summary>
  
  ```js
// Что выведется при запуске?

let x = 10;

function foo() {
    console.log(x);
}

function bar() {
    let x = 20;
    foo();
}

bar();
  ```

  <hr>
  <details>
	<summary><span><b>Ответ</b></span></summary>
	  
  10

  </details>
  <hr>

</details>
<details>
  <summary><b>Задача №6</b></summary>
  
  ```js
// Что выведется при запуске?

const arr = [1, 2, 3];
const str = arr.join("");

console.log(typeof str);
console.log(str);

  ```

  <hr>
  <details>
	<summary><span><b>Ответ</b></span></summary>
	  
  ```js
	string
  123
  ```

  </details>
  <hr>

</details>
<details>
  <summary><b>Задача №7</b></summary>
  
  ```js
// Что выведется при запуске?

let arr = [1, 2, 3, 4, 5];
let newArr = arr.filter((num) => num > 2).map((num) => num * 2);

console.log(newArr);
  ```

  <hr>
  <details>
	<summary><span><b>Ответ</b></span></summary>
	  
  ```js
  [6, 8, 10]
  ```

  </details>
  <hr>

</details>
<details>
  <summary><b>Задача №8</b></summary>
  
  ```js
// Напишите функцию sortByProperty(arr, prop), которая принимает массив объектов и строку,
// представляющую имя свойства. Функция должна возвращать новый массив, отсортированный по указанному
// свойству в порядке возрастания. Если объекты имеют одинаковое значение для данного свойства, порядок
// их следования должен оставаться неизменным (стабильная сортировка).

const data = [
    { name: "Alice", age: 25 },
    { name: "Bob", age: 20 },
    { name: "Charlie", age: 25 },
    { name: "David", age: 30 },
];

console.log(sortByProperty(data, "age"));
// [
//     { name: 'Bob', age: 20 },
//     { name: 'Alice', age: 25 },
//     { name: 'Charlie', age: 25 },
//     { name: 'David', age: 30 }
// ]

// console.log(sortByProperty(data, "name"));
// [
//     { name: 'Alice', age: 25 },
//     { name: 'Bob', age: 20 },
//     { name: 'Charlie', age: 25 },
//     { name: 'David', age: 30 }
// ]
  ```

  <hr>
  <details>
	<summary><span><b>Ответ</b></span></summary>
	  
  ```js
function sortByProperty(data, str) {
    return data.sort((a, b) => (a[str] > b[str] ? 1 : -1));
}
  ```

  </details>
  <hr>

</details>
<details>
  <summary><b>Задача №9</b></summary>
  
  ```js
// Напишите функцию filterNumbers, которая принимает массив чисел и возвращает новый массив,
// содержащий только те числа, которые являются четными и больше 10.

// ▎Условия:

// 1. Функция должна принимать один аргумент — массив чисел.

// 2. В результирующий массив должны попадать только четные числа, которые больше 10.

// 3. Если в исходном массиве нет подходящих чисел, функция должна возвращать пустой массив.

// ▎Пример:

// console.log(filterNumbers([1, 2, 3, 4, 5, 6, 11, 12, 14])); // [12, 14]
// console.log(filterNumbers([10, 15, 20, 25])); // [20]
// console.log(filterNumbers([1, 3, 5])); // []
  ```

  <hr>
  <details>
	<summary><span><b>Ответ</b></span></summary>
	  
  ```js
function filterNumbers(arr) {
  return arr.filter((item) => item % 2 == 0 && item > 10);
}

  ```

  </details>
  <hr>

</details>
<details>
  <summary><b>Задача №10</b></summary>
  
  ```js
// Напишите функцию filterUnique, которая принимает массив чисел и возвращает новый массив,
// содержащий только уникальные значения из исходного массива. Порядок элементов в новом массиве
// должен соответствовать порядку их появления в исходном массиве.

// Пример использования функции:

// console.log(filterUnique([1, 2, 3, 2, 1, 4])); // [1, 2, 3, 4]
// console.log(filterUnique([5, 5, 5, 5])); // [5]
// console.log(filterUnique([10, 20, 10, 30])); // [10, 20, 30]
// console.log(filterUnique([])); // []

  ```

  <hr>
  <details>
	<summary><span><b>Ответ</b></span></summary>
	  
  ```js
function filterUnique(arr) {
    return arr.reduce((acc, item) => {
        return acc.includes(item) ? acc : [...acc, item];
    }, []);
}
  ```

  </details>
  <hr>

</details>
<details>
  <summary><b>Задача №11</b></summary>
  
  ```js
// Помогите Саше выполнить задание и попасть на работу мечты.
// Напишите JavaScript-функцию с одним параметром n, соблюдая несколько требований от специалиста.
// Если входной параметр равен 1, функция должна вернуть 2.
// Если входной параметр равен 2, функция должна вернуть 1.
// Остальные значения параметра n в задаче не участвуют.
// Не допускается использование условных конструкций: if/else, switch/case, тернарных операторов.
// Предоставьте три варианта решения, один из которых выполняется
// в одну строку, например function example () {   // код }.

  ```

  <hr>
  <details>
	<summary><span><b>Ответ</b></span></summary>
	  
  ```js
function example(n) {
    return n === 1 ? 1 : n == 2 ? 2 : "Числа кроме 1 и 2 недопустимы";
}

console.log(example(34));
  ```

  </details>
  <hr>

</details>


