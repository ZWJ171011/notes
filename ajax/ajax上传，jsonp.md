浏览器的js，不能操作本地文件（增删改..）

        上传:
            传统的上传

    最大优点就是我们可以异步上传一个二进制文件.
        var f = new FormData();
        f.append(key,val);
        ajax.send(f);
        
    file控件中的数据是在<input type="file" id="f"> 的files[0]

    ajax.upload.onprogress
        进行监听数据上传进度的，只要后端收到一次数据就会调用这个函数，每次数据的细节信息都放在事件对象上

        ev.loaded    当前传输的进度
        ev.total     总大小    

## 跨域
    同源：
            同源策略：
                一种约定，它是浏览器最核心也最基本的安全功能，如果缺少了同源策略，则浏览器的正常功能可能都会受到影响。可以说Web是构建在同源策略基础之上的，浏览器只是针对同源策略的一种实现

            源：协议、端口、域名
            同源：同协议、端口、域名

            协议：
                http、https、file、ftp...
                http://localhost/2017-10-25/5_%E4%B8%8A%E4%BC%A02.html
                file:///C:/xampp/php/www/2017-10-25/6_%E8%B7%A8%E5%9F%9F.html

            端口:
                专门提供某项服务的"窗口"
                
            域名:IP的别名（方便记）
                www.baidu.com
                www.miaov.com

            跨域（跨源）
                不同协议、端口、域名

            
            解决跨域：
                通过 新版本的XMLHttpRequest  + 服务器开权限
                    'Access-Control-Allow-Origin:*'

                
                服务器代理：
                    服务器文件能访问别的域下的资源，如果服务器文件与自己的页面
                    是同源，我就能访问别的域下的资源了。

                iframe 

                jsonp
## jsonp
    jsonp = JSON + Padding

        函数名 + 括号  括号中带有数据
        fn([])
        fn({})

        ajax的数据是没有函数名的

        img src="xxx"
        link href = "xx"
        script src=""

        jsonp原理

            首先，jsonp数据格式是函数名+括号的

            然后，*全局*需要定义一个与后端函数名一致的函数

            最后，当需要数据的时候，创建一个script标签，进行请求，获取数据(按需加载)。

        需要数据的时候执行一个函数，函数内有想要的数据，提前约定好这个函数名，后端会把数据传到函数中，实现按需加载。    
        