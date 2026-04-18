<!-- # chaoxing -->

```javascript
// ==UserScript==
// @name         学习通工具
// @namespace    http://tampermonkey.net/
// @version      2025-11-29
// @description  解除学习通鼠标检测，新功能更新中
// @author       FANCC
// @match        http://mooc1-1.chaoxing.com/*
// @match        https://mooc1-1.chaoxing.com/*
// @icon         https://tju.edu.cn/favicon.ico
// @grant        none
// ==/UserScript==

(function() {
    'use strict';

    // Your code here...
    // 解除鼠标移动
    Object.defineProperty(document, 'mouseout', {
        set: function() {},// 忽略赋值
        get: function() {
            return null;
        },
        configurable: false,
        enumerable: true
    });
    document.addEventListener('mouseout', function(e) {
        e.stopImmediatePropagation();
    }, true);
})();
```
