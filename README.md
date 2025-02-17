# inverted_index
Реализован простой инвертированный индекс для поиска документов для коллекции документов Cranfield.

## Описание
Код выполняет следующие функции для поиска документов в коллекции документов CranField.
1. Предварительно обрабатывает данные в текстовой коллекции (удаление стоп-слов, морфология, удаление знаков препинания и т. д.)
2. Создает инвертированный индекс для поиска соответствующих документов для каждого слова в словаре коллекции документов
3. Назначает веса каждому слову в документах/запросах с помощью схемы весов TF-IDF
4. Извлекает список соответствующих документов для заданного списка запросов, указанных в query.txt, и ранжирует полученные документы в порядке убывания их косинусного сходства с запросом
5. Вычисляет среднюю точность и полноту для верхних (10/50/100/500) полученных документов с помощью relevance.txt

Перед разбором алгоритма предлагаем пройти инструкцию по настройке `python` и библиотек для дальнейшего запуска приложения.

### Создайте виртуальное окружение (Python >= 3.8.1)

```
python -m venv venv
```

### Активируйте виртуальное окружение

```
source venv/bin/activate
```

### Загрузите нужные библиотеки

```
pip install -r requirements.txt
```

*Python 3 и nltk обязательны для запуска программы*

## Результаты 

### Запуск программы

```
python inverted_index.py <path_to_cranfieldDocs> <path_to_query_file> <path_to_relevance_file>
```

## Precision и Recall скор для запросов
----------------------------------------------------------------
#### Top 10 документов в ранк листе<br>
Query: 1 &nbsp;&nbsp; Pr: 0.0 &nbsp;&nbsp; Re:0.0<br>
Query: 2 &nbsp;&nbsp; Pr: 0.2 &nbsp;&nbsp; Re:0.13333333333333333<br>
Query: 3 &nbsp;&nbsp; Pr: 0.2 &nbsp;&nbsp; Re:0.13333333333333333<br>
Query: 4 &nbsp;&nbsp; Pr: 0.1 &nbsp;&nbsp; Re:0.05555555555555555<br>
Query: 5 &nbsp;&nbsp; Pr: 0.1 &nbsp;&nbsp; Re:0.05263157894736842<br>
Query: 6 &nbsp;&nbsp; Pr: 0.4 &nbsp;&nbsp; Re:0.2222222222222222<br>
Query: 7 &nbsp;&nbsp; Pr: 0.6 &nbsp;&nbsp; Re:0.6666666666666666<br>
Query: 8 &nbsp;&nbsp; Pr: 0.2 &nbsp;&nbsp; Re:0.5<br>
Query: 9 &nbsp;&nbsp; Pr: 0.1 &nbsp;&nbsp; Re:0.125<br>
Query: 10 &nbsp;&nbsp; Pr: 0.2 &nbsp;&nbsp; Re:0.08333333333333333<br>
#### Avg precision: 0.21000000000000002
#### Avg recall: 0.19720760233918128
----------------------------------------------------------------
#### Top 50 документов в ранк листе
Query: 1 &nbsp;&nbsp; Pr: 0.0 &nbsp;&nbsp; Re:0.0<br> 
Query: 2 &nbsp;&nbsp; Pr: 0.12 &nbsp;&nbsp; Re:0.4<br>
Query: 3 &nbsp;&nbsp; Pr: 0.14 &nbsp;&nbsp; Re:0.4666666666666667<br> 
Query: 4 &nbsp;&nbsp; Pr: 0.06 &nbsp;&nbsp; Re:0.16666666666666666<br>
Query: 5 &nbsp;&nbsp; Pr: 0.14 &nbsp;&nbsp; Re:0.3684210526315789<br>
Query: 6 &nbsp;&nbsp; Pr: 0.14 &nbsp;&nbsp; Re:0.3888888888888889<br>
Query: 7 &nbsp;&nbsp; Pr: 0.16 &nbsp;&nbsp; Re:0.8888888888888888<br>
Query: 8 &nbsp;&nbsp; Pr: 0.06 &nbsp;&nbsp; Re:0.75<br>
Query: 9 &nbsp;&nbsp; Pr: 0.12 &nbsp;&nbsp; Re:0.75<br>
Query: 10 &nbsp;&nbsp; Pr: 0.08 &nbsp;&nbsp; Re:0.16666666666666666<br>
#### Avg precision: 0.10200000000000001
#### Avg recall: 0.4346198830409357
----------------------------------------------------------------
#### Top 100 документов в ранк листе
Query: 1 &nbsp;&nbsp; Pr: 0.0 &nbsp;&nbsp; Re:0.0<br>
Query: 2 &nbsp;&nbsp; Pr: 0.09 &nbsp;&nbsp; Re:0.6<br>
Query: 3 &nbsp;&nbsp; Pr: 0.09 &nbsp;&nbsp; Re:0.6<br>
Query: 4 &nbsp;&nbsp; Pr: 0.06 &nbsp;&nbsp; Re:0.3333333333333333<br>
Query: 5 &nbsp;&nbsp; Pr: 0.13 &nbsp;&nbsp; Re:0.6842105263157895<br>
Query: 6 &nbsp;&nbsp; Pr: 0.09 &nbsp;&nbsp; Re:0.5<br>
Query: 7 &nbsp;&nbsp; Pr: 0.09 &nbsp;&nbsp; Re:1.0<br>
Query: 8 &nbsp;&nbsp; Pr: 0.03 &nbsp;&nbsp; Re:0.75<br>
Query: 9 &nbsp;&nbsp; Pr: 0.06 &nbsp;&nbsp; Re:0.75<br>
Query: 10 &nbsp;&nbsp; Pr: 0.04 &nbsp;&nbsp; Re:0.16666666666666666<br>
#### Avg precision: 0.068
#### Avg recall: 0.5384210526315789
----------------------------------------------------------------
#### Top 500 документов в ранк листе
Query: 1 &nbsp;&nbsp; Pr: 0.002 &nbsp;&nbsp; Re:1.0<br>
Query: 2 &nbsp;&nbsp; Pr: 0.03 &nbsp;&nbsp; Re:1.0<br>
Query: 3 &nbsp;&nbsp; Pr: 0.03 &nbsp;&nbsp; Re:1.0<br>
Query: 4 &nbsp;&nbsp; Pr: 0.032 &nbsp;&nbsp; Re:0.8888888888888888<br>
Query: 5 &nbsp;&nbsp; Pr: 0.038 &nbsp;&nbsp; Re:1.0<br>
Query: 6 &nbsp;&nbsp; Pr: 0.036 &nbsp;&nbsp; Re:1.0<br>
Query: 7 &nbsp;&nbsp; Pr: 0.018 &nbsp;&nbsp; Re:1.0<br>
Query: 8 &nbsp;&nbsp; Pr: 0.008 &nbsp;&nbsp; Re:1.0<br>
Query: 9 &nbsp;&nbsp; Pr: 0.016 &nbsp;&nbsp; Re:1.0<br>
Query: 10 &nbsp;&nbsp; Pr: 0.026 &nbsp;&nbsp; Re:0.5416666666666666<br>
#### Avg precision: 0.0236
#### Avg recall: 0.9430555555555555

## Подробное описание методов и функций
#### 1. tokenize_and_remove_punctuations:
Функция принимает текстовые данные в качестве параметра и выполняет следующие операции:
a. Удаляет знаки препинания из текстовых данных
b. Удаляет цифры из данных
c. Преобразует данные в нижний регистр
d. Токенизирует слова из текстовых данных
#### 2. get_stopwords:
Функция считывает распространенные английские стоп-слова из файла stopwords.txt, а затем возвращает их в виде списка
#### 3. parse_data:
Эта функция принимает необработанные данные из файлов SGML из коллекции cranfieldDocs и извлекает данные, находящиеся между тегами <TITLE> и <TEXT>, и возвращает содержимое
#### 4. remove_stop_words:
Функция принимает токенизированные слова и удаляет из них стоп-слова, а также слова, длина которых меньше 2 символов
#### 5. read_data:
Функция берет путь к каталогу crafieldDocs и считывает содержимое файлов, имеющихся в каталоге, вызывает функцию parse_data и возвращает список кортежей следующего формата – (document_no, text_data)
#### 6. calculate_tf:
Функция принимает список токенизированных слов и возвращает словарь с токеном в качестве ключа и tf_score для этого токена в качестве значения
#### 7. get_vocabulary:
Эта функция анализирует все слова из коллекции документов и возвращает словарь всех уникальных слов из коллекции
#### 8. stem_words:
Функция принимает список токенов и возвращает список слов с основой с помощью NLTKs PorterStemmer
#### 9. preprocess_data:
Функция принимает список кортежей, сгенерированных read_data, а затем выполняет следующие функции:
a. токенизирует и удаляет знаки препинания
b. удаляет стоп-слова
c. выделяет основу слов
d. удаляет стоп-слова после выделения корня и слова короче 2 символов
#### 10. calculate_idf:
Функция принимает весь словарь данных и вычисляет оценку idf для каждого слова в словаре для коллекции документов и возвращает словарь со словом в качестве ключа и оценкой idf в качестве значения
#### 11. calculate_tfidf:
Функция принимает словарь данных проанализированных и предварительно обработанных данных и словарь для idf_scores и возвращает словарь, содержащий ключ в качестве идентификатора документа и значение, которое является другим словарем со словами этого документа в качестве ключей и их оценками tf-idf в качестве значений
#### 12. preprocecss_queries:
Эта функция похожа на функцию предварительной обработки данных, она выполняет те же операции с запросами
#### 13. calculate_tfidf_queries:
Эта функция принимает предварительно обработанные запросы и словарь idf_scores, а затем выполняет расчет для вычисление оценок tfidf терминов запроса и возврат аналогичного словаря, возвращаемого функцией calculate_tfidf, но для терминов запроса
#### 14. generate_inverted_index:
Эта функция принимает словарь данных предварительно обработанных данных, создает и инвертирует индекс, а затем возвращает словарь с ключом в качестве каждого уникального слова из словаря документа и значением, имеющим список документов, в которых присутствует слово
#### 15. get_relevance:
Эта функция принимает путь к файлу, содержащему идентификаторы запроса и соответствующие им документы, а затем возвращает словарь с ключом в качестве идентификаторов документов и значением в качестве списка соответствующих ему документов
#### 16. find_precision_recall:
Эта функция принимает извлеченный список документов и соответствующий список документов запроса, вычисляет и возвращает точность и отзыв