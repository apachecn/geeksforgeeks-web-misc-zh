# 如何将带有标记的谷歌地图添加到网站

> 原文:[https://www . geesforgeks . org/add-Google-maps-marker-网站/](https://www.geeksforgeeks.org/add-google-maps-marker-website/)

谷歌地图是由谷歌开发的网络地图服务。它提供卫星图像、街道地图、360°街道全景(街景)、实时交通状况(谷歌交通)以及步行、汽车、自行车(测试版)或公共交通出行的路线规划。

**在网站上添加带有标记的谷歌地图需要三个基本步骤:**

3.  创建一个网页
4.  添加带有标记的地图
5.  Get an API key

    **第一步:创建一个 Html 页面。**

    ```htmlhtml
    <!DOCTYPE html>
    <html>
      <head>
        <style>
          #map {
            width: 100%;
            height: 400px;
            background-color: grey;
          }
        </style>
      </head>
      <body>
        <p>My Google Maps Demo</p>
        <div id="map"></div>
      </body>
    </html>
    ```

    **输出:**
    ![](img/2433e1cf95d3c81191c6d1465c1688c8.png)

    给定的代码描述了设置 div 大小和颜色的 CSS。style 元素设置地图的 div 大小，div 设置为 400 像素的高度和 100%的宽度，以便在整个网页的宽度上显示地图。
    ![](img/cd5552cbc3a7f351d279fdd5df5f99c5.png)

    代码为谷歌地图定义了页面的一个区域。div 在输出中显示为灰色块，因为地图尚未添加。

    ![](img/2d12e847610f21ef5cb3f684280869fa.png)

    **第二步:添加带标记的地图:**

    ```htmlhtml
    <!DOCTYPE html>
    <html>
      <head>
        <style>
          #map {
            height: 400px;
            width: 100%;
           }
        </style>
      </head>
      <body>
        <p>My Google Maps Demo</p>
        <div id="map"></div>
        <script>
          function initMap() {
            var test= {lat: -25.363, lng: 131.044};
            var map = new google.maps.Map(document.getElementById('map'), {
              zoom: 4,
              center: test
            });
            var marker = new google.maps.Marker({
              position: test,
              map: map
            });
          }
        </script>
        <script async defer
        src=
    "https://maps.googleapis.com/maps/api/js?key=YOUR_API_KEY&callback=initMap">
        </script>
      </body>
    </html>
    ```

    **说明:**

    *   在代码中，脚本从指定的网址加载应用编程接口。
    *   回调参数在应用编程接口加载后执行 initMap 函数。
    *   异步属性允许浏览器在应用编程接口加载时继续呈现页面的其余部分。
    *   密钥参数包含应用编程接口密钥。
    *   Type your api key inside “key = “.
        ![](img/2d9f452419087bbdc6133ed63f95cf97.png)

        该代码包含 initMap 函数，该函数在网页加载时初始化并添加地图。脚本标签可以用来添加你自己的 javascript。
        ![](img/bdf5d22fc9526f9bd6b69304d5484a9b.png)

    *   该代码构建了一个新的谷歌地图对象，并向地图添加了属性，包括中心和缩放级别。
    *   在下面的代码中，new google.maps.Map()创建了一个新的 Google maps 对象。
    *   center 属性告诉 API 地图的中心位置。地图坐标按以下顺序设置:纬度、经度。
    *   The zoom property specifies the zoom level for the map. Zoom: 0 is the lowest zoom, and displays the entire earth. Set the zoom value higher to zoom in to the earth at higher resolutions.

        ![](img/49c4c194502347214381a7dc42bf40b4.png)

        下面的代码在地图上放置了一个标记。position 属性设置标记的位置。
        ![](img/6fe7e2c2049aa4ce9c5f896131904adf.png)

**第三步:获取应用编程接口密钥**
获取应用编程接口密钥所需的步骤如下:

1.  转到下面提到的链接
    [https://console.developers.google.com/flows/enableapi?apiid = maps _ 后端，geocode _ 后端，directions _ 后端，distance _ matrix _ 后端，elevation _ 后端，places _ 后端& reusekey=true](https://console.developers.google.com/flows/enableapi?apiid=maps_backend,geocoding_backend,directions_backend,distance_matrix_backend,elevation_backend,places_backend&reusekey=true) 。
2.  创建新项目或从现有项目中进行选择。
3.  单击继续启用应用编程接口。
4.  在“凭据”页面上，获取一个应用编程接口密钥(并设置应用编程接口密钥限制)。
5.  Replace the value of the key parameter in the URL with your own API key

    **输出:**
    ![](img/b4c2cb12669c7000b9dc4e52b9cb3951.png)

    **示例:在谷歌地图上添加 GeeksforGeeks 办公城市**

    **输入:**

    ```htmlhtml
    <!DOCTYPE html>
    <html>
      <head>
        <style>
          #map {
            height: 400px;
            width: 100%;
           }
        </style>
      </head>
      <body>
        <h3>GFG Google Maps Demo</h3>
        <div id="map"></div>
        <script>
          function initMap() {
            var uluru = {lat: 28.501859, lng: 77.410320};
            var map = new google.maps.Map(document.getElementById('map'), {
              zoom: 4,
              center: uluru
            });
            var marker = new google.maps.Marker({
              position: uluru,
              map: map
            });
          }
        </script>
        <script async defer
        src=
    "https://maps.googleapis.com/maps/api/js?key=
    AIzaSyB2bXKNDezDf6YNVc-SauobynNHPo4RJb8&callback=initMap">
        </script>
      </body>
    </html>
    ```

    **输出:**
    ![](img/867c6f0eada03ddd8a4e2666b4576c1a.png)

    本文由 [**舒布罗迪普·班纳吉**](https://auth.geeksforgeeks.org/profile.php?user=Shubrodeep Banerjee) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。