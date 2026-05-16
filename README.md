# 🐝 BeeCube — Игровой магазин

Веб-магазин для продажи игровой валюты и предметов. Полностью статический сайт (HTML/CSS/JS), без бэкенда — легко захостить на любом хостинге.

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)

## 📁 Структура

```
├── swordworld-shop (3) (2).html   # Главная — магазин
├── rules.html                      # Правила магазина
├── contacts.html                   # Контакты
└── README.md
```

## ✨ Возможности

- 🛒 Каталог товаров с категориями (валюта, паки, разное)
- 🎯 Выбор своего количества валюты (кастомный ввод)
- 💳 Интеграция с платёжными системами (Lava, Enot.io)
- 📱 Адаптивный дизайн (телефон / планшет / ПК)
- 🔔 Последние покупки в реальном времени
- 🎟️ Система промокодов
- 🌙 Тёмная тема

## ⚙️ Настройка

### Товары

Товары находятся в массиве `DB.products` в главном HTML-файле (строка ~352):

```js
{ id: 7, name: "Набор мечей", amount: 1, price: 99, oldPrice: 199, discount: 50, category: "packs", color: "#7c5cff", tier: "gold" }
```

| Поле | Описание |
|------|----------|
| `id` | Уникальный ID |
| `name` | Название товара |
| `amount` | Количество (для валюты) |
| `price` | Цена в рублях |
| `oldPrice` | Старая цена (зачёркнутая) |
| `discount` | Скидка в % |
| `category` | `"currency"` / `"packs"` / `"misc"` |
| `color` | Цвет иконки (hex) |
| `tier` | `"bronze"` / `"silver"` / `"gold"` / `"diamond"` / `"epic"` / `"legendary"` |

### Кастомное количество

Цена за 1 единицу валюты задаётся константой:

```js
const PRICE_PER_COIN = 0.5; // руб. за 1 эрис
```

### Платёжные системы

Настройте URL-ы в `PAYMENT_CONFIG`:

```js
const PAYMENT_CONFIG = {
  lava: {
    createPaymentUrl: "/api/lava/create-payment",
    checkPaymentUrl:  "/api/lava/check-payment"
  },
  enot: {
    createPaymentUrl: "/api/enot/create-payment",
    checkPaymentUrl:  "/api/enot/check-payment"
  }
};
```

### Контакты

Отредактируйте ссылки в `contacts.html`:
- Telegram: `https://t.me/ваш_бот`
- Discord: `https://discord.gg/ваш_сервер`
- Email: `support@ваш_домен.ru`
- VK: `https://vk.com/ваша_группа`

## 🚀 Деплой

Сайт полностью статический. Варианты хостинга:

- **GitHub Pages** — бесплатно, привязка домена
- **Netlify** — бесплатно, автодеплой из git
- **Любой хостинг** — просто загрузите файлы

```bash
# Пример для GitHub Pages
git init
git add .
git commit -m "initial commit"
git remote add origin https://github.com/user/beecube-shop.git
git push -u origin main
```

## 📱 Скриншоты

Сайт адаптирован под все устройства:
- Мобильные (320px+) — 2 колонки, кнопка "Купить" всегда видна
- Планшеты (768px+) — 3 колонки
- Десктоп (1025px+) — 4 колонки

## 📄 Лицензия

MIT — используйте как хотите.
