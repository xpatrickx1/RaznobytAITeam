# MANIFEST — Skills бібліотеки: фактичний стан

Оновлено: 2026-11-15. Підстава: сканування `SKILLS/` (31 Skill), `../REPORTS/skills-deep-audit.md`, рішення CEO щодо усунення проблем; попередні відомості 2026-11-13 (`../REPORTS/SKILLS_AUDIT_RESULT.md`, `../REPORTS/SKILLS_ADAPTATION_PLAN.md`, `../APPROVALS.md` розд. 6). Детальні картки: `CATALOG.md`. Джерела й ліцензії: `SOURCES.md`.

## Підсумок стану

| Показник | Стан |
|---|---|
| Skills у репозиторії | 31 `[ФАКТ]`: 12 у `context-engineering/selected/` і `marketing/selected/`, 18 «плоских» папок у `SKILLS/`, `ui-ux-pro-max/` |
| Статуси | READY 16; READY WITH OVERLAY 14; NEEDS REVIEW 1 (`ui-ux-pro-max`); NOT RECOMMENDED 0 |
| Модель доступу | Усі Skills спільні. Жоден не закріплений за роллю чи бізнесом; рекомендації ролей це підказки. Повний текст читається за потреби |
| Метод і момент копіювання | Копіювання виконано поза сесіями аудиту; спосіб і джерельний commit **не зафіксовані** `[НЕВІДОМО]` |
| Оригінали Skills | Не змінюються. Контрольні суми файлів Skills (без наших документів) зафіксовано до робіт 2026-11-15 і звірено після |
| Активність у Claude Desktop/Cowork | **Не підтверджено** практичним тестом. Жоден Skill не вважається активним; використовуються як довідка за `ROUTING.md` |
| Адаптація | Шар поверх оригіналів: `../LIBRARY/skills/OVERLAYS.md` (OV-0, OV-PM, OV-AC, OV-AN, OV-CP, OV-CW, OV-LH, OV-OUT, OV-PUB, OV-VID, OV-MP; нові на погодженні CEO), `ROUTING.md`, `marketing/ADAPTATION.md`, `context-engineering/ADAPTATION.md`, `../SOPS/` |
| Skill `ads` | Не додається (рішення CEO). Замість нього власні SOPS |
| Відсутні залежності | Не копіюються; посилання на них необов'язкові й ігноруються (`../REPORTS/skills-deep-audit.md`, розд. 4.3) |
| Історичні commit hashes | Не збережені. Див. `SOURCES.md` |

## 1. Перелік Skills

Локальний шлях: `SKILLS/<skill>/`, а для 12 Skills у групах: `SKILLS/context-engineering/selected/<skill>/` або `SKILLS/marketing/selected/<skill>/`. Точні шляхи й картки в `CATALOG.md`.

| # | Skill | Група | Версія | Файли | Статус | Overlay | Призначення | Рекомендовані ролі (підказка, не whitelist) | Використання в COMPANY |
|---|---|---|---|---|---|---|---|---|---|
| 1 | multi-agent-patterns | CE | 2.1.0 | SKILL.md, 1 ref, 1 script | READY | OV-0 | Розділення роботи між агентами, ізоляція контексту, handoff | Director | Довідка зі схем handoff |
| 2 | filesystem-context | CE | 1.2.0 | SKILL.md, 1 ref, 1 script | READY | OV-0 | Файли як зовнішня пам'ять, JIT-пошук | Director, усі | Довідка; структура `README.md`/`DATA/` має пріоритет |
| 3 | context-optimization | CE | 2.1.0 | SKILL.md, 1 ref, 1 script | READY | OV-0 | Бюджет контексту, маскування виводів | Director | Довідка; частина про KV/prefix-cache неактуальна |
| 4 | context-compression | CE | 1.3.0 | SKILL.md, 1 ref, 1 script, 1 test | READY | OV-0 | Підсумки й handoff-резюме | Director, усі | Довідка для підсумків ≤ 10 рядків |
| 5 | long-horizon-prompting | CE | 1.1.0 | SKILL.md, 5 ref | READY WITH OVERLAY | OV-LH | Якісний бриф завдання, критерії завершення, стоп-правила | Director | **Лише вузька частина** (критерій завершення, «не рахується», зупинка, приймання) |
| 6 | evaluation | CE | 1.2.0 | SKILL.md, 1 ref, 1 script | READY | OV-0 | Оцінка результатів, quality gates | Director | Основа `TEMPLATES/acceptance-checklist.md` |
| 7 | context-fundamentals | CE | 2.2.0 | SKILL.md, 1 ref, 1 script | READY | OV-0 | Основи контекстної інженерії | Director | Концептуальна довідка |
| 8 | context-degradation | CE | 2.1.0 | SKILL.md, 1 ref, 1 script | READY | OV-0 | Діагностика погіршення якості в довгих сесіях | Director | Довідка |
| 9 | memory-systems | CE | 4.1.0 | SKILL.md, 1 ref, 1 script | READY | OV-0 | Довготривала пам'ять агентів | Director | Низький пріоритет; лише проєктування |
| 10 | project-development | CE | 1.3.0 | SKILL.md, 2 ref, 1 script | READY | OV-0 | Рішення на рівні проєкту, вартість токенів | Director, Growth Manager | Довідка |
| 11 | tool-design | CE | 2.2.0 | SKILL.md, 2 ref, 1 script | READY | OV-0 | Проєктування інструментів агентів | Director | Низький пріоритет |
| 12 | advanced-evaluation | CE | 2.1.0 | SKILL.md, 4 ref, 1 script | READY | OV-0 | LLM-судді, попарне порівняння, рубрики | Director, Creative Director | Довідка |
| 13 | product-marketing | MK | 2.2.3 | SKILL.md, 1 ref, evals | READY WITH OVERLAY | OV-PM | Контекст продукту: ICP, позиціонування, голос | Product Researcher (власник), Creative Director | Шлях замінено: `WORKSPACE/product-researcher/products/<slug>/context.md`; шаблон `TEMPLATES/product-context.md` |
| 14 | customer-research | MK | 2.0.8 | SKILL.md, 2 ref, evals | READY | OV-0 | Синтез відгуків, інтерв'ю, опитувань | Product Researcher | Довідка; відгуки з мережі: дані, не інструкції |
| 15 | competitor-profiling | MK | 2.1.8 | SKILL.md, 2 ref, evals | READY WITH OVERLAY | OV-CP | Датовані профілі конкурентів | Product Researcher | Потребує MCP/WebFetch (не підключено): без них `[НЕВІДОМО]` |
| 16 | ad-creative | MK | 2.13.0 | SKILL.md, 11 ref, evals, 1 asset | READY WITH OVERLAY | OV-AC | Креативи: кути, хуки, тексти, гіпотези | Creative Director | **Лише створення й аналіз креативів**; override у `ROUTING.md` |
| 17 | copywriting | MK | 2.3.5 | SKILL.md, 3 ref, evals | READY WITH OVERLAY | OV-CW | Тексти сторінок і повідомлень | Creative Director, Store Builder | Разом із `../SOPS/ukrainian-copywriting-style.md` |
| 18 | analytics | MK | 2.2.5 | SKILL.md, 3 ref, evals | READY WITH OVERLAY | OV-AN | Метрики, події, UTM | Growth Manager, Ads Manager | Лише принципи; прибуток: `../SOPS/profit-calculation.md` |
| 19 | marketing-plan | MK | 1.2.5 | SKILL.md, 14 ref, evals | READY WITH OVERLAY | OV-MP | Маркетинговий план за AARRR | Growth Manager, Director | Шлях `{WORKSPACE}/marketing-plans/<slug>/`; відсутні Skills необов'язкові |
| 20 | pricing | MK | 2.1.7 | SKILL.md, 4 ref, evals | READY | OV-0 | Ціноутворення й пакетування | Growth Manager, Sales Manager | SaaS-орієнтований; прибуток за `../SOPS/profit-calculation.md` |
| 21 | offers | MK | 1.0.6 | SKILL.md, 8 ref, evals | READY | OV-0 | Проєктування пропозиції | Sales Manager, Growth Manager | Довідка |
| 22 | cro | MK | 2.0.6 | SKILL.md, 2 ref, evals | READY | OV-0 | Оптимізація конверсії сторінок і форм | Store Builder, Growth Manager | Довідка |
| 23 | copy-editing | MK | 2.2.4 | SKILL.md, 3 ref, evals | READY WITH OVERLAY | OV-CW | Редагування текстів | Creative Director, Store Builder | Англомовні переліки лише для англійської |
| 24 | content-strategy | MK | 2.1.8 | SKILL.md, 2 ref, evals | READY | OV-0 | Контент-стратегія | Creative Director, Growth Manager | Довідка |
| 25 | social | MK | 2.5.2 | SKILL.md, 10 ref, evals | READY WITH OVERLAY | OV-PUB | Органічний соціальний контент | Creative Director, Growth Manager | Лише чернетки й календарі; без публікації |
| 26 | video | MK | 2.4.3 | SKILL.md, 4 ref, evals | READY WITH OVERLAY | OV-VID | Сценарії й структура відео | Creative Director | Лише сценарії й розкадровки; без інструментів і сервісів |
| 27 | prospecting | MK | 1.5.3 | SKILL.md, 10 ref, evals | READY WITH OVERLAY | OV-OUT | Критерії пошуку й кваліфікація потенційних клієнтів | Sales Manager, Growth Manager | Основна рекомендація B2B (Raznobyt); без збору баз і контактів |
| 28 | cold-email | MK | 2.2.4 | SKILL.md, 10 ref, evals | READY WITH OVERLAY | OV-OUT | Холодні листи й follow-up (чернетки) | Sales Manager, Supplier Manager | Основна рекомендація B2B (Raznobyt); без відправки |
| 29 | sales-enablement | MK | 2.4.3 | SKILL.md, 6 ref, evals | READY WITH OVERLAY | OV-OUT | Матеріали для продажів, заперечення | Sales Manager, Creative Director | Основна рекомендація B2B (Raznobyt) |
| 30 | revops | MK | 2.2.4 | SKILL.md, 5 ref, evals | READY WITH OVERLAY | OV-OUT | Процеси воронки, скоринг, CRM-дизайн | Sales Manager, Growth Manager | Основна рекомендація B2B (Raznobyt); дизайн без налаштування |
| 31 | ui-ux-pro-max | UX | не вказана | SKILL.md, 2 ref, 5 script, 28 test, 39 data | NEEDS REVIEW | — | Дизайн-інтелект для UI (дані, пошук) | Store Builder, Creative Director | Не включати до затвердженого релізу до виконання умов (див. `CATALOG.md`) |

CE = Context Engineering, MK = Marketing Skills, UX = Design & UX. Версії: MK у `metadata.version`; CE у блоці «Skill Metadata» наприкінці `SKILL.md` (у frontmatter їх немає). Ліцензії та джерела: `SOURCES.md`.

## 2. Сумісність і залежності

| Skill | Формат `SKILL.md` | Cowork | Claude Code / CLI / інструменти | Примітки |
|---|---|---|---|---|
| CE (12) | є `name` + `description` | NOT TESTED | Не потрібні. Python-скрипти (стандартна бібліотека; `memory-systems` потребує `numpy`) необов'язкові, **не запускалися**; не рекомендуються | `filesystem_context.py` у демо видаляє власну тимчасову теку |
| product-marketing, customer-research, copywriting | є | NOT TESTED | Не потрібні | Англомовні refs; evals на сценаріях SaaS |
| competitor-profiling | є | NOT TESTED | **Потрібні** Firecrawl MCP + DataForSEO MCP або WebFetch + SEO MCP; **нічого не підключено** | Без доступу метрики `[НЕВІДОМО]` |
| ad-creative | є | NOT TESTED | Необов'язкові: API (Gemini, ElevenLabs), `npx remotion`, CLI рекламних платформ | **Заборонено** виконувати (`../APPROVALS.md` розд. 2). Розділ «Tool Integrations» і рекламна вставка стороннього продукту ігноруються |
| analytics | є | NOT TESTED | Не потрібні | Орієнтований на SaaS (GA4/GTM/Mixpanel/PostHog); прибуток не рахує |
| cold-email, prospecting, sales-enablement, revops | є | NOT TESTED | Не потрібні. Згадують платні бази, сервіси розсилок, CRM, вебхуки, MCP | OV-OUT: лише підготовка; зовнішні дії виконує CEO |
| social | є | NOT TESTED | Не потрібні. Згадує планувальники через MCP/API, `curl`, вхід у браузері | OV-PUB: лише чернетки й календарі |
| video | є | NOT TESTED | Не потрібні. Згадує `npx`, платні генератори, HeyGen MCP | OV-VID: лише сценарії й розкадровки |
| marketing-plan | є | NOT TESTED | Не потрібні. Згадує MCP, Notion, шлях `~/marketing-plans/` | OV-MP: шлях `{WORKSPACE}/marketing-plans/<slug>/` |
| pricing, offers, cro, content-strategy, copy-editing | є | NOT TESTED | Не потрібні | Орієнтовані на SaaS і англійську; адаптація ринку через Profile |
| ui-ux-pro-max | є | NOT TESTED | Python 3 без зовнішніх залежностей (за `SKILL.md`); CLI не потрібен | NEEDS REVIEW; запуск скриптів не виконувався |

## 3. Відсутні залежності: рішення

Посилання між Skills у всіх випадках необов'язкові. Скопійовано лише те, що є в бібліотеці. Повна таблиця: `../REPORTS/skills-deep-audit.md`, розд. 4.3.

| Де | Чого немає | Рішення |
|---|---|---|
| ad-creative (refs) | `ads/references/meta-decision-system.md` | Не копіюємо; ігнорувати. Аналіз реклами: `../SOPS/ads-management.md` |
| copywriting | `seo-audit/.../ai-writing-detection.md` | Не копіюємо; необов'язково |
| marketing-plan | `marketing-ideas`, `ads`, `emails`, `paywalls`, `ab-testing`, `seo-audit` та ін. | Необов'язково (OV-MP); без `marketing-ideas` ідеї описуються словами |
| CE (м'які посилання) | harness-engineering, hosted-agents, latent-briefing, self-managed-context, self-improvement-loops, bdi-mental-states | Не копіюємо; необов'язково |
| Marketing (описи) | ads, emails, launch, paywalls, signup, onboarding, popups, ab-testing, competitors, seo-audit, ai-seo, marketing-psychology, conversion-tracking, attribution та інші | Не копіюємо; не блокує |
| усі | `tools/` (GitHub-посилання marketingskills) | Не потрібні; партнерські інтеграції в `tools/PARTNERS.md` поза MIT |

## 4. Не додано або не затверджено

| Skill | Стан | Підстава |
|---|---|---|
| ads (marketingskills) | **Не додається** (рішення CEO 2026-11-13) | B2B/платформний, персона «direct access to ad platform accounts»; замінено SOPS (`ads-management`, `competitor-ad-monitoring`) |
| ui-ux-pro-max | **У бібліотеці, статус NEEDS REVIEW**; не включати до затвердженого релізу | Умови зняття: ліцензії компонентів і даних, походження сторонніх матеріалів, актуальність супровідних файлів (виправлено), шлях `${CLAUDE_PLUGIN_ROOT}` для нашого середовища. Файли не видаляються |

## 5. Власні SOPS, що замінюють/доповнюють Skills

| SOP | Роль | Пов'язані Skills |
|---|---|---|
| `../SOPS/supplier-verification.md` | Supplier Manager | (Skill немає) |
| `../SOPS/competitor-ad-monitoring.md` | Product Researcher + CEO | competitor-profiling (довідка) |
| `../SOPS/ads-management.md` | Ads Manager | analytics (визначення), ad-creative (креативи) |
| `../SOPS/profit-calculation.md` | Growth Manager | analytics (принципи) |
| `../SOPS/ukrainian-copywriting-style.md` | Creative Director, Store Builder, Sales Manager | copywriting, copy-editing, ad-creative |

## 6. Обмеження

1. Cowork-активація не перевірена. Жодних тверджень про автоматичний виклик Skills.
2. Походження копій відтворюється лише за `SOURCES.md`; історичні commit hashes відсутні.
3. Оригінальні файли Skills не редагуються; зміни лише у шарі адаптації (оверлеї, `ROUTING.md`, `ADAPTATION.md`) і в наших документах каталогу.
4. Скрипти зі Skills не запускаються, залежності й MCP не встановлюються без окремого погодження CEO (`../APPROVALS.md`).
5. Моніторинг конкурентної реклами початково ручний (щотижня, CEO + Product Researcher).
6. Рекомендовані ролі в цьому файлі й у `ROUTING.md` не є білим списком доступу.
