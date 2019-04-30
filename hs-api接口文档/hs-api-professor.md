#  华商教授端接口文档

##  获取教授个人信息

##  修改教授个人信息

## 修改密码

## 文件上传

> * POST
> * /file/upload.do

### 参数

名称|类型|是否必填|说明
:---:|:---:|:---:|:---:
multipartFile|MultipartFile|是|要上传的文件

### 返回值

```json
{
    code: "0080",
    flag: 0,
    message: "上传文件成功",
    objectList: {
        id: 92,     //文件ID   
        url: "http://13.59.102.146/group1/M00/00/01/rB8pIFzHHL-AOMcJAAAbtrJR3Rg608.bmp",    //文件url
        code: 1
    }
}
```

## 获取教授开设课程列表***

> *  POST
> * /course/getCoursesByTeacherId

### 参数

名称|类型|是否必填|说明
:---:|:---:|:---:|:---:
teacherId|Integer|是|教授ID

### 返回值

```json
{
    "code": "ACK",          //状态码
    "message": "success",           //信息提示
    "data": [           //数据
        {
            "id": 45,               //课程ID
            "name": "创新思维与细节管理",            //课程题目
            "status": "1",            //状态 （0==申请课程；1==审核；2==材料上传；3==开课；4==结课）
            "totalStartTime": "2018-01-17 06:00:00",      //总开课时间
            "totalStopTime": "2018-01-23 06:00:00",     //总结课时间
            "period": "5",              //第几期
            "summary": "刘悦坦教授讲课轻松幽默、深入浅出，让学员们在轻松的气氛中学习到营销管理学知识和做人经商的道理。",     //摘要
            "teachPointList": [           //教学点详情
                {
                    "codeFlag": 0,          //教学点code
                    "codeFlagName": "罗马",       //教学点名称
                    "room": "Viale del Pattinaggio,100,Roma 喜来登酒店",         //具体上课地点
                    "startTime": "2018-01-22 06:00:00",         //开始时间
                    "stopTime": "2018-01-23 06:00:00",        //结束时间
                    "state": 1              //课程状态
                },
                {
                    "codeFlag": 3,
                    "codeFlagName": "普拉托",
                    "room": "Via degli Olmi,7, Calenzano ,Mir 酒店",
                    "startTime": "2018-01-19 06:00:00",
                    "stopTime": "2018-01-20 06:00:00",
                    "state": 1
                },
                {
                    "codeFlag": 1,
                    "codeFlagName": "米兰",
                    "room": "Piazza della repubblica 20,milano 威斯汀酒店",
                    "startTime": "2018-01-17 06:00:00",
                    "stopTime": "2018-01-18 06:00:00",
                    "state": 1
                }
            ],
            "page": null      //分页信息
        }
    ],
    "page": {     //分页信息
        "total": 1,             //总条数
        "totalPages": 1,      //总页数
        "pageNum": 1,     //当前页码
        "pageSize": 10        //每页包含记录条数
    },
    "ext": null
}
```

## 课程跟踪详情***

> * POST
> * course/courseTrackingDetail

### 参数

名称|类型|是否必填|说明
:---:|:---:|:---:|:---:
courseId|Integer|是|课程ID

### 返回值

```json
{
    "code": "ACK",
    "message": "success",
    "data": {
        "status": "2",               //审核状态（0==申请课程；1==审核；2==材料上传；3==开课；4==结课）
        "applyTime": "2019-04-118 10:01:36",    //申请时间
        "auditSuccessTime": null,       //初步审核成功时间
        "uploadTime": null,           //上传材料成功时间
        "courseStartTime": null,        //开课时间（流程显示）
        "courseStopTime": null,         //结课时间（流程显示）
        "courseId": 45,           //课程ID
        "courseName": "创新思维与细节管理",          //课程题目
        "period": "5",        //第几期
        "employer": "山东大学",         //工作单位
        "realName": "刘悦坦",         //教授姓名
        "academic": "教授",           //职称
        "totalBegin": "2019-05-135 05:00:00",       //总开课时间
        "totalEnd": "2019-05-143 05:00:00",         //总结课时间
        "teachPointList": [     //教学点列表
            {
                "courseId": 45,       //课程ID
                "codeFlag": 1,        //教学点code
                "codeFlagName": "米兰",       //教学点名称
                "room": "Viale del Pattinaggio,100,Roma 喜来登酒店",     //具体上课地点
                "startTime": "2019-05-141 05:00:00",      //该教学点开课时间
                "stopTime": "2019-05-143 05:00:00",       //该教学点结课时间
                "state": 1        //课程状态
            },
            {
                "courseId": 46,
                "codeFlag": 3,
                "codeFlagName": "普拉托",
                "room": "Via degli Olmi,7, Calenzano ,Mir 酒店",
                "startTime": "2019-05-138 05:00:00",
                "stopTime": "2019-05-140 05:00:00",
                "state": 1
            },
            {
                "courseId": 47,
                "codeFlag": 1,
                "codeFlagName": "米兰",
                "room": "Piazza della repubblica 20,milano 威斯汀酒店",
                "startTime": "2019-05-135 05:00:00",
                "stopTime": "2019-05-137 05:00:00",
                "state": 1
            }
        ],
        "teacherId": 44,        //教授ID
        "photoId": 75,        //教授头像ID
        "photoUrl": "http://13.59.102.146/group1/M00/00/0E/eSiCMlq7McWAeo1eAAHwIkQTzWY874.jpg",     //头像url
        "summary": "刘悦坦教授讲课轻松幽默、深入浅出，让学员们在轻松的气氛中学习到营销管理学知识和做人经商的道理。",       //课程摘要详情
        "auditMessage": "您好！您申请的创新思维与细节管理课程有新动态，请前往行程跟踪接受邀请。",      //审核消息
        "auditor": "admin",       //审核人
        "auditTime": "2019-04-118 01:03:57",      //审核时间
        "fileList": [],     //文件材料列表
        "commentList": []       //评论列表
    },
    "page": null,
    "ext": null
}
```

## 上传文件（课程所需文件）***

### 注：上传过程为，先调用上传文件接口，将文件上传到文件服务器，获得文件id和url，再调用本接口将文件id传回。

> * POST
> * course/uploadCourseFile

### 参数

名称|类型|是否必填|说明
:---:|:---:|:---:|:---:
courseId|Integer|是|课程ID
fileIdList|List<Integer>|是|文件ID列表，Integer类型的List

### 返回值

```json
{
    "code": "ACK",          //状态码
    "message": "success",           //信息提示
    "data":null,
    "page": null,
    "ext": null
}
```

## 申请新课程

## 行程跟踪列表***

> * POST
> * /trip/getTripTrackingList

### 参数

名称|类型|是否必填|说明
:---:|:---:|:---:|:---:
teacherId|Integer|是|教授ID
pageNum|Integer|否|当前页码
pageSize|Integer|否|每页包含的记录条数

### 返回值

```json
{
    "code": "ACK",
    "message": "success",
    "data": [
        {
            "tripId": 1,        //行程ID
            "name": "创新思维与细节管理",      //课程题目
            "status": "2",        //行程状态
            "totalStartTime": "2019-04-119 10:18:48",     //总开课时间
            "totalStopTime": "2019-05-143 05:00:00",      //总结课时间
            "period": "5",        //第几期
            "summary": "刘悦坦教授讲课轻松幽默、深入浅出，让学员们在轻松的气氛中学习到营销管理学知识和做人经商的道理。",     //课程摘要
            "teachPointList": [       //教学点列表
                {
                    "courseId": 45,     //课程ID
                    "codeFlag": 1,      //教学点code
                    "codeFlagName": "米兰",     //教学点名称
                    "room": "Viale del Pattinaggio,100,Roma 喜来登酒店",     //具体上课地点
                    "startTime": "2019-05-141 05:00:00",      //该教学点开始时间
                    "stopTime": "2019-05-143 05:00:00",       //该教学点结束时间
                    "state": 1        //课程状态
                },
                {
                    "courseId": 46,
                    "codeFlag": 3,
                    "codeFlagName": "普拉托",
                    "room": "Via degli Olmi,7, Calenzano ,Mir 酒店",
                    "startTime": "2019-05-138 05:00:00",
                    "stopTime": "2019-05-140 05:00:00",
                    "state": 1
                },
                {
                    "courseId": 47,
                    "codeFlag": 1,
                    "codeFlagName": "米兰",
                    "room": "Piazza della repubblica 20,milano 威斯汀酒店",
                    "startTime": "2019-05-135 05:00:00",
                    "stopTime": "2019-05-137 05:00:00",
                    "state": 1
                }
            ]
        }
    ],
    "page": {
        "total": 1,
        "totalPages": 1,
        "pageNum": 1,
        "pageSize": 10
    },
    "ext": null
}
```

## 行程跟踪详情***

> * POST
> * /trip/tripTrackingDetail

### 参数

名称|类型|是否必填|说明
:---:|:---:|:---:|:---:
tripId|Integer|是|行程ID

### 返回值

```json
{
    "code": "ACK",
    "message": "请求成功",
    "data": {
        "tripId": 1,        //行程ID
        "tripProgress": {       //行程进度
            "status": "2",        //行程状态
            "waitInvitationTime": "2019-04-119 10:18:48",   //等待邀请时间
            "acceptInvitationTime": "2019-04-119 10:23:33",   //接受邀请时间
            "boardAndLodgingTime": "2019-04-119 10:33:26",    //食宿确认时间
            "uploadTime": null    //上传材料成功时间
        },
        "courseDetail": {         //课程信息
            "courseId": 45,       //课程ID
            "courseName": "创新思维与细节管理",      //课程题目
            "period": "5",        //第几期
            "employer": "山东大学",     //教授工作单位
            "realName": "刘悦坦",      //真实姓名
            "academic": "教授",       //职称
            "totalBegin": "2019-05-135 05:00:00",     //总开课时间
            "totalEnd": "2019-05-143 05:00:00",       //总结课时间
            "teachPointList": [     //教学点列表
                {
                    "courseId": 45,     //课程ID
                    "codeFlag": 1,      //教学点code
                    "codeFlagName": "米兰",       //教学点名称
                    "room": "Viale del Pattinaggio,100,Roma 喜来登酒店",     //具体上课地点
                    "startTime": "2019-05-141 05:00:00",      //该教学点开始时间
                    "stopTime": "2019-05-143 05:00:00",       //该教学点结束时间
                    "state": 1        //课程状态
                },
                {
                    "courseId": 46,
                    "codeFlag": 3,
                    "codeFlagName": "普拉托",
                    "room": "Via degli Olmi,7, Calenzano ,Mir 酒店",
                    "startTime": "2019-05-138 05:00:00",
                    "stopTime": "2019-05-140 05:00:00",
                    "state": 1
                },
                {
                    "courseId": 47,
                    "codeFlag": 1,
                    "codeFlagName": "米兰",
                    "room": "Piazza della repubblica 20,milano 威斯汀酒店",
                    "startTime": "2019-05-135 05:00:00",
                    "stopTime": "2019-05-137 05:00:00",
                    "state": 1
                }
            ],
            "teacherId": 44,    //教授ID
            "photoId": 75,      //头像ID
            "photoUrl": "http://13.59.102.146/group1/M00/00/0E/eSiCMlq7McWAeo1eAAHwIkQTzWY874.jpg",   //头像url
            "summary": "刘悦坦教授讲课轻松幽默、深入浅出，让学员们在轻松的气氛中学习到营销管理学知识和做人经商的道理。"    //课程摘要
        },
        "invitationList": [     //邀请表列表
            {
                "agree": "1",       //是否接受邀请（0==未确认；1==同意；2==更改；3==取消开课）
                "inviteList": [    //教学点列表
                    {
                        "id": 1,      //邀请表ID
                        "city": "米兰",     //城市
                        "place": "Viale del Pattinaggio,100,Roma 喜来登酒店",    //地点
                        "startTime": "2019-05-21T05:00:00.000+0000",      //开始时间
                        "stopTime": "2019-05-23T05:00:00.000+0000"        //结束时间
                    }
                ],
                "message": "学院已确认您的操作！"   //提示信息
            }
        ],
        "boardAndLodgingList": [      //食宿确认
            {
                "id": 1,        //食宿表ID
                "city": "米兰",     //城市
                "place": "Viale del Pattinaggio,100,Roma 喜来登酒店",    //地点
                "startTime": "2019-05-21T05:00:00.000+0000",      //开始时间
                "stopTime": "2019-05-23T05:00:00.000+0000"      //结束时间
            },
            {
                "id": 2,
                "city": "普拉托",
                "place": "Via degli Olmi,7, Calenzano ,Mir 酒店",
                "startTime": "2019-05-18T05:00:00.000+0000",
                "stopTime": "2019-05-20T05:00:00.000+0000"
            },
            {
                "id": 3,
                "city": "米兰",
                "place": "Piazza della repubblica 20,milano 威斯汀酒店",
                "startTime": "2019-05-15T05:00:00.000+0000",
                "stopTime": "2019-05-17T05:00:00.000+0000"
            }
        ],
        "tripFile": {     //手续材料文件
            "visaId": 90,       //签证文件ID
            "visaUrl": "http://13.59.102.146/group1/M00/00/01/rB8pIFzG1jSAIDBoAAAbtrJR3Rg742.bmp",    //签证文件url
            "planeTicketId": 90,      //机票文件ID
            "planeTicketUrl": "http://13.59.102.146/group1/M00/00/01/rB8pIFzG1jSAIDBoAAAbtrJR3Rg742.bmp"    //机票文件url
        }
    },
    "page": null,
    "ext": null
}
```

## 教授接受邀请确认***

> * POST
> * /trip/acceptInvitation

### 参数

名称|类型|是否必填|说明
:---:|:---:|:---:|:---:
tripId|Integer|是|行程ID
agree|String|是|接受邀请（1==同意；2==更改；3==取消开课）
classList|List<ClassDto>|否|更改的信息

#### 入参json

```json
{
	"tripId": 1,
	"agree": "1",
	"classList":[
		{
			"codeFlag": ,     //教学点code
			"codeFlagName": ,   //教学点名称
			"startTime": ,      //开始时间
			"stopTime":         //结束时间
		}]
	
}
```

### 返回值

```json
{
    "code": "ACK",
    "message": "无邀请记录",
    "data": null,
    "page": null,
    "ext": null
}
```

## 食宿确认***

> * POST
> * /trip/confirmBoardAndLodging

### 参数

名称|类型|是否必填|说明
:---:|:---:|:---:|:---:
tripId|Integer|是|行程ID
need|String|是|是否需要学院安排食宿（0==不需要；1==需要）

### 返回值

```json
{
    "code": "ACK",
    "message": "请求成功",
    "data": null,
    "page": null,
    "ext": null
}
```

## 上传签证、机票图片***

### 注：上传过程为，先调用上传文件接口，将文件上传到文件服务器，获得文件id和url，再调用本接口将文件id传回。

> * POST
> * /trip/uploadTripFile

### 参数

名称|类型|是否必填|说明
:---:|:---:|:---:|:---:
tripId|Integer|是|行程ID
visaId|Integer|否|签证文件ID
planeTicketId|Integer|否|机票文件ID

### 返回值

```json
{
    "code": "ACK",
    "message": "请求成功",
    "data": null,
    "page": null,
    "ext": null
}
```

