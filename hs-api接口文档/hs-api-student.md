# 华商学生端接口

##  获取学生个人信息

##  修改学生个人信息

## 修改密码

## 多个教学点课程详情

> * POST
> * /getCourseDetail

### 参数

名称|类型|是否必填|说明
:---:|:---:|:---:|:---:
id|Integer|是|课程ID

### 返回值

```json
{
    "flag": 1,
    "code": "0000",
    "message": "课程信息获取成功",
    "objectList": [
        {
            "realname": "成栋",       //教授姓名
            "academic": "教授",       //职称
            "url": "http://13.59.102.146/group1/M00/00/0E/eSiCMlrPcUyAXrKWAANTO57Azgc951.jpg",    //头像
            "employer": "中国人民大学",   //工作单位
            "totalbegin": "2018年05月10日",    //总开课时间
            "totalend": "2018年05月18日",    //总节课时间
            "courses": [
                {
                    "time": "2018年05月17日-05月18日",   //时间
                    "endtime": 1526572800000,
                    "id": 57,       //课程ID
                    "room": "Via CaVour, 50/a",       //具体上课地点
                    "codeflagname": "罗马",       //教学点名称
                    "starttime": "2018-05-17 13:00:00",     //开始时间
                    "stoptime": "2018-05-18 13:00:00",      //结束时间
                    "createtime": "2018-04-13 11:54:11",    //创建时间
                    "period": "9"     //第几期
                },
                {
                    "time": "2018年05月14日-05月15日",
                    "endtime": 1526313600000,
                    "id": 58,
                    "room": "西班牙马德里",
                    "codeflagname": "马德里",
                    "starttime": "2018-05-14 13:00:00",
                    "stoptime": "2018-05-15 13:00:00",
                    "createtime": "2018-04-13 11:59:38",
                    "period": "9"
                },
                {
                    "time": "2018年05月10日-05月12日",
                    "endtime": 1526054400000,
                    "id": 56,
                    "room": "Hotel Leonardo(Paolo Sarpi 唐人街附近)",
                    "codeflagname": "米兰",
                    "starttime": "2018-05-10 13:00:00",
                    "stoptime": "2018-05-12 13:00:00",
                    "createtime": "2018-04-13 11:50:46",
                    "period": "9"
                }
            ],
            "id": 56,
            "name": "互联网电子商务与供应链",      //课程名称
            "teacherid": 49,      //教授ID
            "starttime": "2018-05-10 13:00:00",     
            "stoptime": "2018-05-12 13:00:00",
            "createtime": "2018-04-13 11:50:46",
            "summary": "互联网电子商务与供应链管理简介：\r\n主要讲授电子商务的核心知识，使学生电子商务战略、网络营销、网上产品与服务的销售、供应链管理等最新发展趋势，帮助企业有效利用电子商务技术的策略与方法，解决企业的实际问题，以提升企业在互联网时代的竞争力。"   //摘要
        }
    ]
}
```

## 单个教学点课程详情

> * POST
> * /course/getCourseDetailSingle

### 参数

名称|类型|是否必填|说明
:---:|:---:|:---:|:---:
courseId|Integer|是|课程ID

### 返回值

```json
{
    "code": "ACK",
    "message": "ACK",
    "data": {
        "id": 57,       //课程ID
        "name": "互联网电子商务与供应链",      //题目
        "teacherId": 49,        //教授ID
        "startTime": "2018-05-137 05:00:00",        //开始时间
        "stopTime": "2018-05-138 05:00:00",       //结束时间
        "createTime": "2018-04-103 03:54:11",       //创建时间
        "summary": "互联网电子商务与供应链管理简介：\r\n主要讲授电子商务的核心知识，使学生电子商务战略、网络营销、网上产品与服务的销售、供应链管理等最新发展趋势，帮助企业有效利用电子商务技术的策略与方法，解决企业的实际问题，以提升企业在互联网时代的竞争力。",    //摘要
        "realName": "成栋",       //教授姓名
        "academic": "教授",       //职称
        "url": "http://13.59.102.146/group1/M00/00/0E/eSiCMlrPcUyAXrKWAANTO57Azgc951.jpg",        //头像
        "employer": "中国人民大学",       //工作单位
        "room": "Via CaVour, 50/a",     //具体上课地点
        "codeFlagName": "罗马",         //教学点
        "period": "9"       //第几期
    },
    "page": null,
    "ext": null
}
```


## 我的课程列表

> * POST
> * /course/getMyCourseList

### 参数

名称|类型|是否必填|说明
:---:|:---:|:---:|:---:
studentId|Integer|是|学生ID

### 返回值

```json
{
    "code": "ACK",
    "message": "success",
    "data": [
        {
            "courseId": 57,        //课程ID
            "enlistId": 46,         //报名表ID
            "name": "互联网电子商务与供应链",        //课程名称
            "period": "9",            //第几期
            "codeFlag": 0,        //教学点code
            "codeFlagName": "罗马",       //教学点名称
            "room": "Via CaVour, 50/a",       //具体上课地点
            "startTime": "2018-05-137 05:00:00",          //开始时间
            "stopTime": "2018-05-138 05:00:00",         //结束时间
            "realName": "成栋",               //教授姓名
            "photoId": 79,                      //教授头像id
            "photoUrl": "http://13.59.102.146/group1/M00/00/0E/eSiCMlrPcUyAXrKWAANTO57Azgc951.jpg",     //教授头像url
            "academic": "教授",             //职称
            "employer": "中国人民大学",           //工作单位
            "status": "2",      //课程状态（0==未开课；1==已开课；2==已结束；3==已退报）
            "page": null
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

## 我的课程状态跟踪详情

## 报名

> * POST
> * enlist/insertEnlist

### 参数

名称|类型|是否必填|说明
:---:|:---:|:---:|:---:
userid|String|是|学生ID
courseid|String|是|课程ID

### 返回值

```json
{
    "code": "ACK",
    "message": "报名成功",
    "data": null,
    "page": null,
    "ext": null
}
```


## 退报

> * POST
> * enlist/backEnlist

### 参数

名称|类型|是否必填|说明
:---:|:---:|:---:|:---:
uid|String|是|学生ID
cid|String|是|课程ID

### 返回值

```json
{
    "code": "ACK",
    "message": "退报成功",
    "data": null,
    "page": null,
    "ext": null
}
```


## 签到

> * POST
> * wechat/signIn

### 参数

名称|类型|是否必填|说明
:---:|:---:|:---:|:---:
studentId|String|是|学生ID
courseId|String|是|课程ID
latitude|String|是|经度
longitude|String|是|纬度

### 返回值

```json
{
    "code": "ACK",
    "message": "签到成功",
    "data": null,
    "page": null,
    "ext": null
}
```



## 评论