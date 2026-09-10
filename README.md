# Отчёт по работе с Git и GitHub

**Дисциплина:** «Управление IT-проектами для корпоративного обучения»  
**Студент:** Клементьев Алексей Александрович  
**Группа:** 2ом_КЭО/25  
**GitHub:** [LyoshaGodX](https://github.com/LyoshaGodX)  
**Репозиторий:** [git-practice-report](https://github.com/LyoshaGodX/git-practice-report)

## Цель работы

Освоить базовые операции системы контроля версий Git и сервиса GitHub:

- создать локальный и удалённый репозитории;
- выполнить коммиты;
- создать отдельную ветку;
- объединить две ветки;
- клонировать удалённый репозиторий;
- оформить отчёт с помощью Markdown.

## Ход работы

### 1. Создание репозитория и первый коммит

На GitHub создан пустой репозиторий `git-practice-report`. Локальный репозиторий инициализирован с основной веткой `main`, после чего добавлен этот отчёт.

```bash
git init -b main
git config user.name "Клементьев Алексей Александрович"
git add README.md .gitignore
git commit -m "Initial commit: add project report"
git remote add origin https://github.com/LyoshaGodX/git-practice-report.git
git push -u origin main
```

### 2. Создание отдельной ветки

Для памятки по командам создана ветка `feature/git-operations`.

```bash
git switch -c feature/git-operations
git add docs/operations.md
git commit -m "Add Git operations notes"
git push -u origin feature/git-operations
```

### 3. Слияние веток

Дополнительная ветка объединена с `main` отдельным merge-коммитом.

```bash
git switch main
git merge --no-ff feature/git-operations -m "Merge feature/git-operations into main"
git push origin main
```

### 4. Клонирование

Удалённый репозиторий повторно клонирован в отдельный каталог `git-practice-report-clone`.

```bash
git clone https://github.com/LyoshaGodX/git-practice-report.git git-practice-report-clone
git -C git-practice-report-clone status
```

## Проверка результата

История должна содержать первый коммит, коммит дополнительной ветки и merge-коммит. Контрольный клон должен находиться на ветке `main` и не содержать незакоммиченных изменений.

```bash
git log --oneline --graph --decorate --all
git status
```

Фактические результаты проверки будут зафиксированы в заключительном коммите после выполнения всех операций.

## Результат

В репозитории представлена воспроизводимая история работы с Git: начальный коммит, отдельная ветка с самостоятельным изменением, её слияние с основной веткой и проверка посредством клонирования.

## Использованные источники

1. Материалы курса по базовым операциям Git.
2. [Документация Git](https://git-scm.com/docs).
3. [Документация GitHub](https://docs.github.com/).
