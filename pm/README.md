# 监控
前端应用监控，通过采集应用数据，一是为应用后期提供分析数据，二是在应用发生错误或crash及时向开发人员报警。<br/>
主要分两种
- 性能监控
- 错误监控

当然，也可以包括埋点

## 性能监控
#### 实现方式
- performance:[mdn](https://developer.mozilla.org/zh-CN/docs/Web/API/Performance)
#### 指标
- 白屏时间
- 首屏时间
- DOMReady时间
- 请求耗时
- 总下载时间
- dom加载时间

## 错误监控
错误一般分为两种：语法错误，运行时错误。

#### 捕捉
- window.onerror
- promise no reject:window.onunhandledrejection
#### 特殊处理
- Script error
- sourcemap:[参考](https://github.com/joeyguo/blog/issues/14)
## 埋点
- pv
- uv
- 点击
- 曝光