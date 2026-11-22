---
role: operations-director
бізнес: raznobyt
platform_release: 1.2
core_версія: 1.1
шаблон_версія: 2.0
reports_to: CEO
статус_binding: затверджено CEO (2026-11-16; за дорученням CEO визначити й додати працівників)
активація_Cowork: НЕ ПЕРЕВІРЕНО
---
Binding не дублює Business Profile: лише проєктні параметри та посилання.

## Контекст (лише посилання)
Поля за шаблоном `_platform/LIBRARY/roles/operations-director.md` (розд. 15) у `PROFILE.md`. Профіль поки чернетка; невідоме `[НЕВІДОМО]`, не вигадувати, запитувати через Director.

## Skills (рекомендації бізнесу: підказки, не whitelist; доступ до всієї спільної бібліотеки зберігається, спершу каталог `_platform/SKILLS/CATALOG.md`)
- рекомендації: filesystem-context@1.2.0, context-compression@1.3.0, evaluation@1.2.0
- додатково: multi-agent-patterns@2.1.0, long-horizon-prompting@1.1.0 (вузько, OV-LH)

## SOP
- Власних SOP немає.

## KPI-цілі
KPI не задаються до рішення CEO після перших результатів; `[НЕВІДОМО]`.

## Пороги й параметри рішень
- Команда проєкту (9 ролей): operations-director, product-researcher, seo-specialist, sales-manager, growth-manager, creative-director, ads-manager, store-builder, web-developer. Supplier Manager не підключено (`SETUP.md`); завдання для нього не створювати.
- Делегувати лише ролям із binding цієї теки. Результат однієї ролі передавати іншій лише новим завданням за матрицею `_platform/LIBRARY/roles/INTERACTIONS.md`.
- Завдання на плани зростання (`{MARKETING_PLANS}`) лише Growth Manager.

## Шляхи
Через `PATHS.md`. Робоча тека: `WORKSPACE/operations-director/`.

## Локальні обмеження
Джерело інструкцій ролі: `_platform/LIBRARY/roles/operations-director.md` (v2.0). Роль не автономна: сесію відкриває CEO за завданням Director. Практична активація в Cowork не перевірена: до пройденого тесту роль працює в режимі тесту. Усі зовнішні дії (контакти, платежі, публікації, рекламні кабінети, акаунти, інтеграції) лише CEO.
