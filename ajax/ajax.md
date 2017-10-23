## AJAX：
            Asynchronous JavaScript and XML（异步JavaScript和XML)
            
       当下的数据格式不再只有XML了，还有JSON
            后端吐的所有的数据都是字符串。
            
            
    前后端的数据交互的。----> 获取数据        
    
    优点:
                可以提高系统性能，优化用户界面，基本不跳转
                
                
### 原理
        ajax的交互模型:
                1.创建一个ajax对象
                2.填写地址
                3.发送给服务器
                4.等待
                5.通话
                
 var ajax = new XMLHttpRequest; //创建一个ajax对象

        //填写地址。
        ajax.open('get','php/get.php?user='+userId.value,true);

        //发送给服务器
        ajax.send();
        
        //等待
        ajax.onload = function(){
            //通话
            console.log(ajax.responseText);
        }
    }                
                
                