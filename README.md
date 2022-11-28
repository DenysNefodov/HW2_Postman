# HW2_Postman

***http://162.55.220.72:5005/first***

**Отправить запрос - Статус код 200**

```Java Script
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```

**Проверить, что в body приходит правильный string**

```Java Script
pm.test("String is correct", function () {
    pm.response.to.have.body("This is the first responce from server!ss");
});
```




