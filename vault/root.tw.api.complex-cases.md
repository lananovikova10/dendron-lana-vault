---
id: 4o0sumc625251txfo637evr
title: Complex Cases and Issues
desc: ''
updated: 1665521051999
created: 1663515147347
---

##  Проблемы с документацией API

https://docs.ozon.ru/main 

- Разграничивать параметры в хедере и в теле запроса
- Насыщать автогенерируемые части осмысленным текстом - общими описаниями, информацией об авторизации, описанием методов, ошибок, параметров, юз кейсами
- Identify dependencies 
- 

## Сложные кейсы

- Составные параметры типа enum, ListQuery, DTO
  
Например, получить список товаров
GET aliexpress.solution.product.list.get
Возвращает список всех ваших товаров в определённом статусе.

aeop_a_e_product_list_query	ItemListQuery[]	Нет	Объект.
↳ product_status_type	string	Да	Статус товара на AliExpress. Может быть onSelling (В продаже), offline (Сняты с продажи), auditing (На рассмотрении) и editingRequired.
↳ current_page	int	Нет	Страница выдачи результатов, по умолчанию 1.
↳ excepted_product_ids	list	Нет	Список идентификаторов товаров, которые нужно исключить из ответа.
↳ off_line_time	list	Нет	Для товаров в статусе offline. Сколько дней прошло с момента снятия с публикации.
↳ owner_member_id	string	Нет	Логин продавца-владельца товара.
↳ page_size	int	Нет	Число товаров на каждой странице выдачи результата.
↳ product_id	int	Нет	Идентификатор товара на AliExpress.
↳ product_subject	string	Нет	Нечёткий поиск по английскому названию товара.
↳ ws_display	string	Нет	Причина, почему товар снят с продажи. Может быть expire_offline; user_offline, violate_offline, punish_offline и grade_offline.
↳ have_national_quote	string	Нет	
Есть ли у товара квота по стране:
y — если да
n — если нет.
↳ group_id	int	Нет	Идентификатор группы товаров.
↳ gmt_create_start	date	Нет	Поиск товаров, созданных после указанной даты и времени в формате yyyy-MM-dd hh:mm:ss.
↳ gmt_create_end	date	Нет	Поиск товаров, созданных до указанной даты и времени в формате yyyy-MM-dd hh:mm:ss.
↳ gmt_modified_start	date	Нет	Поиск товаров, изменённых до указанной даты и времени в формате yyyy-MM-dd hh:mm:ss.
↳ gmt_modified_end	date	Нет	Поиск товаров, изменённых до указанной даты и времени в формате yyyy-MM-dd hh:mm:ss.
↳ sku_code	string	Нет	Идентификатор экземпляра (SKU) товара: его артикул или штрихкод.

marketing_images	MarketImageDto[]	Нет	
Массив ссылок на рекламные изображения товара. Изображение нужно предварительно загрузить на CDN с помощью метода.

↳ image_type	int	Нет	
Тип изображения:
1 — для изображений типа 3:4,
2 – для изображений типа 1:1.
↳ image_url	string	Нет	Ссылка на изображение.

sku_info_list	SkuInfoDto[]	Да	
Содержит три обязательных параметра:
inventory (остаток товара на складе от 1 до 999999),
price (цена товара от 0,01 до 999999),
sku_code (идентификатор экземпляра: артикул или штрихкод)
И ряд необязательных: discount_price, bar_code (штрихкод, обязательно для продавцов, работающих по модели Фулфилмент «Цайняо»), sku_attributes_list (список полей sku_attribute_name, sku_attribute_value и sku_image_url).

Загрузить один товар синхронным способом
POST aliexpress.solution.product.post
С помощью этого метода можно загрузить на площадку товары по одному. Вы должны передать параметры из таблицы ниже внутри объекта post_product_request.

https://developers.aliexpress.com/en/doc.htm?docId=39634&docType=2 

Получить список геоограничений для услуг
POST
/v1/products/geo-restrictions-catalog-by-filter

HEADER PARAMETERS
Client-Id
required
string
Идентификатор клиента.

Api-Key
required
string
API-ключ.

REQUEST BODY SCHEMA: application/json
filter	
object (v2GetGeoRestrictionsByFilterRequestFilter)
Фильтр. Чтобы посмотреть все геоограничения, оставьте names пустым, а в only_visible передайте true.

names	
Array of strings
Список с названиями городов.

only_visible	
boolean
Видимость значения. Рекомендуем всегда передавать true в этом параметре.

last_order_number	
integer <int64>
Порядок геоограничения, с которого выводим данные в ответе.

Если указать 23, то на выходе у первого элемента списка restrictions будет order_number = 24. Если вы хотите получить все геоограничения, укажите 0 в этом параметре.

limit	
integer <int64>
Количество результатов в ответе.

https://docs.ozon.ru/api/seller/#operation/ProductAPI_GetGeoRestrictionsV1 

The "Create non-reference docs" included comments such as providing the big picture, explaining concepts, going beyond simple calls and reference material, explaining workflows, introductory material, how the various endpoints work together, and so on. One person summed up this challenge particularly well in saying:

Understanding and representing how developers will interact and use the API. It's easy to have -- what I call -- “Resource Documentation,” that is auto-generated docs that reference all components of the API, but creating tutorials about how a developer can knit those code pieces together to build what they need is challenging.

Identify dependencies
The "Identify dependencies" includes topics such as identifying inputs, dependencies, legal requirements, and more. The dependencies response might actually fit into the "Create non-reference docs" / bigger picture workflow response. For example, what dependencies are required before you can use an endpoint? Some endpoints require you to pass in an object from another other endpoint, or they may require you to have certain data in order to return a response, or they may have other prerequisites or large workflows and interdependencies.

https://www.copywritech.net/five-common-library-and-api-problems/ 
https://www.researchgate.net/publication/282552024_How_API_Documentation_Fails 

## Tools

- DapperDox
- SwaggerHub

## Examples

- https://docs.github.com/en/rest/guides/getting-started-with-the-rest-api
- https://paystack.com/docs/
- https://developer.twitter.com/en/docs/twitter-api
- 