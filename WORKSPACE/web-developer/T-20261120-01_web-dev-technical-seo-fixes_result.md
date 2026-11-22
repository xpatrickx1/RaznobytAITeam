---
завдання: T-20261120-01
роль: web-developer
виконано: 2026-11-20
статус: частково
версія: 2
---

# Результат: технічні SEO-виправлення в коді сайту (за SEO-ТЗ T-20261119-01)

## Версія 2 (2026-11-21): статична пагінація і `lastmod` за новими ТЗ SEO Specialist
Підстава: пряме доручення CEO 2026-11-21 виконати лише дві задачі: `briefs/brief_web-developer_pagination-static.md` і `briefs/brief_web-developer_sitemap-lastmod.md` (WORKSPACE/seo-specialist). Решту не виконуємо.
**Розділи нижче (версія 1, 2026-11-20) щодо пагінації `?page=N`, `page-N.html`, `/lastmod.json` і nginx для пагінації застаріли й замінені цим розділом.**
Нічого не закомічено й не запушено. Diff версії 2 (відносно вашого останнього коміту): `T-20261120-01_web-dev-technical-seo-fixes/site-code_2026-11-21.patch`.

### Пагінація: `/catalog/<категорія>/page/N/`
- Сторінки 2…N генеруються окремими файлами `catalog/<категорія>/page/<N>/index.html` (UA і RU). nginx не потрібен: неіснуюча сторінка → 404 сама, бо файлу немає. Блок пагінації прибрано з `nginx-raznobyt.conf`.
- На кожній `page/N/` у HTML сервера: 9 товарів саме цієї сторінки (порядок як у даних, стабільний); посилання на всі сторінки категорії; canonical на себе; hreflang uk/ru/x-default на `page/N/`; title «… — сторінка N» / «… — страница N»; description «{опис категорії}. Сторінка N.»; H1 і хлібні крихти як у категорії; SEO-текст лише на сторінці 1.
- У HTML сайту немає посилань із `?page=` і на `/page/1/`. «Завантажити більше» лишилась і дописує товари без зміни адреси.
- JS (браузер): маршрут `/catalog/:slug/page/:page/`; `/page/1/` → перенаправлення на сторінку категорії; `/page/0/`, `/page/abc/`, `/page/99/` → сторінка 404; зміна фільтра на `page/N/` повертає на сторінку 1 з фільтром.
- Сторінки `page/N/` у sitemap не додаються.

### `lastmod`: варіант A (хеш вмісту + реєстр)
Обрано варіант A: дані товарів беруться з Google Sheets без поля дати зміни (`scripts/sync.js`).
- Формат `YYYY-MM-DDThh:mm:ss+00:00` (UTC, час збірки), одразу після `<loc>`; `changefreq`/`priority` лишено.
- Хеш SHA-256 значущого вмісту: title, meta description і `<main>` без шапки, меню, футера, `<script>`/`<style>` і блоку «Схожі товари» (позначений `data-lastmod-ignore`). Хеші файлів збірки й `?v=` нормалізуються. UA і RU рахуються окремо.
- Реєстр `lastmod-manifest.json` лежить у корені проєкту (не в `dist/`, на сайт не потрапляє) і доданий у `.gitignore`. Між збірками в GitHub Actions його зберігає `actions/cache` (кроки restore перед build і save після деплою в `deploy.yml`). Причина: CI збирає з чистої копії репозиторію, а закомічений реєстр застарівав би. Сторінки, яких немає в sitemap, з реєстру випадають.
- Перший запуск у CI: реєстру ще немає, тож усі сторінки отримають час першої збірки (за ТЗ це прийнятно, один раз). Кеш GitHub видаляється, якщо ним не користуватися 7 днів; cron кожні 6 год цьому запобігає. Якщо кеш все ж зникне, буде одноразове скидання дат.

### Змінені файли (версія 2)
| Файл | Суть |
|---|---|
| `scripts/generate.js` | пререндер `page/N/`; sitemap без `page/N/`; `lastmod` (хеш значущого вмісту, реєстр, час UTC); прибрано `/lastmod.json` і запит до живого сайту |
| `src/App.jsx` | маршрут `/catalog/:slug/page/:page/` |
| `src/pages/CategoryPage.jsx` | номер сторінки з адреси/пропса; 404 і перенаправлення `/page/1/`; фільтри на `page/N/` → сторінка 1 |
| `src/components/Category/CategoryView.jsx` | посилання `/page/N/`; title/description сторінки N; прокрутка при зміні сторінки |
| `src/components/SEO/index.jsx` | прибрано проп `query` (canonical/hreflang беруться з адреси) |
| `src/lib/pagination.js` | прибрано `pageQuery` |
| `src/components/Product/ProductView.jsx` | `data-lastmod-ignore` на блоці «Схожі товари» |
| `src/index.css` | лише коментар |
| `.github/workflows/deploy.yml` | кроки `actions/cache/restore@v4` і `actions/cache/save@v4` для `lastmod-manifest.json` |
| `.gitignore` | `lastmod-manifest.json` |

### Перевірки (версія 2)
Локальні збірки `node scripts/generate.js` (без `npm run sync` і мережі; плагін critical CSS піднімає 127.0.0.1 і headless Chromium, на виконання цього завдання CEO погодив 2026-11-20), 7 запусків, кожен exit 0, 719 сторінок, 0 помилок рендеру. Скрипти перевірки лежать у scratchpad сесії й читають лише `dist/` і дані.
| Критерій ТЗ | Результат |
|---|---|
| Пагінація 2: об'єднання товарів сторінки 1 і всіх `page/N/` = усі товари категорії, без пропусків і повторів, 14 категорій × 2 мови | OK (напр. workwear 50 = 6 сторінок, shirts 67 = 8) |
| Пагінація 1: `page/2/` = 10-й…18-й товари | OK (порядок збігається з даними) |
| Пагінація 3–4: canonical на себе; hreflang uk/ru/x-default на `page/N/`; «сторінка N»/«страница N» | OK на всіх 52 сторінках |
| Пагінація 5: `page/99/` → 404 | файлу немає (`page/(total+1)/` не існує для жодної категорії); 404 віддає сервер → перевіряє SEO після деплою |
| Пагінація 6: посилань `?page=` у HTML | 0 з 719 файлів; посилань на `/page/1/` 0 |
| Пагінація 7: після JS ті самі товари, canonical, title | той самий компонент і дані, що й при пререндері; у браузері не перевірялось → SEO Specialist після деплою |
| Пагінація 8: сторінка 1 і картки без змін, sitemap без `page/N/` | sitemap 656 URL, `page/` 0, `unknown` 0 |
| lastmod 1–2: рівно один `<lastmod>` формату `…T…+00:00`, після `<loc>`, не в майбутньому | 656/656 OK |
| lastmod 3: дві збірки без змін | 0 змінених дат з 656 |
| lastmod 4: правка опису TR-55 лише в UA | змінилась лише `https://raznobyt.com/catalog/workwear/tkan-workwear-tr-55/`; RU-картка й категорія без змін (опис у картці категорії не виводиться). Дані після тесту відновлено з копії, `git status` для них чистий |
| lastmod 5: зміна тексту у футері | 0 змінених дат; `Footer.jsx` відновлено з копії |
| lastmod 6: реєстр не на сайті | у `dist/` немає `lastmod-manifest.json` і `lastmod.json` |
| lastmod 7: 3 hreflang на URL, кількість URL і `<loc>` | 656/656 по 3 hreflang; 656 URL як і раніше |

### Ризики (версія 2)
1. На FTP могли лишитися файли версії 1 (`page-N.html`, `lastmod.json`), бо деплой не видаляє старі файли (`dangerous-clean-slate: false`). На них ніщо не посилається; за бажанням видалити вручну.
2. Після першого деплою всі `lastmod` = час першої збірки CI (одноразово, за ТЗ).
3. Старі адреси `?page=N` віддаватимуть сторінку 1 категорії з canonical на неї. Це коректно, бо дублікат склеюється canonical.
4. У корені локальної копії лишився `lastmod-manifest.json` із тестових збірок (у `.gitignore`, у репозиторій і на сайт не потрапляє).

### Відкат (версія 2)
До коміту: `git restore .github/workflows/deploy.yml .gitignore scripts/generate.js src/App.jsx src/components/Category/CategoryView.jsx src/components/Product/ProductView.jsx src/components/SEO/index.jsx src/index.css src/lib/pagination.js src/pages/CategoryPage.jsx` (повертає стан вашого останнього коміту, тобто версію 1). Після коміту: `git revert <коміт>` і push.

---

## Підсумок (≤ 5 рядків)
Пункти 3, 4 (код), 5 («зараз») і 6 реалізовано в `{SITE_CODE}` і перевірено локальною збіркою (719 сторінок, 0 помилок).
Пункт 1 зроблено в коді (посилання зі слешем). Серверна частина пунктів 1, 2 і 4 (редирект на https, кеш, маршрутизація `?page=N`) потребує конфігу nginx. У коді його немає, тому готовий фрагмент лежить у `T-20261120-01_web-dev-technical-seo-fixes/nginx-raznobyt.conf`.
**Порядок для CEO: спершу nginx, потім push.** Push у `master` одразу запускає деплой (GitHub Actions → FTP).
Нічого не закомічено й не запушено.

## Таблиця: пункт ТЗ → стан
| Пункт ТЗ | Стан | Що зроблено / причина |
|---|---|---|
| 1.1 `absolute_redirect off` | частково (на CEO) | фрагмент nginx; у коді конфігу немає |
| 1.2 Слеш у посиланнях меню/шапки/футера | зроблено | 14 посилань меню/футера (ваші незакомічені правки збережено) + решта внутрішніх посилань без слеша (кнопки, крихти, 404, блок «Пожежна безпека»). У зібраному HTML 0 внутрішніх посилань без слеша |
| 1.3 301 `/catalog/personal`, `/catalog/fire` | частково (на CEO) | фрагмент nginx (UA і RU) |
| 2 Кешування | не зроблено в коді (на CEO) | лише сервер; фрагмент nginx |
| 3 Title і description карток | зроблено | шаблон UA/RU; 622 картки: title ≤ 70, UA≠RU; description 70–160 |
| 4 Пагінація | зроблено в коді; маршрутизація на CEO | товари в сирому HTML, `page-N.html`, посилання 1…N, self-canonical і hreflang з `?page=N`, title «— сторінка N», SEO-текст лише на 1-й; `?page=1` → 301 і 404 поза межами робить nginx |
| 5 `unknown` поза sitemap | зроблено | 10 URL прибрано з sitemap; сторінки лишились (перенесення після рішення CEO) |
| 6.1 http-відео | зроблено | `sync.js` пише https; `ProductView` переписує старі http-адреси на відносні |
| 6.2 Українські рядки на RU | зроблено | eyebrow слайдера, «Також цікаво», «Щільність/Склад» у картках товарів, «років тому» у відгуках |
| 6.3 Бренд двічі в title | зроблено | «Про компанію» й «Доставка» UA/RU за текстом ТЗ |
| 6.4 Alt | зроблено | змістовний alt головного слайда; `aria-hidden` для 4 декоративних SVG «Чому ми». У зібраному HTML 0 `<img>` без alt |
| 6.5 meta keywords | зроблено | тег прибрано з компонента SEO і викликів |
| 6.6 `lastmod` | зроблено (див. ризик 4) | дата за хешем змісту сторінки, маніфест `/lastmod.json` |
| 7 Склад тканин | не робилось | за завданням: чекає даних CEO |

## Змінені файли (`C:\Users\Dev\web\fabric-store`)
| Файл | Суть |
|---|---|
| `src/components/Navbar.jsx`, `Footer.jsx`, `Home/HeroSlider.jsx`, `SearchBar.jsx`, `Product/ProductView.jsx` | ваші незакомічені правки (слеш у меню/футері), збережено; доповнено нижче |
| `src/components/Navbar.jsx` | кнопка «Контакти» → `/contacts/` |
| `src/pages/Home.jsx`, `AboutUs.jsx`, `NotFound.jsx`, `CategoryPage.jsx`, `ProductPage.jsx`, `Category/CategoryView.jsx`, `CategoryHighlight.jsx` | кінцевий слеш у внутрішніх посиланнях і `Navigate` |
| `src/components/Product/ProductView.jsx` | шаблон title/description (завд. 3); keywords прибрано; «Також цікаво» RU; відео без http |
| `src/components/SEO/index.jsx` | без `meta keywords`; проп `query` (canonical/hreflang для `?page=N`); проп `brandSuffix` (title без « \| Різнобит») |
| `src/lib/pagination.js` (новий) | розмір сторінки (9) і розрахунок кількості сторінок для `CategoryView` і `generate.js` |
| `src/pages/CategoryPage.jsx` | товари категорії доступні синхронно (потрапляють у пререндер); перевірка `?page` |
| `src/components/Category/CategoryView.jsx` | `?page=N` = окрема сторінка; «Завантажити більше» дописує наступні товари без зміни URL; блок посилань 1…N; title/description «— сторінка N»; SEO-текст лише на 1-й |
| `src/index.css` | стилі `.catalog-pagination` (ваші незакомічені правки меню збережено) |
| `scripts/generate.js` | пререндер `page-N.html`; sitemap без `?page` і `/unknown/`; `<lastmod>` + `dist/lastmod.json` |
| `scripts/sync.js` | відео з `https://` |
| `src/components/Home/HeroSlider.jsx` | alt слайда; eyebrow RU |
| `src/pages/Home.jsx` | `aria-hidden` на SVG; keywords прибрано |
| `src/pages/Blog.jsx`, `News.jsx` | keywords прибрано |
| `src/pages/AboutUs.jsx`, `Delivery.jsx` | title за ТЗ 6.3 |
| `src/components/ProductCard.jsx`, `Reviews.jsx` | RU-рядки |

Повний diff (разом із вашими незакоміченими правками): `T-20261120-01_web-dev-technical-seo-fixes/site-code.patch`.

## Перевірки
| # | Команда | Результат | Виконано |
|---|---|---|---|
| 1 | `node --check scripts/generate.js` | OK | так |
| 2 | `SITEMAP_LASTMOD_OFFLINE=1 node scripts/generate.js` (збірка без `npm run sync` і без завантаження даних; плагін critical CSS піднімав локальний сервер 127.0.0.1 і headless Chromium **з дозволу CEO в цій сесії**) | exit 0; 719 сторінок (667 + 52 сторінки пагінації); 0 помилок рендеру | так, 3 рази |
| 3 | скрипт перевірки `dist/` (у scratchpad сесії, читає лише `dist/`) | canonical: 0 відсутніх, 0 невірних (вкл. `?page=N`); hreflang uk/ru/x-default на всіх; keywords 0; title карток 622: шаблон, ≤70 (мін 31, медіана 59), UA≠RU; description <70: 0, >160: 0; посилань без слеша 0; `<img>` без alt 0; http-відео 0; українські рядки на RU 0; бренд двічі 0 | так |
| 4 | пагінація: обхід `index.html` + `page-N.html` кожної категорії UA і RU | усі товари кожної категорії досяжні (напр. workwear 50/50, 6 сторінок, посилання 2–6) | так |
| 5 | sitemap | 656 URL (666 − 10 unknown); `?page` 0; `/unknown/` 0; без `<lastmod>` 0 | так |
| 6 | стабільність хешів `lastmod` між двома збірками | 0 відмінностей з 719 | так |
| 7 | `html lang` | uk / ru | так |
| 8 | JS у браузері (клік «Завантажити більше», перехід 1→2, консоль Mixed Content) | — | ні: браузер заборонено; перевіряє CEO |
| 9 | заголовки сервера (`curl -sI`) | — | ні: потрібен деплой; перевіряє CEO |

## Як перевірити CEO
**До деплою (локально, необов'язково):** `npm run dev`, відкрити `/catalog/workwear/`, переконатися, що внизу є «Завантажити більше» й посилання 1–6; клік на «2» показує товари 10–18.

**Після nginx + деплою** (команди з ТЗ, cmd/PowerShell):
1. `curl -sI https://raznobyt.com/catalog` → 301, `Location: /catalog/` (не `http://`); те саме для `/catalog/workwear/tkan-workwear-tr-55`.
2. `curl -sI https://raznobyt.com/catalog/personal` → 301 на `/catalog/sfera-poslug/`; `/catalog/fire` → `/catalog/fire-safety/`.
3. `curl -sI https://raznobyt.com/` і `/catalog/workwear/` → `Cache-Control: no-cache`; `/sitemap.xml` → `no-cache`; `/assets/js/index-*.js` → `max-age=31536000`.
4. `curl -sI "https://raznobyt.com/catalog/workwear/?page=1"` → 301 на `/catalog/workwear/`; `?page=99` → 404; `?page=2` → 200.
5. Ctrl+U на `/catalog/workwear/?page=2`: canonical і hreflang з `?page=2`, у HTML 9 товарів-посилань.
6. Ctrl+U на будь-якій картці: title «Тканина … | Різнобит» (RU «Ткань …»), немає `name="keywords"`.
7. `https://raznobyt.com/sitemap.xml`: немає `/unknown/` і `?page`, у кожного `<url>` є `<lastmod>`.
8. F12 → Console на `/catalog/unknown/tkan-army-defender-m-dm-9210/`: немає Mixed Content.
9. Після цього повідомити Director: SEO Specialist робить повторну перевірку за ТЗ.

## Ризики
1. **Порядок деплою.** Якщо код задеплоїти без nginx, `?page=2` віддасть HTML першої сторінки з canonical на першу. Після завантаження JS сторінка покаже товари 10–18, а canonical зміниться на `?page=2`. Пошуковик бачить розбіжність. Тому спершу nginx, потім push. Push = автодеплой; cron перезбирає сайт кожні 6 год.
2. **`add_header` у nginx** скасовує заголовки рівня server (HSTS тощо). Якщо вони є, їх треба продублювати (є коментар у фрагменті). Чинний конфіг і доступ до нього `[НЕВІДОМО]`. На віртуальному хостингу є текст запиту до підтримки.
3. **Пагінація змінила поведінку `?page`.** Раніше `?page=3` показувало товари 1–27 («Завантажити більше» писало page в URL). Тепер `?page=3` показує 19–27, а «Завантажити більше» дописує товари без зміни URL. Старі закладки з `?page=N` відкриють N-ту сторінку.
4. **`lastmod`.** На першому деплої всі сторінки отримають дату деплою, бо попередніх даних немає. Далі дата зберігається, доки зміст сторінки не зміниться: збірка в CI бере попередній `/lastmod.json` із живого сайту, це новий HTTP-запит до власного сайту, таймаут 10 с. Якщо файл недоступний, ставиться дата збірки. Зміна меню/футера оновлює дату всіх сторінок, і це коректно.
5. **Title з артикулом.** 24 із 622 title не влазили в 70 символів навіть без складу. Для них прибрано назву категорії: «Тканина {Артикул}, {Щільність} г/м² \| Різнобит». Це рішення поза явним текстом ТЗ, підтвердити в SEO Specialist. Картки з «МВО» у складі (напр. TR-35 TEFLON) переходять на короткий варіант.
6. **Alt головного слайда** («Технічні тканини різних кольорів: рулони твілу для спецодягу») складено за виглядом зображення `[ПРИПУЩЕННЯ]`. Підтвердить CEO або Creative Director.
7. **Опис UA/RU** у description карток береться з Google Sheets як є. Розбіжності складу (завдання 7) лишаються, доки CEO не виправить дані.
8. Локальну збірку CEO дозволив разово; плагін critical CSS міг звертатися до Google Fonts (посилання в шаблоні). Інших мережевих викликів (sync, завантаження) не було.

## Відкат
- **Код до коміту:** `git restore <файл>` для окремих файлів; новий файл `src/lib/pagination.js` прибрати вручну. Увага: `git restore` для `Navbar.jsx`, `Footer.jsx`, `HeroSlider.jsx`, `SearchBar.jsx`, `ProductView.jsx`, `index.css` прибере й ваші попередні незакомічені правки. Копія всього diff: `site-code.patch`.
- **Після коміту/деплою:** `git revert <коміт>` і push (автодеплой). Застарілі `page-N.html` і `lastmod.json` на FTP лишаться, бо `dangerous-clean-slate: false`. Вони нешкідливі, видалити вручну за бажанням.
- **nginx:** повернути збережену копію конфігу, `nginx -t`, reload. Код без nginx працює (див. ризик 1).

## Підтверджені факти
| Твердження | Мітка | Джерело (+ дата) |
|---|---|---|
| Деплой: GitHub Actions на push у `master` і cron кожні 6 год; `npm run sync` (Google Sheets) → build → FTP | `[ФАКТ]` | `.github/workflows/deploy.yml`, 2026-11-20 |
| Конфігу nginx у коді немає | `[ФАКТ]` | огляд `{SITE_CODE}`, 2026-11-20 |
| Дані товарів перезаписуються з Google Sheets під час кожної збірки CI | `[ФАКТ]` | `scripts/sync.js`, `deploy.yml` |
| 7 карток-посилань блоку `/catalog/fire-safety/` ведуть на неіснуючі категорії (`/catalog/outer-protective/`, `system-530` тощо) | `[ФАКТ]` | `src/components/categoryText/fireHighlights.js`, `CategoryHighlight.jsx`; таких категорій немає в `categories.json` |

## Припущення та невідоме
- `[НЕВІДОМО]` чинний конфіг nginx, доступ CEO до нього, наявність глобального `expires 30d` і `add_header` на рівні server.
- `[НЕВІДОМО]` як зараз налаштовано `error_page 404` (фрагмент покладається на чинну обробку 404).

## Висновки та рекомендації
(впевненість: висока для коду; середня для фрагмента nginx, бо чинний конфіг невідомий)
Код готовий до коміту CEO. Публікувати лише після застосування фрагмента nginx.

## Потрібні погодження
- CEO: коміт і push; застосування `nginx-raznobyt.conf` або запит до хостингу.

## Пропозиція щодо наступних завдань
- SEO Specialist: вирішити долю 7 «битих» посилань блоку «Пожежна безпека» (`fireHighlights.js`). Варіанти: прибрати посилання або вести на фільтр/категорію.
- SEO Specialist: підтвердити fallback title без категорії (ризик 5).
- У корені `{SITE_CODE}` є файл `keys.txt`, і він **відстежується git** (`git ls-files`), тобто потрапляє в GitHub-репозиторій. Роль його не відкривала. Якщо там секрети, CEO має прибрати файл із репозиторію й замінити ключі.
