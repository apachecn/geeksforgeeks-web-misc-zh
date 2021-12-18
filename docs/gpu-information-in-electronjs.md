# 电子表格中的图形处理器信息

> 原文:[https://www . geesforgeks . org/GPU-information-in-electronijs/](https://www.geeksforgeeks.org/gpu-information-in-electronjs/)

[**electronijs**](https://www.geeksforgeeks.org/introduction-to-electronjs/)是一个开源框架，用于使用能够在 Windows、macOS 和 Linux 操作系统上运行的 HTML、CSS 和 JavaScript 等网络技术构建跨平台的本机桌面应用程序。它将铬引擎和[T5 节点 T7】结合成一个单一的运行时。](https://www.geeksforgeeks.org/introduction-to-nodejs/)

**GPU** (图形处理单元)是一种专用的可编程处理器，用于在计算机屏幕上渲染所有图形内容，如图像。它旨在快速操作和更改内存，以加速在帧缓冲区中创建图像，用于在显示设备上输出。所有现代计算机系统都带有内置的图形处理器组件，即它们可以是主板电路的一部分，也可以是从外部连接到主板的另一个组件。**铬**在显示 GPU 加速内容时广泛使用该 GPU 组件。Chromium 使用图形处理器来加速网页渲染、HTML、CSS 和浏览器中的其他图形元素。最新版本的铬也使用图形处理器组件进行视频渲染和处理。图形处理器比中央处理器消耗更少的功率，这降低了功耗，并产生更少的热量。GPU 还通过资源共享帮助平衡中央处理器的负载，因此，允许中央处理器执行更快的任务并承担更重的计算任务。Chromium 浏览器有一个专用的 GPU 选项卡，用于监控和显示系统中所有与 GPU 相关的信息。可以访问浏览器中的 **chrome://gpu/** 页面。电子还可以通过使用**应用程序**模块的实例事件和方法来访问和使用该应用程序的图形处理器相关信息。本教程将演示如何获取，显示和控制电子图形处理器相关的信息。

我们假设您熟悉上述链接中介绍的先决条件。电子要工作， [**节点**](https://www.geeksforgeeks.org/introduction-to-nodejs/) 和 [**npm**](https://www.geeksforgeeks.org/node-js-npm-node-package-manager/) 需要预装在系统中。

*   **项目结构:**

![Project Structure](img/8c3fc521d63aa10fa12672b9633662b1.png)

**示例:**按照 [**中的步骤在电子表格**](https://www.geeksforgeeks.org/printing-in-electronjs/) 中打印，以设置基本的电子应用程序。复制文章中提供的 **main.js** 文件和**index.html**文件的样板代码。此外，对**包进行必要的更改，以启动电子应用程序。我们将继续使用相同的代码库构建我们的应用程序。设置电子应用程序所需的基本步骤保持不变。**

**package.json:**

```htmlhtml
{
  "name": "electron-gpu",
  "version": "1.0.0",
  "description": "GPU Information in Electron",
  "main": "main.js",
  "scripts": {
    "start": "electron ."
  },
  "keywords": [
    "electron"
  ],
  "author": "Radhesh Khanna",
  "license": "ISC",
  "dependencies": {
    "electron": "^8.3.0"
  }
}
```

**输出:**

[![](img/b32d8f95392fcbe0adbaa31fa63d952f.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200512225834/Output-1105.png)

**电子中的 GPU 信息:**app 模块用于控制应用的事件生命周期。该模块是**主流程**的一部分。要在**渲染过程**中导入和使用**应用程序**模块，我们将使用电子**远程**模块。

*   **index.html**:在该文件中添加以下片段。

## 超文本标记语言

```htmlhtml
<h3>GPU Information in Electron</h3>
  <button id="metrics">
    Fetch App Metrics
  </button>
  <br><br>
  <button id="basic">
    Get Basic GPU Information
  </button>
  <br><br>
  <button id="complete">
    Get Complete GPU Information
  </button>
  <br><br>
  <button id="features">
    Get GPU Feature Status
  </button>
```

*   **index.js** :在**index.html**中创建的所有按钮将用于显示与图形处理器和应用程序相关的不同信息。这些按钮还没有任何相关的功能。要进行更改，请在 **index.js** 文件中添加以下代码。

## java 描述语言

```htmlhtml
const electron = require('electron')
// Importing the app module using Electron remote
const app = electron.remote.app;

app.on('gpu-info-update', () => {
    console.log('GPU Information has been Updated');
});

app.on('gpu-process-crashed', (event, killed) => {
    console.log('GPU Process has crashed');
    console.log(event);
    console.log('Whether GPU Process was killed - ', killed);
});

var metrics = document.getElementById('metrics');
metrics.addEventListener('click', () => {
    console.dir(app.getAppMetrics());
});

var basic = document.getElementById('basic');
basic.addEventListener('click', () => {
    app.getGPUInfo('basic').then(basicObj => {
        console.dir(basicObj);
    });
});

var complete = document.getElementById('complete');
complete.addEventListener('click', () => {
    app.getGPUInfo('complete').then(completeObj => {
        console.dir(completeObj);
    });
});

var features = document.getElementById('features');
features.addEventListener('click', () => {
    console.dir(app.getGPUFeatureStatus());
});
```

**应用程序**模块的 **app.getAppMetrics()** 实例方法用于返回一组**进程度量**对象，这些对象对应于与应用程序相关联的所有进程的内存和 CPU 使用统计数据。**过程度量**对象由以下参数组成。

*   **pid:整数**流程的**流程标识(PID)** 。应用程序中运行的每个进程都由数组中单独的**进程度量**对象表示。该参数很重要，因为 [**网络框架**](https://www.electronjs.org/docs/api/web-frame) 模块的几个实例方法使用 **PID** 作为输入参数。此参数对于调试和检查与应用程序相关联的本机系统操作系统中各种正在进行的进程的系统指标也很重要。
*   **类型:字符串**此参数表示应用程序中运行的进程的类型。此参数可以包含以下任何一个值:
    *   **浏览器**
    *   **标签**
    *   **效用**
    *   **合子**
    *   **沙盒助手**
    *   **GPU**
    *   **胡椒插件**
    *   **辣椒插件经纪人**
    *   **未知**
*   **cpu:对象**该参数返回一个 **cpuUsage** 对象，代表进程的 CPU 使用情况。该对象也可以从全局 **Process** 对象的 **process.getCPUUsage()** 实例方法中获得，并且行为完全相同。有关**对象及其行为的更多详细信息，请参考文章: [**电子表格中的【过程对象】**](https://www.geeksforgeeks.org/process-object-in-electronjs/) 。**
*   **创建时间:整数**该参数代表流程的创建时间。时间表示为自纪元以来的毫秒数。该参数也可以从全局**进程**对象的**进程. getCreationTime()** 实例方法中获得，并且行为完全相同。有关**创建时间**参数及其行为的更多详细信息，请参考文章: [**电子表格中的流程对象**](https://www.geeksforgeeks.org/process-object-in-electronjs/) 。
    **注意:**由于 **PID** 可以在进程死亡后被操作系统再次重用，因此同时使用 **pid** 参数和 **creationTime** 参数来唯一识别和区分一个进程是很有用的。
*   **内存**该参数返回一个**内存信息**对象，代表进程的内存信息。该对象由进程在实际物理**内存**上使用的内存的详细信息组成。它由以下参数组成。
    *   **工作集大小:整数**该参数表示进程当前固定到实际物理**内存**的内存量。
    *   **峰值工作集大小:整数**该参数表示进程固定到实际物理**内存**的最大内存量。
    *   **私有字节:整数(可选)**此参数仅在*视窗*操作系统中支持。此参数表示不被其他进程共享的内存量，如[**【V8 引擎内存堆】**](https://www.geeksforgeeks.org/create-a-v8-heap-snapshot-in-electronjs/) 或 HTML 内容。
*   **沙盒:布尔型(可选)**此参数仅在 Windows 和 macOS 中受支持。此参数表示进程是否在操作系统级别上被**沙箱化**。
*   **integrityLevel: String(可选)**此参数仅在 Windows OS 中受支持。此参数可以包含以下任何一个值:
    *   **不可信**
    *   **低**
    *   **中等**
    *   **高**
    *   **未知**

**应用程序**模块的**应用程序获取功能状态()**实例方法返回一个**功能状态**对象。该对象表示 chrome 浏览器中 **chrome://gpu** 页面中 GPU 的**图形特征状态**。

[![](img/aeb5359225fadb7baea4bda63354e7c4.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200725103643/Output-1110.png)

**注意:****gpuffeature status**对象由与上图所示完全相同的参数组成。为**图形特征状态**对象的参数显示的值是缩写格式，可能与图像中显示的不同。这些参数可以用它们各自的颜色代码保存以下任何一个值:

*   **禁用 _ 软件:黄色**仅限软件。硬件加速被禁用。
*   **禁用 _ 关闭:红色**
*   **禁用 _ 关闭 _ 正常:黄色**
*   **不可用 _ 软件:黄色**仅软件，硬件加速不可用。
*   **不可用 _ 关闭:红色**
*   **不可用 _ 关闭 _ 正常:黄色**
*   **enabled_readback:黄色**硬件加速但性能降低。
*   **enabled_force:绿色**所有页面硬件加速。
*   **启用:绿色**硬件加速。
*   **启用 _ 开启:绿色**
*   **启用 _ 强制开启:绿色**强制启用。

**应用程序**模块的**应用程序禁用硬件加速()**实例方法禁用整个应用程序的硬件加速。此实例方法只能在**应用程序**模块的**就绪**事件发出之前使用。因此，这个方法需要在 **main.js** 文件(Main Process)中调用。

## java 描述语言

```htmlhtml
const { app, BrowserWindow } = require('electron')
app.disableHardwareAcceleration();
```

在电子应用程序中，如果**图形处理器**进程崩溃过于频繁，Chromium 会禁用 3D 应用程序接口(例如 WebGL)，直到按域重新启动应用程序。这是 Chromium 的默认行为。可能有多种原因导致 GPU 进程频繁崩溃，包括系统硬件问题或系统资源的过度使用。 **app** 模块的**app . disabledomainblockingfor 3 API()**实例方法禁用 Chromium 的这个默认行为。该实例方法只能在 **app** 模块的**就绪**事件发出之前使用。因此，这个方法需要在 **main.js** 文件(Main Process)中调用。

## java 描述语言

```htmlhtml
const { app, BrowserWindow } = require('electron')
app.disableHardwareAcceleration();
app.disableDomainBlockingFor3DAPIs();
```

**app.getGPUInfo(info)** 实例方法从与电子应用程序相关的 Chromium 获取并返回 GPU 信息。该实例方法返回一个**承诺**，并根据提供的**信息:字符串**参数解析为一个包含相关信息的**对象**。为了更好地理解，请参考输出。**信息**参数可以保存以下任何一个值:

*   **完成:**返回的**承诺**通过一个**对象**实现，该对象包含官方 Chromium 的 [**GPUInfo**](https://chromium.googlesource.com/chromium/src/+/4178e190e9da409b055e5dff469911ec6f6b716f/gpu/config/gpu_info.cc) 对象文档中提到的所有 GPU 信息。这包括铬浏览器的 **chrome://gpu** 页面上显示的**版本**和**驱动程序**信息。当**信息:完成**时，实例方法的执行时间比**信息:基本**要长得多。请参考输出以获得更好的理解。

![Output for GPU Driver and Version Information - 1](img/53b86000f1c42ff1de0165e37cf23598.png)

图形处理器驱动程序和版本信息–1

![Output for GPU Driver and Version Information - 2](img/e5085f87099bf30aa16e7326f4ff74ea.png)

图形处理器驱动程序和版本信息–2

*   **基本:**返回的**承诺**通过一个**对象**实现，该对象仅包含比请求时返回的**对象**更少且更重要的参数**信息:完成**。如果只需要 **vendorId** 参数或 **driverId** 参数等基本信息，则应使用该值。返回的样本参数显示如下:

```htmlhtml
{ auxAttributes:
   { amdSwitchable: true,
     canSupportThreadedTextureMailbox: false,
     directComposition: false,
     directRendering: true,
     glResetNotificationStrategy: 0,
     inProcessGpu: true,
     initializationTime: 0,
     jpegDecodeAcceleratorSupported: false,
     optimus: false,
     passthroughCmdDecoder: false,
     sandboxed: false,
     softwareRendering: false,
     supportsOverlays: false,
     videoDecodeAcceleratorFlags: 0 },
gpuDevice:
   [ { active: true, deviceId: 26657, vendorId: 4098 },
     { active: false, deviceId: 3366, vendorId: 32902 } ],
machineModelName: 'MacBookPro',
machineModelVersion: '11.5' }
```

**应用程序**模块发出以下与**图形处理器**相关的实例事件。

*   **gpu-信息-更新:事件**每当应用程序中不同进程的任何 GPU 相关信息发生变化时，都会发出此实例事件。根据应用程序中活动进程的使用、功能和数量，可以多次发出此实例事件。
*   **gpu 进程崩溃:事件**每当 gpu 进程崩溃或被本机操作系统杀死时，都会发出此实例事件。如果不处理，这可能会导致应用程序挂起，因此我们可以使用这个实例事件来采取必要的操作，并使应用程序干净地退出。此事件返回以下参数。
    *   **事件:事件**全局事件对象。
    *   **被杀:布尔型**该参数表示进程是否被杀。

此时，一旦启动电子应用程序，我们应该能够在**控制台**输出中获取并显示所有与 GPU 相关的信息。

**输出:**

[![](img/ea549dea6188475fb9552f42f288bf8a.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200725123950/Output-4-GIF.gif)

**注意**–我们已经使用了 **console.dir()** JavaScript 方法在 Chrome DevTools 的 console 窗口中输出并显示了一个对象。要显示对象，此方法优于 **console.log()** 方法。

更多详细信息。参考文章:[**console . dir 和 console.log 的区别**](https://www.geeksforgeeks.org/difference-between-console-dir-and-console-log-2/) 。