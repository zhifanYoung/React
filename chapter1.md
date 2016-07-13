
# React
1.工具：
    1. nvm, node.js 工具，可以下载，切换版本
    2. npm, node 包管理工具
    3. Homebrew, MacOs 软件下载，卸载工具
    4. watchman, 监视文件并记录文件的改动
    5. flow, 捕获JavaScript程序运行之前的常见错误

2.组件
    * 组件，即被独立封装的可复用 UI 部件。组件也是 React 的核心思想之一
    * React 为每个组件都提供一个 render 方法，这个方法返回组件的实例，用来渲染实际component可视部分
    * 组件有两个重要的概念： props 和 state ，他们的作用都是用于描述组件的状态
      * props 是组件对外交互的接口，是一种父级向子级传递数据的方式
      * state 用于记录组件的不同状态， React 把组件看成是一个状态机，通过与用户的交互，实现不同状态，然后重新渲染组件，让UI界面及时有效地随数据变化而变化
      * setState 其作用就是用于触发UI更新
3.布局 
    * React Native严重依赖[flexbox布局元素](http://www.ruanyifeng.com/blog/2015/07/flex-grammar.html)，弹性布局
    * 容器默认存在两根轴：水平的主轴（main axis）和垂直的交叉轴（cross axis）。主轴的开始位置（与边框的交叉点）叫做main start，结束位置叫做main end；交叉轴的开始位置叫做cross start，结束位置叫做cross end。项目默认沿主轴排列。单个项目占据的主轴空间叫做main size，占据的交叉轴空间叫做cross size
      * ![](http://www.ruanyifeng.com/blogimg/asset/2015/bg2015071004.png)
     1. 容器属性
       * flex-direction
         * 属性决定主轴的方向（即项目的排列方向） 
            *```.box {
            flex-direction: row | row-reverse | column | column-reverse;
            }```
           *  row（默认值）：主轴为水平方向，起点在左端。
           *  row-reverse：主轴为水平方向，起点在右端。
           *  column：主轴为垂直方向，起点在上沿。
           *  column-reverse：主轴为垂直方向，起点在下沿。
       * flex-wrap
         * 默认情况下，项目都排在一条线（又称"轴线"）上。flex-wrap属性定义，如果一条轴线排不下，如何换行。
           * ```.box{
          flex-wrap: nowrap | wrap | wrap-reverse;
          }```
          * nowrap（默认）：不换行。
          * wrap：换行，第一行在上方。
          * wrap-reverse：换行，第一行在下方。
       * flex-flow
         * flex-flow属性是flex-direction属性和flex-wrap属性的简写形式，默认值为row nowrap
           * ```.box {
          flex-flow: <flex-direction> || <flex-wrap>;
          }```
       * justify-content
         * justify-content属性定义了项目在主轴上的对齐方式。
           * ```.box {
            justify-content: flex-start | flex-end | center | space-between | space-around;
      }```
          * flex-start（默认值）：左对齐
          * flex-end：右对齐
          * center： 居中
          * space-between：两端对齐，项目之间的间隔都相等。
          * space-around：每个项目两侧的间隔相等。所以，项目之间的间隔比项目与边框的间隔大一倍。
       * align-items
         * align-items属性定义项目在交叉轴上如何对齐。
           * ```.box {
            align-items: flex-start | flex-end | center | baseline | stretch;
          }```
          * flex-start：交叉轴的起点对齐。
          * flex-end：交叉轴的终点对齐。
          * center：交叉轴的中点对齐。
          * baseline: 项目的第一行文字的基线对齐。
          * stretch（默认值）：如果项目未设置高度或设为auto，将占满整个容器的高度。
       * align-content
         * align-content属性定义了多根轴线的对齐方式。如果项目只有一根轴线，该属性不起作用。
           * ```.box {
            align-content: flex-start | flex-end | center | space-between | space-around | stretch;
          }```
           * flex-start：与交叉轴的起点对齐。
           * flex-end：与交叉轴的终点对齐。
           * center：与交叉轴的中点对齐。
           * space-between：与交叉轴两端对齐，轴线之间的间隔平均分布。
           * space-around：每根轴线两侧的间隔都相等。所以，轴线之间的间隔比轴线与边框的间隔大一倍。
           * stretch（默认值）：轴线占满整个交叉轴。
    2. 项目属性 6 个
      * order
        * order属性定义项目的排列顺序。数值越小，排列越靠前，默认为0。
        * ```.item {
          order: <integer>;
        }```
      * flex-grow
        * flex-grow属性定义项目的放大比例，默认为0，即如果存在剩余空间，也不放大。
        * ```.item {
          flex-grow: <number>; /* default 0 */
        }```
      * flex-shrink
        * flex-shrink属性定义了项目的缩小比例，默认为1，即如果空间不足，该项目将缩小。
        * ```.item {
          flex-shrink: <number>; /* default 1 */
        }```
      * flex-basis
        * flex-basis属性定义了在分配多余空间之前，项目占据的主轴空间（main size）。浏览器根据这个属性，计算主轴是否有多余空间。它的默认值为auto，即项目的本来大小
        * ```.item {
          flex-basis: <length> | auto; /* default auto */
        }```
      * flex
        * flex属性是flex-grow, flex-shrink 和 flex-basis的简写，默认值为0 1 auto
        * ```.item {
          flex: none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]
        }```
      * align-self
        * align-self属性允许单个项目有与其他项目不一样的对齐方式，可覆盖align-items属性。默认值为auto，表示继承父元素的align-items属性，如果没有父元素，则等同于stretch
        * ```.item {
          align-self: auto | flex-start | flex-end | center | baseline | stretch;
        }```
        
  4.生命周期函数:
    * componentWillMount。这个函数只有在组件首次渲染时才会触发，在React中，设置this.state会导致重新渲染，但是componentWillMount设置this.state并不会对导致render调用多次
    * componentDidMount。在渲染结束后，调用一次。
    * componentWillReceiveProps。在component接收到新的参数前调用，在这个方法中调用this.setState不会触发二次渲染，第一次渲染的时候不会调用这个方法
    * shouldComponentUpdate。在每次重新触发渲染之前调用，其中nextProps和nextState分别对应下一个状态的参数和状态对象。可以在这个方法中返回false来取消本次渲染。 
    * componentWillUpdate。在重新渲染之前调用 Warning：这个方法里不能调用this.setState()否则会陷入死循环
    * componentDidUpdate。在渲染之后调用
    * componentWillUnmount。在被删除之前调用

  
  5.扩展运算符用三个点号表示，功能是把数组或类数组对象展开成一系列用逗号隔开的值 传统写法：foo(arr[0], arr[1], arr[2]); ----> foo(...arr);

  6.箭头函数 ```var a3 = a.map( (s) => s.length );```  (s)用来描述参数，=>后的表示方法的执行体。学过Swift的童鞋，会发现和Swift的必包很像

  7.JS中的对象的属性可以不先声明，而在运行时候动态添加；所以，在React Native中，写代码的时候，存储数据直接this.propertyName ＝即可

      

   
