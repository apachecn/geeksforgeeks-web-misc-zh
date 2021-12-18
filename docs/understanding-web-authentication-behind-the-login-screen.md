# 了解登录屏幕后面的网页认证

> 原文:[https://www . geesforgeks . org/understanding-web-身份验证-登录后屏幕/](https://www.geeksforgeeks.org/understanding-web-authentication-behind-the-login-screen/)

[**认证**](https://www.geeksforgeeks.org/authentication-in-computer-network/) 是验证用户身份或信息的过程。用户身份验证是在用户登录到计算机系统时验证用户身份的过程。

本文简要介绍了现代 web 应用程序中的身份验证。

两种主要的身份验证类型是:

*   无状态认证

*   状态认证

要了解两者之间的显著差异，请查看无状态和有状态协议之间的[差异文章。这两种类型的认证都可以通过理解它们的流程来理解。](https://www.geeksforgeeks.org/difference-between-stateless-and-stateful-protocol/)

**状态认证:**使用会话标识和 Cookies。

**认证流程:**

1.  The user submits login credentials, that is, user name and password.
2.  This is verified by the server against the database.
3.  Then the server generates a temporary user session.
4.  The server issues a cookie with the session ID.
5.  Users/clients can send cookie with each request.
6.  The server authenticates according to the session storage and grants access rights.
7.  When the user logs out, the server destroys the session and clears the cookie.

**注意:**会话 ID 只不过是一个随机字符串，服务器可以根据会话的存储来识别它，以验证用户的请求。因此，没有第三方可以从该会话中提取任何数据/信息。

**有状态身份验证的特性:**每个用户会话都存储在服务器端(有状态)**。**

*   Memory, that is, file system (less common).
*   Cache in the database (Redis or Memcached)
*   (Commonly used ones include Postgres and MongoDb)

**每个用户由会话标识来标识。**

1.  **Opaque reference:**
    *   No third party can extract any data.
    *   Only the issuing bank (server) can map back data.
2.  **stored in Cookie:**
    *   Sign in secret. In addition, cookies are usually protected by flags, so that clients can't tamper with cookies. The process of encrypting and signing cookies on the server side is also to avoid/detect any tampering of client cookies, so the server side can ensure that cookies have not been tampered with.

**无状态认证:**使用令牌，JWT，OAuth &其他。

**使用令牌的身份验证流程:**

*   The user submits login credentials, that is, user name and password.
*   The server verifies the credentials against the database.
*   Then the server generates a temporary Token and embeds the user data in it.
*   Respond with the server token (in the body or title).
*   The user token is stored in the client storage [localStorage or SessionStorage].
*   Send the user token with each request.
*   Server authentication token & granting access rights.
*   When the user logs out, the token is cleared from the client store.

**无状态认证系统的特性:**

*   Tokens are not stored on the server side, but only on the client side.
*   (stateless) signed a secret to prevent tampering.
*   Through verification, it can be trusted by the server.
*   Tokens can be opaque or independent.
*   The token can carry all the required user data in its payload.
*   This can reduce database lookup, but it will expose the data to XSS attack.
*   Tokens are usually sent under the authorization header.
*   When the token is about to expire, it can be refreshed, because the client obtains both the access token and the refresh token.
*   The refresh token can be used to refresh the access token.
*   Used in SPA network applications, network APIs and even mobile applications.