# SMM & Content Growth Strategy — Premium Consulting Presentation

## Як відкрити

1. Відкрийте файл `index.html` у будь-якому сучасному браузері (Chrome, Safari, Firefox, Edge).
2. Або перетягніть файл у вкладку браузера.

Для найкращого відображення рекомендується Google Chrome або Safari.

---

## Як експортувати PDF

### Варіант A — Через браузер (рекомендовано)

1. Відкрийте `index.html` у Chrome.
2. Натисніть кнопку **"Експорт PDF"** у правому куті навігації.
   - Або: `Cmd+P` (Mac) / `Ctrl+P` (Windows).
3. У діалозі друку:
   - Destination: **Save as PDF**
   - Layout: **Portrait**
   - Margins: **None** або **Minimum**
   - Scale: **100%**
   - Увімкніть: **Background graphics**
4. Натисніть **Save**.

### Варіант B — Chrome CLI (автоматизовано)

```bash
/Applications/Google\ Chrome.app/Contents/MacOS/Google\ Chrome \
  --headless \
  --print-to-pdf="strategy-export.pdf" \
  --no-margins \
  file:///path/to/presentation/index.html
```

---

## Структура файлів

```
presentation/
├── index.html        # Основна презентація (всі 20 секцій)
├── styles.css        # Design system і стилі
└── README.md         # Цей файл
```

---

## Як редагувати контент

### Заголовки і текст

Відкрийте `index.html` у будь-якому текстовому редакторі (VS Code, Cursor тощо).

Кожна секція позначена коментарем:
```html
<!-- ═══════════════════════════════════════════════════════
     01. EXECUTIVE SUMMARY
═══════════════════════════════════════════════════════ -->
<section id="s01" ...>
```

Знайдіть потрібну секцію і редагуйте текст всередині HTML-тегів.

### Кольори і типографіка

Всі кольори і шрифти визначені як CSS-змінні на початку `styles.css`:

```css
:root {
  --bg:    #F8F5F0;    /* основний фон */
  --gold:  #B8935A;    /* акцентний колір */
  --navy:  #0F1621;    /* темні секції */
  /* ... */
}
```

Змініть змінну — зміниться по всьому документу.

---

## Як оновити 30-Day Content Plan

Знайдіть секцію `id="s15"` в `index.html`. Таблиця містить рядки формату:

```html
<tr>
  <td><span class="day-num">01</span></td>
  <td>Тема посту</td>
  <td>LinkedIn</td>
  <td>Формат</td>
  <td>Hook / Ідея</td>
  <td><span class="tag tag-gold">Pillar</span></td>
  <td>Ціль</td>
</tr>
```

Редагуйте текст у `<td>` тегах.

**Класи для тегів (Pillar):**
- `tag` — сірий (стандартний)
- `tag tag-gold` — золотий (акцентний)
- `tag tag-dark` — темний (виділений)

---

## Як додати нову секцію

1. Скопіюйте шаблон секції:

```html
<section id="sXX" class="strategy-section">
  <div class="section-inner">
    <div class="section-header">
      <div class="section-number">XX</div>
      <div>
        <h2 class="section-title">Назва<br><strong>Секції</strong></h2>
        <p class="section-desc">Опис секції.</p>
      </div>
    </div>
    <!-- контент тут -->
  </div>
</section>
```

2. Для темної секції додайте клас `dark-section`:
```html
<section id="sXX" class="strategy-section dark-section">
```

3. Додайте посилання у Table of Contents (секція `.toc`).

---

## Доступні компоненти

| Компонент | Клас | Призначення |
|-----------|------|-------------|
| Картки | `.card` | Блоки інформації |
| Таблиця | `.premium-table` | Дані в табличному форматі |
| Framework | `.framework` | Структуровані фреймворки |
| Воронка | `.funnel` | Lead generation funnel |
| Roadmap | `.roadmap` | Часова шкала |
| Insight | `.insight` | Ключові цитати / висновки |
| Статистика | `.stat-block` | Числові показники |
| Pillar | `.pillar` | Контент-пілари |
| Grid 2/3/4 | `.grid-2` / `.grid-3` / `.grid-4` | Сітки |

---

## Технічні деталі

- **Шрифти:** Cormorant Garamond (display) + Inter (body) — завантажуються з Google Fonts
- **Офлайн режим:** Для роботи без інтернету додайте шрифти локально
- **Браузери:** Chrome 90+, Safari 14+, Firefox 88+, Edge 90+
- **Print:** Оптимізовано для A4 Portrait
