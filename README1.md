<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title></title>
</head>
<body>

    <script>
       function is_weixin() {
            var ua = navigator.userAgent.toLowerCase();
            if (ua.match(/MicroMessenger/i) == "micromessenger") { //匹配微信
                return true;
            } else {
                return false;
            }
        }
        var isWeixin = is_weixin();
        var winHeight = typeof window.innerHeight != 'undefined' ? window.innerHeight : document.documentElement.clientHeight;
        function loadHtml(){
            var div = document.createElement('div');
            div.id = 'weixin-tip';
            div.innerHTML = '<p><img src="live_weixin.png" alt="在浏览器中打开"/></p>';
            document.body.appendChild(div);
        }
        
        function loadStyleText(cssText) {
            var style = document.createElement('style');
            style.rel = 'stylesheet';
            style.type = 'text/css';
            try {
                style.appendChild(document.createTextNode(cssText));
            } catch (e) {
                style.styleSheet.cssText = cssText; //ie9以下
            }
            var head=document.getElementsByTagName("head")[0]; //head标签之间加上style样式
            head.appendChild(style); 
        }
        var cssText = "#weixin-tip{position: fixed; left:0; top:0; background: rgba(0,0,0,0.8); filter:alpha(opacity=80); width: 100%; height:100%; z-index: 100;} #weixin-tip p{text-align: center; margin-top: 10%; padding:0 5%;} #weixin-tip img{width:100%;}";
         function toDownload(){ 
            var u = navigator.userAgent;
            var ua = u.toLowerCase();   
            if (/iphone|ipad|ipod/.test(ua)) {  // iOS 系统 ->  跳AppStore下载地址
                window.location.href = 'https://itunes.apple.com/cn/app/id1281932109'//根据发布的id地址书写
            } else if ( (/android/.test(ua))&&(!isWeixin)) { // 安卓系统 -> 跳安卓端下载地址
                window.location.href = 'https:下载地址'
            } else if((/android/.test(ua))&&(isWeixin)){
                loadHtml();
                loadStyleText(cssText);
            } else if (IsPC()){ // PC端
                 document.write("请在相关移动设备下载")
            }
        }
        function IsPC() {  兼容设备
            var userAgentInfo = navigator.userAgent;
            var Agents = ["Android", "iPhone",
                "SymbianOS", "Windows Phone",
                "iPad", "iPod"];
            var flag = true;
            for (var v = 0; v < Agents.length; v++) {
                if (userAgentInfo.indexOf(Agents[v]) > 0) {
                    flag = false;
                    break;
                }
            }
            return flag;
        }
       toDownload(); 
    </script>
</body>
</html>
