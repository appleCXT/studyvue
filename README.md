## vue项目启动配置
下载nodejs进行安装<br/>
修改安装插件的默认路径：<br/>
未更改默认路径，nodejs会将插件安装在【C:\Users\用户名\AppData\Roaming\npm】所以要更改到自己的安装路径下。先在自己的安装目录的nodejs下新建两个文件夹node_cache和node_global。之后cmd中运行<br/>
...npm config set prefix "D:\Develop\nodejs\node_global" <br/>
...npm config set cache "D:\Develop\nodejs\node_cache"<br/>
然后在环境变量中的系统变量中新建【NODE_PATH】，输入【D:\Develop\nodejs\node_global\node_modules】<br/>
将用户变量中的path修改为【D:\Develop\nodejs\node_global】即可，以后在cmd中运行-global均是在自己的安装路径下进行的<br/>

---------------------------------这时npm可以使用了-------------------------<br/>
<br/>
之后在cmd中检查node是否安装好：node -v<br/>
检查npm是否安装好:npm -v<br/>
安装vue<br/>
npm install vue<br/>
安装所有引用的包<br/>
npm install<br/>
安装vue-cli脚手架<br/>
npm install --global vue-cli<br/>
创建一个基于webpack模板的新项目<br/>
vue init webpack project<br/>
cd project //路径转到这个项目所在的文件夹目录<br/>
npm run dev //运行配置文件package.json<br/>
<br/>
---------------------------------------------------<br/>
如果要运行一个已经写好的代码，之前要先进行模块的安装<br/>
npm install vue //安装vue<br/>
npm install //安装package.json中需要的模块<br/>
npm run dev //运行配置文件<br/>

## vuex
### modules
* 参考资料https://segmentfault.com/a/1190000009133424 https://vuex.vuejs.org/zh-cn/modules.html
* store中当项目比较复杂，status比较多的时候，这时可以在store中应用module模块。每个module中有自己的state,mutation,action,getter。
```
const moduleA = {
  state: { ... },
  mutations: { ... },
  actions: { ... },
  getters: { ... }
}

const moduleB = {
  state: { ... },
  mutations: { ... },
  actions: { ... }
}

const store = new Vuex.Store({
  modules: {
    a: moduleA,
    b: moduleB
  }
})
//模块内部的数据：①内部state，模块内部的state是局部的，也就是模块私有的，比如是car.js模块state中的list数据，我们要通过this.$store.state.car.list获取；②内部getter、mutation和action，仍然注册在全局命名空间内，这是为了多模块可以同时响应同一mutation；this.$store.state.car.carGetter的结结果是undefined，而通过this.$store.state.carGetter则可以拿到。
传参：getters====({state(局部状态),getters（全局getters对象）,roosState（根状态）})；actions====({state(局部状态),commit,roosState（根状态）}).
```
