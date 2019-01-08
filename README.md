### 用户行为日志文件分析

##### 1. 需求

- 针对某一特定的群体用户，找出他们最感兴趣top10的类别/商品/页面布局

- 停留时长的占比
- 根据访问时间按比例随机取样session
- 找出这些session，点击、下单、支付，按照二次排序之后的top10类别+商品
- 针对top10的类别和商品，找到对其每一个点击排名top10的session,分析具体session对应的用户的具体行为，调整页面布局及推荐内容

展示需求

- 工具，页面的显示图，柱状图/饼状图/折线图

#### 2. 部分数据展示 

日志信息表

```shell
2018-10-20	user5817	4e7af87e-f01e-479f-8013-05a74c514044	page19	2018-10-20 15:5:48	click_cate282	click_pro12584	order_cate46	order_pro237/order_pro17/order_pro230/order_pro148/order_pro274/order_pro217/order_pro151	-	-
2018-10-20	user9651	25e3f200-15cc-4be3-a97e-d17e5884d421	page17	2018-10-20 13:25:23	click_cate211	click_pro4043	order_cate249/order_cate90/order_cate21	order_pro66/order_pro286/order_pro258/order_pro267/order_pro257/order_pro50/order_pro235/order_pro92	pay_cate90	pay_pro258/pay_pro66
2018-10-20	user1923	cd25c323-2e15-4322-bbdf-d7b944a0f4fa	page17	2018-10-20 11:1:31	click_cate198	click_pro50278	order_cate67/order_cate112/order_cate253	order_pro288/order_pro191/order_pro159/order_pro268/order_pro5	pay_cate112	pay_pro288/pay_pro159
```

用户信息表

```scala
user1	yhzwvwp	VZZXLPL	37	artist	shenzhen	female
user2	khjbcizvy	VZXDEUXMB	31	artist	shanghai	female
user3	fjypja	ZSXABPPXDJ	28	faker	chongqin	female
```

#### 3. 字段说明

日志信息表

```
date               string  //日期
user_id            string  // 用户ID
session_id         string  // sessionID
page_id            string  // 页面ID
action_time        string  // 活动时长
click_category_id  string  // 点击的类型 
click_product_id   string  // 点击的商品
order_category_ids string  // 定单的类型
order_project_ids string   // 定单商品
pay_category_ids   string  // 支付类型
pay_product_ids    string // 支付商品
```

用户表

```
user_id string 用户ID
nick_name string 昵称
real_name string 真实姓名
age int 年龄
profession string  职业
city string 地方
gender string 性别 
```

