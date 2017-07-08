﻿# WonderLand Beta1.0 ApiDoc - Base

标签（空格分隔）： WonderLand

---

[TOC]

---

## **开发环境**
- **wamp server 2.5**
- **CI框架 3.1.4**

---

## **Part 0 · 一些约定**

### **【一】接口返回格式**
- 返回类型为一个 **`json数组`**
| 成员        | 中文   | 类型       | 备注
| ----------- | ------ | ---------- | ----
| **type**    | 结果   | 数字       | 1成功，0失败 
| **message** | 消息   | 字符串     | 失败时：存一条错误信息
| **data**    | 数据   | 字符串数组 | 返回数据


- **成功例子**
```
{
	"type": 0,
	"message": "用户名  至少包含 6  个字",
	"data": []
}
```

- **失败例子**
```
{
	"type": 1,
	"message": "",
	"data": []
}
```

---

### **【二】接口名设计约定**

---

#### **（一）新增一条记录：`post`**
- 例，**新增用户：`.../User/post`**
- 例：**新增队伍训练记录：`.../Team_training/post`**
- 目前版本不对前台提供添加多条资源的接口；

---

#### **（二）获取记录：`get`**

---

**【`url字段` 带参为按主键查询】**

- 例如：**`.../User/get/hs97`**
- 代表查询用户名为 **hs97** 的信息
  
---

**【`url字段` 不带参为查询批量资源】**
 - 例如：**`.../User/get`**
 - 需要支持 **`关键字检索` 和 `分页`**

- **最基本接口输入值格式**：
| 成员          | 中文   | 类型       | 备注
| ------------- | ------ | ---------- | ----
| **page_size** | 页大小 | 数字       | -
| **now_page**  | 当前页 | 数字       | -
| **where**     | 检索表 | 数组       | -


- **最基本接口返回值格式（无发生错误时）**：
| 成员          | 中文   | 类型       | 备注
| ------------- | ------ | ---------- | ----
| **page_size** | 页大小 | 数字       | -
| **now_page**  | 当前页 | 数字       | -
| **max_page**  | 最大页 | 数字       | -
| **data**      | 当前页 | 数组       | 即便没有资源也要返回一个空数组data


- 例：**获取某个队伍训练记录：`.../Team_training/get`**

---

#### **（四）修改记录-部分项：`putch`**
- 只允许提供 **主键** 修改
- 且都需要判定持有 **`Utoken`** 的用户是否有修改的权限
- 例：**修改某条训练记录：`.../Team_training/putch`**

---

#### **（四）删除记录：`delete`**
- 只允许提供 **主键** 删除
- 且都需要判定持有 **`Utoken`** 的用户是否有删除的权限
- 例：**删除某条训练记录：`.../Team_training/delete`**

---


## **Part 1 · 思维导图**

![此处输入图片的描述][1]

![此处输入图片的描述][2]

---


---
  [1]: http://od690gqhu.bkt.clouddn.com/20177413159.png
  [2]: http://od690gqhu.bkt.clouddn.com/201776223736.png