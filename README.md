# HW2_Postman

***http://162.55.220.72:5005/first***

**Отправить запрос - Статус код 200**

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


**Отправить запрос + Статус код 200**

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

***Отправить запрос. + Статус код 200***

```JavaScript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```

***Спарсить response body в json.***

```JavaScript
let resp = pm.response.json();
```

***Спарсить request.***

```JavaScript
let req = pm.request.url.query.toObject();
//console.log(req)
let req_name = req.name;
let req_age = req.age;
let req_salary = +req.salary;
```

***Проверить, что name в ответе равно name s request (name забрать из request.)***

```JavaScript
pm.test("respName = reqName", function () {
    pm.expect(resp.name).to.eql(req.name);
});
```

***Проверить, что age в ответе равно age s request (age забрать из request.)***

```JavaScript
pm.test("respAge = reqAge", function () {
    pm.expect(resp.age).to.eql(req.age);
});
```

***Проверить, что salary в ответе равно salary s request (salary забрать из request.)***

```JavaScript
pm.test("respSalary = reqSalary", function () {
    pm.expect(resp.salary).to.eql(+req.salary);
});
```

***Вывести в консоль параметр family из response.***

```JavaScript
console.log(resp.family)
```

***Проверить, что у параметра dog есть параметры name.***

```JavaScript
pm.test("dog name in JSON", function () {
    pm.expect(resp.family.pets.dog).haveOwnProperty("name");
});
```

***Проверить, что у параметра dog есть параметры age.***

```JavaScript
pm.test("dog age in JSON", function () {
    pm.expect(resp.family.pets.dog).haveOwnProperty("age");
});
```

***Проверить, что параметр name имеет значение Luky.***

```JavaScript
pm.test("Name dog is Luky", function () {
    pm.expect(resp.family.pets.dog.name).to.eql("Luky");
});
```

***Проверить, что параметр age имеет значение 4.***

```JavaScript
pm.test("Age dog is 4 years", function () {
    pm.expect(resp.family.pets.dog.age).to.eql(4);
});
```
***


```JavaScript

```


