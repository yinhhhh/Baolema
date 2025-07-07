# TODO List

### REMINDER

- 如何增加API？
  - 后端改impl、api、routes（在process里面）
  - 前端加.ts（注意端口与后端微服务一致！如.10010）
 
## This weekend

### BACK END

- 增加菜系
  - Done
  - 前端还需要copilot help一下
- 增加Recommendation（算法不必太考察，重要是体现类型的思想，本周末可以先搞一个简单的按照点评推荐；后面可以基于此，增加按照菜系推荐、甜品推荐，等等）
- 增加Score展示panel（比如可以传入某Dish的所有review，传出......下面的东西！）

**突然有一个idea，也许我们可以在panel上做一些文章，体现类型关系，比如说计算该食堂*主食、热菜、冷菜、甜品、饮品、早餐*等几个方向菜的综合评分，形成一个六边形之类的**


**New**删除Dish后 相应的评论是否也应该删除？

</br>

### FRONT END

- 解决button点不动的问题
- Dish的搜索也可以搞起来，后端提供接口QueryMessgage
- Review的增删改查也可以搞，后端提供相应接口
- 请从下面转移过来一些



用户服务：
修改我的基本信息

评论：
星星真实显示而不是全是5星 已解决

统计菜品评分 TODO：移到主界面

推荐及用户操作：
Done点赞--推荐 我赞过的评论-QueryBrowsed

TODO食堂端查看评论？

TODO学生端查看菜品：
Doing ViewMenuPage应该能看出来是哪个食堂（加“紫荆园“），canteen可以加地址？营业时间？（类型安全）
/（暂时可以接受现状）菜品平均评分显示菜品详情页面：评论、加评论、数据统计，ViewMenuPage中的是缩略图加“热门评论（点赞数最多的随机一个）”

Done 水果捞怎么是0条评论
TODO 我希望学生端和食堂端看到的Complaint中”菜品ID“都换成菜品名称
TODO dishID 随机生成
TODO 查看投诉时 看到的不是ID而是名称
TODO viewmenupage 显示食堂名称
TODO 测试：某些跳转（非顺序）时会传不到token
TODO 统一风格和面包屑导航
（TODO）探索浏览器打开
Done 统计评分数据应该直接显现

TODO 尝试上传图片和用户编辑资料？

Done【学生端查看举报：点击“总”->该食堂所有……】



</br>

### UNKNOWN

- 重画关系图
- 增加介绍文档（展示用，选）




</br>
</br>
</br>
</br>
</br>


# 以下过期，请转移到上面

### NOTE FOR EVERYONE

- 注意更新本地所有Service的API接口：UserService中GetUserIdByUserRole中的**id应改为ID**
  - Sol：0703最新版本zip已经发在群里
- 更新了DishListMessage
  - Sol: CanteenService-0703-2.zip发在群里
- 删除了CanteenService的obj；增加了logoutAPI；login-panel相应的plugin中的obj也已删除，增加了logoutAPI
  - Sol: 五个微服务-0703-3最新版本zip已发群里
  - log 25/7/4, 1: 00, fzy: login-panel 待合并，明天发群里
  - Sol: 合并新UI，但没有登出功能的 login-panel-0704.zip已发群里
  - Upt: UserService-0704 增加了logoutAPI

</br>

### BACK END

- 前端console里面事务退出的报错
  - Sol：canteenService，init里面建表（指标不治本）
- 更换一个可持续发展的建表方法
  - Sol：增加一句 ON CONFLICT (canteen_id) DO NOTHING;
- 更新Service，参照上面的东西，打包发给大家
  - Sol：Done
 
    
- DishListMeaasge：在食堂端外，新增一个API，处理用户信息，删除对token的食堂身份核查即可
  - Sol: 并没有新增，减少对token的检验即可

- CreateComplaintMessage: 填表没填全:
  1. 没填userID
  2. reply，resolved at似乎也不支持先不填
  - sol 18：23 gmq尝试修改complaint service
  - 进度：
    19：11   填表问题已修好 学生端可提交complaint，但有新的问题：食堂段无法查询complaint，问题大概出在QueryComplaint API
     
- QueryComplaintMessage
- 进度：
   1.修改了QueryComplaintMessage，真正使用了getuserIDbytoken而不是直接返回token
  2.新的问题：错误: 获取投诉失败: "\"[GetUserIdByTokenMessagePlanner] Token 96c1554c-3ac6-4690-a871-51fff95caec5 无效或已过期\"" 但查表发现存在且未过期

    
- 网上/AI搜索，一般推荐系统的实现，综合考虑浏览和点赞？
  - TODO
 
    
- 调整Obj，并应用到各service
  - Sol: Done
- 增加登出功能（模仿sample）
  - SOl: Done
 
- ReviewService: 增加删除点评、修改点评
  - Sol：现在新增了两个api
  - 注意：两个.ts需要加在plugin里；ReviewService已经更新（发在群里）
  - 理论上是不需要移动到后端其他service的（因为也没用上） 【但万一出现问题，检查点】

</br>
  

### FRONT END

- webstorm有一个增加菜品的报错
  - 新建了一个dish实例来保证类型一致

- 系统学习一下react

- 食堂端，更新菜品页面：解决第二次进入无法更改内容的bug(世界未解之谜)
  - TODO 
- 食堂端，更新菜品页面：showcase所有菜品
  - TODO
  - log 25/7/4, 1: 00, gmq: showcasePage尝试使用Daisy UI 成功加上drawer（未完成跳转 疑似未使用主题而是直接规定颜色）
  - 需要在showcasePage跳转到ViewMenuPage的时候传递canteenID参数，ViewMenuPage通过useLocation获取传递的canteenID hhhjerry
- 注册页：改成小清新
- 学生端：增加菜品页面
  - TODO hhhjerry做showcasepage的修改 
- 用户端，首页：浮窗食堂转换框

- 学生端到ViewReviewPage传入canteenID和dishID
- viewReviewPage返回showcasePage
- 测试返回后能否正常去其他园



</br>


### UNKNOWN B/F

- 食堂端：菜品页面展示的时候展示不全，仅能看本次添加和删除的，之前的没有
  - 检查后端planner实现？
  - 检查前端API调用？
 
- 错误气泡流？参考0703课上最后一组的github？

- ManagerPage登出
  - Sol: done


- ReviewService的删、改还不行哦（实在不行就别改了，只删吧。。。。。。）
  - Sol: 端口问题，前端.ts端口统一为10010（这个数值由微服务决定，可以问问后端）
- title问题，各种api，重新处理一下，要不这几个部分都重开吧:)
  - TODO



</br>
