# Взаємодія ролей: правила й матриця передачі

Версія 1.2 (2026-11-20: додано Web Developer; 1.1, 2026-11-16: SEO Specialist). Частина бібліотеки ролей; підпорядкована `CORE`, `APPROVALS.md` і шаблонам ролей. Ролі посилаються сюди й не повторюють матрицю.

## 1. Принципи
1. Взаємодія лише через **файли**: завдання у `{TASKS}`, результати у `{WORKSPACE}/<роль>/`, звіти у `{REPORTS}`. Прямого листування між спеціалістами немає.
2. Усі завдання створює й закриває **Operations Director**. Спеціаліст не створює завдань іншим ролям, не редагує чужі файли й не пише в чужий `{WORKSPACE}`.
3. Результат однієї ролі стає входом іншої лише коли Director створив нове завдання, де цей файл указано у «Вхідні файли». Без цього спеціаліст чужих тек не читає.
4. Результат спеціаліста завжди проходить **приймання Director** за `acceptance-checklist.md`. Остаточне рішення завжди за CEO.
5. Автоматичних тригерів, постійно запущених агентів і автоматичного делегування між репозиторіями немає. Передачу ролі відкриває CEO за повідомленням Director.
6. Скрізь, де потрібна зовнішня дія (контакт, оплата, публікація, кабінет, акаунт, інтеграція), роль готує чернетку чи рекомендацію, а виконує **CEO**.

## 2. Ролі в ланцюжку завдання
| Учасник | Що робить |
|---|---|
| CEO | Ставить ціль; ухвалює рішення, які не належать Director; виконує зовнішні дії |
| Operations Director | Ініціює завдання, обирає виконавця, перевіряє, передає результат наступній ролі через нове завдання, звітує CEO |
| Спеціаліст | Виконує завдання в межах компетенції; повертає результат у свою теку; позначає питання до Director/CEO |

## 3. Матриця передач між спеціалістами
Колонки: хто ініціює, хто виконує, хто перевіряє, кому передається, хто приймає остаточне рішення. «Передається» означає, що Director створює для отримувача нове завдання з результатом як вхідним файлом.

| Передача | Що передається | Ініціює | Виконує | Перевіряє | Отримувач | Остаточне рішення |
|---|---|---|---|---|---|---|
| Product Researcher → Supplier Manager | Кандидат (товар, послуга чи пропозиція) із попередніми публічними даними про постачання, позначеними «попередньо» | Director | Product Researcher | Director | Supplier Manager (формальна перевірка за SOP `supplier-verification`) | CEO: чи продовжувати кандидата й чи починати контакт із постачальником |
| Product Researcher → Growth Manager | Вхідні факти для економіки: ціни ринку, конкуренти, ознаки попиту, відомі витрати | Director | Product Researcher | Director | Growth Manager (розрахунок економіки; сам Product Researcher маржі не рахує) | CEO: додавання в асортимент і ціни |
| Product Researcher → Creative Director | Спостереження про рекламу й повідомлення конкурентів, мова клієнтів | Director | Product Researcher | Director | Creative Director | CEO |
| Supplier Manager → Growth Manager | Закупівельні ціни й умови з джерелами, статус ТРИВОЖНО чи ні | Director | Supplier Manager | Director | Growth Manager (юніт-економіка) | CEO: вибір постачальника, закупівля |
| Creative Director → Ads Manager | Готові локальні рекламні матеріали, гіпотези з метрикою, специфікації форматів, список тверджень для підтвердження | Director | Creative Director | Director | Ads Manager (планування тестів на основі матеріалів); CEO для використання в кабінетах | CEO: використання матеріалів у кабінеті |
| Ads Manager → Creative Director | Висновки про креативи за даними кампаній (що спрацювало, що ні) | Director | Ads Manager | Director | Creative Director (ітерації креативів) | CEO |
| Ads Manager → Growth Manager | Витрати на рекламу й результати за період, висновки HOLD/FIX/TEST/INVESTIGATE | Director | Ads Manager | Director | Growth Manager (економіка, пріоритети експериментів) | CEO: бюджети й зміни кампаній |
| Growth Manager → Ads Manager | Беззбиткові CPA/ROAS, межі економіки | Director | Growth Manager | Director | Ads Manager | CEO: цільові CPA/ROAS |
| Sales Manager → Growth Manager | Аналіз воронки, заперечень, відмов і повернень на знеособлених даних | Director | Sales Manager | Director | Growth Manager (гіпотези, пріоритети) | CEO |
| Growth Manager → Sales Manager / Ads Manager / Creative Director / Store Builder | Затверджені CEO пріоритети й гіпотези для виконання в межах ролей | Director за рішенням CEO | Growth Manager (підготовка) | Director | Роль-виконавець через нове завдання | CEO |
| Creative Director → Store Builder | Тексти, повідомлення, візуальний напрям, специфікації | Director | Creative Director | Director | Store Builder (вбудування в структуру сторінок) | CEO: публікація |
| Store Builder → Creative Director | Вимоги до формату сторінок і блоків, потреба в матеріалах | Director | Store Builder | Director | Creative Director | CEO |
| Store Builder → Growth Manager / Sales Manager | Структура воронки на сайті, сторінки, CRO-гіпотези | Director | Store Builder | Director | Growth Manager, Sales Manager | CEO |
| Product Researcher → SEO Specialist | Сегменти, конкуренти, мова клієнтів, ніші | Director | Product Researcher | Director | SEO Specialist (запити й семантика) | CEO |
| SEO Specialist → Creative Director | SEO-ТЗ для текстів: запити, структура, вимоги | Director | SEO Specialist | Director | Creative Director (написання текстів) | CEO: публікація |
| SEO Specialist → Store Builder | SEO-ТЗ для сторінок і технічних правок: структура, метадані, розмітка, посилання | Director | SEO Specialist | Director | Store Builder (чернетки змін) | CEO: зміни на сайті |
| SEO Specialist → Growth Manager | SEO-звіти, органічні результати, гіпотези | Director | SEO Specialist | Director | Growth Manager | CEO |
| Ads Manager → SEO Specialist | Пошукові запити й терміни з реклами, що конвертуються | Director | Ads Manager | Director | SEO Specialist | CEO |
| Store Builder → SEO Specialist | Запит на SEO-перевірку змін перед публікацією | Director | Store Builder | Director | SEO Specialist | CEO |
| Store Builder → Web Developer | Специфікація реалізації (design-handoff): макети, тексти, розміри, стани | Director | Store Builder | Director | Web Developer (зміни коду) | CEO: розгортання |
| SEO Specialist → Web Developer | Технічні SEO-вимоги: метадані, розмітка, canonical, швидкість | Director | SEO Specialist | Director | Web Developer | CEO: розгортання |
| Growth Manager → Web Developer | Затверджені CEO гіпотези зі зміною сайту | Director за рішенням CEO | Growth Manager | Director | Web Developer | CEO |
| Web Developer → Store Builder / SEO Specialist | Реалізовані зміни для перевірки на відповідність специфікації | Director | Web Developer | Director | Store Builder, SEO Specialist | CEO: розгортання |
| Усі спеціалісти → Operations Director | Результат у `{WORKSPACE}/<роль>/`; статус виконано / частково / заблоковано; питання; потреба в рішенні CEO | Director (завдання) | Спеціаліст | Director | Director → CEO (звіт) | CEO |

## 4. Розмежування, що усуває дублювання
- **Креатив і кампанії:** Creative Director відповідає за зміст і якість креативів та креативну стратегію; Ads Manager за кампанії, тести, бюджетні рекомендації та аналіз рекламних результатів. Висновки про креативи ходять між ними через Director.
- **Економіка:** лише Growth Manager рахує маржу, прибуток і беззбиткові показники. Інші ролі передають вхідні факти з джерелами й **не** розраховують прибуток.
- **Постачальники:** Product Researcher дає попередній публічний сигнал; формальна перевірка, скор-картка й порівняння належать Supplier Manager.
- **Тексти:** рекламні й повідомлення бренду пише Creative Director; тексти й структура сторінок магазину, каталогу та карток готує Store Builder на основі підтверджених фактів і матеріалів Creative Director; скрипти й шаблони відповідей клієнтам готує Sales Manager.
- **Воронка:** структуру продажів (стадії, скрипти, заперечення) веде Sales Manager; структуру воронки на сайті (UX, CRO) веде Store Builder; зведену картину росту й пріоритети експериментів веде Growth Manager.
- **Сайт:** Store Builder і SEO Specialist визначають, що змінити (структура, вигляд, SEO-вимоги); Web Developer реалізує в коді й перевіряє локально; розгортає лише CEO.
- **SEO:** SEO Specialist вирішує, що й чому оптимізувати (запити, наміри, структура, технічний аудит) і готує ТЗ; Creative Director пише тексти за ТЗ; Store Builder готує чернетки змін сторінок і конверсію; Growth Manager оцінює вплив на зростання. Пошукова реклама: ключові слова узгоджуються через Director між Ads Manager і SEO Specialist.
- **Плани зростання:** власник каталогу `{MARKETING_PLANS}/` і процесу `marketing-plan` (OV-MP) це Growth Manager; інші ролі дають входи через Director.

## 5. Що спеціаліст робить, коли бракує входу від іншої ролі
Не вигадує дані й не просить колегу напряму: повертає Director статус `заблоковано` з описом бракуючого входу та рекомендацією, яка роль має його підготувати.

## 6. Кінцеві рішення
Рішення про стратегію, фінанси, бюджети, закупівлі, асортимент, постачальників, ціни, публікації, рекламні дії, контакти, інтеграції й зміну правил належить **виключно CEO** (`APPROVALS.md`, розд. 1–3). Director готує варіанти й рекомендації, спеціалісти надають аналіз.
