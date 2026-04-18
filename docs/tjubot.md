# tjubot

```javascript
// ==UserScript==
// @name         Peiyang Wiki Tool
// @namespace    http://tampermonkey.net/
// @version      2025-08-05
// @description  解除北洋维基复制限制，右键限制，删除水印
// @author       FANCC
// @run-at       document-start
// @match        https://wiki.tjubot.cn/*
// @match        http://wiki.tjubot.cn/*
// @icon         https://wiki.tjubot.cn/favicon.ico
// @grant        none
// ==/UserScript==

(function() {
    'use strict';

    // 解除禁止选中，并且隐藏水印
    let style_object = document.createElement('style');
    style_object.innerHTML = `
    .mask_div{display: none !important;}
    html{user-select: initial !important;-webkit-user-select: initial !important;-moz-user-select: initial !important;}
    `;
    document.head.appendChild(style_object);

    // 解除复制限制
    Object.defineProperty(document, 'onselectstart', {
        set: function() {},// 忽略赋值
        get: function() {
            return null;
        },
        configurable: false,
        enumerable: true
    });
    document.addEventListener('selectstart', function(e) {
        e.stopImmediatePropagation();
    }, true);
    
    // 解除右键菜单限制
    Object.defineProperty(document, 'oncontextmenu', {
        set: function() {},// 忽略赋值
        get: function() {
            return null;
        },
        configurable: false,
        enumerable: true
    });
    document.addEventListener('contextmenu', function(e) {
        e.stopImmediatePropagation();
    }, true);

    // dom元素加载完毕后继续
    document.addEventListener('DOMContentLoaded', function() {
        let page = document.querySelector("#page-main-content");
        page.setAttribute("oncopy", "return true;");
    });
})();
```
