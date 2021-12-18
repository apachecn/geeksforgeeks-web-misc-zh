# 谷歌地图信息窗口

> 原文:[https://www.geeksforgeeks.org/google-maps-info-windows/](https://www.geeksforgeeks.org/google-maps-info-windows/)

谷歌地图信息窗口用于添加一个窗口来显示特定区域的信息。通常，信息窗口会附加一个标记。您可以通过实例化 google.maps.InfoWindow 类来附加一个信息窗口。

**语法:**

```html
var infowindow = new google.maps.InfoWindow({content: "Content String"});
                 infowindow.open(map, marker);

```

**属性值:**

*   **内容:**用于传递字符串格式的内容。
*   **pixelOffset:** 包含从信息窗口顶端到信息窗口锚定位置的偏移量，可选。
*   **位置:**用于选择信息窗口的位置。
*   **最大宽度:**水平限制信息窗口的大小。默认情况下，信息窗口的宽度将被拉伸，直到文本被换行。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
    <head>
        <!-- Loading map API -->
        <script src=
"https://maps.googleapis.com/maps/api/js">
        </script>

        <script>
            function GFG() {
                var CustomOp = {
                    center: new google.maps.LatLng(28.502212, 77.405603),
                    zoom: 17,
                };

                // Map object
                var map = new google.maps
                .Map(document.getElementById("DivID"), CustomOp);
                var marker = new google.maps.Marker({
                    position: new google.maps.LatLng(28.502211, 77.405512),
                    map: map,
                    draggable: true,
                    icon: 
"https://media.geeksforgeeks.org/wp-content/uploads/20200811003251/logo-100x100.png",
                });

                marker.setMap(map);

                var infowindow = new google.maps.InfoWindow({
                    content: "5th Floor, A-118,Sector-136,"+
                             " Noida, Uttar Pradesh - 201305",
                });
                infowindow.open(map, marker);
            }
        </script>
    </head>

    <!-- load map -->
    <body onload="GFG()">
        <center>
            <h1 style="color: green;">GeeksforGeeks</h1>
            <h3>Google Maps Info Windows</h3>

            <!-- Basic Container -->
            <div id="DivID" 
                 style="width: 400px; height: 300px;"></div>
        </center>
    </body>
</html>
```

**输出:**

![](img/6db2dca1184b3366f368ac6b024821cf.png)