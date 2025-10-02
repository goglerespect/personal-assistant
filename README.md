```markdown
# Personal Assistant CLI

Цей проєкт є реалізацією **персонального помічника (CLI)** з курсу Core.  
Додано конфігурацію віртуального середовища та Dockerfile для запуску застосунку у контейнері.

---

## 🔹 Завдання 1. Віртуальне середовище

### Використано інструмент
**Pipenv** для створення віртуального середовища.

### Версія Python
У файлі `Pipfile` зафіксована версія:
```toml
[requires]
python_version = "3.11"
````

### Залежності

Зараз застосунок використовує лише стандартну бібліотеку Python, тому сторонніх залежностей у `Pipfile` немає.
У майбутньому їх можна буде додати в секцію `[packages]`.

### Як запустити у віртуальному середовищі

```bash
pipenv install
pipenv shell
python assistant/main.py
```

---

## 🔹 Завдання 2. Docker

### Dockerfile

У репозиторії є `Dockerfile`, який:

* Використовує базовий образ `python:3.11-slim`
* Копіює вихідний код застосунку в контейнер
* Встановлює залежності через `pipenv`
* Запускає CLI застосунок як основну команду контейнера

### Як зібрати образ

```bash
docker build -t personal-assistant .
```

### Як запустити контейнер

```bash
docker run -it personal-assistant
```

### Як потрапити всередину контейнера

```bash
docker run -it personal-assistant /bin/bash
```

або (якщо контейнер вже працює):

```bash
docker exec -it <container-id> /bin/bash
```

---

## 📂 Структура проєкту

```
personal-assistant/
│
├── Pipfile
├── Pipfile.lock
├── Dockerfile
├── README.md
└── assistant/
    ├── __init__.py
    ├── main.py
    └── інші модулі...
```

