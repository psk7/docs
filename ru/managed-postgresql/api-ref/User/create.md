---
editable: false
---

# Метод create
Создает пользователя PostgreSQL в указанном кластере.
 

 
## HTTP-запрос {#https-request}
```
POST https://mdb.api.cloud.yandex.net/managed-postgresql/v1/clusters/{clusterId}/users
```
 
## Path-параметры {#path_params}
 
Параметр | Описание
--- | ---
clusterId | Обязательное поле. Идентификатор кластера PostgreSQL, в котором следует создать пользователя. Чтобы получить идентификатор кластера, используйте запрос [list](/docs/managed-postgresql/api-ref/Cluster/list).  Максимальная длина строки в символах — 50.
 
## Параметры в теле запроса {#body_params}
 
```json 
{
  "userSpec": {
    "name": "string",
    "password": "string",
    "permissions": [
      {
        "databaseName": "string"
      }
    ],
    "connLimit": "integer",
    "settings": {
      "defaultTransactionIsolation": "string",
      "lockTimeout": "integer",
      "logMinDurationStatement": "integer",
      "synchronousCommit": "string",
      "tempFileLimit": "integer"
    },
    "login": true,
    "grants": [
      "string"
    ]
  }
}
```

 
Поле | Описание
--- | ---
userSpec | **object**<br><p>Обязательное поле. Свойства создаваемого пользователя.</p> 
userSpec.<br>name | **string**<br><p>Обязательное поле. Имя пользователя PostgreSQL.</p> <p>Максимальная длина строки в символах — 63. Значение должно соответствовать регулярному выражению <code>[a-zA-Z0-9_]*</code>.</p> 
userSpec.<br>password | **string**<br><p>Обязательное поле. Пароль пользователя PostgreSQL.</p> <p>Длина строки в символах должна быть от 8 до 128.</p> 
userSpec.<br>permissions[] | **object**<br><p>Набор разрешений, которые следует предоставить пользователю.</p> 
userSpec.<br>permissions[].<br>databaseName | **string**<br><p>Имя базы данных, к которой предоставляет доступ разрешение.</p> 
userSpec.<br>connLimit | **integer** (int64)<br><p>Количество подключений к базе данных, которые должны быть доступны пользователю.</p> <p>Минимальное значение — 10.</p> 
userSpec.<br>settings | **object**<br><p>Настройки PostgreSQL для этого пользователя</p> <p>Пользовательские параметры PostgreSQL</p> 
userSpec.<br>settings.<br>defaultTransactionIsolation | **string**<br>
userSpec.<br>settings.<br>lockTimeout | **integer** (int64)<br><p>в миллисекундах.</p> 
userSpec.<br>settings.<br>logMinDurationStatement | **integer** (int64)<br><p>в миллисекундах.</p> 
userSpec.<br>settings.<br>synchronousCommit | **string**<br>
userSpec.<br>settings.<br>tempFileLimit | **integer** (int64)<br><p>в байтах.</p> 
userSpec.<br>login | **boolean** (boolean)<br><p>Пользователь может войти (по умолчанию True).</p> 
userSpec.<br>grants[] | **string**<br><p>Пользовательские гранты (GRANT &lt;роль&gt; TO &lt;пользователь&gt;), роль должна быть другим пользователем.</p> <p>Максимальная длина строки в символах для каждого значения — 63. Каждое значение должно соответствовать регулярному выражению <code>[a-zA-Z0-9_]*</code>.</p> 
 
## Ответ {#responses}
**HTTP Code: 200 - OK**

```json 
{
  "id": "string",
  "description": "string",
  "createdAt": "string",
  "createdBy": "string",
  "modifiedAt": "string",
  "done": true,
  "metadata": "object",

  //  включает только одно из полей `error`, `response`
  "error": {
    "code": "integer",
    "message": "string",
    "details": [
      "object"
    ]
  },
  "response": "object",
  // конец списка возможных полей

}
```
Ресурс Operation. Дополнительные сведения см. в разделе
[Объект Operation](/docs/api-design-guide/concepts/operation).
 
Поле | Описание
--- | ---
id | **string**<br><p>Идентификатор операции.</p> 
description | **string**<br><p>Описание операции. Длина описания должна быть от 0 до 256 символов.</p> 
createdAt | **string** (date-time)<br><p>Время создания ресурса в формате в <a href="https://www.ietf.org/rfc/rfc3339.txt">RFC3339</a>.</p> <p>Строка в формате <a href="https://www.ietf.org/rfc/rfc3339.txt">RFC3339</a>.</p> 
createdBy | **string**<br><p>Идентификатор пользователя или сервисного аккаунта, инициировавшего операцию.</p> 
modifiedAt | **string** (date-time)<br><p>Время, когда ресурс Operation последний раз обновлялся. Значение в формате <a href="https://www.ietf.org/rfc/rfc3339.txt">RFC3339</a>.</p> <p>Строка в формате <a href="https://www.ietf.org/rfc/rfc3339.txt">RFC3339</a>.</p> 
done | **boolean** (boolean)<br><p>Если значение равно <code>false</code> — операция еще выполняется. Если <code>true</code> — операция завершена, и задано значение одного из полей <code>error</code> или <code>response</code>.</p> 
metadata | **object**<br><p>Метаданные операции. Обычно в поле содержится идентификатор ресурса, над которым выполняется операция. Если метод возвращает ресурс Operation, в описании метода приведена структура соответствующего ему поля <code>metadata</code>.</p> 
error | **object**<br>Описание ошибки в случае сбоя или отмены операции. <br> включает только одно из полей `error`, `response`<br><br><p>Описание ошибки в случае сбоя или отмены операции.</p> 
error.<br>code | **integer** (int32)<br><p>Код ошибки. Значение из списка <a href="https://github.com/googleapis/googleapis/blob/master/google/rpc/code.proto">google.rpc.Code</a>.</p> 
error.<br>message | **string**<br><p>Текст ошибки.</p> 
error.<br>details[] | **object**<br><p>Список сообщений с подробными сведениями об ошибке.</p> 
response | **object** <br> включает только одно из полей `error`, `response`<br><br><p>Результат операции в случае успешного завершения. Если исходный метод не возвращает никаких данных при успешном завершении, например метод Delete, поле содержит объект <a href="https://developers.google.com/protocol-buffers/docs/reference/google.protobuf#empty">google.protobuf.Empty</a>. Если исходный метод — это стандартный метод Create / Update, поле содержит целевой ресурс операции. Если метод возвращает ресурс Operation, в описании метода приведена структура соответствующего ему поля <code>response</code>.</p> 