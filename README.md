# RazorClaw Systems — Investor Website v2

Статический сайт: `index.html` + папка `assets/`. Сборки нет. Запуск на GitHub Pages: загрузите содержимое папки в корень репозитория (`index.html` и `assets/` рядом), Settings → Pages → Deploy from branch → `/ (root)`.

## Структура
```
index.html
assets/ logo.png, symbol.png, og-image.png, intercept.webm, intercept.mp4, intercept-poster.jpg
```

## Как добавить запись в Engineering Updates
В `index.html` найдите блок `<script type="application/json" id="updatesData">` и добавьте объект в массив (новые записи — сверху):

```json
{
 "date": "2026-11", "date_en": "November 2026", "date_ru": "Ноябрь 2026",
 "title": "Title", "title_ru": "Заголовок",
 "cat": "Tracking", "cat_ru": "Сопровождение",
 "text": "Short factual description.", "text_ru": "Краткое фактическое описание.",
 "status": "Demonstrated",
 "link": "https://... (необязательно, только публичная ссылка на подтверждение)"
}
```
- `cat`: Tracking, Recovery, Control Station, Testing, UI.
- `status`: Demonstrated, In Development, Testing, Planned (другие значения отображаются как Planned).
- Точные результаты тестов публикуйте только после проверки CI/test report. Не публикуйте токены, внутренние адреса и чувствительные детали.
- Страница остальным не затрагивается: список строится скриптом из этого блока.

## Скриншоты Control Station
Сейчас в разделе 06 показана схема-макет с пометкой DESIGN CONCEPT. Когда будут реальные скриншоты, положите их в `assets/` и замените блок `<figure class="cs-visual">` на `<img>` с alt-текстом.

## Откат
Предыдущая версия сохранена в `backup_before_v2/index.html` (рядом с `assets/` из этого же архива).

## Форма
Форма работает через `mailto:` и ничего не отправляет на сервер — это явно написано на сайте.
