# Лекция 7. Лица, PCA и кластеризация

Материалы к лекции по главе 3 книги «Введение в машинное обучение с помощью Python».

## Запуск ноутбука

- **Colab:**
  https://colab.research.google.com/github/aaguberniev/lect17/blob/main/plans/notebooks/lecture7_faces_pca_clustering.ipynb
- **Binder:**
  https://mybinder.org/v2/gh/aaguberniev/lect17/HEAD?labpath=plans/notebooks/lecture7_faces_pca_clustering.ipynb
- **GitHub Codespaces:** Code → Codespaces → Open.

Первый запуск скачивает Labeled Faces in the Wild (~200 МБ).

## Что внутри

- `plans/notebooks/lecture7_faces_pca_clustering.ipynb` — живой ноутбук: LFW, PCA, собственные лица, восстановление, k-средних, агломеративная, DBSCAN.
- `plans/notebooks/README_Лекция_7.md` — как вести демонстрацию и что менять.
- `requirements.txt` — зависимости для Binder/Codespaces.
- `.devcontainer/devcontainer.json` — окружение Codespaces.

## Локальный запуск

```bat
python -m pip install -r requirements.txt
jupyter lab
```

Или открыть ноутбук в VS Code с ядром Python 3.
