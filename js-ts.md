# Тестовое задание Frontend (JavaScript / TypeScript)

## Задача 1 — Работа с вложенными структурами

### Задача

Напиши функцию `collectNodes(tree)`.

Функция должна принять массив элементов с вложенными дочерними элементами и вернуть плоский список.

Для каждого элемента необходимо добавить поле:

* `nested: false` — если элемент находится на верхнем уровне;
* `nested: true` — если элемент находится внутри другого элемента.

---

### Дано

```ts
const tree = [
  {
    id: 11,
    children: [
      {
        id: 24,
      },
    ],
  },
  {
    id: 35,
  },
];
```

---

### Ожидаемый результат

```ts
[
  { id: 11, nested: false },
  { id: 24, nested: true },
  { id: 35, nested: false },
]
```

---

## Задача 2 — Event Loop

### Задача

Не запуская код, определи порядок вывода значений в консоль.

Объясни почему именно такой порядок будет получен.

---

### Код

```ts
console.log("A");

setTimeout(() => {
  console.log("B");
}, 0);

Promise.resolve()
  .then(() => {
    console.log("C");
    return 100;
  })
  .then((value) => {
    console.log("D", value);
  });

console.log("E");

Promise.resolve().then(() => {
  console.log("F");
});

setTimeout(() => {
  console.log("G");
}, 0);
```

---

## Задача 3 — Работа с коллекциями данных

### Задача

Посмотри на код ниже.

1. Объясни, что делает данный код.
2. Напиши результат, который будет находиться в переменной `statuses`.
3. Предложи вариант решения без использования Lodash.

---

### Код

```ts
import lodash from "lodash";

const TASKS = [
  { stateId: 10 },
  { stateId: 20 },
  { stateId: 30 },
  { stateId: 10 },
  { stateId: 20 },
];

const statuses = lodash.uniq(
  lodash.map(TASKS, (task) => task.stateId)
);
```
