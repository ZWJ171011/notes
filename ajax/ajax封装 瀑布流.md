ajax 封装
txt.onkeyup = function(){
        jsonp({
            // 'http://www.wookmark.com/api/json/popular',
            url:'https://sp0.baidu.com/5a1Fazu8AA54nxGko9WTAnF6hhy/su',
            data:{
                wd:txt.value
            },
            success:function(data){
                console.log(data);
            },
            cb:'cb'
        });
    }
    function jsonp(obj){//url,data,fn,cb
        let fnName = ('jquery'+(+new Date)+(Math.random())).replace('.','');
        let opt = {
            url:'',
            data:'',
            success:function(){},
            cb:'callback'
        }
        Object.assign(opt,obj);
        opt.data[opt.cb] = fnName;
        var arr = [];
        for(var attr in opt.data){
            arr.push(attr +'='+opt.data[attr]);
        }
        opt.data = arr.join('&');
        window[fnName] = function(obj){
            opt.success(obj);
        }
        let os = document.createElement('script');
        os.src = opt.url + '?' + opt.data; //+ '&' + opt.cb +'=' + fnName;
        document.getElementsByTagName('head')[0].append(os);
        os.remove();
    }


 //判断图片有没有，进了onload就有
    var img = document.createElement('img');
    img.src = "http:\/\/www.wookmark.com\/images\/thumbs\/661395_wookmark.jpg"

    img.onload = function(){
        alert('有');
    }
    img.onerror = function(){
        alert('没有');
    }    
    
    
    