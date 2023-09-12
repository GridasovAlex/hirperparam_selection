# Hirperparam selection
Пробую различные методы подбора гиперпараметров на примере таких моделей как *LogisticRegression* и *RandomForestClassifier*

## Кейс:
Опробовать такие методы подбора гмперпараметров, как:
  * Подбор по сетке гипермпараметров(GridSearchCV)
  * Случаыйный подбор(RandomizedSearchCV)

И более продвинутые методы:
  * hyperopt
  * optuna

## Выводы:
* GridSearchCV	

    ✔️ Простой в использовании, идеален для небольшой сетки гиперпараметров

    ✔️ Встроенная кросс-валидация

    ✔️ Включает построение итоговой модели на всей обучающей выборке 

    ⛔️ Перебирает просто все комбинации заданной сетки гиперпараметров 

    ⛔️  Требует много времени и вычислительных ресурсов
* RandomizedSearchCV

    ✔️ Эффективнее и экономичнее gridsearchcv
    
    ✔️ Можно задать количество рассматриваемых комбинаций

    ⛔️ Просто выбирает рандомные комбинации гиперпараметров без учёта результатов прошлых итераций
* Hyperopt

    ✔️ Быстрее и эффективнее, чем классические методы перебора (GSCV и RSCV)

    ✔️ Учитывает результаты прошлых итераций — байесовский оптимизатор

    ✔️ Можно отслеживать дополнительную информацию на каждом шаге с помощью класса Trials

    ✔️ Возможность построения условного пространства поиска гиперпараметров и даже моделей

    ⛔️ Старая документация, плохо с поддержкой и обновлением 

    ⛔️ Способен только минимизировать

    ⛔️ Непростой синтаксис описания пространства гиперпараметров (особенно с использованием условных реализаций)

* Optuna

    ✔️ Один из самых быстрых и эффективных

    ✔️ Специально разработан для оптимизации гиперпараметров 

    ✔️ Простой в использовании

    ✔️ Относительно новый фреймворк с хорошей документацией 

    ✔️ Учитывает результаты прошлых итераций — байесовский оптимизатор 

    ✔️ Встроенная визуализация результатов

    ✔️ Возможность явно задавать максимизацию или минимизацию функции качества

    ⛔️ Удаление «плохих» точек пространства из рассмотрения
  
    ⛔️ Не стоит полностью полагаться: важно с умом определять пространство поиска, что может значительно сократить время расчётов.