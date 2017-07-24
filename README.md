# F_BROWER

JS通过navigator.userAgent判定设备信息

使用方式：

引入脚本文件

信息挂在window上，直接读取F_BROWER对象

对象内包含{ browser: { NAME:VER ...}, os: { NAME:VER ...}, client: { NAME:VER ...}, enigne: { NAME:VER ...} }

参数名

browser：浏览器信息，已有的检测类型为IE、Edge、Chrome、FireFox、Safari、Opera、WeChat
os：操作系统信息，已有的检测类型为Windows、MacOS、IOS、Android、Linux、BlackBerry、Tablet，其中还有bit为操作系统的位数
client：平台信息，已有的检测类型为PC、iPhone、iPad、Android、Mobile、Pad
enigne：内核引擎，已有的检测类型为WebKit、Trident、Gecko、AppleWebKit

之后在需要判断的地方进行调用即可，例如判断浏览器是否为Chrome，即：F_BROWER.browser.Chrome，如果为Chrome则会返回对应的版本号，不是的话，为null
