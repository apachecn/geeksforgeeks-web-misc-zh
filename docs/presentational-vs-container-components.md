# 表示性组件与容器组件

> Original: [https://www.geeksforgeeks.org/presentational-vs-container-components/](https://www.geeksforgeeks.org/presentational-vs-container-components/)

在 Reaction 中，构件分为两类：表现性构件和容器构件。 每一个都有自己的特点。 让我们详细看看这两个组件。
**表示成分**

*   主要关注事物的外观。
*   对应用程序的其余部分没有重大依赖关系。
*   与组件外部的数据规范无关。
*   主要通过道具专门接收数据和回调。
*   考虑到它包含 DOM 标记和它们自己的样式，它可能同时包含表示组件和容器组件。

**示例：**
例如，下面的代码表示一个表示组件，它从道具中获取数据，只关注显示元素。

```
// presentational component
const Users = props => 
      (<ul>   
         {props.users.map(user => 
            (<li>{itr}</li>    ))
         }
      </ul>)
```

**容器组件**

*   主要关注事物是如何工作的。
*   可以同时包含表示组件和容器组件，但没有自己的 DOM 和标记。
*   向表示组件或其他容器组件提供数据和行为。
*   调用流量动作，并将它们作为回调提供给表示组件。

```
// container component
classUsersContainerextendsReact.Component{constructor() 
   { 
    this.state = {   
       itr: []    
    }
  } 
 componentDidMount() {   
    axios.get('/users').then(itr=>this.setState({ users: itr}))    
    )  }
render() {
  return<Usersusers={this.state.itr} />  
  }}
```

最后，在结论中，我们可以简单地得出结论：表示组件**与外观**相关，容器组件**与事物工作**相关。