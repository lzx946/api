# 华商学生端接口

##  获取学生个人信息

##  修改学生个人信息

## 修改密码

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

## 退报

## 签到

## 评论