# app模版
```
<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8">
    <meta name="viewport"
        content="maximum-scale=1.0,minimum-scale=1.0,user-scalable=0,width=device-width,initial-scale=1.0" />
    <title>userindex</title>
    <link rel="stylesheet" type="text/css" href="../../css/api.css" />
    <link rel="stylesheet" type="text/css" href="../../css/lib.css" />
    <style>
        /* common */
        html,
        body {
            color: #ffffff;
        }

        ul li {
            list-style: none;
        }
        .icon {
            background-size: 100% 100%;
            border-radius: 50%;
            background-color: #ffffff;
        }

        .ui-nowrap {
            white-space: nowrap;
        }
        }

        .container {

        }
            </style>
</head>

<body id="wrap">
    <header></header>
    <section>
        <div class="container ui-font-size12 ui-column ui-flex-nowrap ui-bold">
        </div>
    </section>
    <footer></footer>
</body>
<script type="text/javascript" src="../../script/api.js"></script>
<script type="text/javascript" src="../../script/knockout.js"></script>
<script type="text/javascript" src="../../script/lib.js"></script>
<script type="text/javascript">
    apiready = function () {
        //适配ios7+
        var header = $api.dom('header');
        var footer = $api.dom('footer');
        var headerH = $api.fixStatusBar(header);
        var footerH = $api.fixTabBar(footer);
        console.log(headerH + footerH);
        $api.css($api.dom('.container'), 'height:calc(100vh - ' + (headerH + footerH) + 'px)');
        // 监听回退键
        api.addEventListener({
            name: 'keyback'
        }, function (ret) {
            api.closeWin();
        });
        //初始化
        init();
    };
    var viewModel = function () {
        var self = this;
        self.tool = function () {
            return $lib.tool();
        }
    }
    var vm = new viewModel();
    ko.applyBindings(vm, $api.dom('#wrap'));

    function init() {

    }
</script>

</html>
```