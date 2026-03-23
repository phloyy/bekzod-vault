# SKILL: case-study

## Назначение
Написание case study для портфолио (Behance, сайт, Telegram).

---

## Входные данные
- `project` — название проекта
- `type` — тип работы (брендинг / веб / приложение / 3D / и т.д.)
- `client` — клиент или "личный проект"
- `year` — год
- `platform` — где публикуется (Behance / сайт / оба)

---

## Структура выходного файла

```md
---
created: {{date}}
tags: [portfolio, case-study, {{type}}, {{year}}]
status: draft
project: {{project}}
type: {{type}}
client: {{client}}
year: {{year}}
---

# {{project}} — Case Study

## Обзор

**Клиент:** {{client}}  
**Тип:** {{type}}  
**Год:** {{year}}  
**Роль:** [что делал лично]

## Проблема / Задача

{{problem_description}}

## Процесс

### Исследование
{{research_notes}}

### Концепция
{{concept_description}}

### Итерации
{{iterations_description}}

## Решение

{{solution_description}}

## Результат

- 
- 

## Чему научился

{{learnings}}

---

## Для Behance (короткая версия)

{{behance_short_text}}

## Ключевые визуалы (список)

1. 
2. 
3. 
```

---

## Правила

- "Проблема" всегда на первом месте — это продаёт работу
- Процесс показывает мышление, не только результат
- Behance-версия = max 3-4 абзаца
- Не используй слово "уникальный"

---

## Именование файла

```
portfolio/{{year}}-{{project-slug}}-case-study.md
```
