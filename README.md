YOLOv8-OBB на датасете DOTA
Этот репозиторий содержит Jupyter Notebook для обучения модели YOLOv8 с использованием ориентированных ограничивающих рамок (OBB) на датасете DOTA v1.5.

Ключевые особенности
Используемая модель: Ultralytics YOLOv8-obb.

Датасет: DOTA v1.5 (Object Detection in Aerial Images).

Формат аннотаций: Поддержка формата OBB (Oriented Bounding Box).

Среда: Оптимизировано для работы в Google Colab.

Функционал:

Автоматическая установка всех необходимых зависимостей (Ultralytics, Kagglehub).

Загрузка и подготовка данных напрямую с Kagglehub.

Монтирование Google Drive для сохранения результатов обучения.

Запуск обучения с возможностью настройки гиперпараметров (количество эпох, размер батча и т.д.).

Визуализация процесса обучения с помощью TensorBoard.

Построение и сохранение графиков метрик (mAP, loss).

Начало работы
Просто откройте Jupyter Notebook YOLO_train_on_DOTA_dataset.ipynb в Google Colab и запустите все ячейки по порядку. Убедитесь, что вы подключили GPU-среду выполнения.

Классы объектов
Модель обучена на 16 классах, включая:

plane (самолет)

baseball-diamond (бейсбольное поле)

bridge (мост)

ground-track-field (легкоатлетическое поле)

small-vehicle (малый транспорт)

large-vehicle (большой транспорт)

ship (корабль)

tennis-court (теннисный корт)

basketball-court (баскетбольная площадка)

storage-tank (резервуар)

soccer-ball-field (футбольное поле)

roundabout (кольцевая развязка)

harbor (гавань)

swimming-pool (бассейн)

helicopter (вертолет)

container-crane (контейнерный кран)
