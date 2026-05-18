# GOST Checker

GOST Checker — Python-инструмент для автоматической проверки и форматирования курсовых работ в формате .word в соответствии с требованиями БГУИР (ГОСТ).

# 🔧 Возможности
- Проверка и исправление:
- Шрифта (имя, размер)
- Межстрочных интервалов
- Отступов и интервалов до/после абзацев
- Форматирования заголовков 1 и 2 уровней
- Добавление разрывов страниц перед разделами
- Удаление лишних абзацев перед заголовками
- Пропуск титульного листа по ключевой фразе (например, "Минск 2025")
- Автоматическое оформление интернет-источников:
- По шаблону из config.yaml
- С извлечением названия по < title >, < meta >, < h1 >, < h2 > и т.д.
- Обработка PDF-ссылок (название из имени файла)
- Генерация отчета о нарушениях в формате CSV

# 📁 Структура проекта
- ghostChecker/
- ├── main.py                  # Точка входа в приложение
- ├── config.yaml              # Настройки стилей и шаблонов
- └── checker/
- -   ├── style_checker.py     # Проверка оформления и структуры
- -   ├── utils.py             # Форматирование 
- -   └── report_generator.py  # Генерация CSV-отчета

# 📦 Установка
- git clone https://github.com/Klivan49/GOST-Checker
- cd GOST Checker
- pip install -r requirements.txt

# 🛠️ Настройка config.yaml

font:
-  name: "Times New Roman"
-  size: 14

paragraph:
-  line_spacing: 1.5
-  space_after: 6

heading:
-  h1:
- -    space_before: 12
- -    space_after: 6
- -    bold: true

bibliography:
-  format_template: "[{index}] «{title}» [Электронный ресурс]. Режим доступа: {url}. Дата доступа: {access_date}."
-  font_name: "Times New Roman"
-  font_size: 14
-  space_after: 6
-  line_spacing: 1.0

# ▶️ Использование
python main.py "путь_к_файлу.docx"
Пример:
python main.py "C:\\Users\\Student\\Desktop\\Kursovaya.docx"

# 📄 Результат работы
- *_gost.docx — исправленный документ
- *_report.csv — отчёт об ошибках оформления

# ⚠️ Примечания
- Работает только с .docx-файлами (Microsoft Word)
- Не анализирует содержание, только оформление
- Для обработки библиографии требуется, чтобы заголовок "СПИСОК ИСТОЧНИКОВ" присутствовал в документе

# ✅ Зависимости
- python-docx
- requests
- beautifulsoup4
- pyyaml

Все зависимости указаны в requirements.txt и устанавливаются автоматически.

Разработано с любовью для студентов БГУИРа
by Klivan<3
