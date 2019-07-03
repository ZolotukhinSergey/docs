---
editable: false
---

# Image
Набор методов для управления ресурсами Image.
## JSON-представление {#representation}
```json 
{
  "id": "string",
  "folderId": "string",
  "createdAt": "string",
  "name": "string",
  "description": "string",
  "labels": "object",
  "family": "string",
  "storageSize": "string",
  "minDiskSize": "string",
  "productIds": [
    "string"
  ],
  "status": "string",
  "os": {
    "type": "string"
  }
}
```
 
Поле | Описание
--- | ---
id | **string**<br><p>Идентификатор образа.</p> 
folderId | **string**<br><p>Идентификатор каталога, которому принадлежит образ диска.</p> 
createdAt | **string** (date-time)<br><p>Строка в формате <a href="https://www.ietf.org/rfc/rfc3339.txt">RFC3339</a>.</p> 
name | **string**<br><p>Имя образа. Длина 1-63 символов.</p> 
description | **string**<br><p>Описание образа. Длина описания должна быть от 0 до 256 символов.</p> 
labels | **object**<br><p>Метки ресурса в формате <code>key:value</code>. Максимум 64 на ресурс.</p> 
family | **string**<br><p>Имя семейства образов, к которому принадлежит этот образ.</p> <p>Вы можете получить самый последний образ из семейства образов, используя запрос <a href="/docs/compute/api-ref/Image/getLatestByFamily">getLatestByFamily</a> , чтобы создать диск из этого образа.</p> 
storageSize | **string** (int64)<br><p>Размер образа в байтах.</p> 
minDiskSize | **string** (int64)<br><p>Минимальный размер диска, который будет создан из этого образа.</p> 
productIds[] | **string**<br><p>Идентификаторы лицензий, указывающие, какие лицензии подключены к этому ресурсу. Идентификаторы лицензий используются для расчета дополнительной платы за использование виртуальной машины.</p> <p>Правильный идентификатор лицензии генерируется Яндексом.Облаком. Идентификаторы наследуются новыми ресурсами, созданными из этого ресурса.</p> <p>Если вам известны идентификаторы лицензий, укажите их при создании образа. Например, если создать образ диска с помощью сторонней утилиты и загрузить его в Yandex Object Storage, то идентификаторы лицензий будут потеряны. Вы можете указать их в запросе <a href="/docs/compute/api-ref/Image/create">create</a>.</p> 
status | **string**<br><p>Текущий статус образа диска.</p> <ul> <li>CREATING: Образ диска создается.</li> <li>READY: Образ диска готов к использованию.</li> <li>ERROR: С образом произошла ошибка, блокирующая работу.</li> <li>DELETING: Образ диска удаляется.</li> </ul> 
os | **object**<br><p>Операционная система, содержащаяся в образе.</p> 
os.<br>type | **string**<br><p>Тип операционной системы.</p> <ul> <li>LINUX: Операционная система Linux.</li> <li>WINDOWS: Операционная система Windows.</li> </ul> 

## Методы {#methods}
Метод | Описание
--- | ---
[create](create.md) | Создает образ в указанном каталоге.
[delete](delete.md) | Удаляет указанный образ.
[get](get.md) | Возвращает указанный ресурс Image.
[getLatestByFamily](getLatestByFamily.md) | Возвращает последний образ из указанного семейства образов.
[list](list.md) | Возвращает список доступных ресурсов Image в указанном каталоге.
[listOperations](listOperations.md) | Список операций для указанного образа.
[update](update.md) | Изменяет указанный образ.