# Обучение YOLOv8-OBB на датасете DOTA

Этот репозиторий содержит Jupyter Notebook (`YOLO_train_on_DOTA_dataset.ipynb`) для обучения модели **YOLOv8** с использованием ориентированных ограничивающих рамок (**OBB**) на датасете **DOTA v1.5**. Весь процесс обучения и настройки среды описан в одном файле, что делает его удобным для запуска в облачных средах, таких как Google Colab.

## Ключевые особенности

* **Модель:** Используется модель из библиотеки Ultralytics YOLOv8-obb.
* **Датасет:** Подготовлен для работы с датасетом DOTA v1.5 (Object Detection in Aerial Images).
* **Формат аннотаций:** Поддерживаются ориентированные ограничивающие рамки (OBB).
* **Среда:** Оптимизировано для работы в Google Colab, включая автоматическую установку зависимостей и монтирование Google Drive для сохранения результатов.
* **Функционал:**
    * Установка всех необходимых библиотек (Ultralytics, Kagglehub).
    * Загрузка и подготовка данных напрямую с Kagglehub.
    * Запуск обучения с настраиваемыми параметрами (эпохи, размер батча).
    * Визуализация процесса обучения с помощью TensorBoard.
    * Построение и сохранение графиков метрик (`mAP`, `loss`).

## Начало работы

1.  Откройте Jupyter Notebook `YOLO_train_on_DOTA_dataset.ipynb` в Google Colab.
2.  Убедитесь, что вы выбрали среду выполнения с GPU (Runtime > Change runtime type).
3.  Запустите все ячейки по порядку.

## Классы объектов

Модель обучена для обнаружения следующих 16 классов объектов:

* `plane`
* `baseball-diamond`
* `bridge`
* `ground-track-field`
* `small-vehicle`
* `large-vehicle`
* `ship`
* `tennis-court`
* `basketball-court`
* `storage-tank`
* `soccer-ball-field`
* `roundabout`
* `harbor`
* `swimming-pool`
* `helicopter`
* `container-crane`
