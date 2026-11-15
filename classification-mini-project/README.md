# Порівняння класичних моделей класифікації
## Постановка задачі
Бінарна класифікація пацієнтів за наявністю ознак серцевого захворювання (позитивний клас — `1`). Основна метрика — `F1-міра`
## Набір даних
Heart Disease Dataset (UCI ML Repository): 303 об'єкти, 13 вхідних ознак (5 числових та 8 категоріальних), цільова змінна `target`
## Методика експерименту
- фіксований train/test split (80/20, `stratify=y`, `random_state=42`);
- підбір гіперпараметрів лише на train через 5-кратну `StratifiedKFold`;
- одноразове фінальне оцінювання на test
## Підготовка даних
- `SimpleImputer` (медіана / мода);
- `StandardScaler` та `OneHotEncoder` у `ColumnTransformer` + `Pipeline`
## Досліджені моделі
- Logistic Regression, k-NN, Gaussian Naive Bayes, LDA, QDA, SVM
## Фінальна модель і test-результат
За результатами крос-валідації обрано модель-переможця з таблиці `reports/cv_model_comparison.csv` (детальні метрики збережено у `reports/final_test_metrics.csv`)

- [Відкрити Notebook](notebooks/PR04_Mylka_D.ipynb)
