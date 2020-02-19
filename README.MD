# 所需工具
  - Chrome
  - Charles
# 流程
使用Chrome打开网站 https://mobile.yangkeduo.com 依次点击 **个人中心** -> **手机登录**<br> 
按F12打开调试窗口选择手机版进行调试，首先我们点开Sources查看网站所有的资源信息<br> 
在static.yangkeduo.com/assets/js 文件夹下查看所有引用的js文件。总共四个<br> 
我们重点关注下react_login这个js文件<br> 
点开react_login 这个js文件，并点击左下角的 **{}** 对js文件进行格式化<br> 
# 解密
重点关注下 **function jt()** 这个函数是在个人中心手机登录界面加载的时候进行调用。主要完成参数信息的初始化, 比如 **jt()** <br> 
函数中调用的函数**e[h("0x115", "43d3")** 函数是用获取界面加载完毕之后的时间信息更新到变量 **G** 中,同样 **jt()** 函数中还有有调用<br>
function yt(t) {<br>
    l[U](t),<br>
    l[h("0xca", "LYQ!")](),<br>
    [lt, ht, dt, wt, pt, gt, mt, xt, _t, bt, ut, st][B](function(t) {<br>
    t[U]()<br>
    })<br>
    }<br>
这个函数主要是对参数信息的初始化，比如将网站的访问链接和端口等信息初始化到对应的变量的data中供下面Ot()函数进行调用。当点击发送验证码时就<br>
会调用如下函数<br>
jt[h("0x11d", "LYQ!")][h("0x11e", "Ca4X")] = function() {<br>
              var t = {};<br>
              return t[h("0x11f", "Sdwk")] = function(t) {<br>
                  return t()<br>
              }<br>
              ,<br>
              t[h("0x120", "J7u(")](Ot)<br>
          }<br>
观察此函数，最主要的是最后一行 t[h("0x120", "J7u(")](Ot) <br>
这个函数的作用是调用函数 Ot()<br>
所以确定登录参数screen_token 的值来源于函数Ot()
                
    
  
