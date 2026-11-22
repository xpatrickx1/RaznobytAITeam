# SOURCES — джерела Skills

Оновлено: 2026-11-15. Позначки за `../STANDARDS.md`. Рівень перевірки: читання локальних файлів; 2026-11-15 додатково прочитано сторінки трьох репозиторіїв на GitHub (README, бічна панель ліцензії, `VERSIONS.md`). Репозиторії не клонувалися, код не запускався. Підстава: `../REPORTS/skills-deep-audit.md` і рішення CEO.

## 1. Репозиторії та ліцензії

| Набір | Репозиторій | Ліцензія | Що скопійовано |
|---|---|---|---|
| A. Context Engineering | https://github.com/muratcankoylan/Agent-Skills-for-Context-Engineering | MIT `[ФАКТ]`: локальний `context-engineering/LICENSE` (Context Engineering Agent Skills Contributors, 2025); README на GitHub: «MIT License, see LICENSE file» | 12 Skills: 6 у `context-engineering/selected/` (+ LICENSE) і 6 «плоских» папок (advanced-evaluation, context-degradation, context-fundamentals, memory-systems, project-development, tool-design) |
| B. Marketing Skills | https://github.com/coreyhaines31/marketingskills | MIT `[ФАКТ]`: локальний `marketing/LICENSE` (Corey Haines, 2025); сторінка GitHub показує MIT і файл `LICENSE` | 18 Skills: 6 у `marketing/selected/` (+ LICENSE) і 12 «плоских» папок (cold-email, content-strategy, copy-editing, cro, marketing-plan, offers, pricing, prospecting, revops, sales-enablement, social, video) |
| C. UI UX Pro Max | https://github.com/nextlevelbuilder/ui-ux-pro-max-skill | MIT для Skill (за README і бічною панеллю GitHub, 2026-11-15; MIT описано для Basic-версії, Premium окремий продукт) `[ФАКТ]` для рівня репозиторію; текст `LICENSE` і власник авторських прав локально відсутні `[НЕВІДОМО]` | 1 Skill: `ui-ux-pro-max/` (`SKILL.md`, `data/`, `references/`, `scripts/`, наші `INSTALL.md` і `source-reference.md`) |

Файли upstream, яких у копіях немає: README, `tools/`, `VERSIONS.md`, release-пакети. Копіювались папки Skills із `SKILL.md`, `references/`, `scripts/`, `tests/`, `assets/`, `evals/`, `data/`.

## 2. Повідомлення про авторські права та ліцензії

Текст ліцензії MIT зберігається в `context-engineering/LICENSE` (Context Engineering Agent Skills Contributors, 2025) і `marketing/LICENSE` (Corey Haines, 2025). Вони не змінювались.

| Skill | Репозиторій | Яка ліцензія застосовується | Локальний `LICENSE` у папці Skill | Статус |
|---|---|---|---|---|
| 6 Skills у `context-engineering/selected/` | A | `context-engineering/LICENSE` | Так, на рівні групи | Підтверджено |
| 6 Skills у `marketing/selected/` | B | `marketing/LICENSE` | Так, на рівні групи | Підтверджено |
| 6 «плоских» Skills CE | A | MIT репозиторію A (текст: `context-engineering/LICENSE`) | Ні | MIT на рівні репозиторію; походження: ім'я Skill є в upstream (README), для `memory-systems` ще й збіг змісту |
| 12 «плоских» Skills Marketing/Sales | B | MIT репозиторію B (текст: `marketing/LICENSE`) | Ні | MIT на рівні репозиторію; походження: імена є в upstream |
| ui-ux-pro-max | C | MIT для Skill (GitHub) | Ні | Текст і copyright holder `[НЕВІДОМО]`; компоненти даних: UNKNOWN |

Копії `LICENSE` у кожну папку «плоских» Skills не додавались (щоб не змінювати структуру Skills); рішення про це належить CEO. Авторські права й ліцензії не переписувались і не припускались: де підтвердження немає, стоїть `[НЕВІДОМО]` або UNKNOWN.

### Сторонні матеріали зі статусом UNKNOWN

| Де | Що | Статус |
|---|---|---|
| `long-horizon-prompting/references/cdc-prompt-annotated.md` | Цитований промпт, опублікований OpenAI (2026-07-10) | UNKNOWN |
| `long-horizon-prompting/references/mass-handoff-contracts.md` | Опис дослідницької роботи (Hyunin Lee та ін.) | UNKNOWN |
| `marketing-plan/references/budget-planning.md`, `growth-patterns.md` | Уривки з книги *Founding Marketing* (Corey Haines) | Чи покриває їх MIT: UNKNOWN |
| `copywriting/references/natural-transitions.md` | Адаптація з University of Manchester Academic Phrasebank і Plain English Campaign | UNKNOWN |
| `copywriting`, `copy-editing`, `product-marketing`, `analytics` | Адаптовані фрагменти Profound і Wispr Flow (у примітках Skills: MIT) | За примітками MIT; не перевірено за першоджерелом |
| `ui-ux-pro-max/data/phosphor-icons-upstream.json` | Каталог іконок Phosphor (`@phosphor-icons/core`) | UNKNOWN |
| `ui-ux-pro-max/data/google-font-licenses.json` | 1 934 родини Google Fonts (OFL 1 894, Apache-2.0 35, UFL 5 за записами в самих даних; ревізія google/fonts `038b637d…`) | Записи не перевірялись окремо |
| marketingskills `tools/PARTNERS.md` | Партнерські інтеграції поза MIT (за README) | У копіях відсутні |

## 3. Відомі версії

| Skill | Версія | Джерело даних |
|---|---|---|
| 18 Marketing/Sales Skills (product-marketing 2.2.3, customer-research 2.0.8, competitor-profiling 2.1.8, ad-creative 2.13.0, copywriting 2.3.5, analytics 2.2.5, cold-email 2.2.4, content-strategy 2.1.8, copy-editing 2.2.4, cro 2.0.6, marketing-plan 1.2.5, offers 1.0.6, pricing 2.1.7, prospecting 1.5.3, revops 2.2.4, sales-enablement 2.4.3, social 2.5.2, video 2.4.3) | як у дужках | `metadata.version` у локальному `SKILL.md` `[ФАКТ]` |
| 12 Skills Context Engineering | context-fundamentals 2.2.0, context-degradation 2.1.0, context-optimization 2.1.0, context-compression 1.3.0, filesystem-context 1.2.0, memory-systems 4.1.0, multi-agent-patterns 2.1.0, long-horizon-prompting 1.1.0, project-development 1.3.0, tool-design 2.2.0, evaluation 1.2.0, advanced-evaluation 2.1.0 | Блок «Skill Metadata» наприкінці локального `SKILL.md` `[ФАКТ]`; у frontmatter версії немає. Для `memory-systems` збігається з upstream (4.1.0, 2026-05-15) |
| ui-ux-pro-max | не вказана | Ні у frontmatter, ні на сторінці репозиторію (Releases порожній). v2.15.0 (2026-08-13) називає лише вторинне джерело `[ПРИПУЩЕННЯ]` |
| ads (не скопійовано) | 2.7.4 | сторінка `skills/ads/SKILL.md` на GitHub, прочитана 2026-11-13 `[ФАКТ]`; лише довідково |

`VERSIONS.md` marketingskills (знімок, останній запис 2026-10-30): локальні версії 18 Skills Marketing/Sales не нижчі за записані там (наприклад, social 2.5.2 проти 2.4.2; cold-email 2.2.4 проти 2.2.1). Висновок: копії зроблено з upstream не раніше цього знімка (або знімок на сторінці застарілий). Версії у frontmatter не є commit hash і не доводять, що копія збігається з певним станом upstream.

## 4. Commit hashes

### Історичні (з яких копіювалися Skills)
**Не збережені.** У проєкті немає тимчасових клонів (перевірено 2026-11-13: `~/Downloads`, `~/Desktop`, `~/Documents`, `~/web`, `~/web/GitHub`, верхній рівень `%TEMP%`; повний пошук по диску не виконувався), немає жодного хешу у файлах `SKILLS/`. Точні версії, з яких копіювали, відновити неможливо `[НЕВІДОМО]`. Це стосується всіх 31 Skills. Хеш не вигадується.

### Поточні upstream (окремо, не історичні)
Не отримано: сторінки GitHub не показують commit hash, `git ls-remote` із робочого середовища заблоковано проксі (HTTP 403), GitHub API недоступний. CEO може виконати й записати нижче **з датою перевірки**:

```
git ls-remote https://github.com/muratcankoylan/Agent-Skills-for-Context-Engineering.git HEAD
git ls-remote https://github.com/coreyhaines31/marketingskills.git HEAD
git ls-remote https://github.com/nextlevelbuilder/ui-ux-pro-max-skill.git HEAD
```

| Репозиторій | Поточний HEAD | Дата перевірки | Примітка |
|---|---|---|---|
| Agent-Skills-for-Context-Engineering | `[НЕВІДОМО]` | — | «Поточний», не історичний |
| marketingskills | `[НЕВІДОМО]` | — | «Поточний», не історичний |
| ui-ux-pro-max-skill | `[НЕВІДОМО]` | — | «Поточний», не історичний |

## 5. Установлення за описами upstream (не виконувалося)

- **A:** Claude Code Plugin Marketplace або ручне копіювання в `.claude/skills/` (за README і описами). Окремого способу для Cowork не виявлено; сумісність `[НЕВІДОМО]`.
- **B:** Claude Code marketplace, clone + copy, git submodule, `npx`; Claude Web ZIP у Releases (за `../REPORTS/SKILLS_AUDIT.md`, у цій перевірці не підтверджено). Сумісність з Cowork `[НЕВІДОМО]`.
- **C:** за вторинними описами CLI `npm install -g ui-ux-pro-max-cli` + `uipro init --ai claude`; але локальний `SKILL.md` описує запуск Python-скриптів без зовнішніх залежностей. **Нічого не виконувати** без окремого рішення CEO. Умови і стан: `ui-ux-pro-max/INSTALL.md`.

## 6. Походження файлів у проєкті

- Вихідний пакет підготовки: `../ai_skills_review/` (три звіти + `PROMPT_FOR_CLAUDE.md`), копії звітів у `../REPORTS/`.
- 12 Skills у `selected/` скопійовано поза сесіями аудиту; спосіб і джерельний commit `[НЕВІДОМО]`.
- 18 «плоских» Skills і `ui-ux-pro-max/` з'явилися в репозиторії 2026-11-14 (за часом створення файлів); спосіб копіювання й джерельний commit `[НЕВІДОМО]`. Поточний стан у Git: не закомічені.
- Додаткові відомості про `ads`: прочитано лише сторінку `SKILL.md` на GitHub; його `references/` не читалися, не копіювались.

## 7. Першоджерела, прочитані 2026-11-15

- https://github.com/coreyhaines31/marketingskills (MIT, список 53 Skills) та `VERSIONS.md` у ньому
- https://github.com/muratcankoylan/Agent-Skills-for-Context-Engineering (MIT за README; список 18 Skills) та `skills/memory-systems/SKILL.md` у ньому
- https://github.com/nextlevelbuilder/ui-ux-pro-max-skill (MIT, Basic-версія)

Текст файлів `LICENSE` на GitHub не відкривався; підтвердження спирається на README і бічну панель GitHub та на локальні копії `LICENSE` для груп A і B.

## 8. Вторинні джерела (довідково)

Описи на ossinsight.io, wikidocs.net, anavem.com, sourcepulse.org, zby.github.io використано лише для ліцензій/версій/способів встановлення з позначкою `[ПРИПУЩЕННЯ]`; першоджерелом вважаються LICENSE і SKILL.md у проєкті та сторінки репозиторіїв (розділ 7).

## 9. Додані 2026-11-20 (SEO й дизайн сайту)

- **SEO (8):** плагін `searchfit-seo` 1.0.0, https://github.com/searchfit/searchfit-seo, MIT (локальний `SKILLS/seo/LICENSE`), копія з локальної установки плагіна 2026-11-20; commit `[НЕВІДОМО]`. 4 Skills пакета не додано: `content-strategy` (дублює наявний), `ai-visibility`, `broken-links` (потребують живих запитів чи обходу сайту) та агенти/команди плагіна.
- **frontend-design:** публічний Skill середовища Claude, Apache-2.0 (`SKILLS/web-design/selected/frontend-design/LICENSE.txt`); версія й commit `[НЕВІДОМО]`.
- **accessibility-review, design-critique, ux-copy, design-handoff:** плагін `design` 1.2.0 (автор Anthropic), копія 2026-11-20; файлу LICENSE у плагіні немає: ліцензія `[НЕВІДОМО]`.
- Пакет-першоджерело імпорту збережено: `../REPORTS/skills-import_2026-11-20.tgz`. Контрольні суми (перші 12 символів SHA-256) файлів зафіксовано в `seo/ADAPTATION.md` і `web-design/ADAPTATION.md`.
- Не додано: `design-system`, `user-research`, `research-synthesis` (поза потребою), `ai-visibility`, `broken-links`, `content-strategy` (дублікат).
