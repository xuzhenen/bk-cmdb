
# 创建对象模型属性

- API:   POST /api/{version}/object/attr
- API 名称：create_object_attribute
- 功能说明：
	- 中文： 新建呢模型属性
	- English：create object attribute 

- input body
``` json
{
	"creator": "user",
	"isreadonly": false,
	"isrequired": false,
	"editable": true,
	"option": "",
	"bk_property_group": "default",
	"bk_obj_id": "cc_test_inst",
	"bk_supplier_account": "0",
	"bk_property_id": "cc_test",
	"bk_property_name": "cc_test",
	"bk_property_type": "singlechar",
	"bk_asst_forward": "undefined"
}
```

**注:以上 JSON 数据中各字段的取值仅为示例数据。**

- input 字段说明

| 字段|类型|必填|默认值|说明|Description|
|---|---|---|---|---|---|
|creator|string|否|无|数据的创建者|creator|
|description|string|否|无|数据的描述信息|description|
|editable|bool|否|false|表明数据是否可编辑|editability|
|isonly|bool|否|false|表明唯一性|unique identity|
|ispre|bool|否|false|true:预置字段,false:非内置字段|preset fields|
|isreadonly|bool|否|false|true:只读，false:非只读|true:read-only， false:writable|
|isrequired|bool|否|false|true:必填，false:可选|true:required，false: option|
|option|string|否|无|用户自定义内容，存储的内容及格式由调用方决定|custom content|
|unit|string|否|无|单位|the unit|
|placeholder|string|否|无|占位符|the placeholder|
|bk_property_group|string|否|无|字段分栏的名字|group recognition|
|bk_obj_id|string|是|无|模型ID|the object identifier|
| bk_supplier_account| string|是|无|开发商账号|supplier account code|
|bk_property_id|string|是|无|模型的属性ID|attribute identifier|
|bk_property_name|string|是|无|模型属性名，用于展示|the attribute name|
|bk_property_type|string|是|无|定义的属性字段用于存储数据的数据类型|the data type|
|bk_asst_obj_id|string|否|无|如果有关联其它的模型，那么就必需设置此字段，否则就不需要设置|the object identifier|
|bk_asst_forward|string|否|无|关联方向，由调用方自行设置|the associated direction|


- output

```
{
	"result": true,
	"bk_error_code": 0,
	"bk_error_msg": null,
	"data": {
		"id": 11142
	}
}
```

**注:以上 JSON 数据中各字段的取值仅为示例数据。**

- output字段说明

| 名称  | 类型  | 说明 |Description|
|---|---|---|---|
| result | bool | 请求成功与否。true:请求成功；false请求失败 |request result true or false|
| bk_error_code | int | 错误编码。 0表示success，>0表示失败错误 |error code. 0 represent success, >0 represent failure code |
| bk_error_msg | string | 请求失败返回的错误信息 |error message from failed request|
| data | object| 请求返回的数据 |the data response|

data 字段说明

| 名称  | 类型  | 说明 |Description|
|---|---|---|---|
|id|int|新增数据记录的ID|the id of the new object attribute |


# 删除对象模型属性

- API: DELETE  /api/{version}/object/attr/{id}
- API 名称：delete_object_attribute
- 功能说明：
	- 中文： 删除模型属性（字段）
	- English：delete the  object attribute 

- input body

    无

- input 字段说明

| 字段|类型|必填|默认值|说明|Description|
|---|---|---|---|---| ---|
|id|int|否|无| 被删除的数据记录的唯一标识ID|the object property identifier|


- output

``` json
{
    "result":true,
    "bk_error_code":0,
    "bk_error_msg":"",
    "data":"success"
}
```

**注:以上 JSON 数据中各字段的取值仅为示例数据。**

- output字段说明

| 名称  | 类型  | 说明 |Description|
|---|---|---|---|
| result | bool | 请求成功与否。true:请求成功；false请求失败 |request result true or false|
| bk_error_code | int | 错误编码。 0表示success，>0表示失败错误 |error code. 0 represent success, >0 represent failure code |
| bk_error_msg | string | 请求失败返回的错误信息 |error message from failed request|
| data | string| 请求返回的数据 |the data response|


# 更新对象属性模型

- API: PUT /api/{version}/object/attr/{id}
- API 名称：update_object_attribute
- 功能说明：
	- 中文： 更新模型属性（字段）
	- english：update the  object attribute 

-  input body

``` json
{
    "ispre": true,
    "creator": "admin",
    "modifier": "admin",
    "bk_classification_id": "bk_host_manage",
    "bk_obj_name": "XXXX",
    "bk_supplier_account": "0",
    "bk_obj_icon": "icon-cc-business"
}
```

**注:以上 JSON 数据中各字段的取值仅为示例数据。**

- input 字段说明

| 字段|类型|必填|默认值|说明|Description|
|---|---|---|---|---|---|
|id|int|是|无|目标数据的记录ID|the id of the target data record|
|creator|string|否|无|数据的创建者|creator|
|description|string|否|无|数据的描述信息|description|
|editable|bool|否|无|表明数据是否可编辑|editability|
|isonly|bool|否|无|表明唯一性|unique identity|
|isreadonly|bool|否|无|表明是否只读|true:read-only, false:writable|
|isrequired|bool|否|无|表明是否必填|true:required， false: option|
|issystem|bool|否|无|系统内部流转使用|internal use|
|bk_property_group|string|否|无|字段分栏的名字|group recognition|
|option|string|否|无|用户自定义内容，存储的内容及格式由调用方决定|custom content|
|bk_property_name|string|否|无|模型属性名，用于展示|the attribute name|
|bk_property_type|string|否|无|定义的属性字段用于存储数据的数据类型|the data type|
|bk_unit|string|否|无|单位|the unit|
|bk_placeholder|string|否|无|占位符|the place holder|
|bk_asst_obj_id|string|否|无|如果有关联其它的模型，那么就必需设置此字段，否则就不需要设置|the object identifier|
|bk_asst_forward|string|否|无|关联方向，由前端自行设置|the association arrow|


- output

``` json
{
    "result":true,
    "bk_error_code":0,
    "bk_error_msg":"",
    "data":"success"
}
```

- output字段说明

| 名称  | 类型  | 说明 |Description|
|---|---|---|---|
| result | bool | 请求成功与否。true:请求成功；false请求失败 |request result true or false|
| bk_error_code | int | 错误编码。 0表示success，>0表示失败错误 |error code. 0 represent success, >0 represent failure code |
| bk_error_msg | string | 请求失败返回的错误信息 |error message from failed request|
| data | string| 请求返回的数据 |the data response|



# 查询对象模型属性

- API : POST /api/{version}/object/attr/search
- API 名称：search_object_attribute
- 功能说明：
	- 中文： 查询模型属性（字段）
	- English：search the  object attribute 

- input body

``` json
{
    "bk_obj_id": "process",
    "bk_supplier_account": "0"
}
```

**注:以上 JSON 数据中各字段的取值仅为示例数据。**

- input 字段说明

| 字段|类型|必填|默认值|说明|Description|
|---|---|---|---|---|---|
|issystem|bool|否|无|系统内部流转使用|internal use|
|isapi|bool|否|无|只有API调用才需要被设置|only API calls need to be set.|
|creator|string|否|无|数据的创建者|creator|
|description|string|否|无|数据的描述信息|description|
|editable|bool|否|无|表明数据是否可编辑|editability|
|isonly|bool|否|无|表明唯一性|unique identity|
|isreadonly|bool|否|无|表明是否只读|true:read-only,  false:writable|
|isrequired|bool|否|无|表明是否必填|true:required， false: option|
|bk_property_group|string|否|无|字段分栏的名字|grouping attributes|
|bk_obj_id|string|否|无|模型ID|the object identifier|
|option|string|否|无|用户自定义内容，存储的内容及格式由调用方决定|custom content|
|bk_supplier_account| string| 否| 无|开发商账号|supplier account code|
|bk_property_id|string|否|无|模型的属性ID|attribute identifier|
|bk_property_name|string|否|无|模型属性名，用于展示|the attribute name|
|bk_property_type|string|否|无|定义的属性字段用于存储数据的数据类型|the data type|
|unit|string|是|无|单位|the unit|
|placeholder|string|否|无|占位符|the placeholder|
|create_time|string|否|无|数据创建的时间|data creation time 
|last_time|string|否|无|数据最后被更新的时间|the last time the data is updated.|
|bk_asst_obj_id|string|否|无|模型的标识符ID|the object identifier|


- output 

``` json
{
    "result": true,
    "bk_error_code": 0,
    "bk_error_msg": null,
    "data": [
        {
            "bk_asst_forward": "",
            "bk_asst_obj_id": "",
            "bk_asst_type": 0,
            "create_time": "2018-03-08T11:30:27.898+08:00",
            "creator": "cc_system",
            "description": "",
            "editable": false,
            "id": 51,
            "isapi": false,
            "isonly": true,
            "ispre": true,
            "isreadonly": false,
            "isrequired": true,
            "last_time": "2018-03-08T11:30:27.898+08:00",
            "bk_obj_id": "process",
            "option": "",
            "placeholder": "",
            "bk_property_group": "default",
            "bk_property_group_name": "基础信息",
            "bk_property_id": "bk_process_name",
            "bk_property_index": 0,
            "bk_property_name": "进程名称",
            "bk_property_type": "singlechar",
            "bk_supplier_account": "0",
            "unit": ""
        }
       ]
}
        
```

**注:以上 JSON 数据中各字段的取值仅为示例数据。**

- output字段说明

| 名称  | 类型  | 说明 |Description|
|---|---|---|---|
| result | bool | 请求成功与否。true:请求成功；false请求失败 |request result true or false|
| bk_error_code | int | 错误编码。 0表示success，>0表示失败错误 |error code. 0 represent success, >0 represent failure code |
| bk_error_msg | string | 请求失败返回的错误信息 |error message from failed request|
| data | array| 请求返回的数据 |the data response|

data字段说明

| 字段|类型|说明|Description|
|---|---|---|---|
|creator|string|数据的创建者|creator|
|description|string|数据的描述信息|description|
|editable|bool|表明数据是否可编辑|editability|
|isonly|bool|表明唯一性|unique identity|
|ispre|bool|true:预置字段,false:非内置字段|preset fields|
|isreadonly|bool|true:只读，false:非只读|true:read-only， false:writable|
|isrequired|bool|true:必填，false:可选|true:required，false: option|
|option|string|用户自定义内容，存储的内容及格式由调用方决定|custom content|
|unit|string|单位|the unit|
|placeholder|string|占位符|the placeholder|
|bk_property_group|string|字段分栏的名字|group recognition|
|bk_obj_id|string|模型ID|the object identifier|
| bk_supplier_account| string|开发商账号|supplier account code|
|bk_property_id|string|模型的属性ID|attribute identifier|
|bk_property_name|string|模型属性名，用于展示|the attribute name|
|bk_property_type|string|定义的属性字段用于存储数据的数据类型|the data type|
|bk_asst_obj_id|string|如果有关联其它的模型，那么就必需设置此字段，否则就不需要设置|the object identifier|
|bk_asst_forward|string|关联方向，由调用方自行设置|the associated direction|