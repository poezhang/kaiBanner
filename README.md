# kaiBanner
- 一款小而美的jQuery轮播插件，配置简单，运行稳定；
- ‘come and back’徘徊式的轮播效果，翻译成人话就是：当轮播到最后一个banner图时，不会回到第一幅banner，而是按照相反的方向从最后一幅banner图轮播回到第一幅banner上，类似于按照‘1234543212345...’这样的顺序无限左右滚动。
# DEMO
[DEMO1](https://poezhang.github.io/kaiBanner/demo/demo1.html) | 响应式宽度
[DEMO2](https://poezhang.github.io/kaiBanner/demo/demo2.html) | 固定宽度
# 使用
## HTML
项目依赖jQuery，请在引入插件之前引入jQuery文件
```
<script type="text/javascript" src="js/jquery-3.1.1.min.js"></script>
<script type="text/javascript" src="js/jquery.kaibanner.js"></script>
```
对HTML中使用的标签节点没有要求，但是有一点是重要的，**请在对应的节点上使用的规定的class name**
- 轮播组件主体部分，且主体部分是轮播组件必须的部分，也就是放置banner图的部分（必须）：`'.kai_banner_body'`
- 轮播组件的“底部按钮”bottomButton（可选）：`'.kai_banner_bottombtns'`
- 轮播组件的“前一页按钮”prevBtn（可选）：`'.kai_banner_prevbtn'`
- 轮播组件的“下一页按钮”nextBtn（可选）：`'.kai_banner_nextbtn'`

```
 // 请使用规定的className，父节点的className不是强制规定的，你可以随意定义
 // example1：
	<div class="banner">
		<div class="kai_banner_body">
			<a href=""><img src="img/banner_01.jpg"></a>
			<a href=""><img src="img/banner_02.jpg"></a>
			<a href=""><img src="img/banner_03.jpg"></a>
			<a href=""><img src="img/banner_04.jpg"></a>
			<a href=""><img src="img/banner_05.jpg"></a>
		</div>
		<div class="kai_banner_bottombtns">
			<span class="highlight" style='background-image:url(img/banner_01.jpg)'></span>
			<span style='background-image:url(img/banner_02.jpg)'></span>
			<span style='background-image:url(img/banner_03.jpg)'></span>
			<span style='background-image:url(img/banner_04.jpg)'></span>
			<span style='background-image:url(img/banner_05.jpg)'></span>
		</div>
		<div class="kai_banner_prevbtn"></div>
		<div class="kai_banner_nextbtn"></div>
	</div>
```
```
 // 请使用规定的className，父节点的className不是强制规定的，你可以随意定义
 // example2：
 <div class="banner2">
		<div class="kai_banner_body">
			<div><img src="img/banner_01.jpg"></div>
			<div><img src="img/banner_02.jpg"></div>
			<div><img src="img/banner_03.jpg"></div>
			<div><img src="img/banner_04.jpg"></div>
		</div>
		<div class="kai_banner_prevbtn"></div>
		<div class="kai_banner_nextbtn"></div>
  </div>
```
## CSS
使用者可以自定义。
## javascript
- 使用默认配置
```
$('').kaiBanner();
```
- 自定义配置
```
$('').kaiBanner({
  speed:1000, // 轮播的动画速度
  fixedWidth:false, // 轮播组件的父容器宽度是否固定
  intervalTime:3000, // 每两次滚动的时间间隔（毫秒）
  highlightClass:'' // 当滚动到相应页面时，底部对应位置按钮的高亮样式类名
});
```

# 配置项
| Item      | Type | Default  | Details|
| :-------- | --------:| :--: |:--: |
|speed|Number|1000| 轮播的动画速度
|intervalTime |Number|3000 |每两次滚动的时间间隔（毫秒）
|fixedWidth|Boolean|false|轮播组件的容器（最外层节点）宽度是否为固定值。虽然是可选的参数，但建议按照实际情况填写，如果宽度是固定的，将不会为组件添加window.onresize事件，利于性能。
|highlightClass|String|''| 当滚动到相应页面时，底部对应位置按钮的高亮样式类名
