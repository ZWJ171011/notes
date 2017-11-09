1. react 运行原理
*2. 声明 react 的组件
    继承了 React.Component 的类就是一个组件
    至少有一个 render 方法
        这个方法应该 return 一份 jsx 的对象,
        这就是这个组件的样子
*3. jsx 语法
    回去复习今天的 jsx 的语法 , 写到下面
    begin here...
        相邻的jsx 元素必须包含在一个闭合的标签里面
        自己声明的组件要大写开头, 内置组件小写开头
        jsx 本身可以是一个表达式
        在 jsx 里面使用 {} 表示表达式
        标签之间的内容就叫 children, 如果是类的组件的标签, 它的 children 通过实例(this)的 props.children 拿到
        关键词要转成另外一种形式 : class->className for->htmlFor, 应该是驼峰式的

4. 把 jsx 渲染到页面
    reactDOM.render
5. virtual DOM 的概念 怎么来的
6. this.props.children

7.webpack 打包 css 文件
    把 css 打包到 js 文件里面 , 一般是在开发阶段 css 的打包方式
    把 css 打包成一个单独的 css 文件, 通过 link 引入(自动创建) 生产阶段

8.关于 css-loader
    引入 css 文件的使用这个 loader 处理它
    遇到 url 或 @import 帮你去引入里面的资源, 引入资源的过程中, 更根据资源的类型再使用相应的 loader 去处理

9.关于 file-loader
    处理资源(字体, 图片, 视频)
    转换出一个路径, 把资源搬到输出目录


**************************************************************************************************10. props: react的属性
    传递属性: <Content a="8"></Content>
    拿到: this.props

****************************************************************************************************************************************************************************************************11. state
    组件有内部状态: this.state = {}
    通过 this.setState() 来改变组件的内部状态, 这个时候页面会更新, 因为组件的 render 执行了, 得到了一份新的 jsx 的结构
    父组件的 render 执行了, 子组件的 render 也会执行
    改变页面状态, 应该通过 setState 更新
    
    
    
    ## router
    
    Router
        browserHistoy
        hashHistory

    BrowserRouter
    HashRouter

关于浏览器的 history
    push push 一个新的 entry 到 history stack
    history stack
        所以的浏览记录都存放在这个 history stack 里面, 它就相当于一个数组
    entry
        每一个访问的页面(访问过的路径)

    点击一下 a 链接, 就是往历史堆里面放入一个地址

BrowserRouter
    使用 browserHistoy
    放到最顶层, 把其它的组件作为 children

Route
    path的属性: 如果地址匹配到了这个路径, 就会显示
    component属性: 接收一个组件变量
        会往组件里面传入3个 props: history, location, match
    不能嵌套元素


Link
    最后会被渲染成 a 链接
    to的属性: 跳转到哪里
    
    
 ##  传入的三个属性
    history
    location
        history 的 location 是可变的, 是实时的, 是不稳定的, 如果你想要 location, 直接读取此 location, 而不是从 history 里面去拿到
    match
NavLink
    activeStyle
    activeClassName
    exact
    其它和 Link一样

Redirect
    to 的属性, 如果他被渲染的时候, 会重定向到一个新的地方
        string 或 object
Switch
    一旦匹配到一个, 不再继续往下匹配

withRouter
    一个高阶组件, 接收一个组件作为参数(比如Aac), 然后导出一个组件, 这个时候 Aac 组件的 props 就有了那3个属性  