# miniwork 新技术栈云开发

## 项目更新月度计划安排

### 8-9月上线计划：（拟定）

- 1、8月份上线评论、搜索、薪资待遇和历史版本模块；
- 2、改造刷题模块，改造[我的]UI；
- 3、数据更新，每日更新校招内容，每周更新笔试题目和面试经验;
- 4、9月份代码规范，云函数整合，完善部署文档。

## 项目介绍

- 小贝校招 项目是集校招资讯、内推、刷题、简历模板下载等功能于一体的小程序，基于微信原生+微信云开发+vant+colorui以及相关技术栈开发，自带图像云开发后台，不需要自己建网站。

- 源代码全部开源，部署详细流程见下面介绍。**代码不易，如果觉得项目不错的话可以给项目一个 Star ，谢谢各位的支持。**

## 项目模块

- 基于腾讯云服务开发，微信云开发，原生微信，使用vant，colorui为UI的开发的小程序，后台基于微信云开项目。
- [资讯模块]校招资讯，包含：查看，点赞，收藏，笔记，分享；
- [题库模块]笔试面试题库，包含面试和随机刷题模块；
- [签到模块]校招，包含精选(按发布时间)、热招(按浏览量)、倒计时(按最近截止简历投递时间)和校招宣讲会资讯四个模块；
- [首页模块]内推，包含内推直招、简历模块和薪资待遇模块，待优化；
- [我的模块]个人中心，包括个人收藏、点赞和笔记信息，签到。

## 项目预览地址

### 小程序

关注小程序：**小贝校招**，【微信小程序内搜索 [ 小贝校招 ] 即可体验】

### 后台cms系统

- 地址:<https://test-4gn9gu0ucc6657ba-1304273986.tcloudbaseapp.com/wx-cms/#/login?redirect=https%3A%2F%2Ftest-4gn9gu0ucc6657ba-1304273986.tcloudbaseapp.com%2Fwx-cms%2F%23%2Fhome>
- 账号：test
- 密码：test12345
- 说明：该账号仅供查看，无法修改内容

## 部署文档

### 说明

- 若无法查看图片，请移步至gitee或者博客：https://gitee.com/lxk2020/miniwork

### 1、下载导入

- 下载release版本v1.0.0，解压zip，导入项目
- 替换自己的AppID
![avatar](pic/46.png)
![avatar](pic/47.png)
![avatar](pic/1.png)

### 2、设置云开发环境

- 在utils/config.js中替换自己的云环境
![avatar](pic/2.png)
![avatar](pic/3.png)
![avatar](pic/4.png)

### 3、开通内容管理

- 内容管理为后台cms系统，需要开通按量付费[略坑]
![avatar](pic/5.png)
![avatar](pic/6.png)
- 点击确定，需要几分钟时间
![avatar](pic/7.png)
- 再次点击开通按钮
![avatar](pic/8.png)
- 设置cms账号密码
![avatar](pic/9.png)
- 焦急等待...
![avatar](pic/10.png)
- 点击网址，进入后台管理页面
![avatar](pic/11.png)
- 输入刚刚设置的账号密码
![avatar](pic/12.png)
- 创建项目，项目id自己设定
![avatar](pic/13.png)
- 导入miniwork/database目录中的模型：schema-export-tyjut65s.json
![avatar](pic/14.png)
- 点击确定
![avatar](pic/15.png)
- 回到开发工具中，点击云开发按钮进入云开发控制台，进入数据库中，可以看到刚刚导入的模型已经在数据库中创建
  
### 4、创建其他数据库

- 创建点赞、收藏等数据库
![avatar](pic/16.png)
![avatar](pic/17.png)
- 创建的数据库名和权限如下图所示，记得要创建图中的所有表，这里不再一一展示。
![avatar](pic/18.png)

### 5、上传部署云函数

- 创建完所有数据库，再回到开发工具中，上传并部署项目中所有的云函数
![avatar](pic/19.png)
- 所有的云函数如下图
![avatar](pic/21.png)

### 6、数据管理

- 到此为止，基本部署工作已经完成，下面介绍向数据库中增加数据
- 首先进入cms后台管理中，选择一个表名，点击导入数据，选择通过JSON导入
![avatar](pic/20.png)
![avatar](pic/29.png)
- 这里我已经给出数据库样例，在miniwork/database文件夹中，json文件名对应数据库名，可以通过查看模型来查看数据库名，依次对应导入除schema-export-tyjut65s.json外的所有数据表
![avatar](pic/48.png)
- 对包含图片的数据库，图片资源获取不到，需要手动导入
![avatar](pic/24.png)
- 点击编辑
![avatar](pic/25.png)
- 上传pic文件夹中的图片，也可自己上传其他图片
![avatar](pic/26.png)
- 点击更新，依次修改完其他数据表
![avatar](pic/27.png)

- 回到开发工具界面，点击刷新运行，即可看到所有界面

### 界面预览

![avatar](pic/31_1.png)
![avatar](pic/36_1.png)
![avatar](pic/41_1.png)

## 联系作者

- QQ：656008660

> 大家有任何问题或者建议都可以在 [issues] 中反馈给我，慢慢完善项目

## 更新日历

## 2021年7月25日更新

- 1、代码部署，环境配置，初步测试模板
- 2、确定主题，确定个功能模块，画思维导图

## 2021年7月26日更新

- 1、首页轮播图，链接跳转
- 2、跳转加载中动画，详情页面UI调整

## 2021年7月27日更新

- 1、宣讲会数据库、页面设计
- 2、题库、内推页面设计
- 3、字体规范：小-14px，中-16px，大-18px，超大-20px

## 2021年7月28日更新

- 1、校招和资讯点赞收藏，[我的]校招和资讯点赞收藏同时显示，可分别跳转
- 2、咨询页顶部swiper功能，链接跳转
- 3、面试题收藏与推荐功能，收藏的题目对应在[我的]中的[我的题库]
- 4、我的笔记，增加笔记。【待办：删除笔记】
- 5、复习书籍，书籍展示与PDF预览

## 2021年7月29日更新

- 1、[题库]和[内推]分离；【待办：二者的收藏点赞目前使用的是同一个数据库】
- 2、[宣讲]页面、[签到]页面UI优化
- 【bug待办】
  点击笔记，进入新增笔记
  点击我的题库，有收藏的内推
  书籍不能下载
  【功能待办】
  倒计时模块
  评论功能
  校招日历功能
  薪资待遇模块
  各模块的搜索查询功能

## 2021年7月30日更新

- 1、环境env，配置在config中，修改env配置，方便部署
- 2、所有云函数env改为动态获取

## 2021年7月31日更新

- 1、修复多页加载数据，特定情况下导致重复的bug
- 2、[我的]页面增加签到功能
- 3、去除无用页面，代码规范

## 2021年8月1日更新

- 1、主页面UI优化，卡片式界面；
- 2、修改点赞收藏按钮大小；
- 3、个人简历模块。

## 2021年8月4日更新

- 1、上线第一版，部署文档


## 2021年8月5日更新

- 1、tabbar优化：调整大小、图片颜色和weight
- 2、资讯/校招详情底部[笔记]、[点赞]和[收藏]UI更新

## 2021年8月6日更新

- 1、校招详情页面增加评论、分享功能，界面UI优化

## 2021年8月7日更新

- 1、完善评论、回复评论，完成搜索功能
- 2、底部UI更新，校招详情页面更新

## 2021年8月15日更新

- 1、增加MBTI职场性格测试

## 2021年8月17日更新

- 1、主页面加载数据库逻辑优化