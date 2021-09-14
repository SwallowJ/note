# CSS 文字

## 文字超出部分显示省略号

1. 单行文本

```css
overflw: hidden;
text-overflow: ellipis;
white-space: nowrap;
```

2. 多行文本(**适用于 WebKit 浏览器及移动端**)

```css
display: -webkit-box; /*将对象作为弹性伸缩盒子模型*/
-webkit-box-orient: vertical; /*设置或检索伸缩盒对象的子元素的排列方式 */
-webkit-line-clamp: 3; /*限制块元素显示的文本行数*/
overflow: hidden;
```
