# 什么是 API？它在网络开发中有什么用？

> 原文:[https://www . geesforgeks . org/什么是 API-web 开发中的有用方法/](https://www.geeksforgeeks.org/what-is-api-how-it-is-useful-in-web-development/)

**API** 代表应用程序编程接口(所有交互性的主要参与者)
它就像一个信使，将我们的请求带到一个系统，并通过无缝连接将响应返回给我们。
我们在很多情况下使用 API，比如为一个 web 应用程序获取数据，或者连接到一个远程服务器，该服务器拥有天气等不断变化的数据，或者使两个应用程序能够相互交换数据。
应用编程接口不仅提供代码的可重用性，而且使用抽象的概念(通过隐藏复杂性来显示功能)。
**API 概念在现实生活中最常见的用法包括:**

*   餐馆里的服务员把你点的菜拿给厨师，并把你点的菜拿回来
*   只需按一下按钮，配电盘就会关闭筒灯
*   从 MMT(基于网络)等网站在线预订航班
*   从脸书账户注册购物网站(基于网络)

**不同的 API 会有不同的沟通方式:**

*   **XML-RCP/SOAP:** 两者都使用 XML
*   **JavaScript:** 围绕 JavaScript 展开
*   **RESTful API:**使用 HTTP 协议(超文本传输协议)(最适合 web APIs)

**API 在网络开发中的主要特性**
API 可以用于混搭，即来自一个站点的信息可以与来自另一个站点的信息混合。身份验证是需要注意的重要事项之一，因为所有 API 都不是公共的。为了安全使用，身份验证时需要 API 密钥。例如请参考 [Gmail API 认证](https://developers.google.com/gmail/api/guides/)
有一些 API 不需要任何访问令牌。

**例:***github API*
**[https://API . github . com](https://api.github.com)**

**输出:**

```
{
  "current_user_url": "https://api.github.com/user",
  "current_user_authorizations_html_url": "https://github.com/settings/connections/applications{/client_id}",
  "authorizations_url": "https://api.github.com/authorizations",
  "code_search_url": "https://api.github.com/search/code?q={query}{&page, per_page, sort, order}",
  "commit_search_url": "https://api.github.com/search/commits?q={query}{&page, per_page, sort, order}",
  "emails_url": "https://api.github.com/user/emails",
  "emojis_url": "https://api.github.com/emojis",
  "events_url": "https://api.github.com/events",
  "feeds_url": "https://api.github.com/feeds",
  "followers_url": "https://api.github.com/user/followers",
  "following_url": "https://api.github.com/user/following{/target}",
  "gists_url": "https://api.github.com/gists{/gist_id}",
  "hub_url": "https://api.github.com/hub",
  "issue_search_url": "https://api.github.com/search/issues?q={query}{&page, per_page, sort, order}",
  "issues_url": "https://api.github.com/issues",
  "keys_url": "https://api.github.com/user/keys",
  "notifications_url": "https://api.github.com/notifications",
  "organization_repositories_url": "https://api.github.com/orgs/{org}/repos{?type, page, per_page, sort}",
  "organization_url": "https://api.github.com/orgs/{org}",
  "public_gists_url": "https://api.github.com/gists/public",
  "rate_limit_url": "https://api.github.com/rate_limit",
  "repository_url": "https://api.github.com/repos/{owner}/{repo}",
  "repository_search_url": "https://api.github.com/search/repositories?q={query}{&page, per_page, sort, order}",
  "current_user_repositories_url": "https://api.github.com/user/repos{?type, page, per_page, sort}",
  "starred_url": "https://api.github.com/user/starred{/owner}{/repo}",
  "starred_gists_url": "https://api.github.com/gists/starred",
  "team_url": "https://api.github.com/teams",
  "user_url": "https://api.github.com/users/{user}",
  "user_organizations_url": "https://api.github.com/user/orgs",
  "user_repositories_url": "https://api.github.com/users/{user}/repos{?type, page, per_page, sort}",
  "user_search_url": "https://api.github.com/search/users?q={query}{&page, per_page, sort, order}"
}

```

**JSON 格式列表**

1.  **[【https://api.github.com/feeds】](https://api.github.com/feeds)**
    **输出:**

    ```
    {
      "timeline_url": "https://github.com/timeline",
      "user_url": "https://github.com/{user}",
      "security_advisories_url": "https://github.com/security-advisories",
      "_links": {
        "timeline": {
          "href": "https://github.com/timeline",
          "type": "application/atom+xml"
        },
        "user": {
          "href": "https://github.com/{user}",
          "type": "application/atom+xml"
        },
        "security_advisories": {
          "href": "https://github.com/security-advisories",
          "type": "application/atom+xml"
        }
      }
    }

    ```

2.  **[【https://api.github.com/rate_limit】](https://api.github.com/rate_limit)**

    ```
    {
      "resources": {
        "core": {
          "limit": 60,
          "remaining": 56,
          "reset": 1567928119
        },
        "search": {
          "limit": 10,
          "remaining": 10,
          "reset": 1567924666
        },
        "graphql": {
          "limit": 0,
          "remaining": 0,
          "reset": 1567928206
        },
        "integration_manifest": {
          "limit": 5000,
          "remaining": 5000,
          "reset": 1567928206
        }
      },
      "rate": {
        "limit": 60,
        "remaining": 56,
        "reset": 1567928119
      }
    }

    ```