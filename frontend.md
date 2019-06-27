Тест для разработчика в компанию Tripster.

Нужно скачать этот файл, заполнить соответствующие поля и прислать модифицированный md-файл по почте.


### 1. Напишите, какие акутальные типы http запросов (Request methods) вы знаете?

~~~
# Напишите тут типы запросов.

~~~


### 2. Нужно заполнить таблицу действий над ресурсами согласно REST-подходу.

*Поставьте «галочки» в нужных ячейках*.

|                                    | /books | /books/17 |
| ---------------------------------- | ------ | --------- |
| Получить коллекцию                 |        |           |
| Создать новую запись о книге       |        |           |
| Изменить отдельную запись о книге  |        |           |
| Удалить всю коллекцию книг         |        |           |
| Удалить отдельную запись о книге   |        |           |
| Получить запись об отдельной книге |        |           |


### 3. Заполните таблицу сложности алгоритмов

*Поставьте «галочки» в нужных ячейках*.

|                                                    | O(1) | O(log n) | O(N) | O(n log n) | O(n^2) | Другой вариант |
| -------------------------------------------------- | ---- | -------- | ---- | ---------- | ------ | -------------- |
| Быстрая сортировка (в среднем)                     |      |          |      |            |        |                |
| Вставка в хеш-таблицу                              |      |          |      |            |        |                |
| Поиск в связном списке                             |      |          |      |            |        |                |
| Двоичный поиск в отсортированном массиве           |      |          |      |            |        |                |
| Вставка в хеш-таблицу в случае коллизии            |      |          |      |            |        |                |
| Удаление из массива (со сдвигом)                   |      |          |      |            |        |                |
| Поиск в хеш-таблице                                |      |          |      |            |        |                |


### 4. Что может происходить в браузере, когда пользователь вводит адрес (https://ya.ru) в адресной строке и нажимает Enter?


*Поставьте «галочки» в нужных ячейках*.

|                                       |      |
| ------------------------------------- | ---- |
| Сжатие исходных JS кода               |      |
| Проверка сертификатов                 |      |
| Парсинг HTML                          |      |
| Запуск PHP скриптов сайта             |      |
| Исполнение Javascript                 |      |
| Парсинг CSS                           |      |
| Загрузка данных html страницы по HTTP |      |
| Деобфускация JS кода                  |      |
| TLS handshake                         |      |
| DNS запрос по UDP                     |      |
| Построение DOM-дерева                 |      |


### 5. Что такое promise?
~~~
// ответьте тут

~~~

### 6. Какие реализации реактивности вам знакомы? Чем отличается реактивность в Angular1, Vue2 и Vue3?
~~~
// ответьте тут

~~~

### 7. SSR(Server Side Rendering) vs CSR(Client Side Rendering).
*Опишите плюсы и минусы обоих подходов и напишите какие реализации данного подхода вы знаете.*
~~~
// ответьте тут

~~~

### 8. Используете ли вы современные версии стандарта ECMA? Какими инструментами для этого пользуетесь?
~~~
// ответьте тут

~~~


### 9. Чем будут отличаться поведения трёх реализаций?
~~~javascript
const fetchData = async id => {
    return {
        response1: await fetchAPI1(id),
        response2: await fetchAPI2(id),
    }
}
~~~
~~~javascript
const fetchData = async id => {
    const request1 = fetchAPI1(id);
    const request2 = fetchAPI2(id);
    return {
        response1: await request1,
        response2: await request2,
    }
}
~~~
~~~javascript
const fetchData = async id => {
    const request1 = fetchAPI1(id);
    const request2 = fetchAPI2(id);
    const [response1, response2] = await Promise.all([request1, request2]);
    return {response1, response2};
}
~~~

~~~
// ответьте тут

~~~


### 10. Сделайте рефакторинг кода.
*приветствуются коментарии с описанием что и для чего изменено*

~~~javascript
function Journal(date) {
  this.date = date;

  this.formatDate = function(date) {
    return date.getDate() + '.' + (date.getMonth() + 1) + '.' + date.getFullYear();
  };

  this.getTitle = function() {
    return "Выпуск от " + this.formatDate(this.date);
  };

}

Journal.compare = function(journalA, journalB) {
  return journalA.date - journalB.date;
};

// использование:
var journals = [
  new Journal(new Date(2012, 1, 1)),
  new Journal(new Date(2012, 0, 1)),
  new Journal(new Date(2011, 11, 1))
];

function findMin(journals) {
  var min = 0;
  for (var i = 0; i < journals.length; i++) {
    if (Journal.compare(journals[min], journals[i]) > 0) min = i;
  }
  return journals[min];
}

alert( findMin(journals).getTitle() );
~~~
