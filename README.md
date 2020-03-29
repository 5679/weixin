<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8" />
<title>请用内置浏览器打开</title>

<style type="text/css">
#weixin-tip {
    position: fixed;
    left: 0;
    top: 0;
    background: rgba(0, 0, 0, 0.8);
    filter: alpha(opacity = 80);
    width: 100%;
    height: 100%;
    z-index: 100;
}

#weixin-tip p {
    text-align: center;
    margin-top: 10%;
    padding: 0 5%;
}
</style>

</head>

<body>
    <div id="weixin_tip" style="width: 100%; height: 100%;">
        <p>
            <img src="/weixin.jpg" alt="微信打开" style="width: 100%; height: 100%;" />
        </p>
    </div>
</body>

<script type="text/javascript">
    function is_weixin() {
        var ua = navigator.userAgent.toLowerCase();
        if (ua.match(/MicroMessenger/i) == "micromessenger") {
            return true;
        } else {
            return false;
        }
    }

    // 微信内置浏览器打开，只是显示遮罩层，其他浏览器进行连接跳转
    if (is_weixin()) {
        document.getElementById("weixin_tip").style.display="block";
    } else {
        document.getElementById("weixin_tip").style.display="none";
        window.location.href = "https://baidu.com";
    }
</script>
</html>
