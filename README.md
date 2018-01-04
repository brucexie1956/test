
### 通用状态码

| 状态码\<code> |   参数说明   |
| ----- | :----------|
|  200  |     成功    |
|  301  |   请求失败   |
|  400  |   参数错误   |
|  401  |   未授权    |
|  403  |   无权访问该资源(白名单验证)   |
|  415  |   请求格式错误   |
|  422  |   校验错误   |
|  430  |   数字格式错误   |
|  431  |   非空字段为空   |
|  432  |   需要登录访问(资源登录验证)   |
|  500  |   系统错误   |

### 通用参数说明

| 参数名 |   参数说明   |
| ------- | :----------|
|  code   |  响应状态码  |
|  ts     |  服务器时间戳 |
| message |  响应状态说明(出错时,这里会提示错误信息) |
| data    |   响应数据   |
| app_key |   请求参数,表示当前项目.此key必填,有需要请联系管理员   |

### 数据分页说明
* 系统中所有查询条件关键字前面需要加"s_"标识

|参数名             |字段类型       |  参数说明                 |
| ---------------- | :-----------| :------------------------|
|  pageSize        |    number   |  每页记录数<默认20,最大500> |
|  pageNumber        |    number   |  当前页<默认第1页> |
|  result        |    array   |  查询结果数据 |
|  totalCount        |    number   |  总记录数 |
|  thisPageNumber        |    number   |  当前页 |
|  firstPage        |    boolean   |  是否为第一页 |
|  lastPage        |    boolean   |  是否为最后一页 |
|  hasNextPage        |    boolean   |  是否有下一页 |
|  hasPreviousPage        |    boolean   |  是否有上一页 |
|  lastPageNumber        |    number   |  最后一页页码 |
|  nextPageNumber        |    number   |  下一页是第几页 |
|  previousPageNumber        |    number   |  上一页是第几页 |
|  linkPageNumbers        |    number   |  页面链接 |

### 通用接口说明：
#### 获取省份信息接口
* 接口: http://${domain}/xhtest-api/location/findProvince
* 请求方式: GET
* 请求参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|
    
    
* 响应参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|
    | id            |  number       |     y        |  唯一键   |
    | provinceName  |  string       |     y        |  名称    |

* 响应成功实例:
```javascript
    {
        "code": 200,
        "message": "SUCCESS",
        "ts": 1512952278598
    }
```

* 响应失败实例:
```javascript
    {
        code: 200,
        message: "SUCCESS",
        data: [
            {
                id: 1,
                uuid: "d4a07a5a443f46a08c9b855db95ca7c0",
                createTime: 1514983155000,
                updateTime: 1514983155000,
                provinceCode: "11",
                provinceName: "北京市"
            },
            {
                id: 9,
                uuid: "d4a07a5a443f46a08c9b855db95ca7c0",
                createTime: 1514983156000,
                updateTime: 1514983156000,
                provinceCode: "31",
                provinceName: "上海市"
            },
            {
                id: 10,
                uuid: "d4a07a5a443f46a08c9b855db95ca7c0",
                createTime: 1514983156000,
                updateTime: 1514983156000,
                provinceCode: "32",
                provinceName: "江苏省"
            },
            {
                id: 11,
                uuid: "d4a07a5a443f46a08c9b855db95ca7c0",
                createTime: 1514983156000,
                updateTime: 1514983156000,
                provinceCode: "33",
                provinceName: "浙江省"
            },
            {
                id: 12,
                uuid: "d4a07a5a443f46a08c9b855db95ca7c0",
                createTime: 1514983156000,
                updateTime: 1514983156000,
                provinceCode: "34",
                provinceName: "安徽省"
            }
        ],
        ts: 1515035952385
    }
```

#### 获取城市信息接口
* 接口: http://${domain}/xhtest-api/location/findCity
* 请求方式: GET
* 请求参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|
    | provinceId    |  number       |     y        |  省份Id |
    
    
* 响应参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|
    | id            |  number       |     y        |  唯一键   |
    | cityName      |  string       |     y        |  城市名字 |

* 响应成功实例:
```javascript
    {
        "code": 200,
        "message": "SUCCESS",
        "ts": 1512952278598
    }
```

* 响应失败实例:
```javascript
    {
        code: 200,
        message: "SUCCESS",
        data: [
            {
                id: 6,
                uuid: "f682d5fa7bd34f088d8276665ac128ea",
                provinceId: 12,
                createTime: 1514983159000,
                updateTime: 1514983159000,
                cityCode: "340100000000",
                cityName: "合肥市"
            },
            {
                id: 18,
                uuid: "f682d5fa7bd34f088d8276665ac128ea",
                provinceId: 12,
                createTime: 1514983159000,
                updateTime: 1514983159000,
                cityCode: "340200000000",
                cityName: "芜湖市"
            },
            {
                id: 227,
                uuid: "f682d5fa7bd34f088d8276665ac128ea",
                provinceId: 12,
                createTime: 1514983160000,
                updateTime: 1514983160000,
                cityCode: "341100000000",
                cityName: "滁州市"
            },
            {
                id: 254,
                uuid: "f682d5fa7bd34f088d8276665ac128ea",
                provinceId: 12,
                createTime: 1514983160000,
                updateTime: 1514983160000,
                cityCode: "341200000000",
                cityName: "阜阳市"
            },
            {
                id: 263,
                uuid: "f682d5fa7bd34f088d8276665ac128ea",
                provinceId: 12,
                createTime: 1514983160000,
                updateTime: 1514983160000,
                cityCode: "341300000000",
                cityName: "宿州市"
            }
        ],
        ts: 1515035998997
    }
```

#### 获取区县信息接口
* 接口: http://${domain}/xhtest-api/location/findCounty
* 请求方式: GET
* 请求参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|
    | cityId        |  string       |     y        |  城市Id |
    
    
* 响应参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|
    | id            |  number       |     y        |  唯一键   | 
    | countyName    |  string       |     y        |  区县名称 |

* 响应成功实例:
```javascript
    {
        "code": 200,
        "message": "SUCCESS",
        "ts": 1512952278598
    }
```

* 响应失败实例:
```javascript
    {
    code: 200,
    message: "SUCCESS",
    data: [
        {
            id: 1899,
            uuid: "12c73107f563407e89361ecc12c4161f",
            cityId: 254,
            createTime: 1514983172000,
            updateTime: 1514983172000,
            countyCode: "341202000000",
            countyName: "颍州区"
        },
        {
            id: 1916,
            uuid: "12c73107f563407e89361ecc12c4161f",
            cityId: 254,
            createTime: 1514983172000,
            updateTime: 1514983172000,
            countyCode: "341203000000",
            countyName: "颍东区"
        },
        {
            id: 1950,
            uuid: "12c73107f563407e89361ecc12c4161f",
            cityId: 254,
            createTime: 1514983172000,
            updateTime: 1514983172000,
            countyCode: "341221000000",
            countyName: "临泉县"
        },
        {
            id: 1963,
            uuid: "12c73107f563407e89361ecc12c4161f",
            cityId: 254,
            createTime: 1514983172000,
            updateTime: 1514983172000,
            countyCode: "341222000000",
            countyName: "太和县"
        }
    ],
    ts: 1515036143095
}
```

#### 获取乡镇信息接口
* 接口: http://${domain}/xhtest-api/location/findTown
* 请求方式: GET
* 请求参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|
    | countyId      |  string       |     y        |  区县Id |
    
    
* 响应参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|
    | id            |  number       |     y        |  唯一键   |
    | townName      |  string       |     y        |  乡镇名称 |

* 响应成功实例:
```javascript
    {
        "code": 200,
        "message": "SUCCESS",
        "ts": 1512952278598
    }
```

* 响应失败实例:
```javascript
    {
    code: 200,
    message: "SUCCESS",
    data: [
        {
            id: 28062,
            uuid: "44c1f0f29825408ca8d4fe9ab2431497",
            countyId: 1963,
            createTime: 1514983321000,
            updateTime: 1514983321000,
            townCode: "341222100000",
            townName: "城关镇"
        },
        {
            id: 28156,
            uuid: "44c1f0f29825408ca8d4fe9ab2431497",
            countyId: 1963,
            createTime: 1514983321000,
            updateTime: 1514983321000,
            townCode: "341222105000",
            townName: "倪邱镇"
        },
        {
            id: 28172,
            uuid: "44c1f0f29825408ca8d4fe9ab2431497",
            countyId: 1963,
            createTime: 1514983321000,
            updateTime: 1514983321000,
            townCode: "341222106000",
            townName: "李兴镇"
        },
        {
            id: 28524,
            uuid: "44c1f0f29825408ca8d4fe9ab2431497",
            countyId: 1963,
            createTime: 1514983323000,
            updateTime: 1514983323000,
            townCode: "341222121000",
            townName: "高庙镇"
        }
        {
            id: 28630,
            uuid: "44c1f0f29825408ca8d4fe9ab2431497",
            countyId: 1963,
            createTime: 1514983323000,
            updateTime: 1514983323000,
            townCode: "341222127000",
            townName: "郭庙镇"
        },
        {
            id: 28646,
            uuid: "44c1f0f29825408ca8d4fe9ab2431497",
            countyId: 1963,
            createTime: 1514983323000,
            updateTime: 1514983323000,
            townCode: "341222201000",
            townName: "赵集乡"
        },
        {
            id: 28663,
            uuid: "44c1f0f29825408ca8d4fe9ab2431497",
            countyId: 1963,
            createTime: 1514983323000,
            updateTime: 1514983323000,
            townCode: "341222203000",
            townName: "马集乡"
        }
    ],
    ts: 1515036168565
}
```


#### 获取图片验证码
* 接口: http://${domain}/xhtest-api/verCode
* 请求方式: GET
* 响应参数: img

#### 短信验证码获取接口
* 接口: http://${domain}/xhtest-api/smsCode
* 请求方式: POST
* 请求参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|
    | imageCode     |  string       |     y        |  验证码   |
    | mobile        |  string       |     y        |  手机号   |
    
    
* 响应参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|
    

* 响应成功实例:
```javascript
    {
        "code": 200,
        "message": "SUCCESS",
        "ts": 1512952278598
    }
```

* 响应失败实例:
```javascript
    {
        code: 432,
        message: "需要登录访问",
        ts: 1493731262065,
        data: "http://api-employee.mmall.com/login?appId=c3&appSecret=a2i23k234&redirectURL=http://authority.mmall.com/api/authority/isLogin"
    }
```

#### 获取Csrf-Token接口
* 接口: http://${domain}/xhtest-api/csrf/getToken
* 请求方式: POST
* 请求参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|
    
    
    
* 响应参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|
    | mobile        |  string       |     y        |  手机号   |
    

* 响应成功实例:
```javascript
    {
        code: 200,
        message: "成功",
        ts: 1493730826880
    }
```

* 响应失败实例:
```javascript
    {
        code: 432,
        message: "需要登录访问",
        ts: 1493731262065,
        data: "http://api-employee.mmall.com/login?appId=c3&appSecret=a2i23k234&redirectURL=http://authority.mmall.com/api/authority/isLogin"
    }
```
    
### 接口说明：
#### 登录接口
* 接口: http://${domain}/xhtest-api/login
* 请求方式: GET
* 请求参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|
    | imageCode     |  string       |     y        |  图片验证码 |
    | loginValue    |  string       |     y        |  登录名(用户名/手机号) |
    | password      |  string       |     y        |  登录密码 |
    
    
* 响应参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|
    | code          |  number       |     y        |  状态码   |

* 响应成功实例:
```javascript
    {
        code: 200,
        message: "成功",
        ts: 1493730826880
    }
```

* 响应失败实例:
```javascript
    {
        code: 432,
        message: "需要登录访问",
        ts: 1493731262065,
        data: "http://api-employee.mmall.com/login?appId=c3&appSecret=a2i23k234&redirectURL=http://authority.mmall.com/api/authority/isLogin"
    }
```

#### 验证用户是否登录接口
* 接口: http://${domain}/xhtest-api/isLogin
* 请求方式: GET
* 请求参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|
    
    
* 响应参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|
    | code          |  number       |     y        |  状态码   |
    | data          |  json         |     y        |  相应数据   |

* 响应成功实例:
```javascript
    {
        code: 200,
        message: "成功",
        ts: 1493730826880,
        data: {
            employId: "51032485",
            name: "谢辉"
        }
    }
```

* 响应失败实例:
```javascript
    {
        code: 432,
        message: "需要登录访问",
        ts: 1493731262065,
        data: "http://api-employee.mmall.com/login?appId=c3&appSecret=a2i23k234&redirectURL=http://authority.mmall.com/api/authority/isLogin"
    }
```

#### 退出登录接口
* 接口: http://${domain}/xhtest-api/logout
* 请求方式: GET
* 请求参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|
    
    
* 响应参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|

* 响应成功实例:
```javascript
    {
        "code": 200,
        "message": "SUCCESS",
        "ts": 1512952278598
    }
```

* 响应失败实例:
```javascript
    {
        code: 432,
        message: "需要登录访问",
        ts: 1493731262065,
        data: "http://api-employee.mmall.com/login?appId=c3&appSecret=a2i23k234&redirectURL=http://authority.mmall.com/api/authority/isLogin"
    }
```

#### 获取首页丢/捡信息列表接口
* 接口: http://${domain}/xhtest-api/losePick/index
* 请求方式: GET
* 请求参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|
    | s_eventType   | number        |     n        | 事件类型   |
    | s_loseType    | number        |     n        | 丢/捡类型   |
    | s_loseNumber  | number        |     n        | 证件号码   |
    
    
* 响应参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|
    | isAuditing    |  number       |     n        |  是否审核(1:已审核; 2:未审核) |
    | eventType     |  json         |     n        |  事件类型(1: 捡; 2:丢) |
    | itemType      |  number       |     n        |  丢失类型(1: 身份证; 2:驾驶证; 3:行驶证; 4:学生证; 5:准考证; 6:毕业证; 7:护照) |

* 响应成功实例:
```javascript
    {
        "code": 200,
        "message": "SUCCESS",
        "data": {
            "result": [
                {
                    "status": 1,
                    "version": 0,
                    "id": 1,
                    "itemType": 1,
                    "itemNumber": "************120192",
                    "locationProvinceCode": "1",
                    "locationProvinceName": "安徽省",
                    "locationCityCode": "1",
                    "locationCityName": "合肥市",
                    "locationAreaCode": "1",
                    "locationAreaName": "合肥市瑶海区",
                    "itemImage": "1",
                    "itemAddress": "安徽省合肥市",
                    "description": "身份证",
                    "contactUsername": "谢辉",
                    "contactPhone": "185****3176",
                    "contactEmail": "b****6@gmail.com",
                    "eventType": 2,
                    "eventTime": "2016-01-01 00:00:00.0",
                    "isAuditing": 1
                }
            ],
            "pageSize": 20,
            "totalCount": 1,
            "firstResult": 0,
            "firstPage": true,
            "lastPage": true,
            "hasNextPage": false,
            "hasPreviousPage": false,
            "lastPageNumber": 1,
            "thisPageFirstElementNumber": 1,
            "thisPageLastElementNumber": 1,
            "nextPageNumber": 2,
            "previousPageNumber": 0,
            "thisPageNumber": 1,
            "linkPageNumbers": [
                1
            ]
        },
        "ts": 1512948998829
    }
```

* 响应失败实例:
```javascript
    {
        code: 432,
        message: "需要登录访问",
        ts: 1493731262065,
        data: "http://api-employee.mmall.com/login?appId=c3&appSecret=a2i23k234&redirectURL=http://authority.mmall.com/api/authority/isLogin"
    }
```

#### 查看详情接口
* 接口: http://${domain}/xhtest-api/losePick/detail
* 请求方式: GET
* 请求参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|
    | id            | number        |     y        | 记录id    |
    
    
* 响应参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|
    | isAuditing    |  number       |     n        |  是否审核(1:已审核; 2:未审核) |
    | eventType     |  json         |     n        |  事件类型(1: 捡; 2:丢) |
    | itemType      |  number       |     n        |  丢失类型(1: 身份证; 2:驾驶证; 3:行驶证; 4:学生证; 5:准考证; 6:毕业证; 7:护照) |

* 响应成功实例:
```javascript
    {
        "code": 200,
        "message": "SUCCESS",
        "data": {
            "status": 1,
            "createTime": 1451577600000,
            "version": 1,
            "mark": "1",
            "itemType": 1,
            "itemNumber": "************120192",
            "locationProvinceCode": "1",
            "locationProvinceName": "安徽省",
            "locationCityCode": "1",
            "locationCityName": "合肥市",
            "locationAreaCode": "1",
            "locationAreaName": "合肥市瑶海区",
            "itemImage": "1",
            "itemAddress": "安徽省合肥市",
            "description": "身份证",
            "contactUsername": "谢辉",
            "contactPhone": "185****3176",
            "contactEmail": "b****6@gmail.com",
            "eventType": 2,
            "isAuditing": 1
        },
        "ts": 1512949863972
    }
```

* 响应失败实例:
```javascript
    {
        code: 432,
        message: "需要登录访问",
        ts: 1493731262065,
        data: "http://api-employee.mmall.com/login?appId=c3&appSecret=a2i23k234&redirectURL=http://authority.mmall.com/api/authority/isLogin"
    }
```

#### 新增丢/捡接口
* 接口: http://${domain}/xhtest-api/losePick/save
* 请求方式: POST
* 请求参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|
    | token         | string        |     y        | 请求token |
    | imageCode     | string        |     y        | 图片验证码 |
    | messageCode   | string        |     y        | 短信验证码 |
    | itemType   | string        |     y        | 物品类型(1:身份证; 2:驾驶证; 3: 行驶证; 4:学生证; 5:准考证; 6:毕业证; 7:护照; 8:港澳通行证; 9:户口本) |
    | itemNumber   | string        |     y        | 物品号码 |
    | locationProvinceCode   | string        |     y        | 丢失身份code |
    | locationProvinceName   | string        |     y        | 丢失省份名称 |
    | locationCityCode   | string        |     y        | 丢失城市code |
    | locationCityName   | string        |     y        | 丢失城市名称 |
    | locationAreaCode   | string        |     y        | 丢失区县code |
    | locationAreaName   | string        |     y        | 丢失区县名称 |
    | contactPhone   | string        |     y        | 联系电话 |
    | contactEmail   | string        |     n        | 联系人邮箱 |
    | eventType   | string        |     y        | 事件类型(1:捡; 2:丢) |
    | contactUsername   | string        |     y        | 联系人 |
    | itemAddress   | string        |     y        | 具体地址 |
    | eventTime   | string        |     y        | 发生时间 |
    
    
* 响应参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|
    | isAuditing    |  number       |     n        |  是否审核(1:已审核; 2:未审核) |
    | eventType     |  json         |     n        |  事件类型(1: 捡; 2:丢) |
    | itemType      |  number       |     n        |  物品类型(1:身份证; 2:驾驶证; 3: 行驶证; 4:学生证; 5:准考证; 6:毕业证; 7:护照; 8:港澳通行证; 9:户口本) |

* 响应成功实例:
```javascript
    {
        "code": 200,
        "message": "SUCCESS",
        "data": {
            "id": 2,
            "createTime": 1513675352158,
            "updateTime": 1513675352158,
            "status": 1,
            "version": 1,
            "userId": 1,
            "itemType": 1,
            "itemNumber": "341222199002131231",
            "locationProvinceCode": "11",
            "locationProvinceName": "安徽省",
            "locationCityCode": "12",
            "locationCityName": "合肥市",
            "locationAreaCode": "13",
            "locationAreaName": "瑶海区",
            "itemAddress": "阜阳市太和县",
            "contactPhone": "13988978787",
            "contactEmail": "13988978787@qq.com",
            "eventType": 1,
            "eventTime": "2017-12-11 11:11:11",
            "isAuditing": 1,
            "contactUsername": "花木兰"
        },
        "ts": 1513675352131
    }
```

* 响应失败实例:
```javascript
    {
        code: 432,
        message: "需要登录访问",
        ts: 1493731262065,
        data: "http://api-employee.mmall.com/login?appId=c3&appSecret=a2i23k234&redirectURL=http://authority.mmall.com/api/authority/isLogin"
    }
```

#### 更新丢/捡接口
* 接口: http://${domain}/xhtest-api/losePick/update
* 请求方式: POST
* 请求参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|
    | id            | number        |     y        | 请求操作记录Id |
    | token         | string        |     n        | 请求token |
    | itemType   | string        |     n        | 物品类型(1:身份证; 2:驾驶证; 3: 行驶证; 4:学生证; 5:准考证; 6:毕业证; 7:护照; 8:港澳通行证; 9:户口本) |
    | itemNumber   | string        |     n        | 物品号码 |
    | locationProvinceCode   | string        |     n        | 丢失身份code |
    | locationProvinceName   | string        |     n        | 丢失省份名称 |
    | locationCityCode   | string        |     n        | 丢失城市code |
    | locationCityName   | string        |     n        | 丢失城市名称 |
    | locationAreaCode   | string        |     n        | 丢失区县code |
    | locationAreaName   | string        |     n        | 丢失区县名称 |
    | contactPhone   | string        |     n        | 联系电话 |
    | contactEmail   | string        |     n        | 联系人邮箱 |
    | eventType   | string        |     n        | 事件类型(1:捡; 2:丢) |
    | contactUsername   | string        |     n        | 联系人 |
    | itemAddress   | string        |     n        | 具体地址 |
    | eventTime   | string        |     n        | 发生时间 |
    
    
* 响应参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|
    | isAuditing    |  number       |     n        |  是否审核(1:已审核; 2:未审核) |
    | eventType     |  json         |     n        |  事件类型(1: 捡; 2:丢) |
    | itemType      |  number       |     n        |  物品类型(1:身份证; 2:驾驶证; 3: 行驶证; 4:学生证; 5:准考证; 6:毕业证; 7:护照; 8:港澳通行证; 9:户口本) |

* 响应成功实例:
```javascript
    {
        "code": 200,
        "message": "SUCCESS",
        "data": {
            "id": 2,
            "createTime": 1513675352158,
            "updateTime": 1513675352158,
            "status": 1,
            "version": 1,
            "userId": 1,
            "itemType": 1,
            "itemNumber": "341222199002131231",
            "locationProvinceCode": "11",
            "locationProvinceName": "安徽省",
            "locationCityCode": "12",
            "locationCityName": "合肥市",
            "locationAreaCode": "13",
            "locationAreaName": "瑶海区",
            "itemAddress": "阜阳市太和县",
            "contactPhone": "13988978787",
            "contactEmail": "13988978787@qq.com",
            "eventType": 1,
            "eventTime": "2017-12-11 11:11:11",
            "isAuditing": 1,
            "contactUsername": "花木兰"
        },
        "ts": 1513675352131
    }
```

* 响应失败实例:
```javascript
    {
        code: 432,
        message: "需要登录访问",
        ts: 1493731262065,
        data: "http://api-employee.mmall.com/login?appId=c3&appSecret=a2i23k234&redirectURL=http://authority.mmall.com/api/authority/isLogin"
    }
```


#### 删除接口
* 接口: http://${domain}/xhtest-api/losePick/delete
* 请求方式: GET
* 请求参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|
    | id            | number        |     y        | 请求token |
    
    
* 响应参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|

* 响应成功实例:
```javascript
    {
        "code": 200,
        "message": "SUCCESS",
        "ts": 1512952278598
    }
```

* 响应失败实例:
```javascript
    {
        code: 432,
        message: "需要登录访问",
        ts: 1493731262065,
        data: "http://api-employee.mmall.com/login?appId=c3&appSecret=a2i23k234&redirectURL=http://authority.mmall.com/api/authority/isLogin"
    }
```

* ******************************************

#### 新增证件接口
* 接口: http://${domain}/xhtest-api/m/myCard/save
* 请求方式: POST
* 请求参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|
    | token         | string        |     y        | 请求token |
    | imageCode     | string        |     y        | 图片验证码 |
    | cardType      | number        |     y        | 证件类型(1:身份证; 2:驾驶证; 3: 行驶证; 4:学生证; 5:准考证; 6:毕业证; 7:护照; 8:港澳通行证; 9:户口本) |
    | cardNumber    | string        |     y        | 证件号(大于2位) |
    
    
* 响应参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|

* 响应成功实例:
```javascript
    {
        "code": 200,
        "message": "SUCCESS",
        "data": {
            "id": 1,
            "createTime": 1513690312000,
            "updateTime": 1513690312000,
            "status": 1,
            "mark": null,
            "version": 1,
            "userName": "admin",
            "email": "",
            "phone": "",
            "score": null,
            "lastLogin": 1513690312000,
            "isCheckPhone": 1,
            "isCheckEmail": 0
        },
        "ts": 1513690311539
    }
```

* 响应失败实例:
```javascript
    {
        code: 432,
        message: "需要登录访问",
        ts: 1493731262065,
        data: "http://api-employee.mmall.com/login?appId=c3&appSecret=a2i23k234&redirectURL=http://authority.mmall.com/api/authority/isLogin"
    }
```


#### 修改接口
* 接口: http://${domain}/xhtest-api/m/myCard/update
* 请求方式: POST
* 请求参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|
    | id            | number        |     y        | 主键      |
    | token         | string        |     y        | 请求token |
    | imageCode     | string        |     y        | 图片验证码 |
    | cardType      | number        |     y        | 证件类型(1:身份证; 2:驾驶证; 3: 行驶证; 4:学生证; 5:准考证; 6:毕业证; 7:护照; 8:港澳通行证; 9:户口本) |
    | cardNumber    | string        |     y        | 证件号(大于2位) |
    
    
* 响应参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|

* 响应成功实例:
```javascript
    {
        "code": 200,
        "message": "SUCCESS",
        "data": {
            "id": 1,
            "createTime": 1513690312000,
            "updateTime": 1513690312000,
            "status": 1,
            "mark": null,
            "version": 1,
            "userName": "admin",
            "email": "",
            "phone": "",
            "score": null,
            "lastLogin": 1513690312000,
            "isCheckPhone": 1,
            "isCheckEmail": 0
        },
        "ts": 1513690311539
    }
```

* 响应失败实例:
```javascript
    {
        code: 432,
        message: "需要登录访问",
        ts: 1493731262065,
        data: "http://api-employee.mmall.com/login?appId=c3&appSecret=a2i23k234&redirectURL=http://authority.mmall.com/api/authority/isLogin"
    }
```


#### 删除接口
* 接口: http://${domain}/xhtest-api/m/myCard/delete
* 请求方式: POST
* 请求参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|
    | id            | number        |     y        | 主键      |
    | token         | string        |     y        | 请求token |
    
    
* 响应参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|

* 响应成功实例:
```javascript
    {
        "code": 200,
        "message": "SUCCESS",
        "ts": 1512952278598
    }
```

* 响应失败实例:
```javascript
    {
        code: 432,
        message: "需要登录访问",
        ts: 1493731262065,
        data: "http://api-employee.mmall.com/login?appId=c3&appSecret=a2i23k234&redirectURL=http://authority.mmall.com/api/authority/isLogin"
    }
```

#### 个人信息发布接口
* 接口: http://${domain}/xhtest-api/m/losePick/list
* 请求方式: POST
* 请求参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|
    | eventType     | number        |     n        | 事件类型      |
    | itemType      | number        |     n        | 物品类型 |
    | itemNumber    | string        |     n        | 物品号码 |
    | pageNumber    | number        |     n        | 第几页 |
    | pageSize      | number        |     n        | 每页记录数 |
    
    
* 响应参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|

* 响应成功实例:
```javascript
    {
        "code": 200,
        "message": "SUCCESS",
        "data": {
            "result": [
                {
                    "id": 2,
                    "createTime": 1513675352000,
                    "updateTime": 1513675352000,
                    "status": 1,
                    "version": 1,
                    "userId": 1,
                    "itemType": 1,
                    "itemNumber": "341222199002131231",
                    "locationProvinceCode": "11",
                    "locationProvinceName": "安徽省",
                    "locationCityCode": "12",
                    "locationCityName": "合肥市",
                    "locationAreaCode": "13",
                    "locationAreaName": "瑶海区",
                    "itemAddress": "阜阳市太和县",
                    "contactPhone": "13988978787",
                    "contactEmail": "13988978787@qq.com",
                    "eventType": 1,
                    "eventTime": "2017-12-11 11:11:11",
                    "isAuditing": 1,
                    "contactUsername": "花木兰"
                },
                {
                    "id": 1,
                    "createTime": 1513675134000,
                    "updateTime": 1513675134000,
                    "status": 1,
                    "version": 1,
                    "userId": 1,
                    "itemType": 1,
                    "itemNumber": "341222199002131231",
                    "locationProvinceCode": "11",
                    "locationProvinceName": "安徽省",
                    "locationCityCode": "12",
                    "locationCityName": "合肥市",
                    "locationAreaCode": "13",
                    "locationAreaName": "瑶海区",
                    "contactPhone": "13988978787",
                    "contactEmail": "13988978787@qq.com",
                    "eventType": 1,
                    "isAuditing": 1,
                    "contactUsername": "花木兰"
                }
            ],
            "pageSize": 20,
            "totalCount": 2,
            "firstResult": 0,
            "firstPage": true,
            "lastPage": true,
            "hasNextPage": false,
            "hasPreviousPage": false,
            "lastPageNumber": 1,
            "thisPageFirstElementNumber": 1,
            "thisPageLastElementNumber": 2,
            "nextPageNumber": 2,
            "previousPageNumber": 0,
            "thisPageNumber": 1,
            "linkPageNumbers": [
                1
            ]
        },
        "ts": 1513696329636
    }
```

* 响应失败实例:
```javascript
    {
        code: 432,
        message: "需要登录访问",
        ts: 1493731262065,
        data: "http://api-employee.mmall.com/login?appId=c3&appSecret=a2i23k234&redirectURL=http://authority.mmall.com/api/authority/isLogin"
    }
```

* *************************************************************

#### 修改密码接口
* 接口: http://${domain}/xhtest-api/users/updatePassword
* 请求方式: POST
* 请求参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|
    | messageCode   | string        |     y        | 短信验证码 |
    | oldPassword   | string        |     y        | 原密码 |
    | newPassword   | string        |     y        | 新密码 |
    
    
* 响应参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|

* 响应成功实例:
```javascript
    {
        "code": 200,
        "message": "SUCCESS",
        "ts": 1512952278598
    }
```

* 响应失败实例:
```javascript
    {
        code: 432,
        message: "需要登录访问",
        ts: 1493731262065,
        data: "http://api-employee.mmall.com/login?appId=c3&appSecret=a2i23k234&redirectURL=http://authority.mmall.com/api/authority/isLogin"
    }
```


#### 验证用户名是否存在接口
* 接口: http://${domain}/xhtest-api/users/existsUsername
* 请求方式: POST
* 请求参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|
    | messageCode   | string        |     y        | 短信验证码 |
    | username      | string        |     y        | 修改后的用户名 |
    
    
* 响应参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|

* 响应成功实例:
```javascript
    {
        "code": 200,
        "message": "SUCCESS",
        "ts": 1512952278598
    }
```

* 响应失败实例:
```javascript
    {
        code: 432,
        message: "需要登录访问",
        ts: 1493731262065,
        data: "http://api-employee.mmall.com/login?appId=c3&appSecret=a2i23k234&redirectURL=http://authority.mmall.com/api/authority/isLogin"
    }
```


#### 修改手机号接口
* 接口: http://${domain}/xhtest-api/users/updatePhone
* 请求方式: POST
* 请求参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|
    | messageCode   | string        |     y        | 短信验证码 |
    | newPhone      | string        |     y        | 修改后的手机号 |
    
    
* 响应参数说明:

    | 参数名         | 参数类型        | 是否必须      |  参数说明  |
    | ------------- |:-------------:|:------------:| --------:|

* 响应成功实例:
```javascript
    {
        "code": 200,
        "message": "SUCCESS",
        "ts": 1512952278598
    }
```

* 响应失败实例:
```javascript
    {
        code: 432,
        message: "需要登录访问",
        ts: 1493731262065,
        data: "http://api-employee.mmall.com/login?appId=c3&appSecret=a2i23k234&redirectURL=http://authority.mmall.com/api/authority/isLogin"
    }
```
