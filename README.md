
知识图谱可视化：https://kg.ownthink.com/

数据下载：关注微信公众号【思知机器人】回复【数据下载】（新版知识图谱开放时间预计为8月份左右，可以先start项目，我们将发布更大更全的知识图谱，亿级别数据集）


# 知识图谱
>>> 知识图谱融合了两千五百多万的实体，拥有亿级别的实体属性关系。

## 知识图谱API

#### 1. 获取歧义关系（mention -> entity）
>>> 输入名称(mention)返回对应实体(entity)的列表。如遇到共指问题，请求将会自动对名称(mention)进行共指消解。

请求方式（名称：mention_name）：
```
https://api.ownthink.com/kg/ambiguous?mention=mention_name
```
mention_name举例：
```
苹果
苹果手机
苏大
苏州大学
Soochow University
番茄
西红柿
```
请求示例：
https://api.ownthink.com/kg/ambiguous?mention=苹果

返回格式说明：
```
[
    [
        "ambiguous_entity1",            // 歧义实体1
        965445
    ],
    [
        "ambiguous_entity2",            // 歧义实体2
        864451
    ],
    [
        "ambiguous_entity3",            // 歧义实体3
        764322
    ]
]
```

#### 2. 获取实体知识（entity -> knowledge）
>>> 输入实体(entity)返回字典格式的全部知识。实体名一般为消歧后的实体(entity)，如果直接输入名称(mention)，请求将会自动进行消歧处理并返回实体(entity)全部知识。

请求方式（实体：entity_name）：
```
https://api.ownthink.com/kg/knowledge?entity=entity_name
```
entity_name举例：
```
苹果
苹果[2007年李玉执导电影]
苹果公司
刘德华
苏大
苏州大学
西红柿
```
请求示例：
https://api.ownthink.com/kg/knowledge?entity=刘德华

返回格式说明：
```
{
    "entity": "entity_name",            // 实体名称
    "desc": "entity_desc",              // 实体描述
    "avp": [                            // AVP列表
        [
            "entity_attribute1",        // 属性1
            "entity_value1"             // 值
        ],
        [
            "entity_attribute2",        // 属性2
            "entity_value2"             // 值
        ]
    ],
    "tag": [                            // 标签列表
        "tag1",                         // 标签1
        "tag2"                          // 标签2
    ]
}
```

#### 3. 获取属性值（entity&attribute -> value）
>>> 给定实体(entity)和属性(attribute)返回其对应的值(value)列表。实体名一般为实体(entity)，属性(attribute)一般为全部知识AVP列表中的属性，如果没有直接对应的entity与attribute请求将会对entity与attribute进行消歧、共指消解处理。

请求方式（实体：entity_name、属性：attribute_name）：
```
https://api.ownthink.com/kg/eav?entity=entity_name&attribute=attribute_name
```
entity&attribute举例：
```
苹果[蔷薇科苹果属果实]      颜色
哈密瓜                     拉丁学名
哈密瓜                     别称
航母                       地位
图灵                       主要成就
图灵奖                     奖励对象
```
请求示例：
https://api.ownthink.com/kg/eav?entity=苹果&attribute=颜色

返回格式说明：
```
[
    "entity_value1",                    // 实体属性所对应的值1
    "entity_value2",                    // 实体属性所对应的值2
    "entity_value3"                     // 实体属性所对应的值3
]
```

### 思知人工智能群
```
知识图谱QQ群：55152968
微信群：可联系作者MrYener邀请进群
```


<p>捐赠作者(您的鼓励是作者开源最大的动力！！！)：<a href="https://github.com/ownthink/Jiagu/wiki/donation"target="_blank">捐赠致谢</a> </p>

![收款码](https://github.com/ownthink/KnowledgeGraph/raw/master/img/%E6%94%B6%E6%AC%BE%E7%A0%81.jpg)

