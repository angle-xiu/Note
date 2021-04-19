# this绑定的优先级
+ 默认绑定的优先级在四条规则中最低。
+ 显示绑定和隐式绑定谁的优先级会更高？
```
function foo() { console.log( this.a );
}
var obj1 = { a: 2,
foo: foo };
var obj2 = { a: 3,
foo: foo };
obj1.foo(); // 2 obj2.foo(); // 3
obj1.foo.call( obj2 ); // 3 obj2.foo.call( obj1 ); // 2
```
通过以上代码可以发现`显式绑定优先级高于隐式绑定`。
+ 那么隐式绑定和new绑定谁的优先级会高？
```
function foo(something){
    this.a = something;
}
var obj1 = {
    foo : foo
}
obj1.foo(2);
console.log(obj1.a);//2
var bar = new obj1.foo(3);
console.log(bar.a);//3
```
通过以上代码可以发现`new绑定优先级会高于隐式绑定`
+ new绑定优先级高于显式绑定（这个不大好理解，所以没解释）

+ 所以`new绑定>显式绑定>隐式绑定>默认绑定`

