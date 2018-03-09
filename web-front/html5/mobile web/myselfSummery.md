# 代码编写流程
  > css
  + 样式初始化。
  + 样式复用类。
  
# @media deviceType and|not|only (media feature)
  + deviceType 设备类型
  + ang|not|only 媒体特征之间的关系
  + media feature 媒体的特征 (指定的条件)
> 给设备设置样式的方式: 一个是设置内部样式表。一个引入外部样式表。
   + 给设备引入外部样式表 <link rel="stylesheet" href="..." media="only deviceType and|not|only (media feature)">
 > iphone5
   + @media only screen and (min-device-width: 320px) and (max-device-width: 568px) and (orientation: portrait) {...}
> iphone6
   + @media only screen and (min-device-width: 375px) and (max-device-width: 667px) and (orientation: portant) {...}
- 补充: 媒体查询的功能: 针对不同的设备可以设置不同的样式和布局。媒体查询的兼容性: css3的样式 

# viewport
<meta name="viewport" content="width=device-width initial-scale=1.0">

+ viewport: 将pc端页面投放在移动端页面。 viewport 会生成一个虚拟的窗口,这个窗口比移动端屏幕要宽。

# 布局视口: 默认的虚拟布局视口。pc端的页面可以在手机上显示
视觉视口和物理像素: 
  视觉视口指的屏幕的可视区域.
  物理像素指的是一个标准设备光点。
理想视口和设备独立像素
理想窗口就是所说的屏幕的分辨率。

pc端下: 一个物理像素 = 一个设备独立像素(css像素) 就是所说的[屏幕的分辨率]

移动端:
移动端手机屏幕通常不可以设置分辨率,一般都是设备厂家默认设置的固定值,
换句话说 dip 的值就是 ideal viewport（理想视口）（也就是分辨率）的值,设备独立像素


像素密度 视网膜屏幕

设备像素 css像素 设备独立像素(例如: ios下css像素就叫做设备独立像素)
缩/放 涉及到设备像素和css像素的关系。

设备像素比 = 物理像素/设备独立像素

# rem
rem是一个相对单位, 相对于根标签设置的。
rem的自适应和适配

以640px设计视图为例。 根据公式 设计视图的宽度=font-size * rem 首先以font-size为100px为基准, 计算出rem为6.4 也就是把窗口分为了
6.4份,每一份为100px;
如果需要适配320px的窗口: 按照比例计算公式: 320/640 * 100px = font-size 或者 320/6.4 = font-size(建议使用)

# 移动端适配方案
rem布局
定高&宽度自适应 {1.宽度采用百分比布局 2.总高度自适应 3.子元素定高}
响应式布局 {自适应和流式布局的结合}

# 理解四大布局
  + 固定布局 {浏览器窗口变化时,元素的大小和位置都不会变化}
  + 自适应布局 {可以适配不同的媒体设备, 元素的大小不变,元素的位置发生变化。 可以看作固定布局的一种}
  + 流式布局 {浏览器窗口变化时,元素的大小改变,元素的位置是不变的} 百分比
  + 响应式布局{浏览器窗口变化时,元素的大小改变,元素的位置变化}
  + rem布局 rem配合media query。
