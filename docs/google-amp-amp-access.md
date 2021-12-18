# 谷歌 amp-access

> 原文:[https://www.geeksforgeeks.org/google-amp-amp-access/](https://www.geeksforgeeks.org/google-amp-amp-access/)

![](img/da896cbc9c91eb6bafeb2ca1d138fca6.png)

有时候，作为一名设计师，你想取悦你的用户，为此，你决定给优质用户提供优质内容，但让他们与众不同可能是一个困难的挑战。 **amp-access** 标签是专门为此目的而设计的。它可以为登录用户、高级会员和非登录用户设置控件。通过使用这个标签，您可以向您的网页添加对身份验证和授权的支持。

**设置:**

首先，导入 amp-access 组件和 amp-analytics。

## 超文本标记语言

```
<!-- amp-access component -->
<script async custom-element="amp-access" src=
    "https://cdn.ampproject.org/v0/amp-access-0.1.js">
</script>

<!-- amp-analytics component -->
<script async custom-element="amp-analytics" src=
    "https://cdn.ampproject.org/v0/amp-analytics-0.1.js">
</script>
```

现在要添加登录和注销页面信息，请使用以下代码。您必须提供登录点，一个用于登录，另一个用于唱出页面。

## 超文本标记语言

```
<script id="amp-access" type="application/json">
 {
     "authorization": "geeksforgeeks.org",
     "pingback": "geeksforgeeks.org",
     "login": {
       "sign-in": "geeksforgeeks.org",
       "sign-out": "geeksforgeeks.org"
     },
     "authorizationFallbackResponse": {
         "error": true,
         "loggedIn": false,
         "powerUser": false
     }
 }
</script>
```

您必须使用上面代码中提到的相同 id，并且可以根据需要更改 URL。

**控制可见性:**非常重要的是，用户只能看到用户应该看到的内容，即如果用户是高级会员，则用户应该获得高级会员，或者如果他没有登录，则应该向他显示登录选项等。为此，请使用下面提到的代码:

*   显示对网站所有访问者可见的部分。

## 超文本标记语言

```
<section>
    Welcome to GeeksForGeeks!
</section>
```