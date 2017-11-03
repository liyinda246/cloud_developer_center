# 如何添加埋点？

埋点是针对特定用户行为或事件进行捕获、处理和发送的相关技术及其实施过程，用于采集用户请求的信息。

## 添加埋点监控代码

请将如下代码粘贴到您的需要采集的HMTL页面的`</body>`前面，成功后，平台将统计到用户在网页上的点击行为信息：

```
<script type="text/javascript" src="https://developer.yonyoucloud.com/iuap-insight.min.js"></script>
<script>
uis.start({
trackerUrl: 'https://collect.yonyoucloud.com/iuapInsight/collect',
userId:'user',
siteId:'chbiu4tz',
});
</script>
``` 

说明：

`trackerUrl` 数据收集接口url

`userId` 页面访问者的用户信息，可以是session或cookie中读取的信息,例如：`getCookie('userName')[javascript]、$('userName')[jsp]`

`siteId` 应用id，#必填项，已加载您的appid，无需修改。

## 进阶使用

平台也开放了用户采集自定义数据的API接口，用于集成到前端代码的业务逻辑中，采集定制的数据。使用方法为:

```
<div id="app" style="background:#ccc;"> 点我发送 </div>
<script>
$('#app').click(function(e){
uis.track(e,'click_text', 'XXXXXXXXX');
})
</script>
```