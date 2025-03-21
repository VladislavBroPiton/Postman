<img align='right' src='https://user-images.githubusercontent.com/5713670/87202985-820dcb80-c2b6-11ea-9f56-7ec461c497c3.gif' width='250'>    

# Postman.  
### HW_1 <img src="https://github.githubassets.com/images/mona-whisper.gif" height="34" />

### Создать запросы в Postman.

Protocol: http  
IP: 162.55.220.72  
Port: 5005  
``` http://162.55.220.72:5005 ``` 

### EP_1  
Method: **GET**  
EndPoint: /get_method  
request url params:   
 name: str  
 age: int  

response:   
[  
    “Str”,  
    “Str”  
]  
``` http://162.55.220.72:5005/get_method?name=str&age=int ``` 
![Postman_aQ2GrYnOG5](https://github.com/user-attachments/assets/ff6b2b9e-af9e-4ea9-868c-bb6674a61718)

___

### EP_2  
Method: **POST**  
EndPoint: /user_info_3  
request form data:   
 name: str  
 age: int  
 salary: int  

response:   
{'name': name,  
          'age': age,  
          'salary': salary,  
          'family': {'children': [['Alex', 24], ['Kate', 12]],  
                     'u_salary_1_5_year': salary * 4}}  

https://imgur.com/jkOWZRl 
![Postman_26TdKIuUB6](https://github.com/user-attachments/assets/1fd7abec-949f-4c80-8a95-8fcd3fb85464)

___

### EP_3  
Method: **GET**  
EndPoint: /object_info_1  
request url params:   
 name: str  
 age: int  
 weight: int  

response:   
{'name': name,  
          'age': age,  
          'daily_food': weight * 0.012,  
          'daily_sleep': weight * 2.5}  


___

### EP_4  
Method: **GET**  
EndPoint: /object_info_2  
request url params:   
 name: str  
 age: int  
 salary: int  

response:   
{'start_qa_salary': salary,  
          'qa_salary_after_6_months': salary * 2,  
          'qa_salary_after_12_months': salary * 2.7,  
          'qa_salary_after_1.5_year': salary * 3.3,  
          'qa_salary_after_3.5_years': salary * 3.8,  
          'person': {'u_name': [user_name, salary, age],  
                     'u_age': age,  
                     'u_salary_5_years': salary * 4.2}  
          }  


___

### EP_5  
Method: **GET**  
EndPoint: /object_info_3  
request url params:   
 name: str  
 age: int  
 salary: int  

response:   
{'name': name,  
          'age': age,  
          'salary': salary,  
          'family': {'children': [['Alex', 24], ['Kate', 12]],  
                     'pets': {'cat':{'name':'Sunny',  
                                     'age': 3},  
                              'dog':{'name':'Luky',  
                                     'age': 4}},  
                     'u_salary_1_5_year': salary * 4}  
          }  


___

### EP_6  
Method: **GET**  
EndPoint: /object_info_4  
request url params:   
 name: str  
 age: int  
 salary: int  

response:   
{'name': name,  
          'age': int(age),  
          'salary': [salary, str(salary * 2), str(salary * 3)]}  


___

### EP_7  
Method: **POST**  
EndPoint: /user_info_2  
request form data:   
 name: str  
 age: int  
 salary: int  

response:   
{'start_qa_salary': salary,  
          'qa_salary_after_6_months': salary * 2,  
          'qa_salary_after_12_months': salary * 2.7,  
          'qa_salary_after_1.5_year': salary * 3.3,  
          'qa_salary_after_3.5_years': salary * 3.8,  
          'person': {'u_name': [user_name, salary, age],  
                     'u_age': age,  
                     'u_salary_5_years': salary * 4.2}  
          }  

[Спасибо за просмотр](https://kartinkof.club/uploads/posts/2022-03/1648262006_1-kartinkof-club-p-mem-spasibo-za-prosmotr-1.jpg)   
