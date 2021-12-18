# Redux Toolkit 是什么，为什么更受青睐？

> 原文:[https://www . geesforgeks . org/what-is-redux-toolkit-and-why-it-more-preferred/](https://www.geeksforgeeks.org/what-is-redux-toolkit-and-why-it-is-more-preferred/)

当作为前端开发人员或全栈开发人员工作时，许多工程师遇到了 Redux。但是最近 Redux 团队推出了 Redux Toolkit，这是一个官方推荐的 SOPE 库，代表简单、固执、强大和有效的状态管理库。它允许我们编写更高效的代码，加快开发过程，并自动应用推荐的最佳实践。它的创建主要是为了解决 Redux 的三大问题:

*   配置 Redux 存储太复杂了
*   必须添加大量的包来构建大规模的应用程序
*   Redux 需要太多样板代码，这使得编写高效干净的代码变得很麻烦。

它还为 Redux Dev-tools Extension 和 immer.js 库提供了自动支持，immer . js 库是处理不可变对象的一个很好的工具。您还可以使用 Redux Toolkit 的各种预定义功能，这不仅加快了流程，还节省了时间。

Redux 工具包附带的依赖项:

*   总是（德语词）
*   回家的
*   redux-thunk
*   重新选

**安装:**

```html
# NPM
npm install @reduxjs/toolkit

# Yarn
yarn add @reduxjs/toolkit
```

**提供了哪些额外功能:**

*   一个 configureStore()函数，它为 Redux-thunk、Redux DevTools 扩展提供自动支持，并且还传递默认中间件。
*   一个 createReducer()实用程序，它为允许可变地编写不可变代码的 immer 库提供支持。
*   返回动作创建者函数的 createAction()实用程序。
*   一个 createSlice()函数，用一个函数代替 create action 和 create Reducer 函数非常方便。
*   一个 createAsyncThunk()，它以 Redux 字符串作为参数，并返回一个 Promise。
*   一个帮助执行 CRUD 操作的 createEntityAdapter()实用程序。

**Redux 和 Redux 工具包的基本比较(带 React):**

1.  **还原**:创建存储和还原器。

    ## java 描述语言

    ```html
    const addHandler=(state=0,action)=>{
    if(action.type==='ADD')
    {
        return state+1;
    }
    return state;
    }

    const store = createStore(addHandler);

    store.dispatch({type:'ADD'});
    ```

2.  **Redux 工具包:**创建商店和减速器。

    ## java 描述语言

    ```html
    // Action Creators
    const add = createAction('ADD'); 

    const addHandler = createReducer(0, {  
      [add]: state => state + 1
    })

    const store = configureStore({
      reducer: addHandler
    })

    store.dispatch(add());
    ```

**使用 Redux 开发工具扩展:**

1.  **反应:**你必须在创建存储时添加一个预定义的语句来访问 Redux DevTools。

    ## java 描述语言

    ```html
    const store = createStore(
      reducer,   window.__REDUX_DEVTOOLS_EXTENSION__ && 
                 window.__REDUX_DEVTOOLS_EXTENSION__()
    );
    ```