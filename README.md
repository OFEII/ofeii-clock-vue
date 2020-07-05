## OFEII CLOCK

### 项目介绍

一个基于Vue2.x框架和ES6规范的有点设计感，用心制作的可拖拽可调节的数据驱动型时钟。

网址直达👉[https://ofeii.github.io/ofeii-clock-vue/](https://ofeii.github.io/ofeii-clock-vue/)（移动端的拖拽功能~~暂未完全实现~~ 已实现）

#### pc端页面展示

![ofeii-clcok-pc](D:\14_Img\ofeii-clock\ofeii-clock.png)

![](D:\14_Img\ofeii-clock\gif1.gif)

![](D:\14_Img\ofeii-clock\gif2.gif)

#### 移动端页面展示

<img src="D:\14_Img\ofeii-clock\ofeii-clock-mobile.jpg" style="zoom:20%;" />

#### 主要功能

1. 一开始时钟与本地时间实时同步变化，时钟表盘的各指针与表盘下面的电子时钟的时分秒相对应变化。
2. 点击上面的的表盘（按下鼠标）即可实现时钟的暂停和启动的切换。
3. 用鼠标顺时针拖拽时针、分针及秒针即可对时间进行调整，下方的电子时钟实时显示。
4. 电子时钟上下有对应的+和-按钮，点击即可实现对应的时分秒加1减1。
5. 增加暗黑模式， 当时间为22:00 -- 7:00时，显示暗黑模式；其余时间为日间正常模式。

兼容性

| Chrome | Firefox | Mircosoft Edge | 360(IE) | 手机浏览器 |
| ------ | ------- | -------------- | ------- | ---------- |
| ⭕      | ⭕       | ⭕              | ⭕       | ⭕          |

### 设计理念

无论是做网页或是做App，技术固然重要的，但设计也很重要，好的技术可以 减少bug的出现，好的设计可以提升用户体验。

#### 1.新拟态设计风格（Neumorphism / soft ui）

在线工具生成网址：[https://neumorphism.io/](https://neumorphism.io/)

虽然有在线生成工具，不过项目中主要还是靠自己调试

介于扁平与阴影的一种表现手法，通过受光面和阴影颜色的对比，引起视觉差异，提高物品的真实感。

其特点：

- **模拟光源照射的真实拟物场景**。物体阴影+受光面+受光面的反射面 ==> 更逼真。
- **元素与背景对比较弱**。与背景颜色相近色，没有丰富的色彩选择 ==> 提高受光面反射光的亮度。
- **主要以圆角或卡片形状为主**。一般不大面积进行覆盖，好比真实物体置身于现实场景中。

其缺点：

- 对比度弱，色彩单一，层次感不够。
- 对背景依赖度高，使用不当易造成视觉干扰。
- 样式复杂，不易修改。

#### 2.暗黑模式（dark mode）

在本项目中还加入了暗黑模式(dark mode)，而非夜间模式，虽然代码中用了day和night来定义。

DARK MODE的好处在于：

1. 极大地提升用户体验。加入了用户在在暗光环境下的使用场景，使用时间覆盖了白天和黑夜
2. dark mode可以降低屏幕的整体视觉亮度减少对眼睛的视觉压力。
3. 节能省耗。可以降低设备耗电速度。
4. 专注内容。对比强烈的层次关系可以让用户更注重被凸显出来的内容和交互操作，优化交互体验。
5. 信息保护。暗黑模式下的屏幕信息在非正视角预览时，信息的辨别可视性反倒会降低。

**与夜间模式night mode的区别？**

夜间模式主要是通过降低对比度和饱和度来得以实现的。而暗黑模式(dark mode)考虑弱光环境，降低对比度，通过深灰来衬托高饱和和明亮像素，减少高对比度模糊，满足阅读效果



### 细节之处

#### 1.配色方案

由于采用了新拟态的设计，就是色彩丰富度上相对而言会简单一点，主要以时钟经典的黑白红为主。

而暗黑模式是一种弱亮度UI，主要显示深色的界面，大量地使用深色和黑色，颜色的减少减弱可以降低屏幕发出的亮度但同时满足看最低色彩对比度的要求。



![](D:\14_Img\ofeii-clock\OFEII-CLOCK-COLORS.png)

#### 2.WCAG2.0标准

WCAG 2.0 (Web Content Accessibility Guidelines，内容可访问性指南)是国际公认的通用标准，在西方国家是作为评判产品优劣的重要指标。

对比度查询工具：[https://contrast-ratio.com/](https://contrast-ratio.com/)

> **对比度（最小）：**文本视觉呈现和文本图像至少要有4.5：1的对比度，以下部分除外：（AA级）

将日间和夜间模式的背景色background及主要文本颜色color对比可得其对比度均在4.5之上，满足了WCAG 2.0 的 AA 级要求。

![](D:\14_Img\ofeii-clock\RADIO1.png)

![](D:\14_Img\ofeii-clock\RADIO2.png)

#### 3.拟物化指针

在日间模式的指针配色主要为黑和红为，且时针和分针的指针尾部有一处白色的装饰，黑与白的相呼应，使得这个时钟在简约设计的同时不失小细节。而在暗黑模式的指针配色主要为白和红，因为尾部的装饰在白色下显得有些突兀，故舍去。而且每个指针都加了一层box-shadow增加指针的拟物感，使得更加逼真，贴近实物。

![](D:\14_Img\ofeii-clock\hand1.png)



<img src="D:\14_Img\ofeii-clock\hand2.png" style="zoom: 33%;" />

#### 4.凸起凹陷的真实质感

点击时钟表盘即可实现对时钟的暂停和启动切换。按下增减按钮可以实现对时间的增减。在这两个click事件中，在click的时候通过CSS伪类选择器:focus改变box-shadow的样式来切换，浮雕凸起(rasied)和凹陷(inset)的真实质感的效果。

:focus选择器用于选取获取得焦点的元素，因为每当鼠标在click点击时就会自动获取焦点，此时运用:focus选择器即可实现对box-shadow的样式切换。



![ofeii-clcok-pc](D:\14_Img\ofeii-clock\ofeii-clock.png)

![](D:\14_Img\ofeii-clock\ofeii-clock-day-plus.png)



![](D:\14_Img\ofeii-clock\ofeii-clock-stop.png)



![](D:\14_Img\ofeii-clock\ofeii-clock-night.png)

### 知识点

#### 1.clientX Y属性 

返回当事件被id触发时鼠标指针相对于浏览器页面窗口（client）的水平 垂直坐标（鼠标的坐标）

其他相关属性

| 属性名           | 含义                                                         | 备注               |
| ---------------- | ------------------------------------------------------------ | ------------------ |
| **offsetTop**    | 返回元素的上外缘距离最近采用定位父元素内壁的距离。           | 只读               |
| **offsetLeft**   | 返回元素的左外缘距离最近采用定位父元素内壁的距离。           | 只读               |
| **offsetWidth**  | 返回元素的宽度（包括元素宽度、内边距和边框，不包括外边距）   | 只读               |
| **offsetHeight** | 返回元素的高度（包括元素高度、内边距和边框，不包括外边距）   | 只读               |
| **scrollLeft**   | 元素被滚动条向左拉动的距离                                   | 可读写             |
| **scrollTop**    | 元素滚动条被向下拉动的距离                                   | 可读写             |
| **clientWidth**  | 返回元素的宽度（包括元素宽度、内边距，不包括边框和外边距）   | 只读               |
| **clientHeight** | 返回元素的高度（包括元素高度、内边距，不包括边框和外边距）   | 只读               |
| **style.width**  | 返回元素的宽度（包括元素宽度，不包括内边距、边框和外边距）   | 返回string，可读写 |
| **style.height** | 返回元素的高度（包括元素高度，不包括内边距、边框和外边距）   | 返回string，可读写 |
| **scrollWidth**  | 返回元素的宽度（包括元素宽度、内边距和溢出尺寸，不包括边框和外边距），无溢出的情况，与clientWidth相同 | 可读写             |
| **scrollHeigh**  | 返回元素的高度（包括元素高度、内边距和溢出尺寸，不包括边框和外边距），无溢出的情况，与clientHeight相同 | 可读写             |



| 属性名          | 含义                                                         |      |
| --------------- | ------------------------------------------------------------ | ---- |
| **clientX**     | 鼠标相对于浏览器（这里说的是浏览器的有效区域）左上角x轴的坐标；  不随滚动条滚动而改变； |      |
| **clientY**     | 鼠标相对于浏览器（这里说的是浏览器的有效区域）左上角y轴的坐标；  不随滚动条滚动而改变； |      |
| **pageX**       | 鼠标相对于浏览器（这里说的是浏览器的有效区域）左上角x轴的坐标；  随滚动条滚动而改变； |      |
| **pageY**       | 鼠标相对于浏览器（这里说的是浏览器的有效区域）左上角y轴的坐标；  随滚动条滚动而改变； |      |
| **screenX**     | 鼠标相对于显示器屏幕左上角x轴的坐标；                        |      |
| **screenY**     | 鼠标相对于显示器屏幕左上角y轴的坐标；                        |      |
| **offsetX**     | 鼠标相对于事件源左上角X轴的坐标                              |      |
| **offsetY**     | 鼠标相对于事件源左上角Y轴的坐标                              |      |
| **innerheight** | 返回窗口的文档显示区的高度。（window.innerHeight）           |      |
| **innerwidth**  | 返回窗口的文档显示区的宽度。（window.innerWidth）            |      |



#### 2.CSS3 transform-origin属性和rotateZ()

#####  0.transform-origin

transform-Origin属性允许您更改转换元素的位置。2D转换元素可以改变元素的X和Y轴。 3D转换元素，还可以更改元素的Z轴。

transform-origin: x-axis y-axis z-axis;



##### 1.rotateZ

> MDN:rotateZ()函数定义了一个转换，它可以让一个元素围绕横Z轴旋转，而不会对其进行变形。它的结果是一个[`transform-function`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/transform-function)数据类型。

rotateZ引起的旋转量由angle制定，正值则为顺时针转动，负值为逆时针转动。

```
rotateZ(a)
```

`a` 是一个[`angle`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/angle) ，表示旋转的角度。正数角度表示顺时针旋转，负数则表示逆时针旋转。

rotateZ(a) 相当于 rotate(a) or rotate3d(0, 0, 1, a)。



##### 2.angle

<angle>是一个用于表示角度大小的css数据类型，单位为度（degrees）、 百分度（gradians）、弧度（radians）或圈数（turns）。在 gradient 和transform 的某些方法等场景中有所应用。

###### 语法

数据类型由 <number> 和下列单位组成。数字与单位之间没有空格。数字为0时，单位可以省略。

 <angle>可以使用+或-开头。正数表示顺时针的角，负数表示逆时针的角。对于静态的角，同样的角度可以使用任意等效的值表示。比如90deg等于-270deg，1turn等于4turn。而对于动态的角，比如应用了animation或 transition时，显示效果则不一样。

###### 单位

- deg度。一个完整的圆是 360deg。例：0deg，90deg，``14.23deg。
- `grad`[百分度](https://zh.wikipedia.org/wiki/百分度)。一个完整的圆是 `400grad`。例：`0grad`，`100grad`，`38.8grad`。
- `rad`[弧度](https://zh.wikipedia.org/wiki/弧度)。一个完整的圆是 2π 弧度，约等于 `6.2832rad`。`1rad` 是 180/π 度。例：`0rad`，`1.0708rad`，`6.2832rad`。
- turn圈数。一个完整的圆是 1turn。例：0turn，0.25turn，1.2turn。



#### 3.拖拽的流程

在HTML5中有原生的拖拽API，设置元素的draggable为true即可拖拽。

- 在拖动目标上触发事件(源元素):
  - ondragstart - 用户开始拖动元素时触发
  - [ondrag](https://www.runoob.com/jsref/event-ondrag.html) - 元素正在拖动时触发
  - [ondragend](https://www.runoob.com/jsref/event-ondragend.html) - 用户完成元素拖动后触发
- 释放目标时触发的事件:
  - [ondragenter](https://www.runoob.com/jsref/event-ondragenter.html) - 当被鼠标拖动的对象进入其容器范围内时触发此事件
  - [ondragover](https://www.runoob.com/jsref/event-ondragover.html) - 当某被拖动的对象在另一对象容器范围内拖动时触发此事件
  - [ondragleave](https://www.runoob.com/jsref/event-ondragleave.html) - 当被鼠标拖动的对象离开其容器范围内时触发此事件
  - ondrop - 在一个拖动过程中，释放鼠标键时触发此事件

tips： 在拖动元素时，每隔 350 毫秒会触发 ondragover 事件。



#### 4.数字和字符串的转换及数字进度处理

```js
Math.round(四舍五入)

Math.ceil 向上取整

Math.floor 向下取整 （也可以采用位运算~~，更加简洁快速）

parseInt 保留整数部分

parseInt(string, radix)   将一个字符串 string 转换为 radix 进制的整数， radix 为介于2-36之间的数。

parseFloat（str:string）=>{

return num:number

}
```



#### 5.Element.getBoundingClientRect()

Element.getBoundingClientRect() 方法返回元素的大小及其相对于视口的位置。

返回值是一个 DOMRect 对象，这个对象是由该元素的 getClientRects() 方法返回的一组矩形的集合，就是该元素的 CSS 边框大小。返回的结果是包含完整元素的最小矩形，并且拥有left, top, right, bottom, x, y, width, 和 height这几个以像素为单位的只读属性用于描述整个边框。除了width 和 height 以外的属性是相对于视图窗口的左上角来计算的。



#### 6.计算拖拽两点之间的角度

Math.atan2( )返回从原点(0,0)到(x,y)点的线段与x轴正方向之间的平面角度(弧度值)，也就是Math.atan2(y,x)

返回一个 -pi 到 pi 之间的数值，表示点 (x, y) 对应的偏移角度。这是一个逆时针角度，以弧度为单位，正X轴和点 (x, y) 与原点连线 之间。注意此函数接受的参数：先传递 y 坐标，然后是 x 坐标。

因为atan2返回的是弧度值（弧度制：1°=π/180 rad），所以如果想得到deg为单位的结果还要对Math.atan2( )的返回值再作处理。



### 遇到的问题

#### 1.时钟中数据类型的选择

指针的旋转角度：number

电子时钟的数字：string

本项目是数据驱动的时钟，在下面的电子时钟（digital clock）中，由于是两位的数字显示（可能会出现00 01 之类的显示），故采用字符串string的类型来定义；而在上面时钟表盘中指针的旋转角度则用数字number来表示。data的定义如下图：

```js
  data() {
    return {
      // 指针转动角度
      secDeg: 0,
      minDeg: 0,
      hourDeg: 0,
      // 电子时钟(时 分 秒) digital-Time(Hour, Min ,Sec)
      digitalHour: "",
      digitalMin: "",
      digitalSec: "",
      // 控制是否停止时间停止的状态
      isTimeStop: false,
      // 控制夜晚或者白天的状态
      isNight: false
    };
  },
```

#### 2.数据的处理

1.时间初始化:获取本地的时间并将其转为string，并用padStart()补全为两位的string

```js
  methods: {
    // 时间初始化:获取本地的时间并将其转为string，并用padStart()补全
    timeInit () {
      const nowTime = new Date()
      this.digitalHour = (nowTime.getHours() + '').padStart(2, '0')
      this.digitalMin = (nowTime.getMinutes() + '').padStart(2, '0')
      this.digitalSec = (nowTime.getSeconds() + '').padStart(2, '0')
    },
  }
```

2.时间（digital clock）转化为指针的旋转角度

```
      this.hourDeg =(this.digitalHour / 12) * 360 + (this.digitalMin / 60) * 30;
      this.minDeg = (this.digitalMin / 60) * 360 + (this.digitalSec / 60) * 6;
      this.secDeg = (this.digitalSec / 60) * 360;
```

3.拖拽时旋转角度转化为时间（digital clock）为上面的逆运算

```
      this.digitalHour = (
        Math.round((this.hourDeg - +this.digitalMin / 2) / 30) + ''
      ).padStart(2, '0')
      
      this.digitalMin = (
        Math.round((this.minDeg - +this.digitalSec / 10) / 6) + ''
      ).padStart(2, '0')
      
      this.digitalSec = (Math.round(this.secDeg / 6) + '').padStart(2, '0')
```

4.时分秒的格式化

可以将时想成是24进制 分和秒是60进制，不过进制的实现在js有些复杂。可以对时间（digital clock）进行一个小小的处理，例如对于digitalHour，大于24时，对其进行取模（求余数）运算，小于0时即再加上24。

```
    // 时针格式化
    formatHour () {
      if (this.digitalHour >= 24) {
        this.digitalHour = ((+this.digitalHour % 24) + '').padStart(2, '0')
      } else if (this.digitalHour < 0) {
        this.digitalHour = (
          +this.digitalHour +
          Math.round(Math.abs(this.digitalHour) / 24 + 1) * 24 +
          ''
        ).padStart(2, '0')
      }
    },
        // 分针格式化
    formatMin () {
      if (this.digitalMin >= 60) {
        this.digitalMin = ((+this.digitalMin % 60) + '').padStart(2, '0')
        this.digitalHour = (+this.digitalHour + 1 + '').padStart(2, '0')
      } else if (this.digitalMin < 0) {
        this.digitalMin = (
          +this.digitalMin +
          Math.round(Math.abs(this.digitalHour) / 60 + 1) * 60 +
          ''
        ).padStart(2, '0')
        this.digitalHour = (+this.digitalHour - 1 + '').padStart(2, '0')
      }
    },
    // 秒针格式化
    formatSec () {
      if (this.digitalSec >= 60) {
        this.digitalSec = ((+this.digitalSec % 60) + '').padStart(2, '0')
        this.digitalMin = (+this.digitalMin + 1 + '').padStart(2, '0')
      } else if (this.digitalSec < 0) {
        this.digitalSec = (
          +this.digitalSec +
          Math.round(Math.abs(this.digitalHour) / 60 + 1) * 60 +
          ''
        ).padStart(2, '0')
        this.digitalMin = (+this.digitalMin - 1 + '').padStart(2, '0')
      }
```

5.时分秒的点击 +1 /-1的操作。 字符串前面加'+'即可隐式转换为数字在增减1，再转为字符串补全，操作比较简单。

```
this.digitalHour = (+this.digitalHour + 1 + '').padStart(2, '0')
```

6.判断夜晚或白天模式

```
    // 判断夜晚或白天模式
    isMode () {
      const numDh = +this.digitalHour
      this.isNight =
        !!((numDh >= 22 && numDh <= 23) || (numDh >= 0 && numDh <= 6))
    }
```



   const numDh = +this.digitalHour

   this.isNight =

​    !!((numDh >= 22 && numDh <= 23) || (numDh >= 0 && numDh <= 6))

  }

#### 3.自定义指令v-drag实现定点拖拽旋转

将定点拖拽旋转的功能封装成一个名为v-drag的自定义指令，可以在template中使用和传参。

在PC端整个事件的流程大概是 

1. mousedown鼠标按下
2. mousemove鼠标移动
3. mouseup释放鼠标

(当前鼠标的坐标-event.clientX和event.clientY)

在pc端的定点拖拽旋转的实现主要分为

1. onmousedown鼠标按下，计算出当前元素（即绑定的元素el）
2. mousemove鼠标移动时，记录下鼠标的移动距离并通过Math.atan2计算出去旋转的角度deg并用binding.value.set(deg)将值传出
3. mouseup释放鼠标时，防止鼠标黏连return false

```
  directives: {
    // 自定义指令 v-drag，el当前元素
    drag (el, binding) {
      // pc端拖拽
      el.onmousedown = e => {
        // 鼠标按下，计算当前元素距离client的距离
        const disX = e.clientX - el.offsetLeft
        const disY = e.clientY - el.offsetTop
        const rect = e.target.getBoundingClientRect()
        const centerX = rect.left + rect.width / 2
        const centerY = rect.top + rect.width / 2
        document.onmousemove = e => {
          // 鼠标移动，计算其移动距离
          const l = e.clientX - centerX - disX
          const t = centerY - e.clientY - disY
          // 计算其旋转角度
          const deg = (Math.atan2(t, l) / Math.PI) * 1.5
          // 旋转
          el.style.transform = `rotateZ(${deg}deg)`
          // set传出deg给data
          binding.value.set(deg)
        }
        document.onmouseup = e => {
          document.onmousemove = null
          document.onmouseup = null
        }
        return false
      }
    }
  }
```



#### 4.vue中自定义指令改变data的值

在directives创建自定义指令传入drag(el, binding) 通过传参的形式将绑定到v-drag的method中的函数并通过binding.value.set(deg)传值到method中的函数，以此来改变data中的值。

```vue
//template
      <!-- hour时针-->
      <div class="hour">
        <div
          class="hr"
          v-drag="{set:setDigitalHour}"
          draggable="false"
          id="clock-hour"
          :style="{transform: `rotateZ(${hourDeg}deg)`}"
        >
          <span class="tail hr-tail"></span>
        </div>
      </div>

//script

methods: {
	setDigitalHour (deg) {
      this.hourDeg = Math.round(this.hourDeg - deg)
      ......
    },
}

directives: {
    // 自定义指令 v-drag，pc端拖拽,el当前元素
    drag (el, binding) {
		......
        // set传出deg给data
        binding.value.set(deg)
        ......
    }
}
```



#### 5.兼容移动端的拖拽

由于移动端是没有鼠标的，取而代之是touch事件，其过程的事件主要有：

(当前触摸点的坐标为event.touches[0].clientX和event.touches[0].clientY)

1. touchstart

2. touchmove

3. touchend

在directives的 drag (el, binding) {}加入移动的定点拖拽旋转函数即可完成移动端的旋转。



#### 6.移动端拖拽时出现NaN问题

出现NaN的原因可能是v-drag的deg拖拽角度没有传入导致methods中函数的return出错，返回NaN。

解决：event.touches  ==> event.touches[0]，在touch后面加入[0]即可看到移动端可以实现完整的定点拖拽旋转效果。

tips：

移动端获取坐标是`event.touches[0].clientX`和`event.touches[0].clientY`

而在PC端获取当前鼠标的坐标是：`event.clientX`和`event.clientY`

同时PC端的event，在移动端是event.touches

<img src="D:\14_Img\ofeii-clock\moblie-error.jpg" style="zoom:50%;" />





#### 7.移动端点击出出现蓝色框的解决问题

在移动端测试点击时钟表盘暂停和启动时出现蓝色框阴影的问题，在查阅资料后明白，应该是移动端上tap事件或者focus会产生一个-webkit-tap-highlight-color以提示用户点击成功。

> MDN: **`-webkit-tap-highlight-color`** 是一个没有标准化的属性，能够设置点击链接的时候出现的高亮颜色。显示给用户的高光是他们成功点击的标识，以及暗示了他们点击的元素。

```
  /* fixed blue rect in android */
  body {
  	...
    -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
  }

  /* fixed blue rect in ios/wechat  */
  a:focus,
  input:focus,
  p:focus,
  div:focus {
    -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
    -webkit-user-modify: read-write-plaintext-only;
  }
```



#### 8.npm run serve出现两个localhost的问题

由于在vue-cli3以上将vue.config不再显示了，若需使用需要自己添加vue.config进行配置，在添加了一个模版vueconfig后出现了两个localhost的问题，无法通过ip地址在移动端进行测试。

![](D:\14_Img\ofeii-clock\localhost8080问题.png)

```
    devServer: {
        overlay: { // 让浏览器 overlay 同时显示警告和错误
            warnings: true,
            errors: true
        },
-old：  host: 'localhost',
+fix：  host: '0.0.0.0',
        port: 8080,
        // 端口号
        https: false,
        // https:{type:Boolean}
        open: false,
        //配置自动启动浏览器
        hotOnly: true,
        // 热更新
        proxy: 'http://localhost:8080' // 配置跨域处理,只有一个代理
    }
```



#### 9.格式化的选择

一开始是使用vetur(默认)和prettier Code Formatter直接对代码进行格式化，后来改成了JS Standard的规范。

编辑器是vscode，在vscode中安装插件'StandardJS - JavaScript Standard Style'

1. **Install the 'JavaScript Standard Style' extension**

2. **Install `standard`, `semistandard` or `standardx`**

3. **Disable the built-in VSCode validator**

   To do this, set `"javascript.validate.enable": false` in your VSCode `settings.json`.

4. config配置 lint `script` tags in `vue` or `html` files：

   ```js
    "standard.validate": [
        "javascript",
        "javascriptreact",
        "html"
    ],
    "standard.options": {
        "plugins": ["html"]
    },
    "files.associations": {
        "*.vue": "html"
    },
   ```

vscode JS standard配置链接https://marketplace.visualstudio.com/items?itemName=chenxsan.vscode-standardjs



#### 10.vue项目打包部署后favicon无法正常显示

🧐：可能原因路径的问题或者vueconfig的配置问题或缓存的问题

解决方法：

1. 将新的favicon.ico小图标放在public里面。

2. 在index.html文件中引入时需要写上./相对路径。

3. file：ofeii-clock -> public -> index.html。

   ```html
   -old:  <link rel="icon" href="<%= BASE_URL %>favicon.ico">
   +fix:  <link rel="icon" href="./favicon.ico">
   ```

4. npm run build打包，网站前面的图标出现。

   ![](D:\14_Img\ofeii-clock\url-ico.jpg)



### 项目心得

人生天地之间,若白驹过隙,忽然而已。在时钟制作在调试过程中看着时分针一秒一秒地转动，感觉时间过得飞快，应该更加发奋努力、虚心学习。三更灯火五更鸡。

一个小小的时钟里面包含了很多基础的前端知识和数学知识，由于是数据驱动的时钟，同时也包含了很多关于数据的处理。在基本功能完全实现后又对UI样式进行了不断地调整，改了两三个版本，加入了dark mode 和neumorphism新拟态的风格，又对配色及文本背景背景色进行钻研，精益求精以致于提高用户的体验。在独自完成项目的过程中，感觉受益匪浅，查漏补缺。虽然还存在待改进的地方。

作为入职前的前置任务，我觉得意义重大，如果把它看作一道面试题，此题可以考察很多方面的东西。

### 待改进之处/todolist

组件化的再度封装

暗夜模式和日间模式的过渡切换

代码的部分解耦及优化

.......