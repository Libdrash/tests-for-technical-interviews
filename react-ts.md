# Тестовое задание Frontend (React + TypeScript)

## Задача 1 — Работа с API

### Задача

Необходимо получить список изображений и вывести их на страницу.

Что нужно реализовать:

* загрузку данных через `fetch`;
* отображение списка изображений;
* поиск по `id`;
* состояния загрузки и ошибки.

---

### Модель данных

```ts
type ImageItem = {
  id: string;
  url: string;
  width: number;
  height: number;
};
```

---

### API

```txt
https://api.thecatapi.com/v1/images/search?limit=12
```

---

### Заготовка

```tsx
const API_URL =
  "https://api.thecatapi.com/v1/images/search?limit=12";

export default function App() {
  return <div>TODO</div>;
}
```

---

## Задача 2 — TypeScript Generics

### Задача

Перед тобой переиспользуемый компонент списка.

Необходимо корректно затипизировать его так, чтобы:

* тип элемента списка выводился автоматически;
* `renderItem` получал правильный тип элемента;
* компонент можно было использовать с любыми сущностями, содержащими поле `id`.

---

### Код

```tsx
import React from "react";

type Props = Record<string, unknown>;

export const DataList: React.FC<Props> = (props) => {
  const { items, renderItem } = props;

  return (
    <ul>
      {items.map((item) => (
        <li key={item.id}>{renderItem(item)}</li>
      ))}
    </ul>
  );
};
```

---

## Задача 3 — Браузер и Event Loop

### Задача

Не запуская код, определи порядок вывода сообщений в консоль.

Объясни результат.

---

### Код

```html
<!DOCTYPE html>
<html>
  <body>
    <button id="action-btn">
      Press me
    </button>

    <script>
      document
        .getElementById("action-btn")
        .addEventListener("click", () => {
          console.log("Button");
        });

      setTimeout(() => {
        console.log("Timer");
      }, 0);

      Promise.resolve().then(() => {
        console.log("Microtask");
      });

      console.log("Finish");
    </script>
  </body>
</html>
```
