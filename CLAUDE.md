# Claude Code — Obsidian Vault Config

## Роль
Ты работаешь как контент-агент внутри Obsidian vault.
Все задачи выполняются строго по skill-файлам из папки `./_skills/`.

---

## Правила выполнения задач

1. **Перед любой задачей** — читай соответствующий `_skills/*.md`
2. **Формат всех файлов** — Markdown (.md) с frontmatter
3. **Ссылки** — используй Obsidian-формат: `[[filename]]`
4. **Сохранение** — в правильную папку согласно типу задачи (см. ниже)
5. **Язык** — русский, если не указано иное

---

## Структура vault

| Папка | Назначение |
|---|---|
| `_skills/` | SKILL.md файлы — инструкции для Claude |
| `_templates/` | Шаблоны Obsidian (Templater) |
| `projects/` | Проекты клиентов и личные |
| `content/posts/` | Посты для соцсетей |
| `content/briefs/` | Брифы |
| `courses/` | Материалы курсов |
| `portfolio/` | Case studies |

---

## Frontmatter — обязательный шаблон

```yaml
---
created: YYYY-MM-DD
tags: []
status: draft
project: ""
---
```

---

## Маппинг задач → skills → папки

| Команда | Skill | Папка |
|---|---|---|
| пост для Instagram/TG | `_skills/social-post.md` | `content/posts/` |
| урок курса | `_skills/lesson-plan.md` | `courses/` |
| бриф проекта | `_skills/project-brief.md` | `content/briefs/` |
| case study | `_skills/case-study.md` | `portfolio/` |
| задачи проекта | `_skills/project-log.md` | `projects/{name}/` |

---

## Пример команды

```bash
claude "Создай пост для Telegram по проекту NOFILLER. Тема: новый дроп. Используй skill social-post"
```

---

## Запрещено

- Создавать файлы без frontmatter
- Игнорировать skill-файл для задачи
- Писать в корень vault (только в подпапки)
