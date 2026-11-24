# Живой ноутбук к лекции 7: лица, PCA и кластеризация

Файл: `lecture7_faces_pca_clustering.ipynb`.

Набор Labeled Faces in the Wild описан в учебнике на с. 164; пример кластеризации
лиц — на с. 213.

## Запуск из GitHub

- **Colab:**
  https://colab.research.google.com/github/levinskaya/ML2026/blob/main/plans/notebooks/lecture7_faces_pca_clustering.ipynb
- **Binder:**
  https://mybinder.org/v2/gh/levinskaya/ML2026/HEAD?labpath=plans/notebooks/lecture7_faces_pca_clustering.ipynb
- **GitHub Codespaces:** Code → Codespaces → Open.

GitHub сам ноутбук не исполняет — он только показывает файл.
Первый запуск в Colab/Binder скачивает LFW (~200 МБ), поэтому нужен интернет.

## Локальный запуск

Окружение подготовлено: `.venv` в корне рабочего пространства и ядро `ml-course`.
Команды для Windows `cmd`:

```bat
cd /d d:\AIGlobalStorage\MAI\ML
.venv\Scripts\activate
cd plans\notebooks
jupyter lab
```

- В Jupyter выберите ядро **Python (ML course)**.
- VS Code: открыть папку, открыть ноутбук, выбрать ядро `Python (ML course)`.
- Версии пакетов: `requirements-notebooks.txt`; минимальные — `requirements.txt`.

## Порядок ячеек

1. Импорты и проверка Colab.
2. «Пульт лектора»: `N_COMPONENTS`, `N_CLUSTERS`, `EPS`, `MIN_SAMPLES`, `N_SHOW`, `RANDOM_STATE`.
3. Загрузка LFW: 3023 изображения 87 × 65, 62 человека, 5655 признаков.
4. `show_faces` и `show_cluster_examples`.
5. PCA и объяснённая дисперсия.
6. Собственные лица.
7. Восстановление по `KS = [10, 50, 100, 300]`.
8. K-средних: размеры, центры, примеры.
9. Агломеративная: 10 кластеров, дендрограмма, прогон с 40.
10. DBSCAN: метки, шум, примеры, перебор `eps`.
11. ARI между разбиениями и силуэт.

## Что менять на лекции

| Параметр | Значения | Что показать |
| --- | --- | --- |
| `N_COMPONENTS` | 10, 50, 100, 300 | собственные лица и дисперсия |
| `KS` | 10, 50, 100, 300 | качество восстановления |
| `N_CLUSTERS` | 5, 10, 20 | центры k-средних |
| `EPS` | 3, 7, 15 | кластеры и доля шума |
| `MIN_SAMPLES` | 2, 3, 10 | чувствительность DBSCAN |
| `N_SHOW` | 5, 8, 10 | число лиц в ряду |

После изменения параметра перезапускайте ячейку и следующую за ней.

Числа кластеров могут отличаться от книги: версия scikit-learn и отсутствие
дополнительного масштабирования компонент влияют на пространство признаков.
Смотрите на поведение алгоритма, а не на точное число кластеров.
