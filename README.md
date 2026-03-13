# 📋 Практична робота №2 — HTML Таблиці

> **Коледж** · Веб-розробка · 2025  
> Автор: **Makarenko Tymur**

---

## 🎯 Тема та мета

**Тема:** Створення таблиць на Web-сторінках за допомогою мови гіпертекстової розмітки HTML.

**Мета:** Навчитися створювати таблиці за допомогою тегів мови HTML — від простих структур до складного форматування з CSS.

---

## 🗂️ Структура проєкту

```
📁 PR2/
│
├── index.html                 ← Головна сторінка-навігатор
├── README.md
│
└── 📁 pages/
    ├── ex1.html               ← Проста таблиця
    ├── ex2.html               ← Складна таблиця (rowspan / colspan)
    ├── ex3.html               ← Накладна
    ├── ex4.html               ← Накладна з оформленням
    ├── ex5.html               ← Таблиця з colgroup
    ├── ex6.html               ← thead / tbody / tfoot
    ├── ex7.html               ← Меню ресторану
    └── ex8.html               ← Кольори через CSS-класи
```

---

## 📚 Завдання

### Завдання 1 — Проста таблиця
```html
<body style="border: 5px solid green;">
  <header style="border: 5px solid green;">
    <h1>Table_1</h1>
  </header>
  <table width="90%" border="10" cellpadding="2" cellspacing="10">
    <caption>1 Table</caption>
    <tr>
      <th>1 column</th> <th>2 column</th> <th>3 column</th>
    </tr>
    <tr>
      <td>10</td> <td>20</td> <td>30</td>
    </tr>
  </table>
  <footer>Makarenko</footer>
</body>
```
> 💡 Перша таблиця — як перший крок у невідоме. Тут я познайомився з `<table>`, `<th>`, `<td>` і зрозумів, що `border="10"` — це не завжди красиво, але зате чітко видно структуру.

---

### Завдання 2 — Складна таблиця (rowspan / colspan)
```html
<BODY bgcolor="silver" text="blue">
  <TABLE WIDTH="90%" BORDER="10" CELLPADDING="2" CELLSPACING="10">
    <CAPTION><font size="6" color="green">Моя друга таблиця</font></CAPTION>
    <TR>
      <TH>Перший стовбець</TH>
      <TH COLSPAN="2">Другий стовбець</TH>
      <TH>Третій стовбець</TH>
    </TR>
    <TR>
      <TD>10</TD>
      <TD ROWSPAN="2">20</TD>
      <TD>30</TD> <TD>40</TD>
    </TR>
  </TABLE>
</BODY>
```
> 💡 `ROWSPAN` і `COLSPAN` — це як тетріс, тільки в HTML. Спочатку здається складним, але варто намалювати таблицю на папері — і все стає зрозумілим.

---

### Завдання 3 — Накладна
```html
<h2 align="center" style="color: red; font-size: 2em;">Накладна</h2>
<table width="90%" border="10" cellpadding="2" cellspacing="10">
  <tr>
    <th>Найменування</th> <th>Ціна</th>
    <th>Кількість</th>   <th>Разом</th>
  </tr>
  <tr>
    <td>Процесор Intel Core i5</td>
    <td>1200</td> <td>2</td> <td>2400</td>
  </tr>
  <tr>
    <td colspan="3">Разом за покупку</td>
    <td>5200</td>
  </tr>
</table>
```
> 💡 Перший реальний документ у HTML. Виявляється, накладну можна зверстати за 20 рядків коду — і вона буде виглядати майже як справжня.

---

### Завдання 4 — Накладна з оформленням
```html
<!-- Та сама накладна, але з CSS-стилізацією -->
<body style="background: #f0ede8;">
  <header style="background: #2c5f2e; color: #fff;">
    <h1>Table_3</h1>
  </header>
  <table>
    <tr>
      <th style="background: #2c5f2e; color: #fff;">Найменування</th>
      ...
    </tr>
    <tr style="background: #2c5f2e; color: #fff;">
      <td colspan="3">Разом за покупку</td>
      <td>5 200</td>
    </tr>
  </table>
</body>
```
> 💡 Один і той самий HTML — зовсім інший вигляд. Тут я зрозумів головне правило веб-дизайну: структура і стиль — це різні речі, і CSS вирішує все. 

> ⚠️ Ні в якомі разі не пишіть CSS в одному коді з HTML!!!

---

### Завдання 5 — Таблиця з colgroup
```html
<table border="1">
  <colgroup>
    <col span="2" style="background: khaki">
    <col style="background-color: LightCyan">
  </colgroup>
  <tr>
    <th>№ з/п</th>
    <th>Найменування</th>
    <th>Ціна, грн</th>
  </tr>
  <tr>
    <td>1</td> <td>Олівець кольоровий</td> <td>20,00</td>
  </tr>
</table>
```
> 💡 `<colgroup>` — секретна зброя для стилізації цілих стовпців одразу. Замість того щоб писати `style` у кожній комірці — один тег і всі стовпці пофарбовані.

---

### Завдання 6 — thead / tbody / tfoot
```html
<table>
  <thead>
    <tr>
      <th>№ з/п</th> <th>Найменування товару</th>
      <th>Од. виміру</th> <th>Кількість</th>
      <th>Ціна, грн</th> <th>Вартість, грн</th>
    </tr>
  </thead>
  <tfoot>
    <tr>
      <td colspan="5" style="text-align: right">Разом</td>
      <td>1168,80</td>
    </tr>
  </tfoot>
  <tbody>
    <tr>
      <td>1</td> <td>Томати свіжі</td>
      <td>кг</td> <td>15,20</td> <td>69,00</td> <td>1048,80</td>
    </tr>
  </tbody>
</table>
```
> 💡 `<thead>`, `<tbody>`, `<tfoot>` — це як розділи книги: кожен знає своє місце. Браузер може прокручувати `<tbody>` окремо, а `<tfoot>` завжди залишається внизу.

---

### Завдання 7 — Меню ресторану
```html
<table>
  <tr class="section-header">
    <td colspan="4">Гарніри</td>
  </tr>
  <tr class="item-row">
    <td class="col-bullet">•</td>
    <td class="col-name">
      Картопля по-селянськи
      <span class="sub">запечена зі спеціями до золотої скоринки</span>
    </td>
    <td class="col-weight">200/30/50</td>
    <td class="col-price">62 грн</td>
  </tr>
  <tr class="section-header">
    <td colspan="4">Десерти</td>
  </tr>
</table>
```
> 💡 Коли я побачив це завдання, подумав: «меню ресторану — це просто таблиця». Виявляється, так і є. CSS-класи на рядках дають повний контроль над виглядом кожного елементу меню.

---

### Завдання 8 — Кольори через CSS-класи
```html
<style>
  table   { width: 100%; }
  td      { padding: 5px; }
  td.col1 { background: red;    color: white; }
  td.col2 { background: orange; color: gray;  }
  td.col3 { background: yellow; }
</style>

<table cellspacing="0">
  <tr>
    <td class="col1">Крок 1</td>
    <td class="col2">Крок 2</td>
    <td class="col3">Крок 3</td>
  </tr>
</table>
```
> 💡 Найпростіше завдання — і найважливіший урок: CSS-класи відокремлюють логіку від зовнішнього вигляду. Один клас — один стиль. Хочеш змінити колір усіх "Крок 1"? Змінюєш один рядок у CSS.

---

## 🧠 Що я засвоїв

| Тема | Теги / властивості |
|------|--------------------|
| Базова структура таблиці | `<table>`, `<tr>`, `<th>`, `<td>`, `<caption>` |
| Об'єднання комірок | `colspan`, `rowspan` |
| Семантичні секції | `<thead>`, `<tbody>`, `<tfoot>` |
| Стилізація стовпців | `<colgroup>`, `<col>` |
| Рамки | `border`, `border-left/right/top/bottom`, `border-radius` |
| Кольори | `bgcolor`, `background-color`, CSS-класи |
| Відступи | `cellpadding`, `cellspacing`, `padding` |
| Форматування тексту | `<b>`, `<i>`, `<u>`, `<font>`, `color` |

---

## 🚀 Як запустити

```bash
git clone https://github.com/g4rnet/College_Web-Design_Pr-2
cd praktychna-robota-2
```

Відкрий `index.html` у браузері — і переходь до будь-якого завдання через головний навігатор.

> Жодних залежностей, жодного сервера — чистий HTML/CSS, що працює прямо з файлової системи.

---

## 📌 Навіщо цей репозиторій

Це частина моєї навчальної колекції з коледжу. Я зберігаю кожну практичну роботу, щоб:

- 📖 Бачити власний прогрес з часом
- 🔍 Повертатись до базових концепцій коли потрібно
- 💼 Показати роботодавцям або іншим студентам як виглядає реальне навчання — з помилками, переробками та зростанням

> *"Найкращий код — це той, який ти написав сам і зрозумів чому він працює."*

---

<div align="center">
  <sub>Makarenko Tymur · Коледж · 2025</sub>
</div>
