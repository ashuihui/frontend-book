# ioc
## 背景

前端发展日新月异，越来越复杂，大型项目模块化是一种趋势，经历了 amd、cmd、es6 module 的发展，模块化基本得到解决；但内部模块间的依赖越来越复杂，模块间的 低复用性问题越来越突出，如果能处理好模块之间的相互依赖，就能有效的提高项目的开发效率和维护成本。<br/>
ioc 作为一种已经被实践证明过的设计模式,广泛应用于后端,可以用来减低模块之间的耦合度，现在前端也可以借鉴和采用，阿里的的 midway 框架就有 injection 专门实现 ioc。<br/>
建议阅读injection[官方文档](https://midwayjs.org/injection/guide.html)，是一个实现ioc非常漂亮的库
#### 概念：控制反转
三个准则：
-   高层次的模块不应该依赖于低层次的模块，它们都应该依赖于抽象
-   抽象不应该依赖于具体实现，具体实现应该依赖于抽象
-   面向接口编程 而不要面向实现编程

#### 要点
- 模块解耦，模块实现单一功能
- 模块接口暴露api，api需薄，api命名需易读，内部实现需可维护

#### 实现方案
es6规范：reflect-metadata

#### demo
```javascript
import 'reflect-metadata';

function Role(name: string): ClassDecorator {
  return target => {
    Reflect.defineMetadata('role', name, target);
  };
}

@Role('admin')
class Post {}

const metadata = Reflect.getMetadata('role', Post);

console.log(metadata);
```