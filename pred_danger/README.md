# python-flask-docker
Итоговый проект курса "Машинное обучение в бизнесе"

Стек:

ML: sklearn, pandas, numpy
API: flask
Данные: https://www.kaggle.com/code/philculliton/nlp-getting-started-tutorial/input

Задача: Cоздать модель машинного обучения, которая предсказывает, какие твиты посвящены реальным бедствиям, а какие нет. Бинарная классификация

Используемые признаки:

- text - текст твита
- keyword - конкретное ключевое слово из твита

Преобразования признаков: OHEEncoder, TfidfVectorizer

Модель: LogisticRegression()

### Клонируем репозиторий и создаем образ
```
$ git clone https://github.com/andrey-w/ml_business/tree/lesson9.git
$ cd pred_danger
$ docker build -t w_lander/pred_danger .
```

### Запускаем контейнер

Здесь Вам нужно создать каталог локально и сохранить туда предобученную модель (<your_local_path_to_pretrained_models> нужно заменить на полный путь к этому каталогу)
```
$ docker run -d -p 8180:8180 -p 8181:8181 -v <your_local_path_to_pretrained_models>:/app/app/models w_lander/pred_danger
```

### Переходим на localhost:8181
