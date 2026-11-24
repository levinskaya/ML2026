# Как забрать ноутбук и запустить у себя

Репозиторий: https://github.com/levinskaya/ML2026

Ноутбук: `plans/notebooks/lecture7_faces_pca_clustering.ipynb`.

## Вариант 1. Без установки — Colab

Открыть ссылку:

```
https://colab.research.google.com/github/levinskaya/ML2026/blob/main/plans/notebooks/lecture7_faces_pca_clustering.ipynb
```

Colab создаст вашу копию ноутбука. Можно менять параметры и запускать ячейки.
Первый запуск скачает LFW (~200 МБ).

## Вариант 2. Скачать и запустить локально

1. На странице GitHub: **Code → Download ZIP**.
2. Распаковать архив.
3. Установить Python 3.10 или новее.
4. В папке проекта выполнить:

```bat
python -m pip install -r requirements.txt
```

5. Запустить Jupyter:

```bat
jupyter lab
```

6. Открыть `plans/notebooks/lecture7_faces_pca_clustering.ipynb` и выбрать ядро Python 3.

### Через git

```bat
git clone https://github.com/levinskaya/ML2026.git
cd ML2026
python -m pip install -r requirements.txt
jupyter lab
```

## Вариант 3. Binder

```
https://mybinder.org/v2/gh/levinskaya/ML2026/HEAD?labpath=plans/notebooks/lecture7_faces_pca_clustering.ipynb
```

Binder собирает окружение несколько минут; ничего устанавливать не нужно.

## Что делать в ноутбуке

В верхнем блоке «Пульт лектора» менять:

- `N_COMPONENTS` — число компонент PCA;
- `N_CLUSTERS` — число кластеров;
- `EPS` и `MIN_SAMPLES` — параметры DBSCAN;
- `N_SHOW` — сколько лиц показывать.

После изменения перезапускать ячейку и следующую за ней.

## Если нет интернета

`fetch_lfw_people` скачивает набор при первом запуске. Без интернета ноутбук
не сможет загрузить LFW. Варианты:

- запустить один раз на машине с интернетом; данные сохранятся в
  `C:\Users\<пользователь>\scikit_learn_data`;
- скопировать папку `scikit_learn_data` на другой компьютер;
- использовать Colab/Binder, где интернет есть.

## Частые проблемы

- `ModuleNotFoundError` — не установлены зависимости: `python -m pip install -r requirements.txt`.
- Ноутбук не видит ядро — выбрать Python 3 в правом верхнем углу.
- Долго работает агломеративная кластеризация — это O(N²); уменьшить число объектов
  или использовать подвыборку.
- Ошибка загрузки LFW — проверить интернет и свободное место (~200 МБ).
