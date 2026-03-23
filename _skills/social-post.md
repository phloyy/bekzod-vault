# SKILL: social-post

## Назначение
Создание постов для Instagram, Telegram, TikTok, Behance.

---

## Входные данные (запроси если не указано)
- `project` — название проекта / бренда
- `platform` — Instagram / Telegram / TikTok / Behance
- `topic` — тема поста
- `tone` — тон (дерзкий / нейтральный / экспертный)
- `cta` — призыв к действию (опционально)

---

## Структура выходного файла

```md
---
created: {{date}}
tags: [content, social, {{platform}}]
status: draft
project: {{project}}
platform: {{platform}}
---

# {{topic}} — {{platform}}

## Текст поста

{{body}}

## Хэштеги

{{hashtags}}

## Визуал (референс)

{{visual_note}}

## CTA

{{cta}}
```

---

## Правила написания

### Instagram
- Первые 2 строки — хук (без воды)
- Абзацы по 2-3 строки max
- 5-10 хэштегов внизу, не в тексте
- Эмодзи умеренно — только если соответствует tone

### Telegram
- Без хэштегов в тексте (или 1-2 max)
- Можно длиннее — аудитория читает
- Bold для акцентов: **слово**
- Ссылка в конце если есть

### TikTok
- Короткий хук — первые 3 слова решают
- Текст = подпись к видео, не эссе
- 3-5 хэштегов, трендовые + нишевые

---

## Правила именования файла

```
content/posts/YYYY-MM-DD-{project}-{platform}.md
```

Пример: `content/posts/2026-03-23-nofiller-instagram.md`
