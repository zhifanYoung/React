
# React
1.工具：
    1. nvm, node.js 工具，可以下载，切换版本
    2. npm, node 包管理工具
    3. Homebrew, MacOs 软件下载，卸载工具
    4. watchman, 监视文件并记录文件的改动
    5. flow, 捕获JavaScript程序运行之前的常见错误

2.组件
    * 组件，即被独立封装的可复用 UI 部件。组件也是 React 的核心思想之一
    * React 为每个组件都提供一个 render 方法，这个方法返回组件的实例
    * 组件有两个重要的概念： props 和 state ，他们的作用都是用于描述组件的状态
      * props 是组件对外交互的接口，是一种父级向子级传递数据的方式
      * state 用于记录组件的不同状态， React 把组件看成是一个状态机，通过与用户的交互，实现不同状态，然后重新渲染组件，让UI界面及时有效地随数据变化而变化
      * setState 其作用就是用于触发UI更新
3.布局
    * React Native严重依赖flexbox布局元素，弹性布局
    * 容器默认存在两根轴：水平的主轴（main axis）和垂直的交叉轴（cross axis）。主轴的开始位置（与边框的交叉点）叫做main start，结束位置叫做main end；交叉轴的开始位置叫做cross start，结束位置叫做cross end。项目默认沿主轴排列。单个项目占据的主轴空间叫做main size，占据的交叉轴空间叫做cross size
      * ![](http://www.ruanyifeng.com/blogimg/asset/2015/bg2015071004.png)


