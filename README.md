# client.navigator.useragent.js
JS通过navigator.userAgent判定设备信息

使用方式：

<pre><code>Client.isMobile()</code></pre>
--返回Boolen类型

<pre><code>
/**
 * JS通过navigator.userAgent判定设备信息
 * @datetime 20160901
 * @author fly(finfinity8@gmail.com) 
 */
var client_info = navigator.userAgent.toLowerCase();
var Client = {
    /*判断移动设备类型*/
    isMobile: function () {
        return !!client_info.match(/ipad|iphone|android|blackberry|windows phone|webos/i);
    },
    isiOS: function () {
        return !!client_info.match(/iphone|ipad|ipod/i);
    },
    isiPhone: function () {
        return !!client_info.match(/iphone/i);
    },
    isiPad: function () {
        return !!client_info.match(/ipad/i);
    },
    isiPod: function () {
        return !!client_info.match(/ipod/i);
    },
    isAndroid: function () {
        return !!client_info.match(/android/i);
    },
    isBlackBerry: function () {
        return !!client_info.match(/blackberry/i);
    },
    isOpera: function () {
        return !!client_info.match(/opera mini/i);
    },
    isWPhone: function () {
        return !!client_info.match(/iemobile/i);
    },

    /*判断浏览器类型*/
    isFirefox: function () {
        return !!(client_info.indexOf('firefox') > -1);
    },
    isChrome: function () {
        return !!(client_info.indexOf('chrome') > -1);
    },
    isIE11: function () {
        return !!(client_info.indexOf('trident') > -1 && client_info.indexOf('rv:11') > -1);
    },
    isIE10_X: function () {
        return !!(client_info.indexOf('msie') > -1);
    },
    isIE: function () {
        return !!(client_info.indexOf('trident') > -1 && client_info.indexOf('rv:11') > -1) || !!(client_info.indexOf('msie') > -1);
    },
    isOpera: function () {
        return !!(client_info.indexOf('opera') > -1);
    },
    isChrome: function () {
        return !!(client_info.indexOf('chrome') > -1);
    },
    /*判断是否为微信浏览器*/
    isWeChat: function () {
        return !!client_info.match(/MicroMessenger/i);
    }
};
</code></pre>

PS

一、微信的http user-agent(关键词MicroMessenger)

1. Iphone(苹果)平台微信的ucweb的useragent：
Mozilla/5.0 (iPhone; CPU iPhone OS 5_1 like Mac OS X) AppleWebKit/534.46 (KHTML, like Gecko) Mobile/9B176 MicroMessenger/4.3.2


2. Android(安卓)平台微信的ucweb的useragent：1
Mozilla/5.0 (Linux; U; Android 2.3.6; zh-cn; GT-S5660 Build/GINGERBREAD) AppleWebKit/533.1 (KHTML, like Gecko) Version/4.0 Mobile Safari/533.1 MicroMessenger/4.5.255


二、UC浏览器的http user-agent(关键词UCWEB)

1. android平台:
android平台ucweb急速模式开启下ucweb浏览器useragent： 
UCWEB/2.0 (Linux; U; Adr 2.3; zh-CN; MI-ONEPlus) U2/1.0.0 UCBrowser/8.6.0.199 U2/1.0.0 Mobile

android平台ucweb急速模式关闭状态下的http_user_agent:
Mozilla/5.0 (Linux; U; Android 2.3; zh-CN; MI-ONEPlus) AppleWebKit/534.13 (KHTML, like Gecko) UCBrowser/8.6.0.199 U3/0.8.0 Mobile Safari/534.13 

2. iPhone 平台

iPhone 平台极速模式开启状态下ucweb浏览器useragent： 
UCWEB/2.0 (iOS; U; iPh OS 4_3_2; zh-CN; iPh4) U2/1.0.0 UCBrowser/8.6.0.199 U2/1.0.0 Mobile 

iPhone 平台极速模式关闭状态下 UA 示例如下：（OBUA 为自带浏览器 UA）\
OBUA UCBrowser/8.6.0.199 Mobile

3. iPad 平台
ipad平台下ucweb浏览器useragent：
Mozilla/5.0 (iPad; U; CPU OS 6_0 like Mac OS X; zh-CN; iPad2) AppleWebKit/534.13 (KHTML, like Gecko) UCBrowser/8.6.0.199 U3/0.8.0 Safari/534.13 

4. windows Phone平台
WP平台下ucweb浏览器useragent：
WP平台极速模式开启状态下：（以 Nokia 900 为例）
UCWEB/2.0 (Windows; U; wds7.10; zh-CN; Nokia 900) U2/1.0.0 UCBrowser/8.6.0.199 U2/1.0.0 Mobile 

5. 诺基亚平台
诺基亚手机Symbian&Java平台ucweb浏览器useragen：
Nokia 5800 XpressMusic/UCWEB8.9.0.253/50/999 

安卓QQ浏览器HD版检测的结果是：mac， Safari，这个很是变态，自己看着处理吧

3个检测浏览器User-Agent信息的网站

三、一些特别的浏览器
QQ浏览器(android)
MQQBrowser/3.6/Adr (Linux; U; 4.0.3; zh-cn; HUAWEI U8818 Build/U8818V100R001C17B926;480*800)

魅族UC浏览器(android)
JUC (Linux; U; 2.3.5; zh-cn; MEIZU MX; 640*960) UCWEB8.5.1.179/145/33232

UC浏览器(iphone)
IUC(U;iOS 5.1;Zh-cn;320*480;)/UCWEB8.8.0.212/42/997

Opera mobile(android)
Opera/9.80 (Android 4.0.3; Linux; Opera Mobi/ADR-1210241554) Presto/2.11.355 Version/12.10

Opera mini(iphone)
Opera/9.80 (iPhone; Opera Mini/7.0.5/28.2690; U; zh) Presto/2.8.119 Version/11.10
