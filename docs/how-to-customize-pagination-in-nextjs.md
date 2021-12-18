# 如何在 NextJS 中自定义分页？

> 原文:[https://www . geesforgeks . org/how-customize-paging-in-next js/](https://www.geeksforgeeks.org/how-to-customize-pagination-in-nextjs/)

在本文中，我们将学习如何使用 Algolia 在 NextJS 项目中添加自定义分页。NextJS 是一个基于 React 的框架。它有能力为不同的平台开发漂亮的网络应用程序，如视窗、Linux 和 mac。动态路径的链接有助于有条件地呈现您的 NextJS 组件。

**方法:**首先添加我们定制的分页，我们将在 algolia 创建一个帐户，使我们能够在几毫秒内搜索内容。之后，我们将获得我们稍后将在应用程序中使用的应用编程接口密钥。然后我们将创建一个新的索引来上传我们的数据。在我们应用的主页上，我们将使用 API 键和 algoliasearch 模块从 algolia 获取数据。然后我们将创建我们定制的分页。

**创建下一个应用程序:**

**步骤 1:** 您可以使用以下命令创建一个新的 NextJs 项目:

```html
npx create-next-app gfg
```

**步骤 2:** 为了在我们的项目中添加 Algolia 搜索，我们将安装两个模块:

```html
npm install algoliasearch react-instantsearch-dom @material-ui/core @material-ui/lab
```

**项目结构:**如下图。

![](img/59db8514a2593194eef2873c24e0eba1.png)

**步骤 3:** 设置 Algolia。Algolia 使开发人员能够构建下一代应用程序，这些应用程序的 API 可以在几毫秒内提供相关内容。所以要使用 algolia，首先创建一个免费账户，并获取该账户的 API 密钥。

1.获取应用编程接口密钥转到**设置** > **应用编程接口密钥**

![](img/f47ca5cc432d1357112afc3f3b73c653.png)

2.之后，创建一个索引并上传您想要搜索的数据。您可以以 json、csv 格式或使用它们的 API 上传数据。

![](img/1f05623cb973df44bb907dffbfc3856f.png)

对于这个例子，我正在上传下面的数据。

```html
Title, Tag, Day
GFG1, python, Monday
GFG2, java, Tuesday
GFG3, css, Wednesday
GFG4, html, Thursday
GFG5, react, Friday
GFG6, nextjs, Saturday
```

![](img/1bf279b36b69bb473fa77f735eb344c0.png)

**第 4 步:**现在我们将为我们的应用程序创建自定义分页。为此，我们将在一个新的组件文件夹中创建一个包含以下内容的新文件。

## java 描述语言

```html
import React from 'react';
import { makeStyles } from '@material-ui/core/styles';
import Pagination from '@material-ui/lab/Pagination';
import { connectPagination } from 'react-instantsearch-dom';

const useStyles = makeStyles((theme) => ({
  root: {
    '& > *': {
      marginTop: theme.spacing(2),
    },

  },

}))

function Pagin({ currentRefinement, 
    nbPages, refine, createURL }) {
  const classes = useStyles();
  const handleChange = (event, value) => {
    event.preventDefault();
    refine(value);
  };

  return (
    <div className={classes.root} >
      <Pagination count={nbPages} shape="rounded" 
        onChange={handleChange} />

    </div>

  );
}

export default connectPagination(Pagin);
```

**第五步:**现在我们可以使用 API 在 NextJs Project 中添加自定义分页了。之后，为了使用我们定制的分页，我们将在 index.js 文件中添加下面的代码。

## java 描述语言

```html
// Importing modules
import algoliasearch from "algoliasearch/lite";
import { InstantSearch, Hits, Configure }
         from "react-instantsearch-dom";
import Pagination from "../components/CustomPagination";

const searchClient = algoliasearch(
  APPLICATION_API_KEY,
  SEARCH_ONLY_API_KEY,
);

export default function CustomizedFilter() {
  return (
    <>
      <InstantSearch 
        searchClient={searchClient} 
        indexName="gfg_dev">

        <Configure hitsPerPage={3}/>
        {/* Adding Data */}
        <Hits />
        {/* Adding Pagination */}
        <Pagination totalPages={5}/>
      </InstantSearch>
    </>
  );
}
```

您也可以在我们定制的分页中使用 CSS 添加样式。

**运行应用的步骤:**在终端使用下面的命令运行应用。

```html
npm run dev
```

### 输出:

![](img/d25202f455a13d7d4c06b54b2454d510.png)