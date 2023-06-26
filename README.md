# UMG UI设计器

[TOC]

**虚幻示意图形界面设计器（Unreal Motion Graphics UI Designer）(UMG)** 是一个可视化的UI创作工具，可以用来创建UI元素，如游戏中的HUD、菜单或您希望呈现给用户的其他界面相关图形。UMG的核心是控件，这些控件是一系列预先制作的函数，可用于构建界面（如按钮、复选框、滑块、进度条等）。这些控件在专门的控件蓝图中编辑，该蓝图使用两个选项卡进行构造：设计器（Designer）选项卡允许界面和基本函数的可视化布局，而图表（Graph）选项卡提供所使用控件背后的功能。

## UMG UI设计器快速入门

参考UE4.27文档[这里](https://docs.unrealengine.com/4.27/zh-CN/InteractiveExperiences/UMG/QuickStart/)

## 控件参考类型

### UE官方参考控件

背景模糊控件、无效化方框、菜单锚、命名槽和自动换行框的介绍参考 [这里](https://docs.unrealengine.com/4.27/zh-CN/InteractiveExperiences/UMG/UserGuide/WidgetTypeReference/)

### 其他常用控件

UMG中常用的控件类型有四种：

<img src="https://raw.githubusercontent.com/000111i/picgo/main/imgimage-20230621143634656.png" alt="常用控件分类" style="zoom:67%;" />



#### Image图片

图片不能添加子控件

<img src="https://raw.githubusercontent.com/000111i/picgo/main/imgimage.png" style="zoom: 80%;" />

图片的属性包括 **Slot、Appearance、Behavior、Render Transform、Clipping**，具体内容可以查询前面的介绍。

由于image的原始资源就是一个白色块，因此任何纯色块资源都不需要额外出资源，只需对image进行染色即可。

这里需要**特别注意**的是：image不仅仅可以引用图片资源，可以添加材质资源，可以通过材质来制作**粒子、模型、特效**等等丰富的效果。

#### Text文本

文本不能添加子控件

![v2-c324800705ad4688c5e8eecd40175e68_r](https://raw.githubusercontent.com/000111i/picgo/main/imgv2-c324800705ad4688c5e8eecd40175e68_r.jpg)

文本的属性包括**Slot、Font、Behavior、Warpping、Render Transform、Clipping**，具体内容可以查询前面的介绍。

在Content内输入内容，可以通过**shift+enter进行换行**

#### Rich Text 富文本

富文本格式可以在一个文本框内显示出不同的字体格式甚至图片文字，为了实现这一效果，我们首先要创建一个字体格式表格。

![v2-7a1865cb15e3c99cde576a9dde5dfc17_720w](https://raw.githubusercontent.com/000111i/picgo/main/imgv2-7a1865cb15e3c99cde576a9dde5dfc17_720w.webp)

然后就可以在UMG中引用这个表格资源来设置文本。

![v2-67c89dd9753e79c1dffa51a466706796_r](https://raw.githubusercontent.com/000111i/picgo/main/imgv2-67c89dd9753e79c1dffa51a466706796_r.jpg)

#### Button 按钮

按钮控件可以添加一个子控件

![v2-02fd72524852b72e4fb20f2b7095ed7f_720w](https://raw.githubusercontent.com/000111i/picgo/main/imgv2-02fd72524852b72e4fb20f2b7095ed7f_720w.webp)

按钮的属性包括**Slot 、Appearance、Interaction、Behavior、Render Transform、Clipping**，具体内容可以查询前面的介绍。

值得注意的是按钮有Normal/Hovered/Pressed/Disabled四种状态，在开发时至少需要为前三种设置资源。

#### CheckBox 复选框

复选框控件可以添加一个子控件。

![v2-40ee4d1c55cebf3850e6ab6f031941d2_r](https://raw.githubusercontent.com/000111i/picgo/main/imgv2-40ee4d1c55cebf3850e6ab6f031941d2_r.jpg)

按钮的属性包括**Slot、Appearance、Interaction、Behavior、Render Transform、Clipping**，具体内容可以查询前面的介绍。

#### progress Bar 进度条

进度条不能添加子控件

![v2-10bf9402c1b9f28846b2e1f762cba07b_720w](https://raw.githubusercontent.com/000111i/picgo/main/imgv2-10bf9402c1b9f28846b2e1f762cba07b_720w.webp)



由于UE4中没有环形进度条控件，需要结合材质与蓝图系统来实现一个环形进度条的效果，具体流程可参见：[这里（需要挂梯子）](https://www.youtube.com/watch?v=9NtSfPq95fQ)

#### Slider 滑块

滑块不能添加子控件

![v2-40b62abf6054c3d6eedba8a46b878f2a_720w](https://raw.githubusercontent.com/000111i/picgo/main/imgv2-40b62abf6054c3d6eedba8a46b878f2a_720w.webp)

#### Text Box 文本输入框

输入框不能添加子节点

文本输入有单行输入(Common>Text Box)和多行输入(Input>Text Box Multi-Line)两种。

![image-20230621155641834](https://raw.githubusercontent.com/000111i/picgo/main/imgimage-20230621155641834.png)

#### Combobox 下拉框

下拉菜单不能添加子控件。

![v2-da6753017394d8125d86d50cda825d57_r](https://raw.githubusercontent.com/000111i/picgo/main/imgv2-da6753017394d8125d86d50cda825d57_r.jpg)

#### Canvans Panel 画布面板

画布面板是一种基础的面板，其允许在任意位置布局、固定控件，并将这些控件与画布的其它子项按Z轴顺序排序。画布面板是非常适用于手动布局的控件。

![v2-7950c8aad1ff1727f3a8c2238d462ec5_720w](https://raw.githubusercontent.com/000111i/picgo/main/imgv2-7950c8aad1ff1727f3a8c2238d462ec5_720w.webp)

如上图，只有Canvas Panel可以这么随意的摆放控件位置，但也更难对齐。因此一般有较强的栅格系统的设计排版不建议采用Canvs Panel。

#### Horizental/Vertical box 水平/竖直框

![v2-c36533bddb4983398b5574e4d44b80a2_r](https://raw.githubusercontent.com/000111i/picgo/main/imgv2-c36533bddb4983398b5574e4d44b80a2_r.jpg)

值得注意的是子控件的Slot属性发生了变化。

![img](https://raw.githubusercontent.com/000111i/picgo/main/imgv2-3978c1cf71de5f3823fb2b7ce0acc6e1_720w.webp)

有两个需要重点关注的地方：

- 通过padding设置子控件之间的间距

如果是数量确定，内容确定的列表，可以手动设置padding。

![v2-4d74fc7464e7aa6e386972f8b02edddf_720w](https://raw.githubusercontent.com/000111i/picgo/main/imgv2-4d74fc7464e7aa6e386972f8b02edddf_720w.webp)

如果数量不确定或内容不确定需要程序动态添加的列表，则需要把间距提前设计好放在node中。

![v2-d144e2952fae42d6a9828d5754b0412a_720w](https://raw.githubusercontent.com/000111i/picgo/main/imgv2-d144e2952fae42d6a9828d5754b0412a_720w.webp)

- 子控件的尺寸不再能自由定义

这里提供了两种调节尺寸的方式

Auto代表自动调节尺寸，与之前Slot中的Size to Content一致

Fill代表自动填满剩余空间

这里展示一下不同设置的效果

![v2-61b761587a44b404380df02ca69149d8_720w](https://raw.githubusercontent.com/000111i/picgo/main/imgv2-61b761587a44b404380df02ca69149d8_720w.webp)

####  **Grid Box 网格面板**

网格面板可以为你创建一套网格系统，并让子控件在该网格内进行布局。

![v2-e7e9a7018ac16584e17226ab62bade6a_720w](https://raw.githubusercontent.com/000111i/picgo/main/imgv2-e7e9a7018ac16584e17226ab62bade6a_720w.webp)

划分好网格后，只需设置子节点的参数即可占用网格。

![v2-0ba6ff7255ae6ad3f15adc109dee550d_720w](https://raw.githubusercontent.com/000111i/picgo/main/imgv2-0ba6ff7255ae6ad3f15adc109dee550d_720w.webp)

#### **Scroll Box 滚动框**

滚动框容器使得内容过多时可以在限定范围内进行滚动。

![v2-1ddeec0b37ff9b89ec7c867c045e3e2a_720w](https://raw.githubusercontent.com/000111i/picgo/main/imgv2-1ddeec0b37ff9b89ec7c867c045e3e2a_720w.webp)

#### **SafeZone 安全区**

安全区控件的子节点会自动避开全面屏的安全区来进行适配。

![v2-f43e839473cd1d7cc55f461623f93d4d_720w](https://raw.githubusercontent.com/000111i/picgo/main/imgv2-f43e839473cd1d7cc55f461623f93d4d_720w.webp)

​                                                                                                   *预览安全区控件在iphone X上的效果*

![img](https://raw.githubusercontent.com/000111i/picgo/main/imgv2-7dfc88fa53bd77ad8466e5fb792af967_720w.webp)

​                                                                                                *屏幕尺寸调整区域可以修改刘海屏的方向来测试*

SafeZone还可以设置只对某一个方向的安全区生效（比如攻击按键只想在iPhoneX上左右偏移，不会向上偏移）。

![img](https://raw.githubusercontent.com/000111i/picgo/main/imgv2-afa3f3606eaf00cb6b3f0ed886f36dd9_720w.webp)

​                                                                                                                        *设置生效的安全区*

#### **Widget Switcher 选项卡切换器**

![img](https://raw.githubusercontent.com/000111i/picgo/main/imgv2-94ac5f2a1b9cac1fe8e4949e9db5f7f5_720w.webp)

#### **User Created**

![img](https://raw.githubusercontent.com/000111i/picgo/main/imgv2-b482744c7e0b319394cf2e777d7ee218_720w.webp)

项目中创建的widget都能在这找到

## 开发案例

下面介绍UMG开发案例

### UI布局介绍

如果自己创建了个控件蓝图，准备开发出类似界面布局:

![image-20230621161813668](https://raw.githubusercontent.com/000111i/picgo/main/imgimage-20230621161813668.png)

其中垂直框有水平框，一是垂直框可以有子控件，二是水平框水平方向可以容纳多个布局（可以容纳多个子控件），如果要调节水平框或者垂直框大小可以用尺寸框包裹它们，在“高度重载“和”宽度重载“调节它们。如果调整大垂直框里的水平框或者垂直框的间距、锚点和对齐规则，如图

![image-20230621163016863](https://raw.githubusercontent.com/000111i/picgo/main/imgimage-20230621163016863.png)

再看另一个复杂的案例：

![image-20230621164103281](https://raw.githubusercontent.com/000111i/picgo/main/imgimage-20230621164103281.png)

第一个覆层，作用是覆盖一个背景图片，但里也可以有水平框，第二行水平框，水平方向有很多内容，大垂直框承载整个布局，最后控件切换器（Widget Switcher）上面有介绍，也可以布局在垂直框里，作为一个子控件。

![image-20230621164744052](https://raw.githubusercontent.com/000111i/picgo/main/imgimage-20230621164744052.png)

这是各个控间在开发时的布局。

其中这些控件的锚点可以手动调节，只有canva panle下面一级子控件才可以调节锚点，其他被父控件覆盖的子控件位置跟随父控件。长按“ctrl”更新控件位置，长按“shift”跟谁鼠标更新锚点位置。

### 开发时需要注意的问题

#### 间距问题

比如一个水平框里有很多子控件，需要一定的间距，尽量用“间隔区”填充，“填充”相对于“自动”在分辨率非正常下变形度较小。

![image-20230621170946836](https://raw.githubusercontent.com/000111i/picgo/main/imgimage-20230621170946836.png)

其中填充比列规则，要根据间距像素的计算，得出所以间距像素的值，各自比值就是填充的比值。

#### 分辨率问题

开发时，最好确定甲方分辨率，其次在每个不同的需要开发的分辨率调节好，如果有些子控件要分开发的话（对于一个用户控件有很多内容建议分为及模块开发）也要确定不同的空间的分辨率，因为这对间距的计算是必要条件。

一般开发的分辨率为“1920×1080”（16：9),如果硬件条件打不到，但尽量保持比例正确。

![image-20230621171955723](https://raw.githubusercontent.com/000111i/picgo/main/imgimage-20230621171955723.png)

![image-20230621172011245](https://raw.githubusercontent.com/000111i/picgo/main/imgimage-20230621172011245.png)

在子控件分辨率正确的前提下再调整其中包裹里面的控件间距大小。

## UI数据与程序对接
