# 如何将应用添加到主屏幕:渐进式网络应用

> 原文:[https://www . geesforgeks . org/how-app-to-home-screen-progress-web-apps/](https://www.geeksforgeeks.org/how-to-add-app-to-home-screen-progressive-web-apps/)

**Web App Manifest 是一个简单的 JSON 文件，它告诉浏览器你的 Web 应用程序，以及当它‘安装’在用户的移动设备或桌面上时应该如何表现。**

我们需要添加一个清单的链接，以便将网络应用程序添加到主屏幕。
在你的代码的 HTML 头部写**。**

****如何创建清单文件:**
要创建此文件，我们需要有某些属性，如:
**1。识别您的应用程序(识别)**–这必须包含名称和短名称**

```
 "name" : "EbullientMind",
     "short_name" : "EbullientMind"
```

****2。展示您的应用程序(展示)**–这必须包含开始网址、主题颜色、背景颜色、方向和显示**

```
 "start_url" : "[provide_path]",
     "background_color" : "[provide_color]",
     "theme-color" : "[provide_color]",
     "orientation" : "any",
     "display" : "standalone" 
```

****3。图标**–这必须包含某些功能，例如:src、类型、尺寸**

```
 "icons" :
      [{
     "src" : "[provide_path]",
     "type" : "[provide_type_of_image]",
     "sizes" : "[provide_size_of_image]" 
      }] 
```

****4。杂项**-必须包含目录、语言、描述、范围、服务人员**

```
 "dir" : "ltr",
        "lang" : "en-US",
        "description" : "Describe your app",
        "scope" : "/",
        "serviceworker" : 
           {
            "src" : "[provide_path]",
            "scope" : "/"
           } 
```

****5。应用程序**-必须包含相关应用程序、首选相关应用程序、截图**

```
 "screenshots" :
   [{
  "src" : "[provide_path]" 
   }],

  "related_applications" : 
   [{
  "platform" : "play",
  "url" : "[provide_path]",
  "id" : "[provide_id]" 
   }],

  "prefer_related_applications" : true 
```

****程序化事件显而易见:**
**1。onappinstalled :****

```
 window.addEventListener('appinstalled',evt => {
   console.log('App Installed');  })
```

****2 .beforeinstallprompt :****

```
 window.addEventListener('beforeinstallprompt',evt => {
   evt.userchoice.then(choice => {
   var message = choice.outcome === 'dismissed' ? 'User Cancelled' : 'User Installed' ;
   console.log(message);
   });
});
   window.addEventListener('beforeinstallprompt',evt => {
   evt.preventDefault();
   prompt Evt = evt;
   return false;
});
  if(promptEvt ! = undefined){
  promptEvt.prompt()
  promptEvt.userchoice.then(choice => {
  console.log('User choice:', choice.outcome);
});
}
```