## 概述
用友云开发者中心提供了针对各种类型的项目应用进行快速迭代开发的持续集成功能。

## 持续集成入口 ##

登录开发者中心，在左侧导航栏点击进入持续集成，默认展示当前用户下应用构建任务列表，应用最新的构建状态等信息将在此展示出来。如图1所示。

<div align="center">
<img src="/articles/cloud/3-/images/create_1.png">
</div>
<p align="center"> 图 1</p>

注：可以点击部署按钮，直接部署最新构建任务。

## 创建新应用 ##

点击左上角的```创建新应用```按钮进入创建新应用页面并编辑表单，为后续部署做前期准备，注意其中的所有内容都是必填项。如图2所示。

<div align="center">
<img src="/articles/cloud/3-/images/create_2.1.png">
</div>
<div align="center">
<img src="/articles/cloud/3-/images/create_2.2.png">
</div>
<p align="center"> 图 2</p>

其中部分功能描述如下：

### 1.上传描述文件 ###

可以点击下载示例描述文件，修改示例文件内容后上传即可把创建新应用表单自动填充，实现一键填充功能。

 ```
	appName: 测试应用
	version: v1
	environment: dev
	modules:
	- module_name: UPLOAD_MODULE
	  content:
	    baseImage: tomcat:6.0.48-jre8-alpine
	    imageName: testimage
	    is_root_path_access: true
	    appType: java
	- module_name: CONFCENTER_MODULE
	  content:
	    appCode: 0.0.1
	    description: This is a test app for one key deploy
	    emails: developercenter@yonyou.com,devops@yonyou.com,superman@yonyou.com
	    conf_files:
	    - configuration.xml
	    - "/content/application.properties"
	- module_name: PUBLISH_MODULE
	  content:
	    app_name: self_design_publish_name
	    port_settings:
	    - port: 8080
	      protocol: TCP
	      access_mode: HTTP
	      access_range: OUTER
	    source_pool_id: 1
	    source_pool_name: 体验资源池1
	    basic_setting:
	      cpu: 0.15
	      memory: 512
	      disk: 1024
	      instances: 3
```
### 2.应用分类 ###

现支持Java Web应用、Node应用、静态网站、Python应用、Go应用、Dubbo应用、PHP应用、Java应用等共8种类型的应用。

### 3.基础环境 ###

每种应用都有相应的基础环境，用户可根据自己项目的实际需求选择所需的基础环境。

## 应用构建任务详情 ##

点击持续集成中构建列表里任一应用，进入该应用的详情列表页。如图3所示。

<div align="center">
<img src="/articles/cloud/3-/images/create_3.png">
</div>
<p align="center"> 图 3</p>

部分功能描述如下：

### 1. 应用多版本构建 ###

可以点击```构建新版本```按钮实现多版本构建，使迭代开发更加便捷。

### 2. 配置文件 ###

现可针对Java Web应用可提取项目内的配置文件，提取项目内配置文件路径（WEB-INF/classes）。
上传一个带有配置文件的项目后，点击提取配置文件。如图4所示。

<div align="center">
<img src="/articles/cloud/3-/images/create_4.png">
</div>
<p align="center"> 图 4</p>

点击```提取配置文件```，勾选所需要提取的配置。如图5所示。

<div align="center">
<img src="/articles/cloud/3-/images/create_5.png">
</div>
<p align="center"> 图 5</p>

点击```提取```按钮，将在提取文件页签下显示出所提取的配置文件。如图6所示。

<div align="center">
<img src="/articles/cloud/3-/images/create_6.png">
</div>
<p align="center"> 图 6</p>

可在线编辑所提取的配置文件。如图7所示。

<div align="center">
<img src="/articles/cloud/3-/images/create_7.png">
</div>
<p align="center"> 图 7</p>

注：所提取得配置文件也可以到配置中心去进行相关操作。左侧导航栏配置中心-->配置管理
选择应用上传时的应用编码、环境、版本（提取配置时所填写的版本）查询。如图8所示。

<div align="center">
<img src="/articles/cloud/3-/images/create_8.png">
</div>
<p align="center"> 图 8</p>

### 3. 部署 ###

选中所需要部署的构建版本后，点击右上角的部署按钮，及跳转到部署页面，进行应用的部署操作。如图9所示。

<div align="center">
<img src="/articles/cloud/3-/images/create_9.png">
</div>
<p align="center"> 图 9</p>

跳转到部署页面。如图10所示。

<div align="center">
<img src="/articles/cloud/3-/images/create_10.png">
</div>
<p align="center"> 图 10</p>