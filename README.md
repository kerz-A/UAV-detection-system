# YOLOv8-OBB: Обучение на датасете DOTA v1.5

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/your_username/your_repo_name/blob/main/YOLO_train_on_DOTA_dataset.ipynb)
![Ultralytics](https://img.shields.io/badge/Ultralytics-YOLOv8-00FFFF?logo=ultralytics)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)
![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Colab](https://img.shields.io/badge/Google%20Colab-T4%20GPU-FF9A00)

Jupyter Notebook для обучения модели **YOLOv8-OBB** (Oriented Bounding Boxes) на аэрокосмическом датасете **DOTA v1.5**. Полностью готов к запуску в Google Colab.

## 📋 Оглавление

- [Особенности](#-особенности)
- [Датасет DOTA v1.5](#-датасет-dota-v15)
- [Технический стек](#-технический-стек)
- [Быстрый старт](#-быстрый-старт)
- [Структура проекта](#-структура-проекта)
- [Использование](#-использование)
- [Гиперпараметры](#-гиперпараметры)
- [Результаты](#-результаты)
- [Вклад в проект](#-вклад-в-проект)
- [Лицензия](#-лицензия)
- [Полезные ссылки](#-полезные-ссылки)

## ✨ Особенности

- **🔄 Полный пайплайн:** Все этапы от установки зависимостей до инференса
- **📥 Автоматическая загрузка данных:** Использование `kagglehub` для загрузки DOTA v1.5 в формате YOLO OBB
- **⚙️ Подготовка для YOLOv8:** Автогенерация YAML-файла конфигурации
- **📊 Мониторинг обучения:** Интеграция с TensorBoard в реальном времени
- **💾 Сохранение результатов:** Автосохранение на Google Drive
- **🎯 Работа с OBB:** Нативная поддержка ориентированных bounding box'ов

## 📊 Датасет DOTA v1.5

DOTA (Dataset for Object deTection in Aerial images) — крупномасштабный датасет для детекции объектов на аэроснимках.

**16 классов объектов:**
- `plane`, `baseball-diamond`, `bridge`, `ground-track-field`
- `small-vehicle`, `large-vehicle`, `ship`, `tennis-court`
- `basketball-court`, `storage-tank`, `soccer-ball-field`, `roundabout`
- `harbor`, `swimming-pool`, `helicopter`, `container-crane`

**Формат разметки:** OBB (x1, y1, x2, y2, x3, y3, x4, y4)

## 🛠 Технический стек

- **Язык:** Python 3.8+
- **Фреймворк:** Ultralytics YOLOv8
- **Формат разметки:** OBB (ориентированные bounding box'ы)
- **Инфраструктура:** Google Colab с GPU T4
- **Визуализация:** TensorBoard
- **Хранение данных:** Google Drive

## 🚀 Быстрый старт

1. **Откройте в Colab:** Нажмите на кнопку "Open in Colab" выше
2. **Активируйте GPU:** `Среда выполнения → Сменить среду выполнения → T4 GPU`
3. **Запустите все ячейки:** Выполните последовательно все ячейки ноутбука
4. **Настройте параметры:** Измените гиперпараметры при необходимости
5. **Мониторьте:** Следите за обучением через TensorBoard

## 📁 Структура проекта
YOLOv8_OBB_Models/
└── YOLOv8_DOTA_OBB_Training/
└── exp1_n/
├── weights/ # Веса модели (best.pt, last.pt)
├── results.png # Графики обучения
├── results.csv # Метрики обучения
└── events.out.tfevents.* # Логи TensorBoard


## 💻 Использование

### Базовый запуск

```python
# Загрузка предобученной модели
model = YOLO('yolov8n-obb.pt')

# Запуск обучения
results = model.train(
    data='dota_obb.yaml',
    epochs=50,
    imgsz=1024,
    batch=4,
    device=0
)

# Доступные архитектуры
MODELS = [
    'yolov8n-obb.pt',  # Nano (наименьшая)
    'yolov8s-obb.pt',  # Small
    'yolov8m-obb.pt',  # Medium
    'yolov8l-obb.pt',  # Large
    'yolov8x-obb.pt'   # XLarge (наибольшая)
]

training_params = {
    'epochs': 50,           # Количество эпох
    'imgsz': 1024,          # Размер изображения
    'batch': 4,             # Размер батча
    'device': 0,            # Использовать GPU (0) или CPU
    'workers': 8,           # Количество workers для загрузки данных
    'cache': True,          # Кэширование данных
    'save': True,           # Сохранять чекпоинты
    'project': 'YOLOv8_OBB_Models',  # Директория проекта
    'name': 'exp1_n'        # Имя эксперимента
}

Рекомендации по настройке

    Память GPU: Уменьшите batch при ошибках CUDA out of memory

    Скорость обучения: Увеличьте workers для ускорения загрузки данных

    Точность: Используйте larger модели (s, m, l) для лучшей accuracy

📈 Результаты

Ноутбук автоматически сохраняет:

    Лучшие веса модели (best.pt)

    Последние веса (last.pt)

    Графики обучения (loss, metrics)

    CSV с метриками

    Логи TensorBoard

🤝 Вклад в проект

Приветствуются contributions!

    Форкните репозиторий

    Создайте feature branch: git checkout -b feature/amazing-feature

    Сделайте commit: git commit -m 'Add amazing feature'

    Запушьте branch: git push origin feature/amazing-feature

    Откройте Pull Request

📜 Лицензия

Распространяется под лицензией MIT. Подробнее см. в файле LICENSE.
🔗 Полезные ссылки

    Официальная документация YOLOv8

    DOTA Dataset Official Page

    Kaggle: DOTA v1.5 YOLO OBB Format

    Ultralytics GitHub
