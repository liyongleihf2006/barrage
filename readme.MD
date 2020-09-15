# barrage #

简单的弹幕效果

1. 自动计算尽量展示到顶部
2. 鼠标悬浮300ms会停止运动
3. 鼠标移开以后弹幕会动画返回它应该移动到的位置
4. 可以自己传入任意事件
5. 可以传入dom或者文本

[demo](https://liyongleihf2006.github.io/barrage/)

```css
.barrage-container {
    position: relative;
    user-select: none;
    overflow: hidden;
}

.barrage-item {
    position: absolute;
    cursor: pointer;
    white-space: nowrap;
}

.barrage-pause {
    z-index: 1;
}
```

```js
import barrage from './barrage.js'
const { addBarrageItem, clearBarrageItem } = barrage({ barrageContainer: document.querySelector('#barrageContainer') })
addBarrageItem(document.createTextNode('一段文字'), {
    click: function (event) {
        console.log(event.target.textContent)
    }
})
```

