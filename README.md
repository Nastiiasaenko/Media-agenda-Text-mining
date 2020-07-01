# Введение  
Краткое описание работы и основные результаты можно посмотреть в этой [презентации](https://drive.google.com/file/d/19g0yzj_QnY03k6_-aXdXh88I50c5HTn0/view?usp=sharing).

Основная практическая цель проекта - с помощью методов тематического моделирования и машинного обучения определить тематическое содержание новостных повесток. 

# Ход работы  
### Данные 

Данные для исследования были собраны  в ручную с помощью API VK и публичного API New York Times. Также был использован готовый [датасет](https://www.kaggle.com/snapcrack/all-the-news) по американским новостям  c сайта [kaggle](kaggle.com).
В итоговую выборку попали 5 российских новостных изданий ( всего 567307 новостей для классификации) и около 15 американских новостных изданий( всего 674654 новостей). 

### Предобработка текстовых данных 

Первый шаг - предобработка текстов( лемматизация, нормализация, токенизация). Пример preprocessing функции можно найти в файле **preprocessor .ipynb**

На следующем шаге было решено провести графовый анализ комбинаций слов, в итоге получились следующие графы по разным новостным корпусам:

![alt text](/images/graphone.PNG)

![alt text](/images/americannews.png)

## Тематическое моделирование

В тематическом моделировании использовалась в основном классическая модель LDA, а также ее дополнение в R  - Structural Topic Modelling. 

Последовательная реализация LDA в следующих ноутбуках:

* [Russian_news_LDAexploration.ipynb](https://github.com/Nastiiasaenko/Agenda-setting_strategies/blob/master/Russian_news_LDAexploration.ipynb)
* [Russia_finale_finale.ipynb](https://github.com/Nastiiasaenko/Agenda-setting_strategies/blob/master/Russia_finale_finale.ipynb)
* [American_news.final.ipynb](https://github.com/Nastiiasaenko/Agenda-setting_strategies/blob/master/American_news.final.ipynb)

### Структурное тематическое моделирование

Модель STM была реализована на корпусе новостей New York Times, где в качестве ковариатов была взята категориальная переменная ( категории - внешняя и внутренняя повестка) и время. 

Реализация STM подробно представлена [здесь](https://htmlpreview.github.io/?https://github.com/Nastiiasaenko/Agenda-setting_strategies/blob/master/stm_model.html).

# Результаты 
Для каждого кластера тем были получены wordclouds по каждой теме, по которым можно было бы судить о смысле той или иной темы, например:
![alt text](/images/sexualass.png)

Темы далее группировались в более широкие кластеры:
![alt text](/images/Anewspie.png)

В дальнейшем брались специфические темы и сравнивалось их освещения в разных источниках:
![alt-text-1](/images/hill.png) ![alt-text-2](/images/protests.png)


Полный процесс исследования и подробные результаты представлены в [презентации](https://drive.google.com/file/d/19g0yzj_QnY03k6_-aXdXh88I50c5HTn0/view?usp=sharing), а также в тексте исследования( обращаться к автору). 






