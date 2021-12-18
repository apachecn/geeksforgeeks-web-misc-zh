# 布尔马|首都

> 原文:[https://www.geeksforgeeks.org/bulma-modal/](https://www.geeksforgeeks.org/bulma-modal/)

布尔玛是一个基于 Flexbox 的免费开源 CSS 框架。它是组件丰富的，兼容的，并且有很好的文档记录。它本质上是高度反应的。它使用类来实现它的设计。

莫代尔是一个经典的覆盖，其中可以包括任何内容。模态组件是一个对话框/弹出窗口，一旦单击触发器按钮，它就会显示在当前页面的顶部。“模式”组件包括几个可以添加到内容设计中的其他组件。这些组件如下所示:

*   **模态-背景:**是透明叠加作为点击目标关闭模态。
*   **模态内容:**是最大宽度为‘640 px’的容器。这个容器显示了模型类的内容。
*   **情态关闭:**是位于右上角的‘十字’用来关闭情态。

**例 1:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
  <title>Bulma Modal</title>

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
      margin-top: 50px;
    }

    .modal-content {
      margin-top: 100px;
      width: 450px;
    }
  </style>
</head>

<body>
  <div class='container has-text-centered'>
    <div class='columns is-mobile is-centered'>
      <div class='column is-4'>
        <button class="button is-primary"
                id='btn'>Click to see modal</button>
        <div class="modal">
          <div class="modal-background"></div>
          <div class="modal-content">

            <div class='box'>
              <h1 class='title' 
                  style='color:green'>
                Geek for Geeks</h1>
              <p class='is-family-monospace'>
                'GeeksforGeeks' is a computer 
                science portal.it was created with
                a goal in mind to provide well 
                written, well thought and
                well explained solutions for 
                selected questions. The core team
                of five super geeks constituting
                of technology lovers and
                computer science enthusiasts 
                have been constantly working
                in this direction .
              </p>
              <div class='buttons'>
                <button class='button is-fullwidth'>
                  Know more about GfG
                </button>
              </div>
            </div>
          </div>
          <button class="modal-close is-large" 
                  aria-label="close">
            Model
          </button>
        </div>
      </div>
    </div>
  </div>

  <script>
    // Bulma does not have JavaScript included,
    // hence custom JavaScript has to be
    // written to open or close the modal
    const modal = 
          document.querySelector('.modal');
    const btn = 
          document.querySelector('#btn')
    const close = 
          document.querySelector('.modal-close')

    btn.addEventListener('click',
                         function () {
      modal.style.display = 'block'
    })

    close.addEventListener('click',
                           function () {
      modal.style.display = 'none'
    })

    window.addEventListener('click',
                            function (event) {
      if (event.target.className === 
          'modal-background') {
        modal.style.display = 'none'
      }
    })
  </script>
</body>
</html>
```

**输出:**

**<video class="wp-video-shortcode" id="video-437458-1" width="665" height="447" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200619185906/simple-modal.mp4?_=1">[https://media . geeksforgeeks . org/WP-content/uploads/20200619185906/simple-modal . MP4](https://media.geeksforgeeks.org/wp-content/uploads/20200619185906/simple-modal.mp4)</video>**

**示例 2:**

登录表单模态。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
  <title>Bulma Modal</title>

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
      margin-top: 50px;
    }

    .modal-content {
      margin-top: 100px;
      width: 450px;
    }

    .buttons {
      margin-top: 12px;
    }
  </style>
</head>

<body>
  <div class='container'>
    <div class='columns is-mobile is-centered'>
      <div class='column is-4'>
        <div class='has-text-centered'>
          <button class="button is-primary"
                  id='btn'>
            Login form modal
          </button>
        </div>
        <div class="modal">
          <div class="modal-background"></div>
          <div class="modal-content">
            <div class="box">
              <div>
                <h1 class='title has-text-centered'>
                  Login
                </h1>
              </div>
              <form action='#' method='post'>
                <div class='field'>
                  <label class='label'
                         id='username'>
                    Username
                  </label>
                  <div class='control has-icons-left'>
                    <input class='input'
                           type='text'
                           for='username' 
                           placeholder='Username'>
                    <span class="icon is-small is-left">
                      <i class="fas fa-user"></i>
                    </span>
                  </div>
                </div>

                <div class='field'>
                  <label class='label' 
                         id='password'>
                    Password
                  </label>
                  <div class='control has-icons-left'>
                    <input class='input'
                           type='password'
                           for='password' 
                           placeholder='Password'>
                    <span class="icon is-small is-left">
                      <i class="fas fa-lock"></i>
                    </span>
                  </div>

                  <div class='buttons'>
                    <button class='button is-link'>
                      Login
                    </button>
                  </div>
                </div>
              </form>
            </div>
          </div>
          <button class="modal-close is-large"
                  aria-label="close">
            Model
          </button>
        </div>
      </div>
    </div>
  </div>

  <script>
    // Bulma does not have JavaScript included,
    // hence custom JavaScript has to be
    // written to open or close the modal
    const modal = document.querySelector('.modal');
    const btn = document.querySelector('#btn')
    const close = document.querySelector('.modal-close')

    btn.addEventListener('click',
                         function () {
      modal.style.display = 'block'
    })

    close.addEventListener('click',
                           function () {
      modal.style.display = 'none'
    })

    window.addEventListener('click',
                            function (event) {
      if (event.target.className ===
          'modal-background') {
        modal.style.display = 'none'
      }
    })
  </script>
</body>
</html>
```

**输出:**

**<video class="wp-video-shortcode" id="video-437458-2" width="665" height="447" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200619191716/login-form-modal1.mp4?_=2">[https://media . geekesforgeks . org/WP-content/uploads/20200619191716/log in-form-Modal 1 . MP4](https://media.geeksforgeeks.org/wp-content/uploads/20200619191716/login-form-modal1.mp4)</video>**

**示例 3:**

Modal 显示推特消息。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
  <title>Bulma Modal</title>

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
      margin-top: 50px;
    }

    .modal-content {
      margin-top: 100px;
      width: 450px;
    }
  </style>
</head>

<body>
  <div class='container'>
    <div class='columns is-mobile is-centered'>
      <div class='column is-4'>
        <div class='has-text-centered'>
          <button class="button is-primary"
                  id='btn'>
            Twitter Messages
          </button>
        </div>
        <div class="modal">
          <div class="modal-background">
          </div>
          <div class="modal-content">
            <div class="box">
              <article class="media">
                <div class="media-left">
                  <figure class="image is-64x64">
                    <img src =
"https://media.geeksforgeeks.org/wp-content/uploads/20200611151025/gfg202.png">
                  </figure>
                </div>
                <div class="media-content">
                  <div class="content">
                    <p>
                      <strong>GeekforGeeks</strong> 
                      <small>@geekforgeeks</small>
                      <small>36m</small>
                      <br>
                      Hey, There!
                      <br>
                      'GeeksforGeeks' is a computer science
                      portal.it was created with a goal in
                      mind to provide well written, well 
                      thought and well explained solutions
                      for selected questions. The core team
                      of five super geeks constituting of
                      technology lovers and computer science
                      enthusiasts have been constantly working
                      in this direction .
                    </p>
                  </div>
                  <nav class="level is-mobile">
                    <div class="level-left">
                      <a class="level-item">
                        <span class="icon is-small">
                          <i class="fas fa-reply"></i>
                        </span>
                      </a>
                      <a class="level-item">
                        <span class="icon is-small">
                          <i class="fas fa-retweet"></i>
                        </span>
                      </a>
                      <a class="level-item">
                        <span class="icon is-small">
                          <i class="fas fa-heart"></i>
                        </span>
                      </a>
                    </div>
                  </nav>
                </div>
              </article>
            </div>
          </div>
          <button class="modal-close is-large" 
                  aria-label="close">
            Model
          </button>
        </div>
      </div>
    </div>
  </div>

  <script>
    // Bulma does not have JavaScript included,
    // hence custom JavaScript has to be
    // written to open or close the modal
    const modal =
          document.querySelector('.modal');
    const btn =
          document.querySelector('#btn')
    const close =
          document.querySelector('.modal-close')

    btn.addEventListener('click',
                         function () {
      modal.style.display = 'block'
    })

    close.addEventListener('click',
                           function () {
      modal.style.display = 'none'
    })

    window.addEventListener('click',
                            function (event) {
      if (event.target.className ===
          'modal-background') {
        modal.style.display = 'none'
      }
    })
  </script>
</body>
</html>
```

**输出:**

<video class="wp-video-shortcode" id="video-437458-3" width="665" height="447" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200619192637/modal-to-show-twitter-messages.mp4?_=3">[https://media.geeksforgeeks.org/wp-content/uploads/20200619192637/modal-to-show-twitter-messages.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200619192637/modal-to-show-twitter-messages.mp4)</video>