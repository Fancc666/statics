<!-- # easyscroll -->

```javascript
// ==UserScript==
// @name         EasyScroll
// @namespace    http://tampermonkey.net/
// @version      2025-12-1
// @description  阅读界面自动滚动
// @author       FANCC
// @match        http://mooc1-1.chaoxing.com/mooc-ans/course/*
// @match        https://mooc1-1.chaoxing.com/mooc-ans/course/*
// @match        https://mooc1-1.chaoxing.com/mooc-ans/ztnodedetailcontroller/visitnodedetail*
// @match        https://mooc1-1.chaoxing.com/mooc-ans/zt/*
// @icon         https://tju.edu.cn/favicon.ico
// @grant        none
// ==/UserScript==

(function () {
    'use strict';

    // Your code here...
    // await new Promise((resolve, reject) => {
    //     setTimeout(resolve, 1000);
    // });
    console.log('injected');

    function startScroll(duration){
        // $('html,body').animate({ scrollTop: 0 }, 50);
        const maxScroll = $(document).height() - $(window).height();
        console.log(maxScroll, duration);
        if (maxScroll <= 0) return;
        $('html,body').animate({ scrollTop: maxScroll }, duration * 60 * 1000);
    }

    const block = document.createElement("div");
    block.style.position = 'fixed';
    block.style.top = '20px';
    block.style.right = '20px';
    const inp = document.createElement("input");
    inp.placeholder = "时长（分钟）";
    inp.defaultValue = 1;
    const b = document.createElement("button");
    b.innerText = "开始滚动";
    b.onclick = ()=>{
        startScroll(Number(inp.value));
    }
    block.appendChild(inp);
    block.appendChild(b);
    document.body.appendChild(block);
})();
```
