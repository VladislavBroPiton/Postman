Чтобы сгенерировать ``` 10,000 email адресов ``` в Postman, вы можете использовать функции JavaScript вместе с Postman. Вот один из способов сделать это с помощью коллекции запросов и скриптов Pre-request Script.

Шаги для выполнения:  
Создайте новую коллекцию в Postman:  
Откройте Postman.  
Нажмите "New" и выберите "Collection".  
Назовите колледцию, например, "Email Generator".  
Добавьте новый запрос:  
Внутри вашей коллекции нажмите "Add Request".  
Назовите запрос, например, "Generate Emails" и укажите любой метод (GET или POST).  
Добавьте Pre-request Script:    
Перейдите на вкладку "Pre-request Script" в запросе.  
Вставьте следующий код:  

```
let emails = [];
const domain = "example.com"; // Измените на нужный вам домен

for (let i = 1; i <= 10000; i++) {
    let email = `user${i}@${domain}`;
    emails.push(email);
}

// Сохраните сгенерированные email адреса в переменной окружения Postman
pm.environment.set("generatedEmails", JSON.stringify(emails));
```
