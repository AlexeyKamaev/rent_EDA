# How Much Is The ....?

![img](img/text-to-image-generated-AAIREAltdLOGO.png)
Вы начали свою работу в отделе **аналитики и оптимизации** международного сервиса по продаже и аренде жилой недвижимости **Alyona Ivanovna Real Estate Agency** или более известного как **AI REA Ltd**. Сервисом пользуются сотни тысяч клиентов, в том числе студенты, из разных городов и стран.

Вашему отделу руководство поставило задачу: 
- создать модель машинного обучения, которая будет оценивать квартиры и предлагать стоимость аренды максимально похожую на ту, которую выставляют люди 
- технически задача предполагает улучшить метрику качества модели **MAPE** с 50% до 30% и менее, т.к. эта метрика показывает *среднюю абсолютную ошибку в процентах* - очень понятную для менеджеров

В качестве пилотного региона выбрана **Москва** (а не родной город основательницы - Петербург).

Вашей группе задача сформулирована более конкретно. Вам необходимо подготовить данные для разработчиков машинного обучения. Они на результатах вашей работы будут учить модели предсказывать стоимость аренды квартир. От вас будет зависеть качество их работы!

**Вам доверили самую сложную часть работы с данными!**

Вам нужно подготовить датасет для обучения, используя таблицу, которую выгрузили дата инженеры (см. в разделе [Выгрузка данных](#выгрузка-данных))


## Релизы 

Реализовать проект необходимо в несколько итераций, где каждый релиз - это уже полноценный этап работы:

### **Релиз 1.0**
Коммит* с результатами EDA или разведочного анализа данных - Exploratory Data Analysis. Например, html-отчёт **EDA.html** сформированный из **EDA.ipynb**. Это необходимо, чтобы топы компании могли понять из отчёта что из себя представляют данные, больше графиков и агрегированной информации, минимум кода в html файле
- состав репозитория на данном релизе:
   - **README.md** описание задачи над которой вы работаете, а также в каком составе
   - **EDA.html** - отчет из графиков и текстового описания
   - **EDA.ipynb** - jupyter notebook, в котором вы делали графики и изучали данные

### **Релиз 2.0** 
Нужно закоммитить результаты очистки данных от пропусков.
- состав репозитория дополняется:
   - **preprocessing.ipynb** - jupyter notebook файл, где показан процесс обработки данных
   - **data.csv** - отвечающий критериям:
      - названия колонок **на английском** языке в одно/несколько слов с нижним подчёркиванием
      - в каждой колонке должны **отсутствовать** пропущенные значения (NaN, None и т.д.)

### **Релиз 3.0** 
Финальный. Коммит данных с новыми фичами (feature engineering) - это тот же файл **preprocessing.ipynb**, но уже отрефакторенный с прошлого релиза и файл **data.csv** c новыми колонками. Но не забудьте оставить колонку с **id** объявления, дабы можно было сравнить результаты разных команд.
- в составе репозитория изменения:
   - **README.md** добавлены основные выводы и иллюстрации
   - **data.csv** - полностью отвечающий предыдущим и новым критериям:
      - все значения внутри данных должны быть **только** численного типа (int или float)
      - должны отсутствовать полные дубликаты объявлений, только **уникальные объявления**
   - **preprocessing.ipynb** - jupyter notebook файл, где показан весь процесс обработки данных с комментариями, которые объясняют мотивацию принятия тех или иных решений в ходе работы
___

Для представления результата вам останется только скинуть ссылку на **ваш репозиторий** в рабочий slack до назначенного срока, иначе вас уволят 😦

___
*коммиты лучше всего сопровождать сообщением, которое развернуто и понятно раскрывает его содержание и суть в рамках одного небольшого предложения, например: 
```
git commit -m 'Release 1. Added EDA report pdf file and refactored contributors at README.md'
```

## Выгрузка данных

Таблица доступна по [ссылке](https://drive.google.com/drive/folders/1fiFYfUzHqdt8ASeYIprfGAWNXn4TAPfO?usp=sharing)
- более 23 тысяч записей реальных объявлений
- доступные колонки: `['ID  объявления', 'Количество комнат', 'Тип', 'Метро', 'Адрес',
       'Площадь, м2', 'Дом', 'Парковка', 'Цена', 'Телефоны', 'Описание',
       'Ремонт', 'Площадь комнат, м2', 'Балкон', 'Окна', 'Санузел',
       'Можно с детьми/животными', 'Дополнительно', 'Название ЖК',
       'Серия дома', 'Высота потолков, м', 'Лифт', 'Мусоропровод',
       'Ссылка на объявление']`

## Помощь коллег

Коллеги из соседней команды, которые решали подобную задачу, скинули вам ссылки "на почитать", чтобы вам было проще справиться с заданием:

1. "Почистить" данные от NaN 
   - 📝  https://loginom.ru/blog/missing
   - 📝  https://pythobyte.com/python-how-to-handle-missing-dataframe-values-in-pandas-d56af629/
2. Обработать категориальные данные
   - 📝  https://dyakonov.org/2016/08/03/python-категориальные-признаки/
   - 📝  https://habr.com/ru/post/511132/
3. Нормировка
   - 📝  https://habr.com/ru/post/527334/

Дополнительно, они скинули ещё пару важных ссылок:
- 📝 http://blog.datalytica.ru/2018/04/blog-post.html

Среди которых их прошлый проект по оценке стоимости квартиры (**продажи**, не аренды): 
- 🐍 [Проект по оценке рыночной стоимости квартиры](https://github.com/maksimkuragin/Kvocenshik)


