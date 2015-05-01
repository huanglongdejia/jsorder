建议到我的blog查看最新的文档更新：http://wuzhi.me/?p=33

代码一共6k,基于jquery的购物车实现，实现订单的本地cookie存储，支持购物车自定义样式，金额的计算。通过json与后台交互。实现可配置化的购物车系统，可应用于电子商务平台。

1.下载地址：http://code.google.com/p/jsorder/downloads/list

2.demo地址：http://wuzhi.me/jsorderdemo.php

3.配置说明： jsorder 支持多参数配置，自定义购物车样式，设置是否记录cookie，提交方式 等。

$.fn.jsorder.defaults = {
> //作为订单数据存储的浏览器端全局变量，通过jquery绑定在body
> staticname : 'jsorder',
> //订单class，确保在页面class唯一不重复，否则将导致错误
> jsorderclass : 'jsorder',
> //是否保存cookie
> savecookie : true,
> //cookie的名字
> cookiename : 'jsorder',
> //ID前缀，暂时无用
> numpre : 'no_',
> //订单项前缀，用来区分不同的订单项，页面内必须不重复
> jsorderpre : 'jsorder_',
> //触发订单控件的价格属性
> pricefiled : 'price',
> > //触发订单控件的订单名属性
> > > namefiled : 'jsordername',

> //购物车左侧显示
> leftdemo : '我的菜单',
> //提交按钮文字
> subbuttom : '',
> //默认加入订单的控件选择
> addbuttom : 'a.jsorderadd',
> //没有订单时显示
> nomessage : '你今天的食谱是还空的',
> //提交时触发
> dosubmit : function(data) {
> > $("body").append(JSON.stringify(data));
> > $("body").data(opts.staticname, {});

> }
};
4.页面代码
1)样式表及js


&lt;link href="../css/order.css" rel="stylesheet"/&gt;




&lt;script type="text/javascript" src="../js/cookie.js" &gt;



&lt;/script&gt;




&lt;script type="text/javascript" src="../js/jsorder.js" &gt;



&lt;/script&gt;


2）触发控件配置

3）覆盖默认配置项

$.fn.jsorder.defaults = {
> //修改触发空间类型
> addbuttom : 'td.jsorderadd',
> //修改提交方案
> dosubmit : function(data) {$("#result").html("json内容："+JSON.stringify(data)).css('background','#e0e0e0');}
};
4)开始加载购物车
$("body").jsorder();


欢迎提供意见和建议。邮箱：1286514442@qq.com
