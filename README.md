# RazorClaw Systems — Investor Website v2.1

Статический сайт: `index.html` + `assets/`. Без сборки. GitHub Pages: загрузите содержимое папки в корень репозитория (`index.html` и `assets/` рядом).

## Реальные материалы: просто положите файлы в `assets/`
Сайт сам подхватывает их, ничего править не нужно:
| Файл | Что появится |
|---|---|
| `control-station-classic.png` (или .jpg/.webp) | реальный скриншот во вкладке Classic вместо схемы |
| `control-station-tactical.png` | изображение во вкладке Tactical; остаётся с пометкой DESIGN CONCEPT, пока реализация не подтверждена |
| `control-station-demo.webm` или `.mp4` | кнопка «Watch Software Demonstration» с модальным окном (Esc закрывает) |
| `founder.jpg` (или .png/.webp) | фотография основателя вместо инициалов |
Пока файла нет, соответствующая кнопка/блок честно не показываются или показывают схему.

## Engineering Updates
В `index.html` найдите `<script type="application/json" id="updatesData">` и добавьте объект в массив (новые сверху). Первые 3 показываются сразу, остальные — по кнопке View All Updates.
```json
{"date_en":"November 2026","date_ru":"Ноябрь 2026","title":"...","title_ru":"...","cat":"Tracking","cat_ru":"Сопровождение","text":"...","text_ru":"...","status":"Demonstrated","link":"https://... (необязательно)"}
```
`cat`: Tracking, Recovery, Control Station, Testing, UI. `status`: Demonstrated, In Development, Testing, Planned. Точные результаты тестов — только после проверки CI/test report.

## Доказательства в Development Progress
Кнопки доказательств скрыты, пока материала нет. Чтобы добавить, в конце `index.html` найдите `var EVIDENCE={};` и заполните, например:
`var EVIDENCE={tracking:[{label:'Screenshot',label_ru:'Скриншот',url:'assets/tracking.png'}]};` (ключи: tracking, identity, recovery, station, runtime, tactical).

## Цвет акцента
По умолчанию — утверждённый Cyber Blue #00E0FF. Красный вариант из ТЗ v2.1 включается одним атрибутом: `<html lang="en" data-lang="en" data-accent="red">`.

## Откат
`backup_before_v2/index.html` — версия до обновлений 17.10.2026; `backup_v2_hud.html` — промежуточная версия v2 (HUD-стиль).

## Форма
Работает через `mailto:` и ничего не отправляет на сервер — на сайте это сказано прямо.
