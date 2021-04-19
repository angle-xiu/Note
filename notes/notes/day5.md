
[文章](https://juejin.cn/post/6844903512845860872#heading-4)
```
console.log('1');

setTimeout(function() {
    console.log('2');
    process.nextTick(function() {
        console.log('3');
    })
    new Promise(function(resolve) {
        console.log('4');
        resolve();
    }).then(function() {
        console.log('5')
    })
})
process.nextTick(function() {
    console.log('6');
})
new Promise(function(resolve) {
    console.log('7');
    resolve();
}).then(function() {
    console.log('8')
})

setTimeout(function() {
    console.log('9');
    process.nextTick(function() {
        console.log('10');
    })
    new Promise(function(resolve) {
        console.log('11');
        resolve();
    }).then(function() {
        console.log('12')
    })
})

```
+ 整体代码作为一个宏任务进入，开始第一个循环
+ 执行同步  //1
+ stime1 放入宏任务队列任务
+ process.nextTick ，process1进入微任务队列，
+ new promise 立即执行 //7
+ then1放入微任务队列
+ stime2 放入入宏任务队列
+ 完成第一个宏任务（整体代码script）
+ 执行微任务process1 then1 //6  8
+ 结束第一次循环，开始第二次循环，执行宏任务stime1，//2 
+ process2放入微队列中
+ new promise //4
+ 添加微任务then2
+ 执行微任务process2  then2 结束第二次循环  // 3  5
+ 执行宏任务stime2  // 9
+ 新增微任务process3  
+ new promise  //11
+ 添加微任务then3
+ 执行process3 then3  结束第三次循环 // 10  12
所以输出结果`1 7 6 8 2 4  3 5 9 11 10 12`