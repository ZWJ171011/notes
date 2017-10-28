 localStorage 前端技术 ，
        作用：本地存储    
        据说 每个域名 5M

        localStorage.setItem();
        localStorage.getItem();
        localStorage.removeItem();
        localStorage.clear(); //清空

        生命周期：
            只要不清，永远在。

        onstorage :
            本域名、本浏览器，当兄弟页面操作了本地数据的时候触发。
            
            
cookie:
            其实是后端的技术，用来记录匹配后端的sessionID的
            从而保证用户只要在当前浏览器访问页面，登录信息不会
            被丢失。

        cookie是在服务器下运行的。

        前端使用一般用来数据存储（配合后端进行一些用户优化）

       设置cookie
            **每个域名**下一般就多少条（多少个、多少k）

            document.cookie = 'key=value';

        生命周期:
            默认的生命周期就是当前的浏览器彻底关闭，生命结束
        
            设置生命周期:            
            
            
            
            