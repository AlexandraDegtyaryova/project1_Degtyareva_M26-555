# Анализ каталога фильмов

Учебный проект на Python 3.12: девять этапов анализа каталога без pandas.

## Запуск

После клонирования необходим установленный uv:

~~~console
uv run catalog_analysis.py
uv run ruff check .
~~~

uv автоматически создаст .venv и установит зависимости из uv.lock.
Обычный запуск вызывает build_report(movies) и печатает итоговый отчет.

## Демонстрации циклов и генератора

Дополнительные примеры запускаются отдельно, чтобы не смешивать их с отчетом:

~~~console
uv run python -c "from catalog_analysis import movies, print_non_comedies; print_non_comedies(movies)"
uv run python -c "from catalog_analysis import movies, print_first_masterpiece; print_first_masterpiece(movies)"
uv run python -c "from catalog_analysis import movies, print_first_masterpiece; print_first_masterpiece([m for m in movies if m['rating'] <= 9])"
uv run python -c "from catalog_analysis import movies, print_high_rated; print_high_rated(movies)"
uv run python -c "from catalog_analysis import movies, total_duration_above_seven; print(total_duration_above_seven(movies))"
~~~

В третьем примере проверяется ветка else цикла while:
«Шедевров не найдено». Суммарная длительность в последнем примере — 713 минут.
