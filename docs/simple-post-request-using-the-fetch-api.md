# 使用提取应用编程接口的简单开机自检请求

> 原文:[https://www . geesforgeks . org/simple-post-request-use-fetch-API/](https://www.geeksforgeeks.org/simple-post-request-using-the-fetch-api/)

像 XMLHttpRequest 和 Axios 请求一样， **fetch()方法**用于向服务器发送请求。主要区别在于 Fetch API 使用了 Promises，这使得 API 变得更加简单和干净。您将使用提取应用编程接口获得整个**获取和发布方法**

**语法:**

*   ```html
    fetch(url, { config }) 
    .then(res => { 
        // Handle response 
    }) 
    .catch(err => { 
        // Handle errors 
    }) 

    ```

*   Since fetch returns a Promise, we can also use the keyword **async/await** to make a request:

    ```html
    async () => {
      const resp = await fetch('http://example.com/example.json');
      // Handle response
    }

    ```

**使用 fetch()创建 POST 请求:**POST 请求广泛用于向服务器提交表单。

```html
fetch(url, {
    method: 'POST',
    headers: {
      "Content-type": "application/x-www-form-urlencoded; charset=UTF-8"
    },
    credentials: 'include',
    body: 'foo=bar&lorem=ipsum'
  })
  .then(res.json())
  .then(res => {
    // Handle response 
    console.log('Response: ', res);
  })
  .catch(err => {
    // Handle error 
    console.log('Error message: ', error);
  });
```

**解释:**

*   To create a POST request, we need to specify some parameters in the request, such as method, first class, etc. First, we need to specify the request method (GET, POST, DELETE, etc.). ) in our example, it is POST. Next is the content type, which tells the client what the content type of the returned data is actually. The key is optional. If you want to use credentials (such as cookies) to make an extraction request, you should use this key. Then, we set up a body composed of the data we want to pass to the server.
*   The response to the fetch () request is a stream object, which means that when we call the json () method, a Promise will be returned, because the reading of the stream will be asynchronous.
*   If the API returns status 201 (created HTTP status code), you can access the data-res (response) returned by the API. If an error occurs, the code in the catch block will be executed.