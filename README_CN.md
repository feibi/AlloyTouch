﻿[English](https://github.com/AlloyTeam/AlloyTouch) | 简体中文

# AlloyTouch

腾讯AlloyTeam移动Web触摸解决方案

# Install
```js
npm install alloytouch
```

# API
```js
new AlloyTouch({
            touch:"#wrapper",//反馈触摸的dom
            vertical: true,//不必需，默认是true代表监听竖直方向touch
            target: target, //运动的对象
            property: "translateY",  //被运动的属性
            min: 100, //不必需,运动属性的最小值
            max: 2000, //不必需,滚动属性的最大值
            sensitivity: 1,//不必需,触摸区域的灵敏度，默认值为1，可以为负数
            factor: 1,//不必需,表示触摸位移与被运动属性映射关系，默认值是1
            spring: true, //不必需,是否有回弹效果。默认是true
            step: 45,//用于校正到step的整数倍
            change:function(value){  }, //不必需，属性改变的回调。alloytouch.css版本不支持该事件
            touchStart:function(evt, value){  },
            touchMove:function(evt, value){  },
            touchEnd:function(evt,value){  },
            tap:function(evt, value){  },
            pressMove:function(evt, value){  },
            animationEnd:function(value){  } //运动结束
 })
```
# 演示(Mobile)

- Simple : [http://alloyteam.github.io/AlloyTouch/](http://alloyteam.github.io/AlloyTouch/)
- 3D : [http://alloyteam.github.io/AlloyTouch/example/3d.html](http://alloyteam.github.io/AlloyTouch/example/3d.html)
- Rotate : [http://alloyteam.github.io/AlloyTouch/example/rotate.html](http://alloyteam.github.io/AlloyTouch/example/rotate.html)
- Carousel : [http://alloyteam.github.io/AlloyTouch/example/carousel.html](http://alloyteam.github.io/AlloyTouch/example/carousel.html)
- Carousel2 : [http://alloyteam.github.io/AlloyTouch/example/carousel2.html](http://alloyteam.github.io/AlloyTouch/example/carousel2.html)
- Three.js : [http://alloyteam.github.io/AlloyTouch/example/threejs/](http://alloyteam.github.io/AlloyTouch/example/threejs/)

## Vue1 & Vue2 Version

### Demo(Mobile)

- 滚动列表Vue1: [http://alloyteam.github.io/AlloyTouch/vue/example/](http://alloyteam.github.io/AlloyTouch/vue/example/vue1)
- 滚动列表Vue2: [http://alloyteam.github.io/AlloyTouch/vue/example/](http://alloyteam.github.io/AlloyTouch/vue/example/vue2)


```html
<div id="wrapper" v-alloytouch="{options: options, methods:{animationEnd: onAnimationEnd}}">
      <div id="scroller" class="alloytouch-target">
            <ul>
            ...  
            </ul>
      </div>
</div>
```
```js
new Vue({
      el: '#page',
      data: {
            options: {
                  touch:"",//反馈触摸的dom, 默认 directive所在dom
                  vertical: true,//不必需，默认是true代表监听竖直方向touch
                  target: '#scroller', //运动的对象
                  property: "translateY",  //被滚动的属性
                  sensitivity: 1,//不必需,触摸区域的灵敏度，默认值为1，可以为负数
                  factor: 1,//不必需,默认值是1代表touch区域的1px的对应target.y的1
                  min: window.innerHeight - 45 - 48 - 2000, //不必需,滚动属性的最小值
                  max: 0, //不必需,滚动属性的最大值
                  step: 40
            }
      },
      methods: {
            onAnimationEnd(){
                  console.log('onAnimationEnd')
            }
      }
      //动态设置属性
      //min: xxx,
      //max: xxx
});
```
# 感谢
- [transformjs](http://alloyteam.github.io/AlloyTouch/transformjs/)

# 谁用AlloyTouch?

![preview](http://sqimg.qq.com/qq_product_operations/im/qqlogo/imlogo.png)

# License
This content is released under the [MIT](http://opensource.org/licenses/MIT) License.
