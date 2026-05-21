# Тестовое задание Frontend (React)

## Задача 1 — Логика / работа с массивами

### Задача

Напиши функцию `buildUsersStats(orders)`.

Функция должна принять массив заказов пользователей и вернуть массив со статистикой по каждому пользователю.

Для каждого пользователя нужно вернуть:

- имя пользователя;
- количество заказов;
- общее количество купленных товаров;
- общую сумму покупок.

Доп: Также отсортируй результат по убыванию общей суммы покупок.

---

### Дано

```ts
const orders = [
  {
    id: 1,
    user: "Anna",
    products: [
      { title: "Phone", price: 500 },
      { title: "Case", price: 20 },
    ],
  },
  {
    id: 2,
    user: "Ivan",
    products: [
      { title: "Laptop", price: 1200 },
    ],
  },
  {
    id: 3,
    user: "Anna",
    products: [
      { title: "Keyboard", price: 100 },
    ],
  },
];
```

```
[
  {
    user: "Anna",
    ordersCount: 2,
    productsCount: 3,
    totalSpent: 620,
  },
  {
    user: "Ivan",
    ordersCount: 1,
    productsCount: 1,
    totalSpent: 1200,
  },
]
```

---

## Задача 2 — React + GraphQL + fetch

### Задача

Сделай React-компонент, который получает список персонажей из Rick and Morty GraphQL API и отображает их.

Что нужно сделать:

- получить персонажей через `fetch`;
- вывести список карточек;
- показать:
  - имя;
  - картинку;
  - статус персонажа;
- добавить `input` для поиска по имени;
- при изменении input обновлять список;
- показать loading и error состояния.

---

### API

GraphQL endpoint:

```txt
https://rickandmortyapi.com/graphql
```

---

### Дано

```graphql
query Characters($name: String) {
  characters(filter: { name: $name }) {
    results {
      id
      name
      status
      species
      image
    }
  }
}
```
