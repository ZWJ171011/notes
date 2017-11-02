1. npm init -y //初始化 package.json
2. 安装依赖
    npm i -D <package包名> // 声明为开发依赖
    npm i -S <package> //声明为生产依赖

3. 新建 webpack.config.js 文件

4. 配置入口和出口, 接着运行

5. 根据报错提示, 添加 loader 配置,

6. 配置好 babel-loader 和 .babelrc

7. import {c as name} from './component/myName';

8. 在 package.json 里面配置好命令 : dev : "webpack" , 使用 npm run dev 运行
9. 


关于 .babelrc 这个配置文件
    干什么的,
    .babelrc是用来设置插件和预设的
    //babel API 的 配置选项 就是告诉babel在运行什么时候会被使用
    使用 babel 编译文件的时候，就会去查看 .babelrc ，根据babelrc 的配置来做相应的操作
    
    
    什么时候会被使用
        当插件和预设复杂且多的时候需要 把所有依赖的插件放在.babelrc中，统一管理；
    如何配置 预设和插件
	{
            "presets":[presetName,presetName], //预设 （是个插件的集合）
            "plugins":['插件名']   // 单独的插件
        }
        在webpack.config.js里面的module下rules下的use:["babel-loader"]
        
关于 babel
    干什么的
    	把能转成ES5的代码转成ES5代码
    	
    如何在 cli 使用
    	npm i -D babel-cli
    	
    如何在 webpack 使用
    	在package.json文件中的scripts里  babel 加上文件，npm run babel
    	.babelrc 里{
            "presets":[presetName,presetName], //预设 （是个插件的集合）
            "plugins":['插件名']   // 单独的插件
        }
    	
    基于什么运行的 (插件)
    	babel-core ,babel-loader;
    预设是什么 (插件的集合)
		把许多插件打包在一起  babel-preset-env(ES6插件集合), babel-preset-react （react插件集合）
		
关于 webpack 的
    干什么的
    	模块打包机，预处理模块：它做的事情是，分析你的项目结构，找到JavaScript模块以及其它的一些浏览器不能直接运行的拓展语言（Scss，TypeScript等），并将其打包为合适的格式以供浏览器使用。
    入口是什么意思, 如何配置
    wbpack打包的时候，通过一个JS文件可以找到其他需要引入的模块，而webpack可以通过这个入口可以找到所有需要引入的模块。
    
     entry: './src/app.js',
    
    输出是什么意思, 如何配置(文件名, 输出路径)
    webpack打包后会生成一个JS文件，而这个出口就是指这个JS文件需要存放的位置和文件名
    
    output: {
        filename: 'bba.js',
        path: path.resolve(__dirname, 'dist')
    },
    
    什么是 loader,
    loader是处理模块里的内容，如 兼容低版本浏览器的语法
    
    在什么情况下会让 loader 起作用
     下载loader的插件，并且在webpack的rules底下引用了这个loader。打包时就可以起作用
    //当某一个rule 被匹配到之后
    
    如何在 webpack 使用 babel-loader
     use:["babel-loader",...arg]//

关于 npm 的
    干什么用的
   	 包管理器，可以通过NPM下载各种插件，包，库。//管理项目的依赖
   	 
    关于package.json的文件
    
        如何生成
        npm init -y
        什么情况下会被使用
      	  需要插件项目装了什么插件的时候，还有通过npm i可以下载该文件下写有的插件
        //安装项目依赖 npm i，声明命令，查看项目依赖的时候
        
        
        *如何在里面声明命令
              	在package.json 底下的scripts创建一个健值对，通过npm run key指来调用声明的命令，例如: "dev":"webpack"
        
            在里面声明命令的好处
        	    可以快速运行复杂的命令行//很方便的描述出和本项目相关的命令操作
        	    
    如何安装依赖 (声明为生产还是开发)
			  npm i/ -D/--dave  packName （开发依赖）
              npm i -S/--save-dev packName (生产依赖)
关于模块化语法
    es6
        import 'f.js'
        //让这个模块运行，但不需要接收它暴露的接口
        
        import a from './ds.js'
        //引入模块的默认导出，让a的变量接收ds.js的默认导出
        
        import a,{b,c} from './ds.js'
        // 让a的变量接收ds.js的默认导出，b,c接收它的标准导出
        
        import a,{b as ccd,c} from './ds.js'
        //让a的变量接收ds.js的默认导出，接收它的标准导出 b，c，并且把b重命名成 ccd

        export         标准         
        export default 默认输出

    commonJS
        require('./a.js')  引入a模块
        
        module.exports
        //模块接收的是 module.exports的导出
        
        exports
        
        //exports=module.exports，传址
        // exports 初始默认指向 module.exports，如果这个指向被重新赋值，就会断掉和module.exports的联系，不能给exports赋值
