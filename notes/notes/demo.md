APICloud 报 api is not defined
+ 原因：api对象调用时需放到函数里面进行调用。
+ 例如
```
self.login = function () {
// 参数是否为空
    if (!self.phone() && !self.code()) {
        $api.toast('手机号或验证码为空');
        return false;
        }
        api.toast({
            msg: 'hello'
        });
    }
```
+ 此时调用就不会报错。