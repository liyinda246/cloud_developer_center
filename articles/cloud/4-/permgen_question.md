# PermGen space的解决办法

在部署Java应用的时候，有时候会碰到**PermGen space**这个错误。

此时可以进入【应用管理】页签，【属性】的【环境变量】里面增加：

> 键：CATALINA_OPTS
> 
> 值：-XX:PermSize=128m -XX:MaxPermSize=256m

如图1所示：

<div align=center>

<img src="images/permgen_question_1.png"/>

</div>

<p align="center">图 1</p>

