# Bulma |下拉式清单

> 原文:[https://www.geeksforgeeks.org/bulma-dropdown/](https://www.geeksforgeeks.org/bulma-dropdown/)

**布尔玛**是一个基于 Flexbox 的免费开源 CSS 框架。它是组件丰富的，兼容的，并且有很好的文档记录。它本质上是高度反应的。它使用类来实现它的设计。

下拉组件是一个包含下拉按钮和下拉菜单的容器。使用下拉菜单及其子类，可以实现交互式下拉菜单。**下拉菜单**组件包括其他几个可以添加来设计内容的组件。这些组件如下所示:

*   **下拉触发器:**是下拉按钮的容器。
*   **下拉菜单:**是可切换菜单的容器。默认情况下，它是隐藏的。
    *   **下拉-内容:**是下拉框。它有带阴影的白色背景。
        *   **下拉项:**代表下拉的每一项。
        *   **下拉分隔符:**是两项之间的横线分隔符。

**示例 1:** 该示例显示了使用布尔玛创建一个简单的下拉列表。

## 超文本标记语言

```htmlhtml
<!DOCTYPE html>
<html>

<head>
  <title>Bulma Dropdown</title>

  <!-- Include Bulma CSS -->
  <link rel='stylesheet' href=
'https://cdnjs.cloudflare.com/ajax/libs/bulma/0.7.5/css/bulma.css'>

  <!-- Custom css -->
  <style>
    div.columns {
      margin-top: 80px;
    }
  </style>
</head>

<body>
  <!-- font-awesome cdn -->
  <script src=
'https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.12.0-2/js/all.min.js'>
  </script>

  <div class='container has-text-centered'>
    <div class='columns is-mobile is-centered'>
      <div class='column is-5'>
        <div class="dropdown is-active">
          <div class="dropdown-trigger">
            <button class="button"
                    aria-haspopup="true"
                    aria-controls="dropdown-menu">
              <span>Todos</span>
              <span class="icon is-small">
                <i class="fas fa-angle-down"
                   aria-hidden="true"></i>
              </span>
            </button>
          </div>

          <div class="dropdown-menu"
               id="dropdown-menu"
               role="menu">
            <div class="dropdown-content">
              <a href="#" class="dropdown-item">
                Design a custom database to
                store your daily activity
              </a>

              <a href="#" class="dropdown-item">
                Take pictures of beautiful flowers
              </a>

              <a href="#" class="dropdown-item">
                Ride to a horse and
                write your experience
              </a>

              <a href="#" class="dropdown-item">
                Go for a trip with bike
              </a>

              <a href="#" class="dropdown-item">
                Design a custom database to
                store your daily activity
              </a>

              <a href="#" class="dropdown-item">
                Buy a sumsung headset
              </a>

              <a href="#" class="dropdown-item">
                Listen music for one hour
              </a>

              <a href="#" class="dropdown-item">
                Go for a morning walk
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>

  <script>
    const dropdown =
          document.querySelector('.dropdown');
    const active =
          document.querySelector('.is-active')
    document.body.addEventListener('click', function () {
      if (active) {
        dropdown.classList.remove('is-active')
      }
    })
    dropdown.addEventListener('click', function (event) {
      event.stopPropagation();
      this.classList.toggle('is-active');
    });
  </script>
</body>
</html>
```

**输出:**

<video class="wp-video-shortcode" id="video-435776-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200618205244/bulma-simple-dropdown.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200618205244/bulma-simple-dropdown.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200618205244/bulma-simple-dropdown.mp4)</video>

**示例 2:** 该示例显示了使用布尔玛创建可悬停的下拉列表。

## 超文本标记语言

```htmlhtml
<!DOCTYPE html>
<html>

<head>
  <title>Bulma Dropdown</title>

  <!-- Include Bulma CSS -->
  <link rel='stylesheet' href=
'https://cdnjs.cloudflare.com/ajax/libs/bulma/0.7.5/css/bulma.css'>

  <!-- FontAwesome Library -->
  <script src=
'https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.12.0-2/js/all.min.js'>
  </script>

  <!-- Custom CSS -->
  <style>
    div.columns {
      margin-top: 80px;
    }
  </style>
</head>

<body>
  <div class='container has-text-centered'>
    <div class='columns is-mobile is-centered'>
      <div class='column is-5'>
        <div class="dropdown is-hoverable">
          <div class="dropdown-trigger">
            <button class="button"
                    aria-haspopup="true"
                    aria-controls="dropdown-menu">
              <span>Todos</span>
              <span class="icon is-small">
                <i class="fas fa-angle-down"
                   aria-hidden="true"></i>
              </span>
            </button>
          </div>

          <div class="dropdown-menu"
               id="dropdown-menu"
               role="menu">
            <div class="dropdown-content">
              <a href="#" class="dropdown-item">
                Design a custom database to store
                your daily activity
              </a>

              <a href="#" class="dropdown-item">
                Take pictures of beautiful
                flowers
              </a>

              <a href="#" class="dropdown-item">
                Ride to a horse and write
                your experience
              </a>

              <a href="#" class="dropdown-item">
                Go for a trip with bike
              </a>

              <a href="#" class="dropdown-item">
                Design a custom database
                to store your daily activity
              </a>

              <a href="#" class="dropdown-item">
                Buy a sumsung headset
              </a>

              <a href="#" class="dropdown-item">
                Listen music for one hour
              </a>

              <a href="#" class="dropdown-item">
                Go for a morning walk
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</body>
</html>
```

**输出:**

<video class="wp-video-shortcode" id="video-435776-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200618210008/hoverable-dropdown.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200618210008/hoverable-dropdown.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200618210008/hoverable-dropdown.mp4)</video>

**示例 3:** 该示例显示了使用布尔玛创建不同的对齐下拉列表。

## 超文本标记语言

```htmlhtml
<!DOCTYPE html>
<html>

<head>
  <title>Bulma Dropdown</title>

  <!-- Include Bulma CSS -->
  <link rel='stylesheet' href=
'https://cdnjs.cloudflare.com/ajax/libs/bulma/0.7.5/css/bulma.css'>

  <!-- FontAwesome Library -->
  <script src=
'https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.12.0-2/js/all.min.js'>
  </script>

  <!-- Custom CSS -->
  <style>
    div.columns {
      margin-top: 80px;
    }
  </style>
</head>

<body>
  <div class='container has-text-centered'>
    <div class='columns is-mobile is-centered'>
      <div class='column is-5'>
        <div class="dropdown is-hoverable">
          <div class="dropdown-trigger">
            <button class="button"
                    aria-haspopup="true"
                    aria-controls="dropdown-menu">
              <span>Left Aligned Todos</span>
              <span class="icon is-small">
                <i class="fas fa-angle-down"
                   aria-hidden="true"></i>
              </span>
            </button>
          </div>

          <div class="dropdown-menu"
               id="dropdown-menu"
               role="menu">
            <div class="dropdown-content">
              <a href="#" class="dropdown-item">
                Design a custom database
                to store your daily activity
              </a>

              <a href="#" class="dropdown-item">
                Take pictures of beautiful
                flowers
              </a>

              <a href="#" class="dropdown-item">
                Ride to a horse and write
                your experience
              </a>

              <a href="#" class="dropdown-item">
                Go for a trip with bike
              </a>

              <a href="#" class="dropdown-item">
                Design a custom database
                to store your daily activity
              </a>

              <a href="#" class="dropdown-item">
                Buy a sumsung headset
              </a>

              <a href="#" class="dropdown-item">
                Listen music for one hour
              </a>

              <a href="#" class="dropdown-item">
                Go for a morning walk
              </a>
            </div>
          </div>
        </div>
      </div>

      <div class='column is-5'>
        <div class="dropdown is-right is-hoverable">
          <div class="dropdown-trigger">
            <button class="button"
                    aria-haspopup="true"
                    aria-controls="dropdown-menu">
              <span>Right Aligned Todos</span>
              <span class="icon is-small">
                <i class="fas fa-angle-down"
                   aria-hidden="true"></i>
              </span>
            </button>
          </div>

          <div class="dropdown-menu"
               id="dropdown-menu"
               role="menu">
            <div class="dropdown-content">
              <a href="#" class="dropdown-item">
                Design a custom database
                to store your daily activity
              </a>

              <a href="#" class="dropdown-item">
                Take pictures of beautiful
                flowers
              </a>

              <a href="#" class="dropdown-item">
                Ride to a horse and write
                your experience
              </a>

              <a href="#" class="dropdown-item">
                Go for a trip with bike
              </a>

              <a href="#" class="dropdown-item">
                Design a custom database
                to store your daily activity
              </a>

              <a href="#" class="dropdown-item">
                Buy a sumsung headset
              </a>

              <a href="#" class="dropdown-item">
                Listen music for one hour
              </a>

              <a href="#" class="dropdown-item">
                Go for a morning walk
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</body>
</html>
```

**输出:**

<video class="wp-video-shortcode" id="video-435776-3" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200618211411/Right-and-left-aligned-dropdowns.mp4?_=3">[https://media.geeksforgeeks.org/wp-content/uploads/20200618211411/Right-and-left-aligned-dropdowns.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200618211411/Right-and-left-aligned-dropdowns.mp4)</video>

**示例 4:** 该示例显示了使用布尔玛创建“dropup”。

## 超文本标记语言

```htmlhtml
<!DOCTYPE html>
<html>

<head>
  <title>Bulma Dropdown</title>

  <!-- Include Bulma CSS -->
  <link rel='stylesheet' href=
'https://cdnjs.cloudflare.com/ajax/libs/bulma/0.7.5/css/bulma.css'>

  <!-- FontAwesome Library -->
  <script src=
'https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.12.0-2/js/all.min.js'>
  </script>

  <!-- Custom CSS -->
  <style>
    div.columns {
      margin-top: 330px;
    }
  </style>
</head>

<body>
  <div class='container has-text-centered'>
    <div class='columns is-mobile is-centered'>
      <div class='column is-5'>
        <div class="dropdown is-up is-hoverable">
          <div class="dropdown-trigger">
            <button class="button"
                    aria-haspopup="true"
                    aria-controls="dropdown-menu">
              <span>Left Aligned Todos</span>
              <span class="icon is-small">
                <i class="fas fa-angle-up"
                   aria-hidden="true"></i>
              </span>
            </button>
          </div>

          <div class="dropdown-menu"
               id="dropdown-menu"
               role="menu">
            <div class="dropdown-content">
              <a href="#" class="dropdown-item">
                Design a custom database
                to store your daily activity
              </a>

              <a href="#" class="dropdown-item">
                Take pictures of beautiful
                flowers
              </a>

              <a href="#" class="dropdown-item">
                Ride to a horse and write
                your experience
              </a>

              <a href="#" class="dropdown-item">
                Go for a trip with bike
              </a>

              <a href="#" class="dropdown-item">
                Design a custom database
                to store your daily activity
              </a>

              <a href="#" class="dropdown-item">
                Buy a sumsung headset
              </a>

              <a href="#" class="dropdown-item">
                Listen music for one hour
              </a>

              <a href="#" class="dropdown-item">
                Go for a morning walk
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</body>
</html>
```

**输出:**

<video class="wp-video-shortcode" id="video-435776-4" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200618212009/dropup-menu.mp4?_=4">[https://media.geeksforgeeks.org/wp-content/uploads/20200618212009/dropup-menu.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200618212009/dropup-menu.mp4)</video>