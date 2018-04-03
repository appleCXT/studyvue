## studyvue
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
如果要运行一个已经写好的代码，之前要先进行模块的安装
npm install vue //安装vue
npm install //安装package.json中需要的模块
npm run dev //运行配置文件
