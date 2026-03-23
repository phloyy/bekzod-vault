# Obsidian + Claude Code + GitHub — Полная инструкция

---

## Что ты получишь

Локальная база знаний в Obsidian, которую Claude Code читает и заполняет по твоим skill-файлам. Всё синхронизируется через GitHub.

```
obsidian-vault/
├── CLAUDE.md          ← главный конфиг для Claude Code
├── _skills/           ← твои инструкции для Claude
├── _templates/        ← шаблоны Obsidian
├── projects/          ← проекты
├── content/           ← посты, брифы
├── courses/           ← уроки WePro
└── portfolio/         ← case studies
```

---

## Шаг 1 — Установить Obsidian

1. Скачай: https://obsidian.md/download
2. Установи
3. При первом запуске → **Create new vault**
4. Назови: `bekzod-vault` (или любое)
5. Выбери папку где хранить — лучше `D:\Vaults\bekzod-vault`

---

## Шаг 2 — Залить готовую структуру в vault

### Вариант A — через скачивание с GitHub (после шага 4)

```bash
# После создания репозитория:
git clone https://github.com/твой-юзернейм/bekzod-vault.git "D:\Vaults\bekzod-vault"
```

Потом в Obsidian: **Open folder as vault** → выбери эту папку.

### Вариант B — вручную

Скопируй все файлы из архива в папку vault.

---

## Шаг 3 — Настроить Git на Windows

### Установить Git

1. Скачай: https://git-scm.com/download/win
2. Установи с дефолтными настройками
3. Проверь в терминале:

```bash
git --version
```

### Настроить имя и email

```bash
git config --global user.name "Bekzod"
git config --global user.email "твой@email.com"
```

---

## Шаг 4 — Создать GitHub репозиторий

1. Заходи на https://github.com
2. **New repository**
3. Название: `bekzod-vault`
4. Visibility: **Private** (твои рабочие файлы — не для всех)
5. ❌ Не добавляй README, .gitignore — они уже есть
6. **Create repository**
7. Копируй URL: `https://github.com/твой-юзернейм/bekzod-vault.git`

---

## Шаг 5 — Инициализировать Git в vault

Открой терминал (PowerShell или Git Bash) в папке vault:

```bash
cd D:\Vaults\bekzod-vault

git init
git add .
git commit -m "initial: obsidian vault structure"
git branch -M main
git remote add origin https://github.com/твой-юзернейм/bekzod-vault.git
git push -u origin main
```

Введи GitHub логин/пароль или токен (см. ниже).

### Если просит токен вместо пароля

1. GitHub → Settings → Developer Settings → Personal Access Tokens → Tokens (classic)
2. Generate new token → отметь `repo`
3. Скопируй токен — вставь вместо пароля в терминале

---

## Шаг 6 — Установить Claude Code

```bash
npm install -g @anthropic/claude-code
```

Проверь:

```bash
claude --version
```

Если Node.js не установлен → https://nodejs.org (LTS версия)

### Авторизация

```bash
claude
```

Откроется браузер → войди в аккаунт Anthropic → скопируй ключ.

---

## Шаг 7 — Запустить Claude Code внутри vault

```bash
cd D:\Vaults\bekzod-vault
claude
```

Claude Code прочитает `CLAUDE.md` автоматически. Теперь можно давать задачи:

```
Создай пост для Telegram по проекту NOFILLER. Тема: весенний дроп. Используй skill social-post
```

Claude прочитает `_skills/social-post.md` и создаст файл в `content/posts/`.

---

## Шаг 8 — Настроить плагин Obsidian Git (автосинк)

1. В Obsidian: Settings → Community plugins → Browse
2. Найди **Obsidian Git** → Install → Enable
3. Settings → Obsidian Git:
   - Auto pull interval: `10` (минут)
   - Auto commit interval: `5` (минут)
   - Auto commit message: `vault: auto-sync {{date}}`
4. Теперь vault сам пушит изменения в GitHub

---

## Шаг 9 — Workflow в ежедневной работе

### Открыть проект и дать задачу Claude

```bash
cd D:\Vaults\bekzod-vault
claude "Добавь запись в лог NOFILLER: сегодня сделал ревизию UI Kit, следующий шаг — контент-план"
```

### Запушить вручную если нужно

```bash
git add .
git commit -m "content: nofiller telegram post"
git push
```

### Посмотреть статус

```bash
git status
git log --oneline -10
```

---

## Шаг 10 — Добавить свой skill

Создай файл `_skills/мой-скилл.md` по структуре:

```md
# SKILL: название

## Назначение
Что делает этот skill.

## Входные данные
- param1 — описание
- param2 — описание

## Структура выходного файла
(frontmatter + тело документа)

## Правила
- правило 1
- правило 2

## Именование файла
папка/YYYY-MM-DD-{slug}.md
```

Потом в CLAUDE.md добавь строку в таблицу маппинга.

---

## Быстрые команды — шпаргалка

```bash
# Зайти в vault и запустить Claude
cd D:\Vaults\bekzod-vault && claude

# Синхронизировать вручную
git add . && git commit -m "sync" && git push

# Посмотреть что изменилось
git diff

# Откатить последний коммит (файлы остаются)
git reset HEAD~1
```

---

## Структура файлов которые ты получил

```
bekzod-vault/
├── CLAUDE.md                        ← читается автоматически Claude Code
├── .gitignore                       ← исключает мусор из Git
├── _skills/
│   ├── social-post.md               ← посты Instagram/TG/TikTok
│   ├── lesson-plan.md               ← уроки WePro
│   ├── project-brief.md             ← брифы
│   ├── case-study.md                ← case studies для портфолио
│   └── project-log.md               ← лог задач по проекту
├── _templates/
│   └── daily-note.md                ← дневной шаблон
├── projects/
│   ├── NOFILLER/README.md
│   └── XIZMAT24/README.md
├── content/
│   ├── posts/                       ← сюда идут посты
│   └── briefs/                      ← сюда идут брифы
├── courses/                         ← уроки WePro
└── portfolio/                       ← case studies
```

---

## Troubleshooting

| Проблема | Решение |
|---|---|
| `claude: command not found` | `npm install -g @anthropic/claude-code` заново |
| `git push` просит пароль | Используй Personal Access Token |
| Claude не читает CLAUDE.md | Запускай `claude` из корня vault, не из другой папки |
| Obsidian Git не пушит | Проверь Settings → Obsidian Git → remote URL |
| Файлы не создаются | Claude Code нужен `--dangerously-skip-permissions` флаг при первом запуске |
