# css 

## 盒模型

- 标准盒模型

```css
box-sizing: content-box;
```

![](http://47.100.243.94:3011/uploads/1578729464066.jpg)

- 怪异盒模型

```css
box-sizing: border-box;
```

![](http://47.100.243.94:3011/uploads/1578729535964.jpg)



## padding+auto

- 右靠

```css
margin-left: auto;
margin-right: 100px;　/* 0px 最右侧 */
width: 100px;
```

- 自适应宽度居中

```css
margin: 0 100px;
```

- 固定宽度居中

```css
width: 100px;
margin: 0 auto;
```

- 超过父盒子

```css
margin-left: 100px;
margin-right: -100px;
```

[codepen](https://codepen.io/kano233333/pen/MWYGvwo)

## margin合并

### 合并类型

![](http://47.100.243.94:3011/uploads/1578720259259.gif)

![](http://47.100.243.94:3011/uploads/1578720300034.gif)

![](http://47.100.243.94:3011/uploads/1578720336176.gif)

![](http://47.100.243.94:3011/uploads/1578720336176.gif)

### 合并应用

> 第一个段落上面的空间等于段落的上外边距。如果没有外边距合并，后续所有段落之间的外边距都将是相邻上外边距和下外边距的和。

![](http://47.100.243.94:3011/uploads/1578720379908.gif)

### 解决合并

- 相邻盒子（触发`BFC`）

`下面的盒子`

```css
position：absolute;
```

```css
float：left；
```

`二选一使用`

```css
dispaly：inline-block；
```



- 父子盒子s

`父盒子`：添加`padding`或者`border`

[BFC](http://47.100.243.94:3006/main/essay/5e1979c9e1b8e00fd9333cd9)     [codepen](https://codepen.io/kano233333/pen/mdyLMJZ)



## BFC 

[参考１](http://47.100.243.94:3006/main/essay/5e1979c9e1b8e00fd9333cd9)

[参考２](https://blog.csdn.net/sinat_36422236/article/details/88763187)



## 层叠上下文

> 归结还是`z-index`的原因

### 触发条件

- `position` + `z-index`
- 父元素`display: flex | inner-flex`，子元素`z-index` !== `auto`
- `opacity` !== 0
- `transform` !== none
- `mix-blend-mode` !== nomal
- `isolation` : isolate
- `will-change`
- `-webkit-overflow-scrolling`: touch

### 顺序

> 是**触发**了层叠上下文的元素才会有这个等级

![](http://47.100.243.94:3011/uploads/1578817532279.png)

[more](https://www.zhangxinxu.com/wordpress/2016/01/understand-css-stacking-context-order-z-index/)     [codepen](https://codepen.io/kano233333/pen/OJPZagr)

## 搞事的transform

- 层叠上下文--->提升元素垂直地位
- 限制`position:fixed`追随效果
- 添加transform有添加`position`的效果--->受到`overflow`的限制  +   将子元素width:100%是父元素的width

[codepen](https://codepen.io/kano233333/pen/dyPeawN)

