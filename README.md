# TODO List


### NOTE FOR EVERYONE

- 注意更新本地所有Service的API接口：UserService中GetUserIdByUserRole中的**id应改为ID**
  - Sol：0703最新版本zip已经发在群里
- 更新了DishListMessage
  - Sol: CanteenService-0703-2.zip发在群里

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
    
- 网上/AI搜索，一般推荐系统的实现，综合考虑浏览和点赞？
  - TODO

</br>
  

### FRONT END

- webstorm有一个增加菜品的报错
  - 新建了一个dish实例来保证类型一致

- 系统学习一下react

- 食堂端，更新菜品页面：解决第二次进入无法更改内容的bug
  - TODO hhhJerry正在改
- 食堂端，更新菜品页面：showcase所有菜品
  - TODO fzy
- 注册页：改成小清新
- 学生端：增加菜品页面
- 用户端，首页：浮窗食堂转换框

</br>


### UNKNOWN B/F

- 食堂端：菜品页面展示的时候展示不全，仅能看本次添加和删除的，之前的没有
  - 检查后端planner实现？
  - 检查前端API调用？
 
- 错误气泡流？参考0703课上最后一组的github？

</br>
