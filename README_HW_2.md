<img align='right' src="https://media.giphy.com/media/836HiJc7pgzy8iNXCn/giphy.gif" width="430" />

# HW_2 Postman


http://162.55.220.72:5005/first
1. Отправить запрос.
2. Статус код 200
3. Проверить, что в body приходит правильный string.

http://162.55.220.72:5005/user_info_3
1. Отправить запрос.
2. Статус код 200
3. Спарсить response body в json.
4. Проверить, что name в ответе равно name s request (name вбить руками.)
5. Проверить, что age в ответе равно age s request (age вбить руками.)
6. Проверить, что salary в ответе равно salary s request (salary вбить руками.)
7. Спарсить request.
8. Проверить, что name в ответе равно name s request (name забрать из request.)
9. Проверить, что age в ответе равно age s request (age забрать из request.)
10. Проверить, что salary в ответе равно salary s request (salary забрать из request.)
11. Вывести в консоль параметр family из response.
12. Проверить что u_salary_1_5_year в ответе равно salary*4 (salary забрать из request)
```
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

var jsonData = pm.response.json();
console.log(jsonData)

var req_body = request.data
var u_name = req_body.name
var u_age = req_body.age
var u_salary = req_body.salary

pm.test("user_name", function () {
    pm.expect(jsonData.name).to.eql("Vlad");
});

pm.test("user_age", function () {
    pm.expect(jsonData.age).to.eql("30");
});

pm.test("user_salary", function () {
    pm.expect(jsonData.salary).to.eql(550);
});

pm.test("user_name_automative", function () {
    pm.expect(jsonData.name).to.eql(u_name);
});

pm.test("user_age_automative", function () {
    pm.expect(jsonData.age).to.eql(u_age);
});

pm.test("user_salary_automative", function () {
    pm.expect(jsonData.salary).to.eql(+u_salary);
});

console.log(jsonData.family)

var salary_1_5 = jsonData.family.u_salary_1_5_year
pm.test("user_salary_1_5", function () {
    pm.expect(salary_1_5).to.eql(Number(u_salary*4));
});
```
___
http://162.55.220.72:5005/object_info_3
1. Отправить запрос.
2. Статус код 200
3. Спарсить response body в json.
4. Спарсить request.
5. Проверить, что name в ответе равно name s request (name забрать из request.)
6. Проверить, что age в ответе равно age s request (age забрать из request.)
7. Проверить, что salary в ответе равно salary s request (salary забрать из request.)
8. Вывести в консоль параметр family из response.
9. Проверить, что у параметра dog есть параметры name.
10. Проверить, что у параметра dog есть параметры age.
11. Проверить, что параметр name имеет значение Luky.
12. Проверить, что параметр age имеет значение 4.
```
var responce_JSON = pm.response.json();
var req_url = pm.request.url.query.toObject()

var resp_u_name = responce_JSON.name
var req_url_name = req_url.name


pm.test("user_name", function () {
    pm.expect(resp_u_name,typeof resp_u_name).to.eql(req_url_name, typeof req_url_name);
});

var resp_u_age = responce_JSON.age
var req_url_age = req_url.age

pm.test("user_age", function () {
    pm.expect(resp_u_age).to.eql(req_url_age);
});

var resp_u_salary = responce_JSON.salary
var req_url_salary = req_url.salary

pm.test("user_salary", function () {
    pm.expect(resp_u_salary).to.eql(+req_url_salary);
});

console.log(responce_JSON.family)

var param_dog = responce_JSON.family.pets.dog
pm.test("Check dogs parametrs 'NAME'", function () { 
    pm.expect(param_dog).haveOwnProperty('name'); 
});

pm.test("Check dogs parametrs 'AGE'", function () { 
    pm.expect(param_dog).haveOwnProperty('age'); 
});

pm.test("Check dog name", function () {
    pm.expect(param_dog.name).to.eql("Luky");
});

pm.test("Check dog age", function () {
    pm.expect(param_dog.age).to.eql(4);
});
```
___
http://162.55.220.72:5005/object_info_4
1. Отправить запрос.
2. Статус код 200
3. Спарсить response body в json.
4. Спарсить request.
5. Проверить, что name в ответе равно name s request (name забрать из request.)
6. Проверить, что age в ответе равно age из request (age забрать из request.)
7. Вывести в консоль параметр salary из request.
8. Вывести в консоль параметр salary из response.
9. Вывести в консоль 0-й элемент параметра salary из response.
10. Вывести в консоль 1-й элемент параметра salary параметр salary из response.
11. Вывести в консоль 2-й элемент параметра salary параметр salary из response.
12. Проверить, что 0-й элемент параметра salary равен salary из request (salary забрать из request.)
13. Проверить, что 1-й элемент параметра salary равен salary*2 из request (salary забрать из request.)
14. Проверить, что 2-й элемент параметра salary равен salary*3 из request (salary забрать из request.)
15. Создать в окружении переменную name
16. Создать в окружении переменную age
17. Создать в окружении переменную salary
18. Передать в окружение переменную name
19. Передать в окружение переменную age
20. Передать в окружение переменную salary
21. Написать цикл который выведет в консоль по порядку элементы списка из параметра salary.
```
var responce_JSON = pm.response.json();
var req_url = pm.request.url.query.toObject()

var resp_u_name = responce_JSON.name
var req_url_name = req_url.name
pm.test("user_name", function () {
    pm.expect(resp_u_name,typeof resp_u_name).to.eql(req_url_name, typeof req_url_name);
});

var resp_u_age = responce_JSON.age
var req_url_age = req_url.age
pm.test("user_age", function () {
    pm.expect(resp_u_age).to.eql(+req_url_age);
});

var resp_u_salary = responce_JSON.salary
var req_url_salary = req_url.salary

console.log("salary from request = ", req_url_salary)
console.log ("salary from responce = ", resp_u_salary)

console.log ("1st element salary from responce = ", resp_u_salary[0])
console.log ("2nd element salary from responce = ", resp_u_salary[1])
console.log ("3rd element salary from responce = ", resp_u_salary[2])

pm.test("user_salary", function () {
    pm.expect(+req_url_salary).to.eql(resp_u_salary[0]);
});

pm.test("user_salary for 2 mounth", function () {
    pm.expect(+req_url_salary*2).to.eql(+resp_u_salary[1]);
});

pm.test("user_salary for 3 mounth", function () {
    pm.expect(+req_url_salary*3).to.eql(+resp_u_salary[2]);
});

pm.environment.set("name", responce_JSON.name);
pm.environment.set("age", responce_JSON.age);
pm.environment.set("salary", responce_JSON.salary[0]);

for (item in resp_u_salary) {
    console.log(+resp_u_salary[item]);
};
```
___

http://162.55.220.72:5005/user_info_2
1. Вставить параметр salary из окружения в request
2. Вставить параметр age из окружения в age
3. Вставить параметр name из окружения в name
4. Отправить запрос.
5. Статус код 200
6. Спарсить response body в json.
7. Спарсить request.
8. Проверить, что json response имеет параметр start_qa_salary
9. Проверить, что json response имеет параметр qa_salary_after_6_months
10. Проверить, что json response имеет параметр qa_salary_after_12_months
11. Проверить, что json response имеет параметр qa_salary_after_1.5_year
12. Проверить, что json response имеет параметр qa_salary_after_3.5_years
13. Проверить, что json response имеет параметр person
14. Проверить, что параметр start_qa_salary равен salary из request (salary забрать из request.)
15. Проверить, что параметр qa_salary_after_6_months равен salary*2 из request (salary забрать из request.)
16. Проверить, что параметр qa_salary_after_12_months равен salary*2.7 из request (salary забрать из request.)
17. Проверить, что параметр qa_salary_after_1.5_year равен salary*3.3 из request (salary забрать из request.)
18. Проверить, что параметр qa_salary_after_3.5_years равен salary*3.8 из request (salary забрать из request.)
19. Проверить, что в параметре person, 1-й элемент из u_name равен salary из request (salary забрать из request.)
20. Проверить, что что параметр u_age равен age из request (age забрать из request.)
21. Проверить, что параметр u_salary_5_years равен salary*4.2 из request (salary забрать из request.)
22. ***Написать цикл который выведет в консоль по порядку элементы списка из параметра person.
```
var resp_json = pm.response.json();
console.log(resp_json)

pm.test("Check resp for 'start_qa_salary'", function () { 
    pm.expect(resp_json).haveOwnProperty("start_qa_salary"); 
});

pm.test("Check resp for 'qa_salary_after_6_months'", function () { 
    pm.expect(resp_json).haveOwnProperty("qa_salary_after_6_months"); 
});

pm.test("Check resp for 'qa_salary_after_12_months'", function () { 
    pm.expect(resp_json).haveOwnProperty("qa_salary_after_12_months"); 
});

pm.test("Check resp for 'qa_salary_after_1.5_year'", function () { 
    pm.expect(resp_json).haveOwnProperty("qa_salary_after_1.5_year"); 
});

pm.test("Check resp for 'qa_salary_after_3.5_years'", function () { 
    pm.expect(resp_json).haveOwnProperty("qa_salary_after_3.5_years"); 
});

pm.test("Check resp for 'person'", function () { 
    pm.expect(resp_json).haveOwnProperty("person"); 
});

var request_salary = pm.environment.get("salary")
console.log(request_salary)

pm.test("start_user_salary", function () {
    pm.expect(request_salary).to.eql(resp_json.start_qa_salary);
});

pm.test("qa_salary_after_6_months", function () {
    pm.expect(request_salary*2).to.eql(resp_json.qa_salary_after_6_months);
});

pm.test("qa_salary_after_12_months", function () {
    pm.expect(request_salary*2.7).to.eql(resp_json.qa_salary_after_12_months);
});

pm.test("qa_salary_aftery_1.5_year", function () {
    pm.expect(request_salary*3.3).to.eql(resp_json['qa_salary_after_1.5_year']);
});

pm.test("qa_salary_aftery_3.5_year", function () {
    pm.expect(request_salary*3.8).to.eql(resp_json['qa_salary_after_3.5_years']);
});

pm.test("person salary", function () {
    pm.expect(request_salary).to.eql(resp_json.person.u_name[1]);
});

var request_age = pm.environment.get("age")
console.log(request_age)

pm.test("person age", function () {
    pm.expect(request_age).to.eql(resp_json.person.u_age);
});

pm.test("qa_salary_aftery_3.5_year", function () {
    pm.expect(request_salary*4.2).to.eql(resp_json.person.u_salary_5_years);
});

for (var key in resp_json.person) {
    console.log(key,':', resp_json.person[key]);
};
```
  
