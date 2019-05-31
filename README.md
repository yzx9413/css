### Css全局样式:
- - -
* 个人的样式表文件
* Bootstrap v3.3.7 
* 加class名称即可

```
/**
* 以750为基础做适配，1rem = 100px, 1rem = 100rpx;
* 监听pc端的resize事件和mobile的横屏（orientationchange）事件
*/
var fun = function(doc, win) {
    var docEl = doc.documentElement,
        resizeEvt = 'orientationchange' in window ? 'orientationchange' : 'resize',
        recalc = function() {
            var clientWidth = docEl.clientWidth;
            if (!clientWidth) return;
            //这里是在750px宽度设计稿的情况下，1rem = 100px；
            docEl.style.fontSize = (clientWidth / 750) * 100 + 'px';
        };
    if (!doc.addEventListener) return;
    win.addEventListener(resizeEvt, recalc, false);
    doc.addEventListener('DOMContentLoaded', recalc, false);
}
fun(document, window);
```
_ _ _
>>> 个人私用
***