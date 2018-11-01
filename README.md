## JavaScript Style Guide

1. Используйте `const` для ссылок
```js
// Плохо
var a = 1;
var b = 2;

// Хорошо
const a = 1;
const b = 2;
```

2. Используйте литеральный синтаксис для создания объекта

```js
// Плохо
const item = new Object();

// Хорошо
const item = {};
```

3. Используйте сокращенную запись свойств

```js
const lukeSkywalker = 'Luke Skywalker';

// Плохо
const obj = {
  lukeSkywalker: lukeSkywalker,
};

// Хорошо
const obj = {
  lukeSkywalker,
};
```

4. Используйте деструкторизацию объектов

```js
// Плохо
function getFullName(user) {
  const firstName = user.firstName;
  const lastName = user.lastName;

  return `${firstName} ${lastName}`;
}

// Хорошо
function getFullName(user) {
  const { firstName, lastName } = user;
  return `${firstName} ${lastName}`;
}

// Лучшее
function getFullName({ firstName, lastName }) {
  return `${firstName} ${lastName}`;
}
```

5. Используйте деструктуризацию массивов

```js
const arr = [1, 2, 3, 4];

// Плохо
const first = arr[0];
const second = arr[1];

// Хорошо
const [first, second] = arr;
```


6. Используйте `''` для простых строк

```js
// Плохо
const name = "Capt. Janeway";

// Плохо
const name = `Capt. Janeway`;

// Хорошо
const name = 'Capt. Janeway';
```

7. Используйте шаблонные строки (Когда это оправдано)


```js
// Плохо
function sayHi(name) {
  return 'How are you, ' + name + '?';
}

// Плохо
function sayHi(name) {
  return ['How are you, ', name, '?'].join();
}

// Плохо
function sayHi(name) {
  return `How are you, ${ name }?`;
}

// Хорошо
function sayHi(name) {
  return `How are you, ${name}?`;
}
```

8. Используйте комментарии

```js
/**
 * Возвращает x в степени n, только для натуральных n
 *
 * @param {number} x Число для возведения в степень.
 * @param {number} n Показатель степени, натуральное число.
 * @return {number} x в степени n.
 */
function pow(x, n) {
  ...
}
```

9. Уровней вложенности должно быть немного.

```js
// Плохо
for (var i = 0; i < 10; i++) {
  if (i подходит) {
    ... // <- уровень вложенности 2
  }
}

// Хорошо
for (var i = 0; i < 10; i++) {
  if (i не подходит) continue;
  ...  // <- уровень вложенности 1
}
```

10. Всегда объявляйте переменные. В противном случае переменная будет объявлена глобальной. Загрязнение глобального пространства имен — всегда плохо.

```js
// Плохо
superPower = new SuperPower();

// Хорошо
let superPower = new SuperPower();
```