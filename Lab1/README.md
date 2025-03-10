# Анализ пользовательских сессий интернет-магазина

## Описание проекта
Проект посвящён предварительной обработке данных из CSV-файла, содержащего информацию о пользовательских сессиях интернет-магазина. Основные задачи включают выявление и устранение проблем в данных, а также проведение анализа с использованием библиотеки Pandas.

## Данные
Входной датасет содержит следующие столбцы:
- **User_Id** – уникальный идентификатор пользователя.
- **Region** – страна пользователя.
- **Device** – устройство пользователя.
- **Channel** – источник рекламы, из которого пришёл пользователь.
- **Session_Start** – дата и время начала сессии.
- **Session_End** – дата и время окончания сессии.

## Этапы работы
### 1. Загрузка и первичный анализ данных
- Выгружены и проанализированы первые 20 строк таблицы.
- Проведено описание данных и предметной области.
- Выявлены пропуски в столбцах `Region`, `Device`, `Session_Start` и `Session_End`.

### 2. Очистка данных
- Заполнены пропущенные значения в `Region` значением "United States".
- Удалены оставшиеся строки с пропусками.
- Выявлены и устранены явные и неявные дубликаты.
- Приведены типы данных к корректному формату (`User_Id` → `int64`, `Session_Start`, `Session_End` → `datetime64`).

### 3. Группировки и сводные таблицы
- Подсчитано количество устройств для каждого региона.
- Создан датафрейм с переименованием столбцов и сортировкой по количеству.
- Построена сводная таблица с количеством пользователей по источникам трафика.
- Построена сводная таблица с количеством уникальных пользователей по регионам и устройствам.

### 4. Основные результаты
- Всего обработано **952 сессии**.
- **946 сессий** пришлись на США.
- Самые популярные устройства: **iPhone (331)** и **Mac (201)**.
- Самый популярный источник: **organic (608 сессий)**, на втором месте **Face Boom (149 сессий)**.
- Средняя продолжительность сессии составила **29 минут**.
- **358 сессий** длились дольше среднего.
- Почти все сессии оказались короткими по разработанной классификации (41 средняя, 1 длинная).

## Используемые технологии
- **Python 3**
- **pandas**
- **Google Colab**

## Запуск проекта
1. Открыть Google Colab по [ссылке](https://colab.research.google.com/drive/1uHK6Sc57YdVmksraK3HLJOeQWbDCCoYM?usp=sharing).
2. Запустить все ячейки для выполнения кода.
3. Ознакомиться с результатами обработки и анализа данных.

## Вывод
Произведена очистка данных, устранены пропуски и дубликаты, выполнен анализ пользовательских сессий. Проект продемонстрировал возможности библиотеки Pandas для обработки данных и построения сводных таблиц.

