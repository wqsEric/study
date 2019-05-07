# React 虚拟dom
#### 虚拟DOM
- 虚拟DOM的简单实现（diff算法）
- 虚拟DOM的内部工作原理
- React中的虚拟DOM与Vue中的虚拟DOM比较
#### 那么虚拟DOM和DOM之间的关系是什么呢？ 
- Virtual DOM并没有完全实现DOM，即虚拟DOM和真正地DOM是不一样的
- Virtual DOM最主要的还是保留了Element之间的层次关系和一些基本属性。
- 因为真实DOM实在是太复杂，一个空的Element都复杂得能让你崩溃，并且几乎所有内容我根本不关心好吗。所以Virtual DOM里每一个Element实际上只有几个属性，即最重要的，最为有用的，并且没有那么多乱七八糟的引用，比如一些注册的属性和函数啊，这些都是默认的，创建虚拟DOM进行diff的过程中大家都一致，是不需要进行比对的。
- 哪怕是直接把Virtual DOM删了，根据新传进来的数据重新创建一个新的Virtual DOM出来都非常非常非常快。（每一个component的render函数就是在做这个事情，给新的virtual dom提供input）。
#### 虚拟dom的简单实现
- 用JS对象模拟DOM树
- 比较两棵虚拟DOM树的差异
- 把差异应用到真正的DOM树上
#### 1、用JS对象模拟DOM树
- 首先我们要明白**真实的DOM元素是非常强大的**