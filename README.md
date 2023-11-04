# Postman
**Основное назначение Postman** - облегчить разработку, тестирование и документирование API. С его помощью можно отправить данные в запросе и проверить полученный ответ. Также у него есть много других интересных возможностей. Можно например сохранять запросы в папки и коллекции, удобно параметризовывать запросы. Запускать коллекции с помощью Collection Runner и использовать их как автоматизированные тесты. Postman позволяет проектировать дизайн API и создавать на его основе Mock-сервер.   
Тестировщики, с помощью Postman могут отправлять **HTTP/HTTPS запросы** к сервисам и получать ответы от них. С помощью такого подхода можно протестировать бэкенд сервисы и убедиться, что они работают корректно. С помощью Postman можно выполнять запросы к различным API, таким как REST, SOAP и GraphQL.     
**Основная функциональность Postman** - возможность создания и отправки запросов к API для проверки его функциональности и получения данных. Для этого не потребуется писать код или команды в терминале. В интерфейсе Postman вы создаете запрос, нажимаете кнопку отправить и получаете ответ от API. API расшифровывается как Application Programming Interface или **программный интерфейс приложения**. С его помощью мы можем  получить доступ к возможностям другого приложения и обмениваться с ним данными. Такое приложение называется **API сервером**. Отправка запросов и получение ответов происходит через интернет с помощью **протокола HTTP**. Приложение, которое отправляет запрос, называется **клиентом**. Это может быть **мобильное приложение, web сайт или другой сервис**.   
Запрос всегда содержит **URL** вызываемого эндпоинта **API и HTTP** метод запроса. **Эндпоинт это URL**, который предоставляет доступ к определенной функциональности сервиса. Он позволяет клиентским приложениям *отправлять запросы на сервер и получить доступ к данным или выполнить определенные операции*. Каждый эндпоинт обычно связан с определенным HTTP-методом, таким как например **GET или POST**, который определяет тип операции, которую можно выполнить с помощью этого эндпоинта. Наиболее часто используются следующие методы:  
- POST - для добавления новых данных  
- GET - для чтения данных
- PUT - для обновления данных
- PATCH - для частичного обновления данных
- DELETE - для удаления данных  
  
### Чек-лист проверок
**Общий чек-лист:**    
1. Правильное тело (пример)  
2. Бизнес-логика: позитив, негатив   
3. Различные параметры (обязательность, работа параметров)   
4. Перестановка мест слагаемых (заголовки, тело)   
5. Регистрозависимость (заголовки, тело)   
6. Ошибки: не well formed xml / json   

**Где искать параметры:**  
- В URL  
- В заголовках   
- В теле запроса   
- Комбинация   

**Тестирование параметров:**   
1. Правильный параметр (из примера)   
2. Обязательность (что, если параметр не указать?)   
3. Бизнес-логика (тест-дизайн)   
4. Регистрозависимость (если параметр текстовый)   
5. Перестановка местами   

**Тестирование заголовков:**  
- Заголовки из документации работают (в целом)   
- А если какой-то не передать? (обязательность)   
- А если передать, но неправильно? (текст ошибки)   
- Позитивные тесты по доке   
- Регистронезависимость заголовков   

**Что смотрим в ответе:**  
- Status Code   
- Body   

**В теле смотрим:**   
1. Какие поля вернулись в ответе?   
2. Значения в полях   
3. Текст ошибок    

**Поля в ответе нужно:**   
- сравнить с ТЗ   
- сравнить между собой SOAP \ REST   
