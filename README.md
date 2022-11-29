# HW2_Postman

***http://162.55.220.72:5005/first***

**Отправить запрос + cтатус код 200**

```JavaScript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```

**Проверить, что в body приходит правильный string**

```JavaScript
pm.test("String is correct", function () {
    pm.response.to.have.body("This is the first responce from server!ss");
});
```
***
***http://162.55.220.72:5005/user_info_3***


**Отправить запрос + cтатус код 200**

```JavaScript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```

**Спарсить response body в json.**

```JavaScript
let resp = pm.response.json();
```

**Проверить, что name в ответе равно name s request (name вбить руками.)**

```JavaScript
pm.test("Name is true", function () {
    //let respName = pm.response.json();
    pm.expect(resp.name).to.eql("Denys");
});

```

**Проверить, что age в ответе равно age s request (age вбить руками.)**

```JavaScript
pm.test("Age is true", function () {
    //let respAge = pm.response.json();
    pm.expect(resp.age).to.eql("29");
});
```

**Проверить, что salary в ответе равно salary s request (salary вбить руками.)**

```JavaScript
pm.test("Salary is true", function () {
    //let respAge = pm.response.json();
    pm.expect(resp.salary).to.eql(3000);
});
```

**Спарсить request.**

```JavaScript
let req =  request.data;
let req_name = req.name;
let req_age = req.age;
let req_salary = +req.salary;
```

**Проверить, что name в ответе равно name s request (name забрать из request.)**

```JavaScript
pm.test("respName = reqName", function () {
    pm.expect(resp.name).to.eql(req.name);
});

```

**Проверить, что age в ответе равно age s request (age забрать из request.)**

```JavaScript
pm.test("respAge = reqAge", function () {
    pm.expect(resp.age).to.eql(req.age);
});
```

**Проверить, что salary в ответе равно salary s request (salary забрать из request.)**

```JavaScript
pm.test("respSalary = reqSalary", function () {
    pm.expect(resp.salary).to.eql(+req.salary);
});
```

**Вывести в консоль параметр family из response.**

```JavaScript
console.log(resp.family)
```

**Проверить что u_salary_1_5_year в ответе равно salary*4 (salary забрать из request)**

```JavaScript
let resp_salary_1_5_year = req_salary * 4;
console.log(resp_salary_1_5_year)

pm.test("u_salary 12000", function () {
    let u_salary = pm.response.json();
    pm.expect(u_salary.family.u_salary_1_5_year).to.eql(resp_salary_1_5_year);
});
```
***

***http://162.55.220.72:5005/object_info_3***

**Отправить запрос + cтатус код 200**

```JavaScript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```

**Спарсить response body в json.**

```JavaScript
let resp = pm.response.json();
```

**Спарсить request.**

```JavaScript
let req = pm.request.url.query.toObject();
//console.log(req)
let req_name = req.name;
let req_age = req.age;
let req_salary = +req.salary;
```

**Проверить, что name в ответе равно name s request (name забрать из request.)**

```JavaScript
pm.test("respName = reqName", function () {
    pm.expect(resp.name).to.eql(req.name);
});
```

**Проверить, что age в ответе равно age s request (age забрать из request.)**

```JavaScript
pm.test("respAge = reqAge", function () {
    pm.expect(resp.age).to.eql(req.age);
});
```

**Проверить, что salary в ответе равно salary s request (salary забрать из request.)**

```JavaScript
pm.test("respSalary = reqSalary", function () {
    pm.expect(resp.salary).to.eql(+req.salary);
});
```

**Вывести в консоль параметр family из response.**

```JavaScript
console.log(resp.family)
```

**Проверить, что у параметра dog есть параметры name.**

```JavaScript
pm.test("dog name in JSON", function () {
    pm.expect(resp.family.pets.dog).haveOwnProperty("name");
});
```

**Проверить, что у параметра dog есть параметры age.**

```JavaScript
pm.test("dog age in JSON", function () {
    pm.expect(resp.family.pets.dog).haveOwnProperty("age");
});
```

**Проверить, что параметр name имеет значение Luky.**

```JavaScript
pm.test("Name dog is Luky", function () {
    pm.expect(resp.family.pets.dog.name).to.eql("Luky");
});
```

**Проверить, что параметр age имеет значение 4.**

```JavaScript
pm.test("Age dog is 4 years", function () {
    pm.expect(resp.family.pets.dog.age).to.eql(4);
});
```
***
***http://162.55.220.72:5005/object_info_4***

**Отправить запрос + cтатус код 200**
```JavaScript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
**Спарсить response body в json.**
```JavaScript
let resp = pm.response.json();
console.log(resp)
```
**Спарсить request.**
```JavaScript
let req = pm.request.url.query.toObject();
console.log(req)
let req_name = req.name;
let req_age = +req.age;
let req_salary = req.salary;
```
**Проверить, что name в ответе равно name s request (name забрать из request.)**
```JavaScript
pm.test("respName = reqName", function () {
    pm.expect(resp.name).to.eql(req.name);
});
```
**Проверить, что age в ответе равно age из request (age забрать из request.)**
```JavaScript
pm.test("respAge = reqAge", function () {
    pm.expect(resp.age).to.eql(+req.age);
});
```
**Вывести в консоль параметр salary из request.**
```JavaScript
console.log (req_salary)
```
**Вывести в консоль параметр salary из response.**
```JavaScript
console.log (resp.salary)
```
**Вывести в консоль 0-й элемент параметра salary из response.**
```JavaScript
console.log (resp.salary[0])
```
**Вывести в консоль 1-й элемент параметра salary параметр salary из response.**
```JavaScript
console.log (resp.salary[1])
```
**Вывести в консоль 2-й элемент параметра salary параметр salary из response.**
```JavaScript
console.log (resp.salary[2])
```
**Проверить, что 0-й элемент параметра salary равен salary из request (salary забрать из request.)**
```JavaScript
pm.test("respSalary[0] = reqSalary", function () {
    pm.expect(resp.salary[0]).to.eql(+req.salary);
});
```
**Проверить, что 1-й элемент параметра salary равен salary*2 из request (salary забрать из request.)**
```JavaScript
pm.test("respSalary[1] = reqSalary", function () {
    pm.expect(+resp.salary[1]).to.eql(+req.salary * 2);
});
```
**Проверить, что 2-й элемент параметра salary равен salary*3 из request (salary забрать из request.)**
```JavaScript
pm.test("respSalary[2] = reqSalary", function () {
    pm.expect(+resp.salary[2]).to.eql(+req.salary * 3);
});
```
**Создать в окружении переменную name + передать в окружение переменную name**
```JavaScript
pm.environment.set("name_2", "Markus");
```
**Создать в окружении переменную age + передать в окружение переменную age**
```JavaScript
pm.environment.set("age_2", 30);
```
**Создать в окружении переменную salary + передать в окружение переменную salary**
```JavaScript
pm.environment.set("salary_2", 2500);
```

**Написать цикл который выведет в консоль по порядку элементы списка из параметра salary.**
```JavaScript
for (let i = 0; i < resp.salary.length; i++) {
    console.log(resp.salary[i])
}
```
***
***http://162.55.220.72:5005/user_info_2***

**Отправить запрос + статус код 200**
```JavaScript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
**Спарсить response body в json.**
```JavaScript
let resp = pm.response.json();
```
**Спарсить request.**
```JavaScript
let req =  request.data;
let req_salary = +req.salary
```
**Проверить, что json response имеет параметр start_qa_salary**
```JavaScript
pm.test("Start QA Salary in JSON", function () {
    pm.expect(resp).haveOwnProperty("start_qa_salary");
});
```
**Проверить, что json response имеет параметр qa_salary_after_6_months**
```JavaScript
pm.test("Response has QA Salary after 6 month in JSON", function () {
    pm.expect(resp).haveOwnProperty("qa_salary_after_6_months");
});
```
**Проверить, что json response имеет параметр qa_salary_after_12_months**
```JavaScript
pm.test("Response has QA Salary after 12 month in JSON", function () {
    pm.expect(resp).haveOwnProperty("qa_salary_after_12_months");
});
```
**Проверить, что json response имеет параметр qa_salary_after_1.5_year**
```JavaScript
pm.test("Response has QA Salary after 1.5 year in JSON", function () {
    pm.expect(resp).haveOwnProperty("qa_salary_after_1.5_year");
});
```
**Проверить, что json response имеет параметр qa_salary_after_3.5_years**
```JavaScript
pm.test("Response has QA Salary after 3.5 years in JSON", function () {
    pm.expect(resp).haveOwnProperty("qa_salary_after_3.5_years");
});
```
**Проверить, что json response имеет параметр person**
```JavaScript
pm.test("Response has person params", function () {
    pm.expect(resp).haveOwnProperty("person");
});
```
**Проверить, что параметр start_qa_salary равен salary из request (salary забрать из request.)**
```JavaScript
pm.test("start_qa_salary = salary from request", function () {
    pm.expect(resp.start_qa_salary).to.eql(+req.salary)
});
```
**Проверить, что параметр qa_salary_after_6_months равен salary*2 из request (salary забрать из request.)**
```JavaScript
pm.test("qa_salary_after_6_months = salary*2 from request", function () {
    pm.expect(resp.qa_salary_after_6_months).to.eql(+req.salary * 2)
});
```
**Проверить, что параметр qa_salary_after_12_months равен salary*2.7 из request (salary забрать из request.)**
```JavaScript
pm.test("qa_salary_after_6_months = salary*2 from request", function () {
    pm.expect(resp.qa_salary_after_12_months).to.eql(+req.salary * 2.7)
});
```
**Проверить, что параметр qa_salary_after_1.5_year равен salary*3.3 из request (salary забрать из request.)**
```JavaScript
pm.test("qa_salary_after_1.5_year = salary*3.3 from request", function () {
    pm.expect(resp['qa_salary_after_1.5_year']).to.eql(+req.salary * 3.3)
});
```
**Проверить, что параметр qa_salary_after_3.5_years равен salary*3.8 из request (salary забрать из request.)**
```JavaScript
pm.collectionVariables.set("qa_salary_after_3.5_years", +req.salary*3.8);
pm.test("qa_salary_after_3.5_years = salary*3.8 from request", function () {
    pm.expect(+req.salary * 3.8).to.eql(pm.collectionVariables.get("qa_salary_after_3.5_years"))
});
```
**Проверить, что в параметре person, 1-й элемент из u_name равен salary из request (salary забрать из request.)**
```JavaScript
pm.test("Person from u_name[1] = salary from request", function () {
    pm.expect(resp.person.u_name[1]).to.eql(+req.salary);
});
```
**Проверить, что что параметр u_age равен age из request (age забрать из request.)**
```JavaScript
pm.test("Params u_age = age from request", function () {
    pm.expect(resp.person.u_age).to.eql(+req.age);
});
```
**Проверить, что параметр u_salary_5_years равен salary*4.2 из request (salary забрать из request.)**
```JavaScript
pm.test("u_salary_5_years = salary*4.2 from request", function () {
    pm.expect(resp.person.u_salary_5_years).to.eql(+req.salary * 4.2)
});
```
**Написать цикл который выведет в консоль по порядку элементы списка из параметра person.**
```JavaScript
let resp_person = pm.response.json()
for (let key in resp_person) {
    console.log (key, resp_person[key])
}
```



