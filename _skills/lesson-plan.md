# SKILL: lesson-plan

## Назначение
Создание уроков для курса по графическому дизайну (WePro).
Покрывает: Illustrator, CorelDRAW, Photoshop, типографику, брендинг, карьеру.

---

## Входные данные
- `lesson_number` — номер урока (01–60)
- `block` — блок курса (1–8)
- `topic` — тема урока
- `tool` — инструмент (AI / CDR / PS / теория)
- `duration` — длительность в минутах
- `level` — уровень (intro / core / advanced)

---

## Структура выходного файла

```md
---
created: {{date}}
tags: [course, wepro, {{tool}}, block-{{block}}]
status: draft
lesson: {{lesson_number}}
block: {{block}}
duration: {{duration}}min
---

# Урок {{lesson_number}}: {{topic}}

## Цель урока
Студент после урока умеет: ...

## Теория ({{X}} мин)

### Ключевые понятия
- 
- 

### Объяснение
{{theory_body}}

## Практика ({{X}} мин)

### Задание
{{task_description}}

### Шаги выполнения
1. 
2. 
3. 

### Ожидаемый результат
{{expected_output}}

## Домашнее задание

{{homework}}

## Ресурсы и референсы

- [[_templates/]] 
- 

## Заметки преподавателя

{{teacher_notes}}
```

---

## Правила

- Теория max 30% времени урока, практика min 70%
- Каждый урок = один навык, не несколько
- Домашнее задание должно быть выполнимо за 30-60 мин
- Используй Obsidian-ссылки на смежные уроки: `[[lesson-05]]`

---

## Именование файла

```
courses/lesson-{{NN}}-{{slug}}.md
```

Пример: `courses/lesson-07-pen-tool-basics.md`
