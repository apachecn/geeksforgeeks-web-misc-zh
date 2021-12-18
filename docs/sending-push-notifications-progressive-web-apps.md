# 发送推送通知:渐进式网络应用

> 原文:[https://www . geesforgeks . org/sensing-push-notifications-progressive-web-apps/](https://www.geeksforgeeks.org/sending-push-notifications-progressive-web-apps/)

**我们需要权限才能发送推送通知。**

**要点:**

*   通知必须及时。
*   应该是精确的(包含用户需要的所有信息)。
*   应该与用户相关。

**基本示例:**航空公司应用程序必须发送推送通知，如“您的航班将从……开始登机。”

**支持推送通知的浏览器有:**

*   镀铬 44
*   Firefox 44
*   歌剧 42

**通知类型:**

*   **Persistent Notifications:** It is associated with the Service Worker.

    ```
    self.registration.showNotification('Title', { 
             actions : [ {              
             action : 'View',
             title : 'Action title',
             icon : 'Path' }],
     // other options});
    ```

    **要和他们互动，有不同的 API :**

    ```
    self.addEventListener('notificationclick', evt=>{ 
      if(!evt.action)
        {
           Console.log('Notification Clicked');
           return ;
        }
          // Handles action clicks
      });
    ```

    **视图:**

    ```
    self.addEventListener('notificationclick', evt=>{ 
        switch(evt.action) {
          case 'view' : Console.log('View action clicked');
          break;
          default : Console.warn('${evt.action}action clicked');
          break;
    }});
    ```

*   **Non-Persistent Notifications:** It is not associated with the Service Worker. As a developer, we interact with this through the notification API.

    **通知静态成员:**

    ```
    if(Notification.permission === 'granted')
      {
           showNotification();
           return;
      }
    if(Notification.permission !== 'denied')
      {
            Notification.request Permission().then (p=> {
               if(p === 'granted')
               showNotification();
            });
     }
    ```

    **如何显示通知:**

    ```
    var n = new Notification('Title', // object
    {
        body : 'body text',

        // Little tiny badge at top left
        // corner of screen
        badge :'path',      

        // Setting picture related to the
        // notification, For Ex: Soda image
        // in case of Sodapopped website
        icon : 'path',      

        // Combining different Notifications
        // by providing them with the same
        // tag name
        tag : 'tag name',     

        // To notify buzz, set it true 
        renotify : false,    
        data : { //object} 
    );
    ```

**不同的其他属性也可以用以下格式编写:**

*   **动作相关属性–**

    ```
    var n = new Notification('Title', // body, images, tag, etc.
    {
        // True, when notifications remain open until
        // the user explicitly clicks on it to         
        requiredInteraction : false, close
        actions : [ {              
            // Takes objects which has three properties
            action : 'Id',
            title : 'Action title',
            icon : 'Path' 
        }],
    });
    ```

    *   **声音属性–**

    ```
    // body, images, tag, data, action
    // True, vibrate or make sound
    silent : false, 

    // path to sound (Till date no browser
    // supports this)
    sound : 'path',     

    // This indicates to vibrate for 200ms
    // then 100ms then 200ms, so on      
    vibrate : [200 100 200], 
    ```

    *   **Miscellaneous Properties –**

    ```
    // Direction (left to right or right to left(rtl))
    dir : 'ltr',    

    // Language
    lang :'en-US',   
    timestamp : Date.now()   // Time
    ```

    **通知实例成员:**

    > var n =新通知(' Title '，{//options })；
    > 
    > *   n.addEventListener('错误'，evt=>{ Console.error('出现问题'，evt)；});
    > *   n.addEventListener('click '，evt = > { console . log(' Notification clicked ')；});
    >     n . close()；