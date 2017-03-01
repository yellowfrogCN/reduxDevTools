# reduxDevTools
优雅到哭的Redux DevTools应用
------------------------------------------------------------------------------------------------------
## 预览 ##

* 概览

<p align="center">
    <img src="./src/state.avi" alt="截频演示" width="100%">
</p>

使用方法
------------------------------------------------------------------------------------------------------
```jsx
import thunk from 'redux-thunk' // redux-thunk 支持 dispatch function，并且可以异步调用它
import createLogger from 'redux-logger' // 利用redux-logger打印日志
import { createStore, applyMiddleware } from 'redux'; // 引入redux createStore、中间件及compose 
import reducer from '../reducers';// 引入reducers集合

//引入redux-devtools-extension的可视化工具（有点吊）
import { composeWithDevTools } from 'redux-devtools-extension';//devToolsEnhancer,

// 调用日志打印方法 collapsed是让action折叠，看着舒服点
const loggerMiddleware = createLogger({collapsed:true});

// 创建一个中间件集合
const middleware = [thunk, loggerMiddleware];

//创建store
const store = createStore(
    reducer,
    composeWithDevTools(
        applyMiddleware(...middleware)
    )
);

export default store;
```
## API
---------------------------------------------------------------------------------------------------------


