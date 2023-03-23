# Models-and-architectures-of-programs-and-knowledge
Итоговый проект по моделям и архитектурам программ и знаний.
## Задача
Необходимо разработать парсер для сайта [`bsn.ru`](https://www.bsn.ru/build/sell/) и предсказать ценобразование по параметрам.
## Содержание
1. [`Эйрих_Финальный_проект.ipynb`](https://github.com/Michael-200/Models-and-architectures-of-programs-and-knowledge/blob/main/%D0%AD%D0%B9%D1%80%D0%B8%D1%85_%D0%A4%D0%B8%D0%BD%D0%B0%D0%BB%D1%8C%D0%BD%D1%8B%D0%B9_%D0%BF%D1%80%D0%BE%D0%B5%D0%BA%D1%82.ipynb) содержит код реализации задачи.
2. [`apartment.csv`](https://github.com/Michael-200/Models-and-architectures-of-programs-and-knowledge/blob/main/apartment.csv) содержит предобработанные данные.
### Данные
* `Type` - содержит информацию о типе квартиры `int`. Где:
  - 0 = студия
  - 1 = 1-комнатная
  - 2 = 2-комнатная
  - ...
  - 8 = 8-комнатная
* `Square` - содержит информацию о жилой площади `float`
* `Floor` - содержит информацию о этаже, на котором распологается квартира `int`
* `Metro` - содержит информацию о наличии метро `int`. Где:
  - 0 = метро отсутствует
  - 1 = есть метро
* `Price` - содержит информацию о цене новостройки в рублях `int`

Общее колличество данных `6600`, количество параметров `5`.

### Используемые модели
1. [`LinearRegression`](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html)
2. [`DecisionTreeRegressor`](https://scikit-learn.org/stable/modules/generated/sklearn.tree.DecisionTreeRegressor.html)
3. [`RandomForestRegressor`](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestRegressor.html)

### Метрики оценивания
1. [`Mean Absolute Error (MAE)`](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.mean_absolute_error.html)
2. [`Mean Squared Error (MSE)`](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.mean_squared_error.html)
3. [`R2 Score`](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.r2_score.html)

### Результат
В ходе работы было доказано 2 гипотезы:
1. Была опровергнута гипотеза о равенстве средних значений по критерию [`Флингера-Килина`](https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.fligner.html) в отоношении наличия метро на ценообразование новостроек.
2. Шкала Чеддока для определения силы кореляции цены и жилой площади по [`Пирсону`](https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.pearsonr.html) показала заметную корреляцию между этими параметрами. 
