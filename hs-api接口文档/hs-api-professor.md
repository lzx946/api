#  华商教授端接口文档

##  获取教授个人信息

##  修改教授个人信息

## 修改密码

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

## 上传文件（课程所需文件）***

## 申请新课程

## 行程跟踪列表***

## 行程跟踪详情***

## 教授接受邀请确认***

## 食宿安排申请***

## 上传签证、机票图片***

