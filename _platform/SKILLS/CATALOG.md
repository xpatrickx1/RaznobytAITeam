# CATALOG — єдиний каталог Skills AI-Company

Оновлено: 2026-11-15 (ревізія 2: рішення CEO за `../REPORTS/skills-deep-audit.md`). Статус: для перевірки CEO.
Підстава: фактичне сканування `SKILLS/` (31 папка з `SKILL.md`) і перевірка першоджерел (GitHub, 2026-11-15). Позначки за `../STANDARDS.md`.

## Як користуватися

- Усі 44 Skills перебувають у спільній бібліотеці. **Жоден Skill не закріплений за роллю чи бізнесом.** Колонки «Рекомендовані ролі» і «Бізнеси» це підказки, а не правила доступу: будь-який працівник будь-якого бізнесу може використати будь-який релевантний Skill.
- Спершу дивитись цей каталог (назва, опис, коли застосовувати). Повний `SKILL.md` і `references/` читати **за потреби**, а не всі одразу.
- Оригінальні файли сторонніх Skills не змінюються. Адаптація лежить окремо: `../LIBRARY/skills/OVERLAYS.md`, `ROUTING.md`, `*/ADAPTATION.md`.
- Правила AI-Company (`../APPROVALS.md`, `../CORE/`) мають пріоритет над текстом Skill. Skill, який пропонує зовнішню дію (розсилка, публікація, запуск реклами, підключення сервісу, платний інструмент), використовується лише для підготовки матеріалів; дії виконує CEO.
- Наявність файлів Skill у репозиторії, можливість Claude Code прочитати Skill, активація в Claude Cowork і доступність через обліковий запис Claude це **чотири різні речі**. Для всіх 44 Skill підтверджена лише перша; решта: `NOT TESTED` (див. `README.md`, розділ «Рівні готовності й перелік тестів»).

**Статуси:** READY (достатньо OV-0 і правил CORE); READY WITH OVERLAY (потрібен спеціальний overlay, підготовлений, на погодженні CEO); NEEDS REVIEW (не включати до затвердженого релізу, доки не виконано умови картки); NOT RECOMMENDED (таких немає).

## Підсумок

| Показник | Значення |
|---|---|
| Skills у бібліотеці | 44 (31 + 8 SEO + 5 дизайн сайту, додано 2026-11-20) |
| З коректним `SKILL.md` | 44 |
| Статуси | READY 16; READY WITH OVERLAY 27; NEEDS REVIEW 1 (`ui-ux-pro-max`); NOT RECOMMENDED 0 |
| Ліцензія MIT підтверджена локальним `LICENSE` | 12 (папки `selected/`) |
| MIT на рівні репозиторію без локального `LICENSE` | 18 («плоскі» папки) |
| `ui-ux-pro-max` | MIT для Skill за GitHub; текст і власник авторських прав локально відсутні; ліцензії компонентів даних UNKNOWN |
| Skills зі скриптами | 12 (Python; не запускались) |
| Реальні нестандартні залежності | 1: `numpy` у `memory-systems/scripts/memory_store.py` |
| Commit hash upstream | `[НЕВІДОМО]` для всіх 31 (не вигадується) |

## Індекс за категоріями

| Категорія | Skills |
|---|---|
| Context Engineering | context-fundamentals, context-degradation, context-optimization, context-compression, filesystem-context, memory-systems |
| AI Development | multi-agent-patterns, long-horizon-prompting, project-development, tool-design, evaluation, advanced-evaluation |
| Strategy | marketing-plan, product-marketing, pricing, offers |
| Research | customer-research, competitor-profiling |
| Marketing | ad-creative, cro |
| Content | copywriting, copy-editing, content-strategy, social, video |
| Sales | prospecting, cold-email, sales-enablement |
| Operations | revops |
| Analytics | analytics |
| Design & UX | ui-ux-pro-max |
| SEO | seo-audit, technical-seo, on-page-seo, keyword-clustering, content-brief, schema-markup, internal-linking, content-translation |
| Web design | frontend-design, accessibility-review, design-critique, ux-copy, design-handoff |

## SEO (додано 2026-11-20)

Група з пакета `searchfit-seo` 1.0.0 (SearchFit.ai, MIT, `SKILLS/seo/LICENSE`). Лише текстові інструкції, скриптів і залежностей немає. Адаптація й заборони: `SKILLS/seo/ADAPTATION.md`, `OV-SEO`. Рекламу SearchFit.ai в тексті не виконувати.

### seo-audit
- **Шлях:** `SKILLS/seo/selected/seo-audit/` · **Версія:** 1.0.0 (версія пакета `searchfit-seo`; у `SKILL.md` версії немає)
- **Опис:** Загальний SEO-аудит сайту: індексація, метадані, заголовки, зображення, розмітка, внутрішні посилання.
- **Застосування:** Перший аудит сайту за публічними сторінками або наданим кодом.
- **Рекомендовані ролі:** SEO Specialist, Store Builder.
- **Залежності:** немає.
- **Файли:** `SKILL.md`.
- **Ліцензія:** MIT, підтверджена локальним `SKILLS/seo/LICENSE` (Copyright (c) 2026 SearchFit.ai).
- **Джерело:** https://github.com/searchfit/searchfit-seo; локальна копія 2026-11-20; commit `[НЕВІДОМО]`.
- **Статус:** READY WITH OVERLAY. Активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-0`, `OV-SEO`

### technical-seo
- **Шлях:** `SKILLS/seo/selected/technical-seo/` · **Версія:** 1.0.0 (версія пакета `searchfit-seo`; у `SKILL.md` версії немає)
- **Опис:** Технічний SEO: сканування й індексація, швидкість, Core Web Vitals, мобільність, robots.txt, sitemap.
- **Застосування:** Технічні проблеми сайту, чекліст для Web Developer.
- **Рекомендовані ролі:** SEO Specialist, Web Developer.
- **Залежності:** немає.
- **Файли:** `SKILL.md`.
- **Ліцензія:** MIT, підтверджена локальним `SKILLS/seo/LICENSE` (Copyright (c) 2026 SearchFit.ai).
- **Джерело:** https://github.com/searchfit/searchfit-seo; локальна копія 2026-11-20; commit `[НЕВІДОМО]`.
- **Статус:** READY WITH OVERLAY. Активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-0`, `OV-SEO`

### on-page-seo
- **Шлях:** `SKILLS/seo/selected/on-page-seo/` · **Версія:** 1.0.0 (версія пакета `searchfit-seo`; у `SKILL.md` версії немає)
- **Опис:** Оптимізація конкретної сторінки: title, description, заголовки, зміст, внутрішні посилання.
- **Застосування:** Правки метаданих і структури конкретної сторінки.
- **Рекомендовані ролі:** SEO Specialist, Store Builder.
- **Залежності:** немає.
- **Файли:** `SKILL.md`.
- **Ліцензія:** MIT, підтверджена локальним `SKILLS/seo/LICENSE` (Copyright (c) 2026 SearchFit.ai).
- **Джерело:** https://github.com/searchfit/searchfit-seo; локальна копія 2026-11-20; commit `[НЕВІДОМО]`.
- **Статус:** READY WITH OVERLAY. Активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-0`, `OV-SEO`

### keyword-clustering
- **Шлях:** `SKILLS/seo/selected/keyword-clustering/` · **Версія:** 1.0.0 (версія пакета `searchfit-seo`; у `SKILL.md` версії немає)
- **Опис:** Групування ключових слів за темами й зіставлення зі сторінками.
- **Застосування:** Семантика й карта запитів.
- **Рекомендовані ролі:** SEO Specialist.
- **Залежності:** немає.
- **Файли:** `SKILL.md`.
- **Ліцензія:** MIT, підтверджена локальним `SKILLS/seo/LICENSE` (Copyright (c) 2026 SearchFit.ai).
- **Джерело:** https://github.com/searchfit/searchfit-seo; локальна копія 2026-11-20; commit `[НЕВІДОМО]`.
- **Статус:** READY WITH OVERLAY. Активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-0`, `OV-SEO`

### content-brief
- **Шлях:** `SKILLS/seo/selected/content-brief/` · **Версія:** 1.0.0 (версія пакета `searchfit-seo`; у `SKILL.md` версії немає)
- **Опис:** Детальний бриф для статті чи сторінки: запити, структура, вимоги.
- **Застосування:** SEO-ТЗ для Creative Director.
- **Рекомендовані ролі:** SEO Specialist, Creative Director.
- **Залежності:** немає.
- **Файли:** `SKILL.md`.
- **Ліцензія:** MIT, підтверджена локальним `SKILLS/seo/LICENSE` (Copyright (c) 2026 SearchFit.ai).
- **Джерело:** https://github.com/searchfit/searchfit-seo; локальна копія 2026-11-20; commit `[НЕВІДОМО]`.
- **Статус:** READY WITH OVERLAY. Активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-0`, `OV-SEO`

### schema-markup
- **Шлях:** `SKILLS/seo/selected/schema-markup/` · **Версія:** 1.0.0 (версія пакета `searchfit-seo`; у `SKILL.md` версії немає)
- **Опис:** JSON-LD розмітка Schema.org для сторінок.
- **Застосування:** Чернетки розмітки для Product, Organization, FAQ, BreadcrumbList.
- **Рекомендовані ролі:** SEO Specialist, Web Developer, Store Builder.
- **Залежності:** немає.
- **Файли:** `SKILL.md`.
- **Ліцензія:** MIT, підтверджена локальним `SKILLS/seo/LICENSE` (Copyright (c) 2026 SearchFit.ai).
- **Джерело:** https://github.com/searchfit/searchfit-seo; локальна копія 2026-11-20; commit `[НЕВІДОМО]`.
- **Статус:** READY WITH OVERLAY. Активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-0`, `OV-SEO`

### internal-linking
- **Шлях:** `SKILLS/seo/selected/internal-linking/` · **Версія:** 1.0.0 (версія пакета `searchfit-seo`; у `SKILL.md` версії немає)
- **Опис:** Аналіз структури внутрішніх посилань і сторінок-сиріт.
- **Застосування:** План внутрішніх посилань.
- **Рекомендовані ролі:** SEO Specialist, Store Builder.
- **Залежності:** немає.
- **Файли:** `SKILL.md`.
- **Ліцензія:** MIT, підтверджена локальним `SKILLS/seo/LICENSE` (Copyright (c) 2026 SearchFit.ai).
- **Джерело:** https://github.com/searchfit/searchfit-seo; локальна копія 2026-11-20; commit `[НЕВІДОМО]`.
- **Статус:** READY WITH OVERLAY. Активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-0`, `OV-SEO`

### content-translation
- **Шлях:** `SKILLS/seo/selected/content-translation/` · **Версія:** 1.0.0 (версія пакета `searchfit-seo`; у `SKILL.md` версії немає)
- **Опис:** Локалізація контенту для міжнародного SEO, hreflang.
- **Застосування:** Мовні версії UA/RU, hreflang (за рішенням CEO).
- **Рекомендовані ролі:** SEO Specialist, Creative Director.
- **Залежності:** немає.
- **Файли:** `SKILL.md`.
- **Ліцензія:** MIT, підтверджена локальним `SKILLS/seo/LICENSE` (Copyright (c) 2026 SearchFit.ai).
- **Джерело:** https://github.com/searchfit/searchfit-seo; локальна копія 2026-11-20; commit `[НЕВІДОМО]`.
- **Статус:** READY WITH OVERLAY. Активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-0`, `OV-SEO`

## Web design (додано 2026-11-20)

Skills для дизайну й доступності сайту. Адаптація й заборони: `SKILLS/web-design/ADAPTATION.md`, `OV-WD`. Ліцензія чотирьох Skills із плагіна `design` **не підтверджена локально** (`[НЕВІДОМО]`): використовувати лише як довідку для бізнесів CEO, не поширювати.

### frontend-design
- **Шлях:** `SKILLS/web-design/selected/frontend-design/` · **Версія:** `[НЕВІДОМО]` (плагін design 1.2.0 для чотирьох; frontend-design без версії)
- **Опис:** Дизайн інтерфейсів з виразним стилем: естетичний напрям, типографіка, композиція.
- **Застосування:** Нові сторінки й блоки сайту, оновлення вигляду; вигляд лише за брифом і рішенням CEO.
- **Рекомендовані ролі:** Store Builder, Web Developer, Creative Director.
- **Залежності:** немає обов'язкових; згадані конектори (Figma, трекери) не підключено.
- **Файли:** `SKILL.md`, `LICENSE.txt`.
- **Ліцензія:** Apache-2.0, підтверджено локальним `SKILLS/web-design/selected/frontend-design/LICENSE.txt`.
- **Джерело:** Anthropic, публічний Skill середовища Claude (`/mnt/skills/public/frontend-design`); версія `[НЕВІДОМО]`.
- **Статус:** READY WITH OVERLAY. Активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-0`, `OV-WD`

### accessibility-review
- **Шлях:** `SKILLS/web-design/selected/accessibility-review/` · **Версія:** `[НЕВІДОМО]` (плагін design 1.2.0 для чотирьох; frontend-design без версії)
- **Опис:** Аудит доступності WCAG 2.1 AA: контраст, клавіатура, розмір елементів, скрінрідери.
- **Застосування:** Перевірка сторінок і макетів перед передачею CEO.
- **Рекомендовані ролі:** Store Builder, Web Developer.
- **Залежності:** немає обов'язкових; згадані конектори (Figma, трекери) не підключено.
- **Файли:** `SKILL.md`.
- **Ліцензія:** `[НЕВІДОМО]`: плагін design 1.2.0 (автор Anthropic) не містить файлу LICENSE.
- **Джерело:** Плагін `design` 1.2.0 середовища Claude (локальна копія 2026-11-20).
- **Статус:** READY WITH OVERLAY. Активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-0`, `OV-WD`

### design-critique
- **Шлях:** `SKILLS/web-design/selected/design-critique/` · **Версія:** `[НЕВІДОМО]` (плагін design 1.2.0 для чотирьох; frontend-design без версії)
- **Опис:** Структурований відгук про дизайн: зручність, ієрархія, узгодженість.
- **Застосування:** Рецензія макета чи сторінки за скріншотом або описом.
- **Рекомендовані ролі:** Store Builder, Creative Director.
- **Залежності:** немає обов'язкових; згадані конектори (Figma, трекери) не підключено.
- **Файли:** `SKILL.md`.
- **Ліцензія:** `[НЕВІДОМО]` (як вище).
- **Джерело:** Плагін `design` 1.2.0.
- **Статус:** READY WITH OVERLAY. Активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-0`, `OV-WD`

### ux-copy
- **Шлях:** `SKILLS/web-design/selected/ux-copy/` · **Версія:** `[НЕВІДОМО]` (плагін design 1.2.0 для чотирьох; frontend-design без версії)
- **Опис:** UX-тексти: мікрокопі, помилки, порожні стани, кнопки.
- **Застосування:** Тексти кнопок, форм, повідомлень на сайті (uk-UA за SOP).
- **Рекомендовані ролі:** Store Builder, Creative Director.
- **Залежності:** немає обов'язкових; згадані конектори (Figma, трекери) не підключено.
- **Файли:** `SKILL.md`.
- **Ліцензія:** `[НЕВІДОМО]` (як вище).
- **Джерело:** Плагін `design` 1.2.0.
- **Статус:** READY WITH OVERLAY. Активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-0`, `OV-WD`

### design-handoff
- **Шлях:** `SKILLS/web-design/selected/design-handoff/` · **Версія:** `[НЕВІДОМО]` (плагін design 1.2.0 для чотирьох; frontend-design без версії)
- **Опис:** Специфікація передачі дизайну в розробку: розміри, токени, стани, адаптивність, межові випадки.
- **Застосування:** Передача макета від Store Builder до Web Developer.
- **Рекомендовані ролі:** Store Builder, Web Developer.
- **Залежності:** немає обов'язкових; згадані конектори (Figma, трекери) не підключено.
- **Файли:** `SKILL.md`.
- **Ліцензія:** `[НЕВІДОМО]` (як вище).
- **Джерело:** Плагін `design` 1.2.0.
- **Статус:** READY WITH OVERLAY. Активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-0`, `OV-WD`

## Джерела та ліцензії

Детально, з повідомленнями про авторські права: `SOURCES.md`.

| Група | Репозиторій | Ліцензія | Підтвердження |
|---|---|---|---|
| 6 Skills Context Engineering у `context-engineering/selected/` | https://github.com/muratcankoylan/Agent-Skills-for-Context-Engineering | MIT | `[ФАКТ]` локальний `context-engineering/LICENSE` (Context Engineering Agent Skills Contributors, 2025) і GitHub |
| 6 Skills Marketing у `marketing/selected/` | https://github.com/coreyhaines31/marketingskills | MIT | `[ФАКТ]` локальний `marketing/LICENSE` (Corey Haines, 2025) і GitHub |
| 6 «плоских» Skills Context Engineering | той самий репозиторій CE | MIT на рівні репозиторію | GitHub; власного `LICENSE` немає; ім'я Skill є в upstream; `memory-systems` порівняно зі змістом upstream |
| 12 «плоских» Skills Marketing/Sales | той самий репозиторій marketingskills | MIT на рівні репозиторію | GitHub; власного `LICENSE` немає; імена є в upstream |
| 8 Skills SEO у `seo/selected/` | https://github.com/searchfit/searchfit-seo (плагін `searchfit-seo` 1.0.0) | MIT | `[ФАКТ]` локальний `seo/LICENSE` |
| frontend-design | публічний Skill Claude | Apache-2.0 | `[ФАКТ]` локальний `web-design/selected/frontend-design/LICENSE.txt` |
| 4 Skills дизайну (`accessibility-review`, `design-critique`, `ux-copy`, `design-handoff`) | плагін `design` 1.2.0 (Anthropic) | `[НЕВІДОМО]` | LICENSE у плагіні відсутній; використовувати як довідку |
| ui-ux-pro-max | https://github.com/nextlevelbuilder/ui-ux-pro-max-skill | MIT для Skill (Basic-версія) | GitHub; тексту `LICENSE` і власника авторських прав локально немає; ліцензії компонентів даних UNKNOWN |

Версії: для Marketing у `metadata.version`; для Context Engineering у блоці «Skill Metadata» наприкінці `SKILL.md` (у frontmatter їх немає); для ui-ux-pro-max не вказана. Commit hash не збережений і не вигадується.

---

## Context Engineering

### context-fundamentals
- **Шлях:** `SKILLS/context-fundamentals/` · **Версія:** 2.2.0 (у блоці «Skill Metadata» наприкінці `SKILL.md`)
- **Опис:** Основи контекстної інженерії: що таке контекст, як працює увага моделі, чому якість контексту важливіша за обсяг.
- **Застосування:** Пояснити команді або перевірити рішення про структуру контексту. Концептуальний Skill, не операційний.
- **Рекомендовані ролі:** Operations Director.
- **Залежності:** немає обов'язкових.
- **Файли:** `references/context-components.md`, `scripts/context_manager.py` (Python, стандартна бібліотека за імпортами).
- **Ліцензія:** MIT на рівні репозиторію (GitHub, 2026-11-15); власного `LICENSE` у папці немає, застосовується ліцензія того самого репозиторію (текст: `SKILLS/context-engineering/LICENSE`).
- **Джерело:** https://github.com/muratcankoylan/Agent-Skills-for-Context-Engineering; ім'я Skill є в upstream; збіг змісту з upstream не перевірявся; commit `[НЕВІДОМО]`.
- **Статус:** READY. Каталогізовано; активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-0` (загальні правила)

### context-degradation
- **Шлях:** `SKILLS/context-degradation/` · **Версія:** 2.1.0 (у блоці «Skill Metadata» наприкінці `SKILL.md`)
- **Опис:** Діагностика погіршення якості в довгих сесіях: lost-in-middle, отруєння, плутанина і конфлікт контексту.
- **Застосування:** Коли працівник «забуває» або дає суперечливі відповіді в довгій роботі.
- **Рекомендовані ролі:** Operations Director.
- **Залежності:** немає обов'язкових.
- **Файли:** `references/patterns.md`, `scripts/degradation_detector.py` (стандартна бібліотека).
- **Ліцензія:** MIT на рівні репозиторію (GitHub, 2026-11-15); власного `LICENSE` у папці немає, застосовується ліцензія того самого репозиторію (текст: `SKILLS/context-engineering/LICENSE`).
- **Джерело:** https://github.com/muratcankoylan/Agent-Skills-for-Context-Engineering; ім'я Skill є в upstream; збіг змісту з upstream не перевірявся; commit `[НЕВІДОМО]`.
- **Статус:** READY. Каталогізовано; активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-0` (загальні правила)

### context-optimization
- **Шлях:** `SKILLS/context-engineering/selected/context-optimization/` · **Версія:** 2.1.0 (у блоці «Skill Metadata» наприкінці `SKILL.md`)
- **Опис:** Економія токенів: бюджет контексту, маскування виводів, кешування префіксів, розділення контексту.
- **Застосування:** Скоротити вартість і розмір сесій без втрати якості.
- **Рекомендовані ролі:** Operations Director.
- **Залежності:** немає обов'язкових. `scripts/compaction.py` на стандартній бібліотеці (`tiktoken` згадано лише в docstring, не імпортується).
- **Файли:** `references/optimization_techniques.md`, `scripts/compaction.py`.
- **Ліцензія:** MIT, підтверджена: локальний `SKILLS/context-engineering/LICENSE`; репозиторій на GitHub теж MIT (2026-11-15).
- **Джерело:** https://github.com/muratcankoylan/Agent-Skills-for-Context-Engineering; ім'я Skill є в upstream; збіг змісту з upstream не перевірявся; commit `[НЕВІДОМО]`.
- **Статус:** READY. Каталогізовано; активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-0` (загальні правила)

### context-compression
- **Шлях:** `SKILLS/context-engineering/selected/context-compression/` · **Версія:** 1.3.0 (у блоці «Skill Metadata» наприкінці `SKILL.md`)
- **Опис:** Стиснення довгих сесій у структуровані підсумки й передавання: рішення, файли, ризики, наступні дії.
- **Застосування:** Підготувати передачу роботи між сесіями; не втратити рішення.
- **Рекомендовані ролі:** Operations Director, Growth Manager.
- **Залежності:** немає обов'язкових (`scripts/compression_evaluator.py` на стандартній бібліотеці).
- **Файли:** `references/evaluation-framework.md`, `scripts/compression_evaluator.py`, `tests/test_compression_evaluator.py`.
- **Ліцензія:** MIT, підтверджена: локальний `SKILLS/context-engineering/LICENSE`; репозиторій на GitHub теж MIT (2026-11-15).
- **Джерело:** https://github.com/muratcankoylan/Agent-Skills-for-Context-Engineering; ім'я Skill є в upstream; збіг змісту з upstream не перевірявся; commit `[НЕВІДОМО]`.
- **Статус:** READY. Каталогізовано; активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-0` (загальні правила)

### filesystem-context
- **Шлях:** `SKILLS/context-engineering/selected/filesystem-context/` · **Версія:** 1.2.0 (у блоці «Skill Metadata» наприкінці `SKILL.md`)
- **Опис:** Файлова система як зовнішня пам'ять: чернетки, винесення великих результатів, обмін файлами між сесіями.
- **Застосування:** Основа нашої моделі, де працівники передають результати через файли репозиторію.
- **Рекомендовані ролі:** Operations Director (корисний усім).
- **Залежності:** немає обов'язкових.
- **Файли:** `references/implementation-patterns.md`, `scripts/filesystem_context.py`.
- **Ліцензія:** MIT, підтверджена: локальний `SKILLS/context-engineering/LICENSE`; репозиторій на GitHub теж MIT (2026-11-15).
- **Джерело:** https://github.com/muratcankoylan/Agent-Skills-for-Context-Engineering; ім'я Skill є в upstream; збіг змісту з upstream не перевірявся; commit `[НЕВІДОМО]`.
- **Статус:** READY. Каталогізовано; активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-0` (загальні правила)

### memory-systems
- **Шлях:** `SKILLS/memory-systems/` · **Версія:** 4.1.0 (у блоці «Skill Metadata» наприкінці `SKILL.md`)
- **Опис:** Проєктування довготривалої пам'яті агентів: сутності, граф знань, векторний пошук, консолідація.
- **Застосування:** Лише для майбутнього проєктування пам'яті. У поточній file-based моделі потреби немає.
- **Рекомендовані ролі:** Operations Director.
- **Залежності:** `scripts/memory_store.py` імпортує `numpy` (єдина реальна нестандартна залежність у бібліотеці; не встановлювалась; для читання інструкції не потрібна). Інструкція згадує фреймворки пам'яті (Mem0, Zep, Letta, Cognee) як приклади, їх підключати не потрібно.
- **Файли:** `references/implementation.md`, `scripts/memory_store.py`.
- **Ліцензія:** MIT на рівні репозиторію (GitHub, 2026-11-15); власного `LICENSE` у папці немає, застосовується ліцензія того самого репозиторію (текст: `SKILLS/context-engineering/LICENSE`).
- **Джерело:** https://github.com/muratcankoylan/Agent-Skills-for-Context-Engineering; збіг із upstream підтверджено частково (опис дослівний, 229 рядків, версія 4.1.0); commit `[НЕВІДОМО]`.
- **Статус:** READY. Каталогізовано; активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-0` (загальні правила)

## AI Development

### multi-agent-patterns
- **Шлях:** `SKILLS/context-engineering/selected/multi-agent-patterns/` · **Версія:** 2.1.0 (у блоці «Skill Metadata» наприкінці `SKILL.md`)
- **Опис:** Патерни мультиагентних систем: ізоляція контексту, супервізор, передачі, коли кілька агентів виправдані.
- **Застосування:** Розподіл роботи Director між спеціалістами; рішення «чи потрібен окремий працівник».
- **Рекомендовані ролі:** Operations Director.
- **Залежності:** немає обов'язкових (`scripts/coordination.py`, стандартна бібліотека).
- **Файли:** `references/frameworks.md`, `scripts/coordination.py`.
- **Ліцензія:** MIT, підтверджена: локальний `SKILLS/context-engineering/LICENSE`; репозиторій на GitHub теж MIT (2026-11-15).
- **Джерело:** https://github.com/muratcankoylan/Agent-Skills-for-Context-Engineering; ім'я Skill є в upstream; збіг змісту з upstream не перевірявся; commit `[НЕВІДОМО]`.
- **Статус:** READY. Каталогізовано; активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-0` (загальні правила)

### long-horizon-prompting
- **Шлях:** `SKILLS/context-engineering/selected/long-horizon-prompting/` · **Версія:** 1.1.0 (у блоці «Skill Metadata» наприкінці `SKILL.md`)
- **Опис:** Написання стартового промпта для довгої автономної роботи: умова успіху, результати, що не рахуються, правила зупинки.
- **Застосування:** Лише для складних дослідницьких завдань. У нашій моделі автономних довгих запусків немає, тож використовувати як довідку.
- **Рекомендовані ролі:** Operations Director.
- **Залежності:** немає. Описує паралельних агентів і ресурсомісткі запуски, що потребують окремого погодження.
- **Файли:** `references/` (5 файлів: task-brief-template, mass-handoff-contracts, vendor-guidance, research-evidence, cdc-prompt-annotated).
- **Ліцензія:** MIT, підтверджена: локальний `SKILLS/context-engineering/LICENSE`; репозиторій на GitHub теж MIT (2026-11-15). Сторонні матеріали в `references/` (промпт OpenAI, робота Lee та ін.): UNKNOWN.
- **Джерело:** https://github.com/muratcankoylan/Agent-Skills-for-Context-Engineering; ім'я Skill є в upstream; збіг змісту з upstream не перевірявся; commit `[НЕВІДОМО]`.
- **Статус:** READY WITH OVERLAY. Каталогізовано; активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-LH` (`../LIBRARY/skills/OVERLAYS.md`; на погодженні CEO)

### project-development
- **Шлях:** `SKILLS/project-development/` · **Версія:** 1.3.0 (у блоці «Skill Metadata» наприкінці `SKILL.md`)
- **Опис:** Рішення на рівні проєкту: чи підходить LLM для задачі, форма пайплайна, оцінка вартості токенів, ітерації.
- **Застосування:** Планування багатокрокових завдань і оцінка їхньої вартості.
- **Рекомендовані ролі:** Operations Director, Growth Manager.
- **Залежності:** немає обов'язкових. `scripts/pipeline_template.py` на стандартній бібліотеці. Згадує API-ключі як частину інфраструктури проєкту.
- **Файли:** `references/case-studies.md`, `references/pipeline-patterns.md`, `scripts/pipeline_template.py`.
- **Ліцензія:** MIT на рівні репозиторію (GitHub, 2026-11-15); власного `LICENSE` у папці немає, застосовується ліцензія того самого репозиторію (текст: `SKILLS/context-engineering/LICENSE`).
- **Джерело:** https://github.com/muratcankoylan/Agent-Skills-for-Context-Engineering; ім'я Skill є в upstream; збіг змісту з upstream не перевірявся; commit `[НЕВІДОМО]`.
- **Статус:** READY. Каталогізовано; активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-0` (загальні правила)

### tool-design
- **Шлях:** `SKILLS/tool-design/` · **Версія:** 2.2.0 (у блоці «Skill Metadata» наприкінці `SKILL.md`)
- **Опис:** Проєктування інструментів для агентів: описи, схеми, повідомлення про помилки, дизайн MCP-серверів.
- **Застосування:** Лише якщо колись проєктуватимемо власні інструменти. Зараз не потрібен.
- **Рекомендовані ролі:** Operations Director.
- **Залежності:** немає обов'язкових. Згадує MCP як тему, підключення не вимагає.
- **Файли:** `references/architectural_reduction.md`, `references/best_practices.md`, `scripts/description_generator.py`.
- **Ліцензія:** MIT на рівні репозиторію (GitHub, 2026-11-15); власного `LICENSE` у папці немає, застосовується ліцензія того самого репозиторію (текст: `SKILLS/context-engineering/LICENSE`).
- **Джерело:** https://github.com/muratcankoylan/Agent-Skills-for-Context-Engineering; ім'я Skill є в upstream; збіг змісту з upstream не перевірявся; commit `[НЕВІДОМО]`.
- **Статус:** READY. Каталогізовано; активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-0` (загальні правила)

### evaluation
- **Шлях:** `SKILLS/context-engineering/selected/evaluation/` · **Версія:** 1.2.0 (у блоці «Skill Metadata» наприкінці `SKILL.md`)
- **Опис:** Оцінювання роботи агентів: детерміновані перевірки, регресійні набори, рубрики, контроль якості.
- **Застосування:** Систематична перевірка результатів працівників.
- **Рекомендовані ролі:** Operations Director.
- **Залежності:** немає обов'язкових.
- **Файли:** `references/metrics.md`, `scripts/evaluator.py`.
- **Ліцензія:** MIT, підтверджена: локальний `SKILLS/context-engineering/LICENSE`; репозиторій на GitHub теж MIT (2026-11-15).
- **Джерело:** https://github.com/muratcankoylan/Agent-Skills-for-Context-Engineering; ім'я Skill є в upstream; збіг змісту з upstream не перевірявся; commit `[НЕВІДОМО]`.
- **Статус:** READY. Каталогізовано; активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-0` (загальні правила)

### advanced-evaluation
- **Шлях:** `SKILLS/advanced-evaluation/` · **Версія:** 2.1.0 (у блоці «Skill Metadata» наприкінці `SKILL.md`)
- **Опис:** Оцінювання за допомогою LLM-суддів: пряма оцінка, попарне порівняння, калібрування рубрик, боротьба з упередженістю.
- **Застосування:** Вибрати найкращий із кількох варіантів (тексти, креативи) за єдиною рубрикою.
- **Рекомендовані ролі:** Operations Director, Creative Director.
- **Залежності:** немає обов'язкових (`scripts/evaluation_example.py` на стандартній бібліотеці).
- **Файли:** `references/` (4 файли), `scripts/evaluation_example.py`.
- **Ліцензія:** MIT на рівні репозиторію (GitHub, 2026-11-15); власного `LICENSE` у папці немає, застосовується ліцензія того самого репозиторію (текст: `SKILLS/context-engineering/LICENSE`).
- **Джерело:** https://github.com/muratcankoylan/Agent-Skills-for-Context-Engineering; ім'я Skill є в upstream; збіг змісту з upstream не перевірявся; commit `[НЕВІДОМО]`.
- **Статус:** READY. Каталогізовано; активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-0` (загальні правила)

## Strategy

### marketing-plan
- **Шлях:** `SKILLS/marketing-plan/` · **Версія:** 1.2.5 (`metadata.version`)
- **Опис:** Повний 12-місячний маркетинговий план за структурою AARRR: канали, бюджет, команда, цілі, розмір ринку.
- **Застосування:** Стартовий план просування бізнесу або перегляд пріоритетів. Орієнтований на SaaS і консалтинг (fCMO), для товарного бізнесу потребує адаптації.
- **Рекомендовані ролі:** Growth Manager, Operations Director, Creative Director.
- **Залежності:** немає обов'язкових. Згадує Notion, MCP, GA4, Mixpanel; план виходить як markdown-документ.
- **Файли:** `references/` (14 файлів), `evals/evals.json`. Описує зв'язок з іншими Skills, яких у бібліотеці немає (див. «Відомі обмеження» і `../REPORTS/skills-deep-audit.md`, розд. 4.3).
- **Ліцензія:** MIT на рівні репозиторію (GitHub, 2026-11-15); власного `LICENSE` у папці немає, застосовується ліцензія того самого репозиторію (текст: `SKILLS/marketing/LICENSE`). Уривки з книги *Founding Marketing* у `references/`: UNKNOWN.
- **Джерело:** https://github.com/coreyhaines31/marketingskills; ім'я Skill є в upstream; збіг змісту з upstream не перевірявся; commit `[НЕВІДОМО]`.
- **Статус:** READY WITH OVERLAY. Каталогізовано; активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-MP` (`../LIBRARY/skills/OVERLAYS.md`; на погодженні CEO)
- **Власник каталогу `{WORKSPACE}/marketing-plans/` і процесу:** Growth Manager. Marketing Plan це аналітика й рекомендації, а не дозвіл виконувати кампанії.
- **Адаптація (OV-MP):** шлях `~/marketing-plans/` замінено на `{WORKSPACE}/marketing-plans/<slug>/` бізнесу; посилання на відсутні Skills необов'язкові; зовнішні публікації, платні інтеграції й самостійні зовнішні дії заборонені.

### product-marketing
- **Шлях:** `SKILLS/marketing/selected/product-marketing/` · **Версія:** 2.2.3 (`metadata.version`)
- **Опис:** Створення й підтримка документа з маркетинговим контекстом: продукт, ЦА, позиціонування, мова клієнтів, голос бренду.
- **Застосування:** Базовий контекст для інших маркетингових Skills. Каталог за замовчуванням зберігає його в `.agents/product-marketing.md`; у нас цю роль виконує `PRODUCT_CONTEXT` бізнесу (див. `marketing/ADAPTATION.md`).
- **Рекомендовані ролі:** Product Researcher, Creative Director, Sales Manager, Growth Manager, Store Builder.
- **Залежності:** немає.
- **Файли:** `references/brand-voice.md`, `evals/evals.json`.
- **Ліцензія:** MIT, підтверджена: локальний `SKILLS/marketing/LICENSE`; репозиторій на GitHub теж MIT (2026-11-15). Адаптовані фрагменти (Wispr Flow): за примітками MIT, не перевірено.
- **Джерело:** https://github.com/coreyhaines31/marketingskills; ім'я Skill є в upstream; збіг змісту з upstream не перевірявся; commit `[НЕВІДОМО]`.
- **Статус:** READY WITH OVERLAY. Каталогізовано; активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-PM` (`../LIBRARY/skills/OVERLAYS.md`; на погодженні CEO)

### pricing
- **Шлях:** `SKILLS/pricing/` · **Версія:** 2.1.7 (`metadata.version`)
- **Опис:** Ціноутворення і пакетування: тарифи, цінові метрики, дослідження готовності платити, підвищення цін.
- **Застосування:** Перегляд цін і умов продажу. Орієнтований на SaaS; для товарного бізнесу застосовувати лише ідеї про цінність і тестування, а розрахунок прибутку вести за `../SOPS/profit-calculation.md`.
- **Рекомендовані ролі:** Growth Manager, Sales Manager, Product Researcher, Store Builder.
- **Залежності:** немає. Згадує Notion, HubSpot.
- **Файли:** `references/` (4 файли), `evals/evals.json`.
- **Ліцензія:** MIT на рівні репозиторію (GitHub, 2026-11-15); власного `LICENSE` у папці немає, застосовується ліцензія того самого репозиторію (текст: `SKILLS/marketing/LICENSE`).
- **Джерело:** https://github.com/coreyhaines31/marketingskills; ім'я Skill є в upstream; збіг змісту з upstream не перевірявся; commit `[НЕВІДОМО]`.
- **Статус:** READY. Каталогізовано; активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-0` (загальні правила)

### offers
- **Шлях:** `SKILLS/offers/` · **Версія:** 1.0.6 (`metadata.version`)
- **Опис:** Проєктування пропозиції: стекінг цінності, бонуси, гарантії, дефіцит, оплата частинами, апсели.
- **Застосування:** Коли товар не продається через слабку пропозицію, а не через текст. За описом найкраще для послуг і високого чека, для масового товару частково.
- **Рекомендовані ролі:** Sales Manager, Growth Manager, Creative Director.
- **Залежності:** немає.
- **Файли:** 9 допоміжних файлів (references, evals).
- **Ліцензія:** MIT на рівні репозиторію (GitHub, 2026-11-15); власного `LICENSE` у папці немає, застосовується ліцензія того самого репозиторію (текст: `SKILLS/marketing/LICENSE`).
- **Джерело:** https://github.com/coreyhaines31/marketingskills; ім'я Skill є в upstream; збіг змісту з upstream не перевірявся; commit `[НЕВІДОМО]`.
- **Статус:** READY. Каталогізовано; активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-0` (загальні правила)

## Research

### customer-research
- **Шлях:** `SKILLS/marketing/selected/customer-research/` · **Версія:** 2.0.8 (`metadata.version`)
- **Опис:** Дослідження клієнтів: аналіз відгуків і інтерв'ю, пошук у відкритих джерелах, персони, JTBD.
- **Застосування:** Зрозуміти реальні потреби й мову покупців.
- **Рекомендовані ролі:** Product Researcher, Sales Manager, Growth Manager, Creative Director.
- **Залежності:** немає. Попереджає, що тексти відгуків це недовірені дані.
- **Файли:** `references/interviews-and-surveys.md`, `references/source-guides.md`, `evals/evals.json`.
- **Ліцензія:** MIT, підтверджена: локальний `SKILLS/marketing/LICENSE`; репозиторій на GitHub теж MIT (2026-11-15).
- **Джерело:** https://github.com/coreyhaines31/marketingskills; ім'я Skill є в upstream; збіг змісту з upstream не перевірявся; commit `[НЕВІДОМО]`.
- **Статус:** READY. Каталогізовано; активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-0` (загальні правила)

### competitor-profiling
- **Шлях:** `SKILLS/marketing/selected/competitor-profiling/` · **Версія:** 2.1.8 (`metadata.version`)
- **Опис:** Датовані профілі конкурентів: позиціонування, ціни, функції, відгуки, SEO; факти окремо від висновків.
- **Застосування:** Аналіз конкурентів із публічних джерел.
- **Рекомендовані ролі:** Product Researcher, Growth Manager, Ads Manager.
- **Залежності:** згадує MCP та платні SEO/скрепінг-інструменти. Не підключати без погодження CEO; користуватися публічними сторінками.
- **Файли:** `references/templates.md`, `references/tool-reference.md`, `evals/evals.json`.
- **Ліцензія:** MIT, підтверджена: локальний `SKILLS/marketing/LICENSE`; репозиторій на GitHub теж MIT (2026-11-15).
- **Джерело:** https://github.com/coreyhaines31/marketingskills; ім'я Skill є в upstream; збіг змісту з upstream не перевірявся; commit `[НЕВІДОМО]`.
- **Статус:** READY WITH OVERLAY. Каталогізовано; активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-CP` (`../LIBRARY/skills/OVERLAYS.md`; на погодженні CEO)

## Marketing

### ad-creative
- **Шлях:** `SKILLS/marketing/selected/ad-creative/` · **Версія:** 2.13.0 (`metadata.version`)
- **Опис:** Рекламні тексти й концепції: заголовки, основні тексти, хуки, кути, ітерації за результатами.
- **Застосування:** Підготувати локальні матеріали для реклами. Завантаження в рекламні кабінети виконує лише CEO.
- **Рекомендовані ролі:** Creative Director, Ads Manager.
- **Залежності:** згадує генеративні інструменти, Remotion, Veo, OAuth і рекламні кабінети; жодних не підключати. Є HTML-шаблон огляду.
- **Файли:** `assets/creative-review-template.html`, `references/` (11 файлів), `evals/evals.json`.
- **Ліцензія:** MIT, підтверджена: локальний `SKILLS/marketing/LICENSE`; репозиторій на GitHub теж MIT (2026-11-15).
- **Джерело:** https://github.com/coreyhaines31/marketingskills; ім'я Skill є в upstream; збіг змісту з upstream не перевірявся; commit `[НЕВІДОМО]`.
- **Статус:** READY WITH OVERLAY. Каталогізовано; активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-AC` (`../LIBRARY/skills/OVERLAYS.md`; на погодженні CEO)

### cro
- **Шлях:** `SKILLS/cro/` · **Версія:** 2.0.6 (`metadata.version`)
- **Опис:** Оптимізація конверсії сторінок і форм: що змінити першим, ідеї експериментів за типами сторінок.
- **Застосування:** Аналіз сторінок і карток товару магазину.
- **Рекомендовані ролі:** Store Builder, Growth Manager, Ads Manager.
- **Залежності:** немає. Посилається на Skills `signup`, `onboarding`, `popups`, `ab-testing`, яких у бібліотеці немає.
- **Файли:** `references/experiments.md`, `references/form.md`, `evals/evals.json`.
- **Ліцензія:** MIT на рівні репозиторію (GitHub, 2026-11-15); власного `LICENSE` у папці немає, застосовується ліцензія того самого репозиторію (текст: `SKILLS/marketing/LICENSE`).
- **Джерело:** https://github.com/coreyhaines31/marketingskills; ім'я Skill є в upstream; збіг змісту з upstream не перевірявся; commit `[НЕВІДОМО]`.
- **Статус:** READY. Каталогізовано; активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-0` (загальні правила)

## Content

### copywriting
- **Шлях:** `SKILLS/marketing/selected/copywriting/` · **Версія:** 2.3.5 (`metadata.version`)
- **Опис:** Написання й переписування текстів сторінок (головна, лендінг, ціни, опис функцій) із перевіркою тверджень.
- **Застосування:** Тексти магазину й лендингів. Українську мову та стиль задає `../SOPS/ukrainian-copywriting-style.md`, оригінал англомовний.
- **Рекомендовані ролі:** Creative Director, Store Builder, Sales Manager.
- **Залежності:** немає.
- **Файли:** `references/ai-tells.md`, `references/copy-frameworks.md`, `references/natural-transitions.md`, `evals/evals.json`.
- **Ліцензія:** MIT, підтверджена: локальний `SKILLS/marketing/LICENSE`; репозиторій на GitHub теж MIT (2026-11-15). Адаптовані фрагменти (Profound, Wispr Flow, Academic Phrasebank): частина UNKNOWN.
- **Джерело:** https://github.com/coreyhaines31/marketingskills; ім'я Skill є в upstream; збіг змісту з upstream не перевірявся; commit `[НЕВІДОМО]`.
- **Статус:** READY WITH OVERLAY. Каталогізовано; активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-CW` (`../LIBRARY/skills/OVERLAYS.md`; на погодженні CEO)

### copy-editing
- **Шлях:** `SKILLS/copy-editing/` · **Версія:** 2.2.4 (`metadata.version`)
- **Опис:** Редагування готових текстів: сім проходів, вичитування, оновлення контенту, прибирання «ШІ-ознак».
- **Застосування:** Вичитка текстів і звітів перед передачею CEO. Правила «ШІ-ознак» розраховані на англійську.
- **Рекомендовані ролі:** Creative Director, Store Builder, Sales Manager, Operations Director.
- **Залежності:** немає.
- **Файли:** `references/checklist.md`, `references/content-refresh.md`, `references/plain-english-alternatives.md`, `evals/evals.json`.
- **Ліцензія:** MIT на рівні репозиторію (GitHub, 2026-11-15); власного `LICENSE` у папці немає, застосовується ліцензія того самого репозиторію (текст: `SKILLS/marketing/LICENSE`). Адаптовані фрагменти (Profound, Wispr Flow): за примітками MIT, не перевірено.
- **Джерело:** https://github.com/coreyhaines31/marketingskills; ім'я Skill є в upstream; збіг змісту з upstream не перевірявся; commit `[НЕВІДОМО]`.
- **Статус:** READY WITH OVERLAY. Каталогізовано; активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-CW` (`../LIBRARY/skills/OVERLAYS.md`; на погодженні CEO)

### content-strategy
- **Шлях:** `SKILLS/content-strategy/` · **Версія:** 2.1.8 (`metadata.version`)
- **Опис:** Планування контенту: тематичні кластери, редакційний календар, пріоритизація тем під пошук і клієнтів.
- **Застосування:** Контент-план магазину й блогу.
- **Рекомендовані ролі:** Creative Director, Growth Manager, Store Builder.
- **Залежності:** немає. Посилається на `seo-audit`, якого в бібліотеці немає.
- **Файли:** `references/content-distribution.md`, `references/headless-cms.md`, `evals/evals.json`.
- **Ліцензія:** MIT на рівні репозиторію (GitHub, 2026-11-15); власного `LICENSE` у папці немає, застосовується ліцензія того самого репозиторію (текст: `SKILLS/marketing/LICENSE`).
- **Джерело:** https://github.com/coreyhaines31/marketingskills; ім'я Skill є в upstream; збіг змісту з upstream не перевірявся; commit `[НЕВІДОМО]`.
- **Статус:** READY. Каталогізовано; активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-0` (загальні правила)

### social
- **Шлях:** `SKILLS/social/` · **Версія:** 2.5.2 (`metadata.version`)
- **Опис:** Органічний контент для LinkedIn, X, Instagram, TikTok, Facebook: пости, каруселі, сценарії коротких відео, календарі.
- **Застосування:** Готувати тексти і календар. Публікує CEO.
- **Рекомендовані ролі:** Creative Director, Growth Manager.
- **Залежності:** згадує планувальники й `curl`-рецепти для Reddit, Hacker News, Bluesky (у `references/listening.md`); не запускати без погодження CEO. Не орієнтований на український ринок.
- **Файли:** `references/` (10 файлів), `evals/evals.json`.
- **Ліцензія:** MIT на рівні репозиторію (GitHub, 2026-11-15); власного `LICENSE` у папці немає, застосовується ліцензія того самого репозиторію (текст: `SKILLS/marketing/LICENSE`).
- **Джерело:** https://github.com/coreyhaines31/marketingskills; ім'я Skill є в upstream; збіг змісту з upstream не перевірявся; commit `[НЕВІДОМО]`.
- **Статус:** READY WITH OVERLAY. Каталогізовано; активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-PUB` (`../LIBRARY/skills/OVERLAYS.md`; на погодженні CEO)

### video
- **Шлях:** `SKILLS/video/` · **Версія:** 2.4.3 (`metadata.version`)
- **Опис:** Створення відео: демо, AI-генерація (Veo, Sora), AI-аватари (HeyGen), програмне відео (Remotion, HyperFrames).
- **Застосування:** Сценарії й структура відео. Генерація через зовнішні сервіси та встановлення CLI заборонені без погодження CEO.
- **Рекомендовані ролі:** Creative Director.
- **Залежності:** потребує зовнішніх платних сервісів і `npx` (приклади `npx hyperframes ...`) для повної роботи. Нічого не встановлювалось. Питає про наявність API-ключів.
- **Файли:** `references/` (4 файли), `evals/evals.json`.
- **Ліцензія:** MIT на рівні репозиторію (GitHub, 2026-11-15); власного `LICENSE` у папці немає, застосовується ліцензія того самого репозиторію (текст: `SKILLS/marketing/LICENSE`).
- **Джерело:** https://github.com/coreyhaines31/marketingskills; ім'я Skill є в upstream; збіг змісту з upstream не перевірявся; commit `[НЕВІДОМО]`.
- **Статус:** READY WITH OVERLAY. Каталогізовано; активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-VID` (`../LIBRARY/skills/OVERLAYS.md`; на погодженні CEO)

## Sales

### prospecting
- **Шлях:** `SKILLS/prospecting/` · **Версія:** 1.5.3 (`metadata.version`)
- **Опис:** Пошук і кваліфікація потенційних клієнтів: сигнали купівлі, збагачення, верифікація, дослідження акаунтів.
- **Застосування:** Складання списків потенційних клієнтів (B2B, місцевий бізнес). Підходить Raznobyt; для дропшипінгу малозастосовний. Контакт із клієнтами здійснює тільки CEO; персональні дані (К3) не зберігати.
- **Рекомендовані ролі:** Sales Manager, Growth Manager, Supplier Manager (пошук контрагентів, потребує оцінки).
- **Бізнеси:** основна рекомендація для B2B (Raznobyt); можливе використання в інших бізнесах за доречності; жодного обмеження доступу для Dropshipping.
- **Залежності:** згадує Apollo, Clay, Hunter, Sales Navigator, MCP. Усі платні/зовнішні, не підключати.
- **Файли:** `references/` (10 файлів), `evals/evals.json`.
- **Ліцензія:** MIT на рівні репозиторію (GitHub, 2026-11-15); власного `LICENSE` у папці немає, застосовується ліцензія того самого репозиторію (текст: `SKILLS/marketing/LICENSE`).
- **Джерело:** https://github.com/coreyhaines31/marketingskills; ім'я Skill є в upstream; збіг змісту з upstream не перевірявся; commit `[НЕВІДОМО]`.
- **Статус:** READY WITH OVERLAY. Каталогізовано; активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-OUT` (`../LIBRARY/skills/OVERLAYS.md`; на погодженні CEO)

### cold-email
- **Шлях:** `SKILLS/cold-email/` · **Версія:** 2.2.4 (`metadata.version`)
- **Опис:** B2B-холодні листи й follow-up: теми, послідовності, домени для відправки, доставлюваність, обробка відповідей.
- **Застосування:** Готувати текст листів. Відправку та налаштування доменів виконує CEO.
- **Рекомендовані ролі:** Sales Manager, Supplier Manager (тексти для постачальників; готує текст, надсилає CEO).
- **Бізнеси:** основна рекомендація для B2B (Raznobyt); можливе використання в інших бізнесах за доречності; жодного обмеження доступу для Dropshipping.
- **Залежності:** згадує Instantly, Hunter, HubSpot, LinkedIn, webhooks. Не підключати.
- **Файли:** `references/` (10 файлів), `evals/evals.json`.
- **Ліцензія:** MIT на рівні репозиторію (GitHub, 2026-11-15); власного `LICENSE` у папці немає, застосовується ліцензія того самого репозиторію (текст: `SKILLS/marketing/LICENSE`).
- **Джерело:** https://github.com/coreyhaines31/marketingskills; ім'я Skill є в upstream; збіг змісту з upstream не перевірявся; commit `[НЕВІДОМО]`.
- **Статус:** READY WITH OVERLAY. Каталогізовано; активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-OUT` (`../LIBRARY/skills/OVERLAYS.md`; на погодженні CEO)

### sales-enablement
- **Шлях:** `SKILLS/sales-enablement/` · **Версія:** 2.4.3 (`metadata.version`)
- **Опис:** Матеріали для продажів: презентації, односторінкові, робота із запереченнями, демо-скрипти, battle cards, пропозиції.
- **Застосування:** Скрипти й матеріали для переговорів і заперечень.
- **Рекомендовані ролі:** Sales Manager, Creative Director.
- **Бізнеси:** основна рекомендація для B2B (Raznobyt); можливе використання в інших бізнесах за доречності; жодного обмеження доступу для Dropshipping.
- **Залежності:** немає. Орієнтований на B2B SaaS.
- **Файли:** `references/` (6 файлів), `evals/evals.json`.
- **Ліцензія:** MIT на рівні репозиторію (GitHub, 2026-11-15); власного `LICENSE` у папці немає, застосовується ліцензія того самого репозиторію (текст: `SKILLS/marketing/LICENSE`).
- **Джерело:** https://github.com/coreyhaines31/marketingskills; ім'я Skill є в upstream; збіг змісту з upstream не перевірявся; commit `[НЕВІДОМО]`.
- **Статус:** READY WITH OVERLAY. Каталогізовано; активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-OUT` (`../LIBRARY/skills/OVERLAYS.md`; на погодженні CEO)

## Operations

### revops
- **Шлях:** `SKILLS/revops/` · **Версія:** 2.2.4 (`metadata.version`)
- **Опис:** Операції доходу: стадії життєвого циклу, MQL/SQL, скоринг, маршрутизація, воронка, автоматизація CRM.
- **Застосування:** Якщо з'явиться CRM або структурована воронка (наприклад, у Raznobyt). Рішення про CRM поки не прийняте.
- **Рекомендовані ролі:** Sales Manager, Growth Manager, Operations Director.
- **Бізнеси:** основна рекомендація для B2B (Raznobyt); можливе використання в інших бізнесах за доречності; жодного обмеження доступу для Dropshipping.
- **Залежності:** згадує Salesforce, HubSpot, Apollo, Clay, Zapier, MCP. Не підключати.
- **Файли:** `references/` (5 файлів), `evals/evals.json`.
- **Ліцензія:** MIT на рівні репозиторію (GitHub, 2026-11-15); власного `LICENSE` у папці немає, застосовується ліцензія того самого репозиторію (текст: `SKILLS/marketing/LICENSE`).
- **Джерело:** https://github.com/coreyhaines31/marketingskills; ім'я Skill є в upstream; збіг змісту з upstream не перевірявся; commit `[НЕВІДОМО]`.
- **Статус:** READY WITH OVERLAY. Каталогізовано; активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-OUT` (`../LIBRARY/skills/OVERLAYS.md`; на погодженні CEO)

## Analytics

### analytics
- **Шлях:** `SKILLS/marketing/selected/analytics/` · **Версія:** 2.2.5 (`metadata.version`)
- **Опис:** Налаштування й аудит аналітики: план відстеження, події, GA4, GTM, UTM, правильний розрахунок метрик.
- **Застосування:** Визначити, що вимірювати; перевірити розрахунок метрик. Налаштування в сервісах виконує CEO.
- **Рекомендовані ролі:** Growth Manager, Ads Manager, Store Builder.
- **Залежності:** згадує GA4, GTM, Mixpanel, PostHog; не підключати.
- **Файли:** `references/event-library.md`, `references/ga4-implementation.md`, `references/gtm-implementation.md`, `evals/evals.json`.
- **Ліцензія:** MIT, підтверджена: локальний `SKILLS/marketing/LICENSE`; репозиторій на GitHub теж MIT (2026-11-15). Адаптований фрагмент (Wispr Flow, за приміткою MIT): не перевірено.
- **Джерело:** https://github.com/coreyhaines31/marketingskills; ім'я Skill є в upstream; збіг змісту з upstream не перевірявся; commit `[НЕВІДОМО]`.
- **Статус:** READY WITH OVERLAY. Каталогізовано; активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** `OV-AN` (`../LIBRARY/skills/OVERLAYS.md`; на погодженні CEO)

## Design & UX

### ui-ux-pro-max
- **Шлях:** `SKILLS/ui-ux-pro-max/` · **Версія:** не вказана (ні у frontmatter, ні в репозиторії)
- **Опис:** Дизайн-інтелект для UI: пошук стилів, палітр, шрифтових пар, UX-правил, іконок, типів графіків, стеків технологій.
- **Застосування:** Дизайн магазину й лендингів перед розробкою.
- **Рекомендовані ролі:** Store Builder, Creative Director.
- **Залежності:** `scripts/search.py` та інші Python-скрипти використовують стандартну бібліотеку; CLI (`npm`, `uipro`) із `INSTALL.md` не виконувався. Сумісність із Cowork `[НЕВІДОМО]`.
- **Файли:** `data/` (CSV, JSON, 22 файли стеків), `references/` (2), `scripts/` (5 + тести), `INSTALL.md`, `source-reference.md`. Усього 76 допоміжних файлів.
- **Ліцензія:** MIT для Skill за сторінкою репозиторію (GitHub, 2026-11-15); текст `LICENSE` і власник авторських прав локально відсутні `[НЕВІДОМО]`. Ліцензії компонентів даних (шрифти, іконки Phosphor) не підтверджені: UNKNOWN.
- **Джерело:** https://github.com/nextlevelbuilder/ui-ux-pro-max-skill; commit `[НЕВІДОМО]`; версія в Skill не вказана.
- **Статус:** NEEDS REVIEW. Каталогізовано; активація в Cowork і Claude Code: NOT TESTED.
- **Overlay:** окремого не передбачено; спершу умови зняття NEEDS REVIEW (нижче), загальні правила `OV-0`
- **Умови зняття NEEDS REVIEW** (не включати до затвердженого релізу, доки не виконано): (1) перевірено ліцензії компонентів і даних (шрифти, іконки Phosphor); (2) уточнено походження сторонніх матеріалів; (3) виправлено застарілі `INSTALL.md` і `source-reference.md` (виконано 2026-11-15 лише в межах правдивого опису стану); (4) перевірено шлях `${CLAUDE_PLUGIN_ROOT}/.claude/skills/ui-ux-pro-max/scripts/search.py` для нашого середовища. Skill і допоміжні файли не видаляються.

---

---

## Відомі обмеження

1. **Походження копій.** Для 18 «плоских» Skills збіг із upstream встановлено за назвою (для `memory-systems` також за змістом). Точний commit невідомий: його треба отримати на машині CEO (`git ls-remote`) і записати в `SOURCES.md` з датою.
2. **Локальні `LICENSE` для «плоских» Skills.** Власних копій у їхніх папках немає; ліцензійні повідомлення зібрані в `SOURCES.md`. Додавання копій у кожну папку потребує рішення CEO.
3. **Сторонні матеріали зі статусом UNKNOWN:** матеріали OpenAI та дослідницької роботи в `long-horizon-prompting`; уривки з книги в `marketing-plan`; Academic Phrasebank у `copywriting`; компоненти даних `ui-ux-pro-max` (іконки Phosphor, кожен шрифт).
4. **Орієнтація на SaaS і англійську.** Більшість Skills Marketing/Sales написані для SaaS. Для фізичних товарів в Україні (післяплата, доставка, повернення) і для B2B-опту потрібна адаптація через Business Profile та `marketing/ADAPTATION.md`; вона ще не розширена.
5. **Посилання на Skills, яких немає в бібліотеці,** необов'язкові (перелік у `../REPORTS/skills-deep-audit.md`, розд. 4.3).
6. **Cowork і Claude Code:** активація й читання Skills не тестувались; статус `NOT TESTED` для всіх 31 (перелік тестів у `README.md`).
7. **Два каталоги.** `SKILLS/CATALOG.md` це актуальний каталог усіх 44 Skill. `../LIBRARY/skills/CATALOG.md` замінено повідомленням про тимчасовий застарілий каталог; після окремо погодженої міграції структури офіційний каталог буде перенесений до `LIBRARY/skills/CATALOG.md`.
