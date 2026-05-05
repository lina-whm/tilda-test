# Tilda Zero Block Test - Complete Solution

## Task 2 Approach Explanation

### Magnetic Button
Использовала физическую модель с плавным возвратом через requestAnimationFrame. Подход: вычисляю расстояние от центра кнопки до курсора, при входе в радиус 50px тяну кнопку к курсору с коэффициентом strength (0.35), при выходе - плавно возвращаю на место с easing. Это даёт естественный "магнитный" эффект без рывков. Никаких библиотек - только ванильный JS с одним RAF циклом.

### Smart Ticker
Скорость движения привязала к velocity скролла (разница позиций между кадрами). Направление меняется по знаку velocity: вниз - едет влево, вверх - вправо. Использую плавный lerp для сглаживания рывков. Преимущество: ticker реагирует на интенсивность скролла, а не на абсолютную позицию - получается живой отклик.

---

## Files Structure

```
tilda-test/
├── index.html              # Full demo page (open in browser)
├── task1-t123.html         # Task 1 for T123 block
├── task2-t123.html         # Task 2 for T123 block
├── task3-t123.html         # Task 3 for T123 block
└── README.md              # This file
```

## How to Use in Tilda

### Task 1: Sticky + Step-by-Step
1. Создать Zero Block высотой 100vh
2. Добавить 2 колонки: слева 3 заголовка, справа 3 изображения
3. Добавить T123 с кодом из task1-t123.html
4. Container обернуть в класс .t1-container

### Task 2: Magnetic + Ticker
1. Кнопка в Zero Block - добавить класс .t2-btn-magnetic
2. Обертка для кнопки - класс .t2-magnetic-wrap
3. Для тикера - добавить classes .t2-ticker-wrap, .t2-ticker-track
4. T123 с кодом из task2-t123.html

### Task 3: Adaptive Layers
1. Zero Block с Container
2.-bg: .t3-bg-logo
3. Photos: .t3-photo (3 штуки в .t3-photos-row)
4. Title: .t3-title
5. T123 с кодом из task3-t123.html

## Key Features

- Pure Vanilla JS (no jQuery, GSAP, etc.)
- Passive scroll listeners
- requestAnimationFrame for smooth animations
- CSS custom properties + clamp() for responsive
- No console errors
- Clean class naming
- Mobile-first breakpoints at 960px, 480px
- Window Container scaling for 1920px+

## Notes

- Task 1: On mobile (≤960px) switch to vertical layout (titles on top, images below)
- Task 2: Magnetic radius ~50px, strength 0.35, return smooth
- Task 3: Photo hover effect uses CSS :hover + z-index stacking
- All scripts use IIFE to avoid global namespace pollution