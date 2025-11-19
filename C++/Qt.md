## Qt 的下载与安装
1. 进入`Qt`官方网站：https://www.qt.io/zh-cn/. 
2. 点击右上角**下载试用**. ![](assets/images/9bf32d1c13a824aa83b3330abc5d39d184534bc51a1b7ee745ad54852a456dc7b1ac1db35e6e603fb81ca4ee6b6c404e9c17a21be4a2acde8fc5fd950a3d53a4.png)
3. 点击**探索`QT`社区版**.![](assets/images/2c0d7bee4aa38bf88f449e2ce8c4034bd0aeed0a019e38d43cf13770d39a24642849f7a3befb1a62ef8769cbe3de4c4cfdcdd0efc6a4ab04e8c606514ba95ede.png)
4. 点击**Download the `Qt` Online Installer**，下载`Qt`在线下载器。
![](assets/images/91ef3b5bfab1435f9c24851508037cf013b28ac55612bd54037a45236e4e77ae82f1e5e05f7da32ca824f539e294020493cb1c054eb6f0f206170846ce37bf40.png)
5. 注册`Qt`账号.![](assets/images/ef7b975af7180d2e3d989a47cb3310d23d166113331b0cdef1401e9310432dd56ae98748e58fbf97aeb27124d2325bb12359e41a0d778234bca1a7c7d1a469c4.png)
6. 操作`Qt Online Installer`下载`Qt`.
## Qt 控件
## Qt 绘图
`Qt` 绘图应该继承`QWidget`作为画布，并重写`protected void paintEvent(QPaintEvent *event)`，在`paintEvent`函数中构造画笔`QPainter(this)`，`this`为画布指针，通过画笔绘制图像。
1. `QPainter`常见方法。
	1. `setRenderHint(RenderHint, bool = true)`。`RenderHint`的可选值有：
		1. `Antialiasing`, 线段抗锯齿。
		2. `TextAntialiasing`，文字抗锯齿。
		3. `SmoothPixmapTransform`，图像插值平滑，对于缩放后图像有用。
		4. `VerticalSubpixelPositioning`，高精度文字排版。
		5. `LosslessImageRendering`，无损图像渲染，与`SmoothPixmapTransform`互斥。
		6. `NonCosmeticBrushPatterns`，画刷纹理、渐变等随画布缩放。
		`bool`默认表示启动，`bool`为`false`表示关闭。
	2. `setRenderHints(RenderHints, bool = true)`。功能与`setRenderHint`相同，支持通过`|`连接开启多个选项。
	3. `drawRect(QRect&),drawRect(QRectF&),drawRect(int, int, int, int)`。绘制矩形，边框通过`QPen`绘制，内部通过`QBrush`填充。`drawRect`的四个`int`参数分别为`(x, y)`左上点坐标，`(w, h)`矩形大小。`QRect`支持如下图所示的构造函数。![](assets/images/cf0c37a35fbca8b7461e0e365a763697da599d9294e6f1dffa634dbe5afbb9276ed87e25232687578f58d718c97e24865b7b6e1c47424721204cf64ae5d6b1d9.png)`QRectF`与`QRect`类似，但是支持浮点数做参数。
	4. `drawRects(QList<QRect>&),drawRects(QList<QRectF>&)`。`QList`底层实现类似`std::vector`。
	5. `setPen(const QColor&)`，`setPen(const QPen &)`，`setPen(Qt::PenStyle)`。设置画笔。一般来说，画笔有如下属性：
		1. `QColor`
	
	6. sandfkjsafhksalhfhhfhfhfhfhfhfhfhfhfhfhfhfhfhfhfhfhfhfhfhfhfhfhfhfhfhfhfhfhfhfhfhf