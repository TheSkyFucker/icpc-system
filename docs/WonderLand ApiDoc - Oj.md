# WonderLand ApiDoc - Oj

标签（空格分隔）： WonderLand

---

## **日志**

| 日期         | 备注  
| ------------ | ------
| **17/11/07** | 添加接口 · **【添加oj关联账号 add_oj_account】**
| **17/11/07** | 添加接口 · **【获取oj过题数信息 get_oj_acproblems】**
| **17/11/08** | 添加接口 · **【查询用户所有oj关联账号信息 get_oj_account】**
| **17/11/08** | 添加接口 · **【删除用户oj关联账号信息 del_oj_account】**

---

## **属性**

- **【oj_account 表】**

| 属性名        | 中文    | 最小长度 | 最大长度 | 类型      | 特殊要求
| ------------- | ------  | -------- | -------- | --------- | --------
| **Uusername** | 用户名  | 6        | 16       | char(20)  | 字母/数字/下划线/破折号
| **OJname** 	| oj名称  | -        | -        | char(20)  | 为"hdu"或"foj"或"cf"                     
| **OJpassword**| oj用户名| -        | -        | char(20)  | - 
| **OJusername**| oj密码  | -        | -        | char(20)  | -                

---

## **接口 · 添加oj关联账号**

- **请求方法：POST**
- **接口网址：http://icpc-system.and-who.cn/Oj/add_oj_account**

- **表单要求**

| 属性名         | 必要性 | 最小长度 | 最大长度 | 特殊要求
| -------------  | ------ | -------- | -------- | --------
| **Uusername**  | O      | 6        | 16       | 字母/数字/下划线/破折号
| **OJname**     | O      | -        | -        | 为"hdu"或"foj"或"cf" 分别表示添加对应oj的账号                     
| **OJpassword** | O      | -        | -        | -                     
| **OJusername** | O      | -        | -        | -                     


- **成功返回例子**

```
{
	"type": 1,
	"message": "添加成功",
	"data": []
}
```

---

## **接口 · 获取oj过题数信息**

- **请求方法：GET**
- **接口网址：http://icpc-system.and-who.cn/Oj/get_oj_acproblems?Uusername=&OJname=**

- **表单要求**

| 属性名         | 必要性 | 最小长度 | 最大长度 | 特殊要求
| -------------  | ------ | -------- | -------- | --------
| **Uusername**  | O      | 6        | 16       | 字母/数字/下划线/破折号
| **OJname**     | O      | -        | -        | 为"hdu"或"foj"或"cf" 分别表示查询对应oj的过题数  


- **成功返回例子**

```
{
	"type": 1,
	"message": "查询成功",
	"data": "22" 
}
```

---

## **接口 · 查询用户所有oj关联账号信息**

- **请求方法：POST**
- **接口网址：http://icpc-system.and-who.cn/Oj/get_oj_account**

- **表单要求**

| 属性名         | 必要性 | 最小长度 | 最大长度 | 特殊要求
| -------------  | ------ | -------- | -------- | --------
| **Uusername**  | O      | 6        | 16       | 字母/数字/下划线/破折号


- **成功返回例子**

```
{
	"type": 1,
	"message": "查询成功",
	"data": [
		{
			"OJname": "cf",
			"OJusername": "xxxxxxx",
			"OJpassword": "xxxxxxx"
		},
		{
			"OJname": "foj",
			"OJusername": "xxxxxxx",
			"OJpassword": "xxxxxxx"
		},
		{
			"OJname": "hdu",
			"OJusername": "xxxxxxx",
			"OJpassword": "xxxxxxx"
		}
	]
}
```

---

## **接口 · 删除oj关联账号信息**

- **请求方法：POST**
- **接口网址：http://icpc-system.and-who.cn/Oj/del_oj_account**

- **表单要求**

| 属性名         | 必要性 | 最小长度 | 最大长度 | 特殊要求
| -------------  | ------ | -------- | -------- | --------
| **Uusername**  | O      | 6        | 16       | 字母/数字/下划线/破折号
| **OJname**     | O      | -        | -        | 为"hdu"或"foj"或"cf" 分别表示删除对应oj的关联账号


- **成功返回例子**

```
{
	"type": 1,
	"message": "删除成功",
	"data": []
}
```