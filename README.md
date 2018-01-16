##### Released API: [v1.0.0](https://github.com/GoogleChrome/puppeteer/blob/v1.0.0/docs/api.md) | [v0.13.0](https://github.com/GoogleChrome/puppeteer/blob/v0.13.0/docs/api.md) | [v0.12.0](https://github.com/GoogleChrome/puppeteer/blob/v0.12.0/docs/api.md) | [v0.11.0](https://github.com/GoogleChrome/puppeteer/blob/v0.11.0/docs/api.md) | [v0.10.2](https://github.com/GoogleChrome/puppeteer/blob/v0.10.2/docs/api.md) | [v0.10.1](https://github.com/GoogleChrome/puppeteer/blob/v0.10.1/docs/api.md) | [v0.10.0](https://github.com/GoogleChrome/puppeteer/blob/v0.10.0/docs/api.md) | [v0.9.0](https://github.com/GoogleChrome/puppeteer/blob/v0.9.0/docs/api.md)

# Puppeteer API v<!-- GEN:version -->1.0.0-post<!-- GEN:stop-->

##### 目录

<!-- toc -->

- [总览](#overview)
- [环境变量](#environment-variables)
- [class: Puppeteer](#class-puppeteer)
  * [puppeteer.connect(options)](#puppeteerconnectoptions)
  * [puppeteer.defaultArgs()](#puppeteerdefaultargs)
  * [puppeteer.executablePath()](#puppeteerexecutablepath)
  * [puppeteer.launch([options])](#puppeteerlaunchoptions)
- [class: Browser](#class-browser)
  * [event: 'disconnected'](#event-disconnected)
  * [event: 'targetchanged'](#event-targetchanged)
  * [event: 'targetcreated'](#event-targetcreated)
  * [event: 'targetdestroyed'](#event-targetdestroyed)
  * [browser.close()](#browserclose)
  * [browser.disconnect()](#browserdisconnect)
  * [browser.newPage()](#browsernewpage)
  * [browser.pages()](#browserpages)
  * [browser.process()](#browserprocess)
  * [browser.targets()](#browsertargets)
  * [browser.userAgent()](#browseruseragent)
  * [browser.version()](#browserversion)
  * [browser.wsEndpoint()](#browserwsendpoint)
- [class: Page](#class-page)
  * [event: 'console'](#event-console)
  * [event: 'dialog'](#event-dialog)
  * [event: 'error'](#event-error)
  * [event: 'frameattached'](#event-frameattached)
  * [event: 'framedetached'](#event-framedetached)
  * [event: 'framenavigated'](#event-framenavigated)
  * [event: 'load'](#event-load)
  * [event: 'metrics'](#event-metrics)
  * [event: 'pageerror'](#event-pageerror)
  * [event: 'request'](#event-request)
  * [event: 'requestfailed'](#event-requestfailed)
  * [event: 'requestfinished'](#event-requestfinished)
  * [event: 'response'](#event-response)
  * [page.$(selector)](#pageselector)
  * [page.$$(selector)](#pageselector)
  * [page.$$eval(selector, pageFunction[, ...args])](#pageevalselector-pagefunction-args)
  * [page.$eval(selector, pageFunction[, ...args])](#pageevalselector-pagefunction-args)
  * [page.$x(expression)](#pagexexpression)
  * [page.addScriptTag(options)](#pageaddscripttagoptions)
  * [page.addStyleTag(options)](#pageaddstyletagoptions)
  * [page.authenticate(credentials)](#pageauthenticatecredentials)
  * [page.bringToFront()](#pagebringtofront)
  * [page.click(selector[, options])](#pageclickselector-options)
  * [page.close()](#pageclose)
  * [page.content()](#pagecontent)
  * [page.cookies(...urls)](#pagecookiesurls)
  * [page.coverage](#pagecoverage)
  * [page.deleteCookie(...cookies)](#pagedeletecookiecookies)
  * [page.emulate(options)](#pageemulateoptions)
  * [page.emulateMedia(mediaType)](#pageemulatemediamediatype)
  * [page.evaluate(pageFunction, ...args)](#pageevaluatepagefunction-args)
  * [page.evaluateHandle(pageFunction, ...args)](#pageevaluatehandlepagefunction-args)
  * [page.evaluateOnNewDocument(pageFunction, ...args)](#pageevaluateonnewdocumentpagefunction-args)
  * [page.exposeFunction(name, puppeteerFunction)](#pageexposefunctionname-puppeteerfunction)
  * [page.focus(selector)](#pagefocusselector)
  * [page.frames()](#pageframes)
  * [page.goBack(options)](#pagegobackoptions)
  * [page.goForward(options)](#pagegoforwardoptions)
  * [page.goto(url, options)](#pagegotourl-options)
  * [page.hover(selector)](#pagehoverselector)
  * [page.keyboard](#pagekeyboard)
  * [page.mainFrame()](#pagemainframe)
  * [page.metrics()](#pagemetrics)
  * [page.mouse](#pagemouse)
  * [page.pdf(options)](#pagepdfoptions)
  * [page.queryObjects(prototypeHandle)](#pagequeryobjectsprototypehandle)
  * [page.reload(options)](#pagereloadoptions)
  * [page.screenshot([options])](#pagescreenshotoptions)
  * [page.select(selector, ...values)](#pageselectselector-values)
  * [page.setContent(html)](#pagesetcontenthtml)
  * [page.setCookie(...cookies)](#pagesetcookiecookies)
  * [page.setDefaultNavigationTimeout(timeout)](#pagesetdefaultnavigationtimeouttimeout)
  * [page.setExtraHTTPHeaders(headers)](#pagesetextrahttpheadersheaders)
  * [page.setJavaScriptEnabled(enabled)](#pagesetjavascriptenabledenabled)
  * [page.setOfflineMode(enabled)](#pagesetofflinemodeenabled)
  * [page.setRequestInterception(value)](#pagesetrequestinterceptionvalue)
  * [page.setUserAgent(userAgent)](#pagesetuseragentuseragent)
  * [page.setViewport(viewport)](#pagesetviewportviewport)
  * [page.tap(selector)](#pagetapselector)
  * [page.target()](#pagetarget)
  * [page.title()](#pagetitle)
  * [page.touchscreen](#pagetouchscreen)
  * [page.tracing](#pagetracing)
  * [page.type(selector, text[, options])](#pagetypeselector-text-options)
  * [page.url()](#pageurl)
  * [page.viewport()](#pageviewport)
  * [page.waitFor(selectorOrFunctionOrTimeout[, options[, ...args]])](#pagewaitforselectororfunctionortimeout-options-args)
  * [page.waitForFunction(pageFunction[, options[, ...args]])](#pagewaitforfunctionpagefunction-options-args)
  * [page.waitForNavigation(options)](#pagewaitfornavigationoptions)
  * [page.waitForSelector(selector[, options])](#pagewaitforselectorselector-options)
- [class: Keyboard](#class-keyboard)
  * [keyboard.down(key[, options])](#keyboarddownkey-options)
  * [keyboard.press(key[, options])](#keyboardpresskey-options)
  * [keyboard.sendCharacter(char)](#keyboardsendcharacterchar)
  * [keyboard.type(text, options)](#keyboardtypetext-options)
  * [keyboard.up(key)](#keyboardupkey)
- [class: Mouse](#class-mouse)
  * [mouse.click(x, y, [options])](#mouseclickx-y-options)
  * [mouse.down([options])](#mousedownoptions)
  * [mouse.move(x, y, [options])](#mousemovex-y-options)
  * [mouse.up([options])](#mouseupoptions)
- [class: Touchscreen](#class-touchscreen)
  * [touchscreen.tap(x, y)](#touchscreentapx-y)
- [class: Tracing](#class-tracing)
  * [tracing.start(options)](#tracingstartoptions)
  * [tracing.stop()](#tracingstop)
- [class: Dialog](#class-dialog)
  * [dialog.accept([promptText])](#dialogacceptprompttext)
  * [dialog.defaultValue()](#dialogdefaultvalue)
  * [dialog.dismiss()](#dialogdismiss)
  * [dialog.message()](#dialogmessage)
  * [dialog.type()](#dialogtype)
- [class: ConsoleMessage](#class-consolemessage)
  * [consoleMessage.args()](#consolemessageargs)
  * [consoleMessage.text()](#consolemessagetext)
  * [consoleMessage.type()](#consolemessagetype)
- [class: Frame](#class-frame)
  * [frame.$(selector)](#frameselector)
  * [frame.$$(selector)](#frameselector)
  * [frame.$$eval(selector, pageFunction[, ...args])](#frameevalselector-pagefunction-args)
  * [frame.$eval(selector, pageFunction[, ...args])](#frameevalselector-pagefunction-args)
  * [frame.$x(expression)](#framexexpression)
  * [frame.addScriptTag(options)](#frameaddscripttagoptions)
  * [frame.addStyleTag(options)](#frameaddstyletagoptions)
  * [frame.childFrames()](#framechildframes)
  * [frame.content()](#framecontent)
  * [frame.evaluate(pageFunction, ...args)](#frameevaluatepagefunction-args)
  * [frame.executionContext()](#frameexecutioncontext)
  * [frame.isDetached()](#frameisdetached)
  * [frame.name()](#framename)
  * [frame.parentFrame()](#frameparentframe)
  * [frame.select(selector, ...values)](#frameselectselector-values)
  * [frame.setContent(html)](#framesetcontenthtml)
  * [frame.title()](#frametitle)
  * [frame.url()](#frameurl)
  * [frame.waitFor(selectorOrFunctionOrTimeout[, options[, ...args]])](#framewaitforselectororfunctionortimeout-options-args)
  * [frame.waitForFunction(pageFunction[, options[, ...args]])](#framewaitforfunctionpagefunction-options-args)
  * [frame.waitForSelector(selector[, options])](#framewaitforselectorselector-options)
- [class: ExecutionContext](#class-executioncontext)
  * [executionContext.evaluate(pageFunction, ...args)](#executioncontextevaluatepagefunction-args)
  * [executionContext.evaluateHandle(pageFunction, ...args)](#executioncontextevaluatehandlepagefunction-args)
  * [executionContext.queryObjects(prototypeHandle)](#executioncontextqueryobjectsprototypehandle)
- [class: JSHandle](#class-jshandle)
  * [jsHandle.asElement()](#jshandleaselement)
  * [jsHandle.dispose()](#jshandledispose)
  * [jsHandle.executionContext()](#jshandleexecutioncontext)
  * [jsHandle.getProperties()](#jshandlegetproperties)
  * [jsHandle.getProperty(propertyName)](#jshandlegetpropertypropertyname)
  * [jsHandle.jsonValue()](#jshandlejsonvalue)
- [class: ElementHandle](#class-elementhandle)
  * [elementHandle.$(selector)](#elementhandleselector)
  * [elementHandle.$$(selector)](#elementhandleselector)
  * [elementHandle.$x(expression)](#elementhandlexexpression)
  * [elementHandle.asElement()](#elementhandleaselement)
  * [elementHandle.boundingBox()](#elementhandleboundingbox)
  * [elementHandle.click([options])](#elementhandleclickoptions)
  * [elementHandle.dispose()](#elementhandledispose)
  * [elementHandle.executionContext()](#elementhandleexecutioncontext)
  * [elementHandle.focus()](#elementhandlefocus)
  * [elementHandle.getProperties()](#elementhandlegetproperties)
  * [elementHandle.getProperty(propertyName)](#elementhandlegetpropertypropertyname)
  * [elementHandle.hover()](#elementhandlehover)
  * [elementHandle.jsonValue()](#elementhandlejsonvalue)
  * [elementHandle.press(key[, options])](#elementhandlepresskey-options)
  * [elementHandle.screenshot([options])](#elementhandlescreenshotoptions)
  * [elementHandle.tap()](#elementhandletap)
  * [elementHandle.toString()](#elementhandletostring)
  * [elementHandle.type(text[, options])](#elementhandletypetext-options)
  * [elementHandle.uploadFile(...filePaths)](#elementhandleuploadfilefilepaths)
- [class: Request](#class-request)
  * [request.abort([errorCode])](#requestaborterrorcode)
  * [request.continue([overrides])](#requestcontinueoverrides)
  * [request.failure()](#requestfailure)
  * [request.frame()](#requestframe)
  * [request.headers()](#requestheaders)
  * [request.method()](#requestmethod)
  * [request.postData()](#requestpostdata)
  * [request.resourceType()](#requestresourcetype)
  * [request.respond(response)](#requestrespondresponse)
  * [request.response()](#requestresponse)
  * [request.url()](#requesturl)
- [class: Response](#class-response)
  * [response.buffer()](#responsebuffer)
  * [response.headers()](#responseheaders)
  * [response.json()](#responsejson)
  * [response.ok()](#responseok)
  * [response.request()](#responserequest)
  * [response.status()](#responsestatus)
  * [response.text()](#responsetext)
  * [response.url()](#responseurl)
- [class: Target](#class-target)
  * [target.createCDPSession()](#targetcreatecdpsession)
  * [target.page()](#targetpage)
  * [target.type()](#targettype)
  * [target.url()](#targeturl)
- [class: CDPSession](#class-cdpsession)
  * [cdpSession.detach()](#cdpsessiondetach)
  * [cdpSession.send(method[, params])](#cdpsessionsendmethod-params)
- [class: Coverage](#class-coverage)
  * [coverage.startCSSCoverage(options)](#coveragestartcsscoverageoptions)
  * [coverage.startJSCoverage(options)](#coveragestartjscoverageoptions)
  * [coverage.stopCSSCoverage()](#coveragestopcsscoverage)
  * [coverage.stopJSCoverage()](#coveragestopjscoverage)

<!-- tocstop -->

### 总览

Puppeteer 是一个Node库，它提供了一个上层API通过DevTools Protocol来控制Chromium或Chrome.

Puppeteer API 是一个多层架构并且复制了浏览器的结构. 在下图中, 浅色的元素都是当前Puppeteer还没有提供的特性.

![puppeteer overview](https://user-images.githubusercontent.com/746130/31592143-089f6f9a-b1db-11e7-9a20-16b7fc754fa1.png)

- [`Puppeteer`](#class-puppeteer) 基于 [devtools protocol](https://chromedevtools.github.io/devtools-protocol/) 和浏览器通信.
- [`Browser`](#class-browser) 实例拥有多个 page.
- [`Page`](#class-page) 至少包含一个frame: main frame. 也可能会有其他的由 [iframe](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) 或 [frame](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/frame) 标签创建的frame.
- [`Frame`](#class-frame) 包含至少一个执行上下文 - default execution context - 在这里 frame 的 JavaScript 被执行. 由于 [extensions](https://developer.chrome.com/extensions)的帮助，Frame 有可能还有其他的执行上下文

(Diagram source: [link](https://docs.google.com/drawings/d/1Q_AM6KYs9kbyLZF-Lpp5mtpAWth73Cq8IKCsWYgi8MM/edit?usp=sharing))


### 环境变量

Puppeteer 会获取指定的 [环境变量](https://en.wikipedia.org/wiki/Environment_variable) 来辅助自己的行为. 这些变量既可以通过环境变量设置（系统级），也可以通过 [npm 配置](https://docs.npmjs.com/cli/config)来实现.

- `HTTP_PROXY`, `HTTPS_PROXY`, `NO_PROXY` - 定义了下载和运行Chromium所使用的http代理.
- `PUPPETEER_SKIP_CHROMIUM_DOWNLOAD` - 在安装阶段不要下载打包的Chromium.
- `PUPPETEER_DOWNLOAD_HOST` - 重写用于下载Chromium所使用URL中的host部分

### class: Puppeteer

Puppeteer 模块提供了一个方法来启动Chromium实例.
以下代码是使用Puppeteer做自动化的典型例子:
```js
const puppeteer = require('puppeteer');

puppeteer.launch().then(async browser => {
  const page = await browser.newPage();
  await page.goto('https://www.google.com');
  // other actions...
  await browser.close();
});
```

#### puppeteer.connect(options)
- `options` <[Object]>
  - `browserWSEndpoint` <[string]> 一个用于连接的 [browser websocket endpoint](#browserwsendpoint).
  - `ignoreHTTPSErrors` <[boolean]> 在导航阶段是否忽略HTTPS错误. 默认为 `false`.
- returns: <[Promise]<[Browser]>>

此方法将Puppeteer附加到一个已经存在的Chromium实例.

#### puppeteer.defaultArgs()
- returns: <[Array]<[string]>> 用于Chromium启动的默认的flags.

#### puppeteer.executablePath()
- returns: <[string]> 一个Puppeteer预期能够找到打包的Chromium的路径. 如果使用[`PUPPETEER_SKIP_CHROMIUM_DOWNLOAD`](#environment-variables)忽略下载的话, Chromium 可能不在那个位置.

#### puppeteer.launch([options])

- `options` <[Object]>  在browser上设置一些可配置的项. 它可以包含以下字段:
  - `ignoreHTTPSErrors` <[boolean]> 导航期间是否忽略 HTTPS 错误. 默认 `false`.
  - `headless` <[boolean]> 是否以[headless mode](https://developers.google.com/web/updates/2017/04/headless-chrome)模式运行browser. 除了 `devtools` 选项为 `true`的情况， 默认为 `true`.
  - `executablePath` <[string]> Chromium 或 Chrome 执行文件的目录 而非打包的Chromium. 如果 `executablePath` 是一个相对目录, 那么它将基于 [current working directory](https://nodejs.org/api/process.html#process_process_cwd) 的相对位置解析.
  - `slowMo` <[number]> 基于指定数量的毫秒数减慢 Puppeteer 的行为. 当你想要看清都有什么事情发生的时候会有用.
  - `args` <[Array]<[string]>> 用于传递给浏览器实例的额外的参数. Chromium 的 flags 列表可以去 [这里](http://peter.sh/experiments/chromium-command-line-switches/).
  - `ignoreDefaultArgs` <[boolean]> 不要使用 [`puppeteer.defaultArgs()`](#puppeteerdefaultargs). 危险的配置项; 使用时请小心. 默认 `false`.
  - `handleSIGINT` <[boolean]> 在你 Ctrl-C的时候结束浏览器进程. 默认 `true`.
  - `handleSIGTERM` <[boolean]> 在收到 SIGTERM 信号时结束浏览器进程. 默认 `true`.
  - `handleSIGHUP` <[boolean]> 在收到 SIGHUP 信号时结束浏览器进程. 默认 `true`.
  - `timeout` <[number]> 等待浏览器实例启动的毫秒数限制. 默认 `30000` (30 秒).  `0` 表示不限制.
  - `dumpio` <[boolean]> 是否将浏览器的标准输出和错误管道到 `process.stdout` 和 `process.stderr`. 默认 `false`.
  - `userDataDir` <[string]> [User Data Directory](https://chromium.googlesource.com/chromium/src/+/master/docs/user_data_dir.md) 的路径.
  - `env` <[Object]> 指定浏览器的环境变量. 默认为 `process.env`.
  - `devtools` <[boolean]> 是否自动给每个tab开启 DevTools 面板. 如果本选项设为 `true`, 则 `headless` 选项会被设置为 `false`.
- returns: <[Promise]<[Browser]>> resolve 一个 browser 实例的 Promise.

这个方法使用给定的参数启动一个浏览器实例. 浏览器进程会在node.js进程结束时自动关闭.

> **NOTE** Puppeteer 也可以用于控制 Chrome 浏览器, 但是它最好和对应的打包版本的 Chromium. 在不对应的版本上并不保证运行. 使用 `executablePath` 选项需要额外的注意.
如果你更喜欢 Google Chrome , 建议使用 [Chrome Canary](https://www.google.com/chrome/browser/canary.html) 或 [Dev Channel](https://www.chromium.org/getting-involved/dev-channel) 版本.
>
> 在前面的 [puppeteer.launch([options])](#puppeteerlaunchoptions) , 所有提及 Chromium 的内容同样适用 Chrome.
>
> 请阅读 [`这篇文章`](https://www.howtogeek.com/202825/what%E2%80%99s-the-difference-between-chromium-and-chrome/) 了解 Chromium 和 Chrome 的不同. [`这篇文章`](https://chromium.googlesource.com/chromium/src/+/lkcr/docs/chromium_browser_vs_google_chrome.md) 描述了 Linux 用户的一些不同.

### class: Browser

* extends: [`EventEmitter`](https://nodejs.org/api/events.html#events_class_eventemitter)

当 Puppeteer 链接到 Chromium 实例的时候， 一个 Browser 就会被创建, 不论是通过 [`puppeteer.launch`](#puppeteerlaunchoptions) 还是 [`puppeteer.connect`](#puppeteerconnectoptions).

使用一个 [Browser] 创建一个 [Page] 的例子:
```js
const puppeteer = require('puppeteer');

puppeteer.launch().then(async browser => {
  const page = await browser.newPage();
  await page.goto('https://example.com');
  await browser.close();
});
```

一个断开和重连到一个 [Browser] 的例子:
```js
const puppeteer = require('puppeteer');

puppeteer.launch().then(async browser => {
  // Store the endpoint to be able to reconnect to Chromium
  const browserWSEndpoint = browser.wsEndpoint();
  // Disconnect puppeteer from Chromium
  browser.disconnect();

  // Use the endpoint to reestablish a connection
  const browser2 = await puppeteer.connect({browserWSEndpoint});
  // Close Chromium
  await browser2.close();
});
```
#### event: 'disconnected'
当 puppeteer 从 Chromium 实例断开时触发. 出现这种情况可能是因为以下原因:
- Chromium 被关闭或崩溃
- `browser.disconnect` 方法被调用

#### event: 'targetchanged'
- <[Target]>

在 target 的 url 变化时触发.

#### event: 'targetcreated'
- <[Target]>

当一个 target 被创建时触发, 例如当一个页面由 [`window.open`](https://developer.mozilla.org/en-US/docs/Web/API/Window/open) 或 [`browser.newPage`](#browsernewpage) 创建时.

#### event: 'targetdestroyed'
- <[Target]>

当 target 被销毁时触发, 例如页面被关闭.

#### browser.close()
- returns: <[Promise]>

关闭 Chromium 和它的所有页面. browser 对象本身被认为是已销毁并且无法使用的.

#### browser.disconnect()

将 Puppeteer 从浏览器断开, 但是保留 Chromium 进程继续运行. 在 `disconnect` 之后, browser 对象被认为是已销毁并且无法使用的.

#### browser.newPage()
- returns: <[Promise]<[Page]>> resolve 一个新的 [Page] 对象的 Promise.

#### browser.pages()
- returns: <[Promise]<[Array]<[Page]>>> resolve 一个包含所有打开页面的数组 的 Promise.

#### browser.process()
- returns: <?[ChildProcess]> Spawned 浏览器进程. 如果通过 `puppeteer.connect` 方法创建则返回 `null`.

#### browser.targets()
- returns: <[Array]<[Target]>> 一个包含所有活跃 target 的数组.

#### browser.userAgent()
- returns: <[Promise]<[string]>> resolve 浏览器原始 user agent 的 Promise.

> **NOTE** Pages 可以通过 [page.setUserAgent](#pagesetuseragentuseragent) 设置覆盖浏览器的 user agent

#### browser.version()
- returns: <[Promise]<[string]>> 对于 headless 的 Chromium, 结果类似于 `HeadlessChrome/61.0.3153.0`. 对于非 headless 模式的, 结果类似于 `Chrome/61.0.3153.0`.

> **NOTE** browser.version() 的格式有可能在未来的 Chromium 发布中发生变化.

#### browser.wsEndpoint()
- returns: <[string]> 浏览器的 websocket url.

浏览器的 websocket endpoint 可以作为 [puppeteer.connect](#puppeteerconnectoptions) 的参数. 格式： `ws://${host}:${port}/devtools/browser/<id>`

你可以在 `http://${host}:${port}/json/version` 找到 `webSocketDebuggerUrl`. 点击了解更多关于 [devtools protocol](https://chromedevtools.github.io/devtools-protocol) 和 [browser endpoint](https://chromedevtools.github.io/devtools-protocol/#how-do-i-access-the-browser-target) 的信息.

### class: Page

* extends: [`EventEmitter`](https://nodejs.org/api/events.html#events_class_eventemitter)

Page 提供了各种方法来和 Chromium 中一个单独的 tab 交互. 一个 [Browser] 实例可以包含多个 [Page] 实例.

本例子展示了创建一个 page， 导航到一个 URL， 然后保存截图:
```js
const puppeteer = require('puppeteer');

puppeteer.launch().then(async browser => {
  const page = await browser.newPage();
  await page.goto('https://example.com');
  await page.screenshot({path: 'screenshot.png'});
  await browser.close();
});
```

Page 类触发多种 events (下面会细讲) ， 这些 events 可以通过 node.js 原生的 EventEmitter 方法来处理, 例如 `on` 或者 `once`.

这个例子在一个页面 `load` event 触发时输出日志:
```js
page.once('load', () => console.log('Page loaded!'));
```

#### event: 'console'
- <[ConsoleMessage]>

当页面中的 JavaScript 调用 console API 方法时触发, 例如 `console.log` 或 `console.dir`. 在页面抛出错误或警告时也会触发.

传递到 `console.log` 的参数会作为 event handler 的参数.

一个处理 `console` 事件的例子:
```js
page.on('console', msg => {
  for (let i = 0; i < msg.args.length; ++i)
    console.log(`${i}: ${msg.args[i]}`);
});
page.evaluate(() => console.log('hello', 5, {foo: 'bar'}));
```

#### event: 'dialog'
- <[Dialog]>

当 JavaScript 弹窗出现时触发 , 例如 `alert`, `prompt`, `confirm` 或 `beforeunload`. Puppeteer 可以通过 [Dialog]'s [accept](#dialogacceptprompttext) 或 [dismiss](#dialogdismiss) 对这些弹窗进行应答.

#### event: 'error'
- <[Error]>

当页面崩溃时触发.

> **NOTE** `error` 事件在Node中具有特殊的含义, 参考 [error events](https://nodejs.org/api/events.html#events_error_events) 了解详情.

#### event: 'frameattached'
- <[Frame]>

当一个 frame 接入的时候触发.

#### event: 'framedetached'
- <[Frame]>

当一个 frame 移除的时候触发.

#### event: 'framenavigated'
- <[Frame]>

当一个frame导航到新的url时触发.

#### event: 'load'

当 JavaScript [`load`](https://developer.mozilla.org/en-US/docs/Web/Events/load) 事件分发的时候触发.

#### event: 'metrics'
- <[Object]>
  - `title` <[string]> 传递给 `console.timeStamp` 的标题.
  - `metrics` <[Object]> 包含 metrics 作为键值对. metrics 的值都是 <[number]> 类型.

当 JavaScript 代码调用 `console.timeStamp` 时触发. 参考 `page.metrics` 了解 metrics 列表.

#### event: 'pageerror'
- <[string]> 异常的消息文本

当页面内出现未捕获的异常时触发.

#### event: 'request'
- <[Request]>

当页面发起一个请求时触发. [request] 对象是只读的.
想要拦截和修改请求，参考 `page.setRequestInterception`.

#### event: 'requestfailed'
- <[Request]>

当一个请求失败时触发, 例如超时.

#### event: 'requestfinished'
- <[Request]>

Emitted when a request finishes successfully.

#### event: 'response'
- <[Response]>

Emitted when a [response] is received.

#### page.$(selector)
- `selector` <[string]> A [selector] to query page for
- returns: <[Promise]<?[ElementHandle]>>

The method runs `document.querySelector` within the page. If no element matches the selector, the return value resolve to `null`.

Shortcut for [page.mainFrame().$(selector)](#frameselector).

#### page.$$(selector)
- `selector` <[string]> A [selector] to query page for
- returns: <[Promise]<[Array]<[ElementHandle]>>>

The method runs `document.querySelectorAll` within the page. If no elements match the selector, the return value resolve to `[]`.

Shortcut for [page.mainFrame().$$(selector)](#frameselector-1).


#### page.$$eval(selector, pageFunction[, ...args])
- `selector` <[string]> A [selector] to query frame for
- `pageFunction` <[function]> Function to be evaluated in browser context
- `...args` <...[Serializable]|[JSHandle]> Arguments to pass to `pageFunction`
- returns: <[Promise]<[Serializable]>> Promise which resolves to the return value of `pageFunction`

This method runs `document.querySelectorAll` within the page and passes it as the first argument to `pageFunction`.

If `pageFunction` returns a [Promise], then `page.$$eval` would wait for the promise to resolve and return its value.

Examples:
```js
const divsCounts = await page.$$eval('div', divs => divs.length);
```

#### page.$eval(selector, pageFunction[, ...args])
- `selector` <[string]> A [selector] to query page for
- `pageFunction` <[function]> Function to be evaluated in browser context
- `...args` <...[Serializable]|[JSHandle]> Arguments to pass to `pageFunction`
- returns: <[Promise]<[Serializable]>> Promise which resolves to the return value of `pageFunction`

This method runs `document.querySelector` within the page and passes it as the first argument to `pageFunction`. If there's no element matching `selector`, the method throws an error.

If `pageFunction` returns a [Promise], then `page.$eval` would wait for the promise to resolve and return its value.

Examples:
```js
const searchValue = await page.$eval('#search', el => el.value);
const preloadHref = await page.$eval('link[rel=preload]', el => el.href);
const html = await page.$eval('.main-container', e => e.outerHTML);
```

Shortcut for [page.mainFrame().$eval(selector, pageFunction)](#frameevalselector-pagefunction-args).

#### page.$x(expression)
- `expression` <[string]> Expression to [evaluate](https://developer.mozilla.org/en-US/docs/Web/API/Document/evaluate).
- returns: <[Promise]<[Array]<[ElementHandle]>>>

The method evluates the XPath expression.

Shortcut for [page.mainFrame().$x(expression)](#frameexpression)

#### page.addScriptTag(options)
- `options` <[Object]>
  - `url` <[string]> Url of a script to be added.
  - `path` <[string]> Path to the JavaScript file to be injected into frame. If `path` is a relative path, then it is resolved relative to [current working directory](https://nodejs.org/api/process.html#process_process_cwd).
  - `content` <[string]> Raw JavaScript content to be injected into frame.
- returns: <[Promise]<[ElementHandle]>> which resolves to the added tag when the script's onload fires or when the script content was injected into frame.

Adds a `<script>` tag into the page with the desired url or content.

Shortcut for [page.mainFrame().addScriptTag(options)](#frameaddscripttagoptions).

#### page.addStyleTag(options)
- `options` <[Object]>
  - `url` <[string]> Url of the `<link>` tag.
  - `path` <[string]> Path to the CSS file to be injected into frame. If `path` is a relative path, then it is resolved relative to [current working directory](https://nodejs.org/api/process.html#process_process_cwd).
  - `content` <[string]> Raw CSS content to be injected into frame.
- returns: <[Promise]<[ElementHandle]>> which resolves to the added tag when the stylesheet's onload fires or when the CSS content was injected into frame.

Adds a `<link rel="stylesheet">` tag into the page with the desired url or a `<style type="text/css">` tag with the content.

Shortcut for [page.mainFrame().addStyleTag(options)](#frameaddstyletagoptions).

#### page.authenticate(credentials)
- `credentials` <?[Object]>
  - `username` <[string]>
  - `password` <[string]>
- returns: <[Promise]>

Provide credentials for [http authentication](https://developer.mozilla.org/en-US/docs/Web/HTTP/Authentication).

To disable authentication, pass `null`.

#### page.bringToFront()

- returns: <[Promise]>

Brings page to front (activates tab).

#### page.click(selector[, options])
- `selector` <[string]> A [selector] to search for element to click. If there are multiple elements satisfying the selector, the first will be clicked.
- `options` <[Object]>
  - `button` <[string]> `left`, `right`, or `middle`, defaults to `left`.
  - `clickCount` <[number]> defaults to 1. See [UIEvent.detail].
  - `delay` <[number]> Time to wait between `mousedown` and `mouseup` in milliseconds. Defaults to 0.
- returns: <[Promise]> Promise which resolves when the element matching `selector` is successfully clicked. The Promise will be rejected if there is no element matching `selector`.

This method fetches an element with `selector`, scrolls it into view if needed, and then uses [page.mouse](#pagemouse) to click in the center of the element.
If there's no element matching `selector`, the method throws an error.

Bare in mind that if `click()` triggers a navigation event and there's a separate `page.waitForNavigation()` promise to be resolved, you may end up with a race condition that yields unexpected results. The correct pattern for click and wait for navigation is the following:

```javascript
const [response] = await Promise.all([
  this.waitForNavigation(waitOptions),
  this.click(selector, clickOptions),
]);
```

#### page.close()
- returns: <[Promise]>

#### page.content()
- returns: <[Promise]<[String]>>

Gets the full HTML contents of the page, including the doctype.

#### page.cookies(...urls)
- `...urls` <...[string]>
- returns: <[Promise]<[Array]<[Object]>>>
  - `name` <[string]>
  - `value` <[string]>
  - `domain` <[string]>
  - `path` <[string]>
  - `expires` <[number]> Unix time in seconds.
  - `httpOnly` <[boolean]>
  - `secure` <[boolean]>
  - `session` <[boolean]>
  - `sameSite` <[string]> `"Strict"` or `"Lax"`.

If no URLs are specified, this method returns cookies for the current page URL.
If URLs are specified, only cookies for those URLs are returned.

#### page.coverage

- returns: <[Coverage]>

#### page.deleteCookie(...cookies)
- `...cookies` <...[Object]>
  - `name` <[string]> **required**
  - `url` <[string]>
  - `domain` <[string]>
  - `path` <[string]>
  - `secure` <[boolean]>
- returns: <[Promise]>

#### page.emulate(options)
- `options` <[Object]>
  - `viewport` <[Object]>
    - `width` <[number]> page width in pixels.
    - `height` <[number]> page height in pixels.
    - `deviceScaleFactor` <[number]> Specify device scale factor (can be thought of as dpr). Defaults to `1`.
    - `isMobile` <[boolean]> Whether the `meta viewport` tag is taken into account. Defaults to `false`.
    - `hasTouch`<[boolean]> Specifies if viewport supports touch events. Defaults to `false`
    - `isLandscape` <[boolean]> Specifies if viewport is in landscape mode. Defaults to `false`.
  - `userAgent` <[string]>
- returns: <[Promise]>

Emulates given device metrics and user agent. This method is a shortcut for calling two methods:
- [page.setUserAgent(userAgent)](#pagesetuseragentuseragent)
- [page.setViewport(viewport)](#pagesetviewportviewport)

To aid emulation, puppeteer provides a list of device descriptors which can be obtained via the `require('puppeteer/DeviceDescriptors')` command.
Below is an example of emulating an iPhone 6 in puppeteer:
```js
const puppeteer = require('puppeteer');
const devices = require('puppeteer/DeviceDescriptors');
const iPhone = devices['iPhone 6'];

puppeteer.launch().then(async browser => {
  const page = await browser.newPage();
  await page.emulate(iPhone);
  await page.goto('https://www.google.com');
  // other actions...
  await browser.close();
});
```

List of all available devices is available in the source code: [DeviceDescriptors.js](https://github.com/GoogleChrome/puppeteer/blob/master/DeviceDescriptors.js).

#### page.emulateMedia(mediaType)
  - `mediaType` <?[string]> Changes the CSS media type of the page. The only allowed values are `'screen'`, `'print'` and `null`. Passing `null` disables media emulation.
  - returns: <[Promise]>

#### page.evaluate(pageFunction, ...args)
- `pageFunction` <[function]|[string]> Function to be evaluated in the page context
- `...args` <...[Serializable]|[JSHandle]> Arguments to pass to `pageFunction`
- returns: <[Promise]<[Serializable]>> Resolves to the return value of `pageFunction`

If the function, passed to the `page.evaluate`, returns a [Promise], then `page.evaluate` would wait for the promise to resolve and return its value.

If the function passed into `page.evaluate` returns a non-[Serializable] value, then `page.evaluate` resolves to `undefined`.
Passing arguments to ```pageFunction```.

```js
const result = await page.evaluate(x => {
  return Promise.resolve(8 * x);
}, 7);
console.log(result); // prints "56"
```

A string can also be passed in instead of a function.

```js
console.log(await page.evaluate('1 + 2')); // prints "3"
const x = 10;
console.log(await page.evaluate(`1 + ${x}`)); // prints "11"
```

[ElementHandle] instances can be passed as arguments to the `page.evaluate`:
```js
const bodyHandle = await page.$('body');
const html = await page.evaluate(body => body.innerHTML, bodyHandle);
await bodyHandle.dispose();
```

Shortcut for [page.mainFrame().evaluate(pageFunction, ...args)](#frameevaluatepagefunction-args).

#### page.evaluateHandle(pageFunction, ...args)
- `pageFunction` <[function]|[string]> Function to be evaluated in the page context
- `...args` <...[Serializable]|[JSHandle]> Arguments to pass to `pageFunction`
- returns: <[Promise]<[JSHandle]>> Resolves to the return value of `pageFunction`

If the function, passed to the `page.evaluateHandle`, returns a [Promise], then `page.evaluateHandle` would wait for the promise to resolve and return its value.

```js
const aWindowHandle = await page.evaluateHandle(() => Promise.resolve(window));
aWindowHandle; // Handle for the window object.
```

A string can also be passed in instead of a function.

```js
const aHandle = await page.evaluateHandle('document'); // Handle for the 'document'.
```

[JSHandle] instances can be passed as arguments to the `page.evaluateHandle`:
```js
const aHandle = await page.evaluateHandle(() => document.body);
const resultHandle = await page.evaluateHandle(body => body.innerHTML, aHandle);
console.log(await resultHandle.jsonValue());
await resultHandle.dispose();
```

Shortcut for [page.mainFrame().executionContext().evaluateHandle(pageFunction, ...args)](#executioncontextevaluatehandlepagefunction-args).


#### page.evaluateOnNewDocument(pageFunction, ...args)
- `pageFunction` <[function]|[string]> Function to be evaluated in browser context
- `...args` <...[Serializable]> Arguments to pass to `pageFunction`
- returns: <[Promise]>

Adds a function which would be invoked in one of the following scenarios:
- whenever the page is navigated
- whenever the child frame is attached or navigated. In this case, the function is invoked in the context of the newly attached frame

The function is invoked after the document was created but before any of its scripts were run. This is useful to amend JavaScript environment, e.g. to seed `Math.random`.

An example of overriding the navigator.languages property before the page loads:

```js
// preload.js

// overwrite the `languages` property to use a custom getter
Object.defineProperty(navigator, "languages", {
  get: function() {
    return ["en-US", "en", "bn"];
  };
});

// In your puppeteer script, assuming the preload.js file is in same folder of our script
const preloadFile = fs.readFileSync('./preload.js', 'utf8');
await page.evaluateOnNewDocument(preloadFile);
```

#### page.exposeFunction(name, puppeteerFunction)
- `name` <[string]> Name of the function on the window object
- `puppeteerFunction` <[function]> Callback function which will be called in Puppeteer's context.
- returns: <[Promise]>

The method adds a function called `name` on the page's `window` object.
When called, the function executes `puppeteerFunction` in node.js and returns a [Promise] which resolves to the return value of `puppeteerFunction`.

If the `puppeteerFunction` returns a [Promise], it will be awaited.

> **NOTE** Functions installed via `page.exposeFunction` survive navigations.

An example of adding an `md5` function into the page:
```js
const puppeteer = require('puppeteer');
const crypto = require('crypto');

puppeteer.launch().then(async browser => {
  const page = await browser.newPage();
  page.on('console', msg => console.log(msg.text));
  await page.exposeFunction('md5', text =>
    crypto.createHash('md5').update(text).digest('hex')
  );
  await page.evaluate(async () => {
    // use window.md5 to compute hashes
    const myString = 'PUPPETEER';
    const myHash = await window.md5(myString);
    console.log(`md5 of ${myString} is ${myHash}`);
  });
  await browser.close();
});
```

An example of adding a `window.readfile` function into the page:

```js
const puppeteer = require('puppeteer');
const fs = require('fs');

puppeteer.launch().then(async browser => {
  const page = await browser.newPage();
  page.on('console', msg => console.log(msg.text));
  await page.exposeFunction('readfile', async filePath => {
    return new Promise((resolve, reject) => {
      fs.readFile(filePath, 'utf8', (err, text) => {
        if (err)
          reject(err);
        else
          resolve(text);
      });
    });
  });
  await page.evaluate(async () => {
    // use window.readfile to read contents of a file
    const content = await window.readfile('/etc/hosts');
    console.log(content);
  });
  await browser.close();
});

```

#### page.focus(selector)
- `selector` <[string]> A [selector] of an element to focus. If there are multiple elements satisfying the selector, the first will be focused.
- returns: <[Promise]> Promise which resolves when the element matching `selector` is successfully focused. The promise will be rejected if there is no element matching `selector`.

This method fetches an element with `selector` and focuses it.
If there's no element matching `selector`, the method throws an error.

#### page.frames()
- returns: <[Array]<[Frame]>> An array of all frames attached to the page.

#### page.goBack(options)
- `options` <[Object]> Navigation parameters which might have the following properties:
  - `timeout` <[number]> Maximum navigation time in milliseconds, defaults to 30 seconds, pass `0` to disable timeout. The default value can be changed by using the [page.setDefaultNavigationTimeout(timeout)](#pagesetdefaultnavigationtimeouttimeout) method.
  - `waitUntil` <[string]|[Array]<[string]>> When to consider navigation succeeded, defaults to `load`. Given an array of event strings, navigation is considered to be successful after all events have been fired. Events can be either:
    - `load` - consider navigation to be finished when the `load` event is fired.
    - `domcontentloaded` - consider navigation to be finished when the `DOMContentLoaded` event is fired.
    - `networkidle0` - consider navigation to be finished when there are no more than 0 network connections for at least `500` ms.
    - `networkidle2` - consider navigation to be finished when there are no more than 2 network connections for at least `500` ms.
- returns: <[Promise]<?[Response]>> Promise which resolves to the main resource response. In case of multiple redirects, the navigation will resolve with the response of the last redirect. If
can not go back, resolves to `null`.

Navigate to the previous page in history.

#### page.goForward(options)
- `options` <[Object]> Navigation parameters which might have the following properties:
  - `timeout` <[number]> Maximum navigation time in milliseconds, defaults to 30 seconds, pass `0` to disable timeout. The default value can be changed by using the [page.setDefaultNavigationTimeout(timeout)](#pagesetdefaultnavigationtimeouttimeout) method.
  - `waitUntil` <[string]|[Array]<[string]>> When to consider navigation succeeded, defaults to `load`. Given an array of event strings, navigation is considered to be successful after all events have been fired. Events can be either:
    - `load` - consider navigation to be finished when the `load` event is fired.
    - `domcontentloaded` - consider navigation to be finished when the `DOMContentLoaded` event is fired.
    - `networkidle0` - consider navigation to be finished when there are no more than 0 network connections for at least `500` ms.
    - `networkidle2` - consider navigation to be finished when there are no more than 2 network connections for at least `500` ms.
- returns: <[Promise]<?[Response]>> Promise which resolves to the main resource response. In case of multiple redirects, the navigation will resolve with the response of the last redirect. If
can not go back, resolves to `null`.

Navigate to the next page in history.

#### page.goto(url, options)
- `url` <[string]> URL to navigate page to. The url should include scheme, e.g. `https://`.
- `options` <[Object]> Navigation parameters which might have the following properties:
  - `timeout` <[number]> Maximum navigation time in milliseconds, defaults to 30 seconds, pass `0` to disable timeout. The default value can be changed by using the [page.setDefaultNavigationTimeout(timeout)](#pagesetdefaultnavigationtimeouttimeout) method.
  - `waitUntil` <[string]|[Array]<[string]>> When to consider navigation succeeded, defaults to `load`. Given an array of event strings, navigation is considered to be successful after all events have been fired. Events can be either:
    - `load` - consider navigation to be finished when the `load` event is fired.
    - `domcontentloaded` - consider navigation to be finished when the `DOMContentLoaded` event is fired.
    - `networkidle0` - consider navigation to be finished when there are no more than 0 network connections for at least `500` ms.
    - `networkidle2` - consider navigation to be finished when there are no more than 2 network connections for at least `500` ms.
- returns: <[Promise]<?[Response]>> Promise which resolves to the main resource response. In case of multiple redirects, the navigation will resolve with the response of the last redirect.

The `page.goto` will throw an error if:
- there's an SSL error (e.g. in case of self-signed certificates).
- target URL is invalid.
- the `timeout` is exceeded during navigation.
- the main resource failed to load.

> **NOTE** `page.goto` either throw or return a main resource response. The only exception is navigation to `about:blank`, which would succeed and return `null`.

> **NOTE** Headless mode doesn't support navigating to a PDF document. See the [upstream issue](https://bugs.chromium.org/p/chromium/issues/detail?id=761295).

#### page.hover(selector)
- `selector` <[string]> A [selector] to search for element to hover. If there are multiple elements satisfying the selector, the first will be hovered.
- returns: <[Promise]> Promise which resolves when the element matching `selector` is successfully hovered. Promise gets rejected if there's no element matching `selector`.

This method fetches an element with `selector`, scrolls it into view if needed, and then uses [page.mouse](#pagemouse) to hover over the center of the element.
If there's no element matching `selector`, the method throws an error.

#### page.keyboard

- returns: <[Keyboard]>

#### page.mainFrame()
- returns: <[Frame]> returns page's main frame.

Page is guaranteed to have a main frame which persists during navigations.

#### page.metrics()
- returns: <[Promise]<[Object]>> Object containing metrics as key/value pairs.
  - `Timestamp` <[number]> The timestamp when the metrics sample was taken.
  - `Documents` <[number]> Number of documents in the page.
  - `Frames` <[number]> Number of frames in the page.
  - `JSEventListeners` <[number]> Number of events in the page.
  - `Nodes` <[number]> Number of DOM nodes in the page.
  - `LayoutCount` <[number]> Total number of full or partial page layout.
  - `RecalcStyleCount` <[number]> Total number of page style recalculations.
  - `LayoutDuration` <[number]> Combined durations of all page layouts.
  - `RecalcStyleDuration` <[number]> Combined duration of all page style recalculations.
  - `ScriptDuration` <[number]> Combined duration of JavaScript execution.
  - `TaskDuration` <[number]> Combined duration of all tasks performed by the browser.
  - `JSHeapUsedSize` <[number]> Used JavaScript heap size.
  - `JSHeapTotalSize` <[number]> Total JavaScript heap size.

> **NOTE** All timestamps are in monotonic time: monotonically increasing time in seconds since an arbitrary point in the past.

#### page.mouse

- returns: <[Mouse]>

#### page.pdf(options)
- `options` <[Object]> Options object which might have the following properties:
  - `path` <[string]> The file path to save the PDF to. If `path` is a relative path, then it is resolved relative to [current working directory](https://nodejs.org/api/process.html#process_process_cwd). If no path is provided, the PDF won't be saved to the disk.
  - `scale` <[number]> Scale of the webpage rendering. Defaults to `1`.
  - `displayHeaderFooter` <[boolean]> Display header and footer. Defaults to `false`.
  - `headerTemplate` <[string]> HTML template for the print header. Should be valid HTML markup with following classes used to inject printing values into them:
    - `date` formatted print date
    - `title` document title
    - `url` document location
    - `pageNumber` current page number
    - `totalPages` total pages in the document
  - `footerTemplate` <[string]> HTML template for the print footer. Should use the same format as the `headerTemplate`.
  - `printBackground` <[boolean]> Print background graphics. Defaults to `false`.
  - `landscape` <[boolean]> Paper orientation. Defaults to `false`.
  - `pageRanges` <[string]> Paper ranges to print, e.g., '1-5, 8, 11-13'. Defaults to the empty string, which means print all pages.
  - `format` <[string]> Paper format. If set, takes priority over `width` or `height` options. Defaults to 'Letter'.
  - `width` <[string]> Paper width, accepts values labeled with units.
  - `height` <[string]> Paper height, accepts values labeled with units.
  - `margin` <[Object]> Paper margins, defaults to none.
    - `top` <[string]> Top margin, accepts values labeled with units.
    - `right` <[string]> Right margin, accepts values labeled with units.
    - `bottom` <[string]> Bottom margin, accepts values labeled with units.
    - `left` <[string]> Left margin, accepts values labeled with units.
- returns: <[Promise]<[Buffer]>> Promise which resolves with PDF buffer.

> **NOTE** Generating a pdf is currently only supported in Chrome headless.

`page.pdf()` generates a pdf of the page with `print` css media. To generate a pdf with `screen` media, call [page.emulateMedia('screen')](#pageemulatemediamediatype) before calling `page.pdf()`:

```js
// Generates a PDF with 'screen' media type.
await page.emulateMedia('screen');
await page.pdf({path: 'page.pdf'});
```

The `width`, `height`, and `margin` options accept values labeled with units. Unlabeled values are treated as pixels.

A few examples:
- `page.pdf({width: 100})` - prints with width set to 100 pixels
- `page.pdf({width: '100px'})` - prints with width set to 100 pixels
- `page.pdf({width: '10cm'})` - prints with width set to 10 centimeters.

All possible units are:
- `px` - pixel
- `in` - inch
- `cm` - centimeter
- `mm` - millimeter

The `format` options are:
- `Letter`: 8.5in x 11in
- `Legal`: 8.5in x 14in
- `Tabloid`: 11in x 17in
- `Ledger`: 17in x 11in
- `A0`: 33.1in x 46.8in
- `A1`: 23.4in x 33.1in
- `A2`: 16.5in x 23.4in
- `A3`: 11.7in x 16.5in
- `A4`: 8.27in x 11.7in
- `A5`: 5.83in x 8.27in
- `A6`: 4.13in x 5.83in

#### page.queryObjects(prototypeHandle)
- `prototypeHandle` <[JSHandle]> A handle to the object prototype.
- returns: <[Promise]<[JSHandle]>> Promise which resolves to a handle to an array of objects with this prototype.

The method iterates JavaScript heap and finds all the objects with the given prototype.

```js
// Create a Map object
await page.evaluate(() => window.map = new Map());
// Get a handle to the Map object prototype
const mapPrototype = await page.evaluateHandle(() => Map.prototype);
// Query all map instances into an array
const mapInstances = await page.queryObjects(mapPrototype);
// Count amount of map objects in heap
const count = await page.evaluate(maps => maps.length, mapInstances);
await mapInstances.dispose();
await mapPrototype.dispose();
```

Shortcut for [page.mainFrame().executionContext().queryObjects(prototypeHandle)](#executioncontextqueryobjectsprototypehandle).

#### page.reload(options)
- `options` <[Object]> Navigation parameters which might have the following properties:
  - `timeout` <[number]> Maximum navigation time in milliseconds, defaults to 30 seconds, pass `0` to disable timeout. The default value can be changed by using the [page.setDefaultNavigationTimeout(timeout)](#pagesetdefaultnavigationtimeouttimeout) method.
  - `waitUntil` <[string]|[Array]<[string]>> When to consider navigation succeeded, defaults to `load`. Given an array of event strings, navigation is considered to be successful after all events have been fired. Events can be either:
    - `load` - consider navigation to be finished when the `load` event is fired.
    - `domcontentloaded` - consider navigation to be finished when the `DOMContentLoaded` event is fired.
    - `networkidle0` - consider navigation to be finished when there are no more than 0 network connections for at least `500` ms.
    - `networkidle2` - consider navigation to be finished when there are no more than 2 network connections for at least `500` ms.
- returns: <[Promise]<[Response]>> Promise which resolves to the main resource response. In case of multiple redirects, the navigation will resolve with the response of the last redirect.

#### page.screenshot([options])
- `options` <[Object]> Options object which might have the following properties:
    - `path` <[string]> The file path to save the image to. The screenshot type will be inferred from file extension. If `path` is a relative path, then it is resolved relative to [current working directory](https://nodejs.org/api/process.html#process_process_cwd). If no path is provided, the image won't be saved to the disk.
    - `type` <[string]> Specify screenshot type, can be either `jpeg` or `png`. Defaults to 'png'.
    - `quality` <[number]> The quality of the image, between 0-100. Not applicable to `png` images.
    - `fullPage` <[boolean]> When true, takes a screenshot of the full scrollable page. Defaults to `false`.
    - `clip` <[Object]> An object which specifies clipping region of the page. Should have the following fields:
        - `x` <[number]> x-coordinate of top-left corner of clip area
        - `y` <[number]> y-coordinate of top-left corner of clip area
        - `width` <[number]> width of clipping area
        - `height` <[number]> height of clipping area
    - `omitBackground` <[boolean]> Hides default white background and allows capturing screenshots with transparency. Defaults to `false`.
- returns: <[Promise]<[Buffer]>> Promise which resolves to buffer with captured screenshot

#### page.select(selector, ...values)
- `selector` <[string]> A [selector] to query page for
- `...values` <...[string]> Values of options to select. If the `<select>` has the `multiple` attribute, all values are considered, otherwise only the first one is taken into account.
- returns: <[Promise]<[Array]<[string]>>> Returns an array of option values that have been successfully selected.

Triggers a `change` and `input` event once all the provided options have been selected.
If there's no `<select>` element matching `selector`, the method throws an error.

```js
page.select('select#colors', 'blue'); // single selection
page.select('select#colors', 'red', 'green', 'blue'); // multiple selections
```

Shortcut for [page.mainFrame().select()](#frameselectselector-values)

#### page.setContent(html)
- `html` <[string]> HTML markup to assign to the page.
- returns: <[Promise]>

#### page.setCookie(...cookies)
- `...cookies` <...[Object]>
  - `name` <[string]> **required**
  - `value` <[string]> **required**
  - `url` <[string]>
  - `domain` <[string]>
  - `path` <[string]>
  - `expires` <[number]> Unix time in seconds.
  - `httpOnly` <[boolean]>
  - `secure` <[boolean]>
  - `sameSite` <[string]> `"Strict"` or `"Lax"`.
- returns: <[Promise]>

#### page.setDefaultNavigationTimeout(timeout)
- `timeout` <[number]> Maximum navigation time in milliseconds

This setting will change the default maximum navigation time of 30 seconds for the following methods:
- [page.goto(url, options)](#pagegotourl-options)
- [page.goBack(options)](#pagegobackoptions)
- [page.goForward(options)](#pagegoforwardoptions)
- [page.reload(options)](#pagereloadoptions)
- [page.waitForNavigation(options)](#pagewaitfornavigationoptions)

#### page.setExtraHTTPHeaders(headers)
- `headers` <[Object]> An object containing additional http headers to be sent with every request. All header values must be strings.
- returns: <[Promise]>

The extra HTTP headers will be sent with every request the page initiates.

> **NOTE** page.setExtraHTTPHeaders does not guarantee the order of headers in the outgoing requests.

#### page.setJavaScriptEnabled(enabled)
- `enabled` <[boolean]> Whether or not to enable JavaScript on the page.
- returns: <[Promise]>

> **NOTE** changing this value won't affect scripts that have already been run. It will take full effect on the next [navigation](#pagegotourl-options).

#### page.setOfflineMode(enabled)
- `enabled` <[boolean]> When `true`, enables offline mode for the page.
- returns: <[Promise]>

#### page.setRequestInterception(value)
- `value` <[boolean]> Whether to enable request interception.
- returns: <[Promise]>

Activating request interception enables `request.abort`, `request.continue` and
`request.respond` methods.

An example of a naïve request interceptor that aborts all image requests:
```js
const puppeteer = require('puppeteer');

puppeteer.launch().then(async browser => {
  const page = await browser.newPage();
  await page.setRequestInterception(true);
  page.on('request', interceptedRequest => {
    if (interceptedRequest.url.endsWith('.png') || interceptedRequest.url.endsWith('.jpg'))
      interceptedRequest.abort();
    else
      interceptedRequest.continue();
  });
  await page.goto('https://example.com');
  await browser.close();
});
```

> **NOTE** Enabling request interception disables page caching.

#### page.setUserAgent(userAgent)
- `userAgent` <[string]> Specific user agent to use in this page
- returns: <[Promise]> Promise which resolves when the user agent is set.

#### page.setViewport(viewport)
- `viewport` <[Object]>
  - `width` <[number]> page width in pixels.
  - `height` <[number]> page height in pixels.
  - `deviceScaleFactor` <[number]> Specify device scale factor (can be thought of as dpr). Defaults to `1`.
  - `isMobile` <[boolean]> Whether the `meta viewport` tag is taken into account. Defaults to `false`.
  - `hasTouch`<[boolean]> Specifies if viewport supports touch events. Defaults to `false`
  - `isLandscape` <[boolean]> Specifies if viewport is in landscape mode. Defaults to `false`.
- returns: <[Promise]>

> **NOTE** in certain cases, setting viewport will reload the page in order to set the `isMobile` or `hasTouch` properties.

In the case of multiple pages in a single browser, each page can have its own viewport size.

#### page.tap(selector)
- `selector` <[string]> A [selector] to search for element to tap. If there are multiple elements satisfying the selector, the first will be tapped.
- returns: <[Promise]>

This method fetches an element with `selector`, scrolls it into view if needed, and then uses [page.touchscreen](#pagetouchscreen) to tap in the center of the element.
If there's no element matching `selector`, the method throws an error.

#### page.target()
- returns: <[Target]> a target this page was created from.

#### page.title()
- returns: <[Promise]<[string]>> Returns page's title.

Shortcut for [page.mainFrame().title()](#frametitle).

#### page.touchscreen
- returns: <[Touchscreen]>

#### page.tracing
- returns: <[Tracing]>

#### page.type(selector, text[, options])
- `selector` <[string]> A [selector] of an element to type into. If there are multiple elements satisfying the selector, the first will be used.
- `text` <[string]> A text to type into a focused element.
- `options` <[Object]>
  - `delay` <[number]> Time to wait between key presses in milliseconds. Defaults to 0.
- returns: <[Promise]>

Sends a `keydown`, `keypress`/`input`, and `keyup` event for each character in the text.

To press a special key, like `Control` or `ArrowDown`, use [`keyboard.press`](#keyboardpresskey-options).

```js
page.type('#mytextarea', 'Hello'); // Types instantly
page.type('#mytextarea', 'World', {delay: 100}); // Types slower, like a user
```

#### page.url()
- returns: <[string]>

This is a shortcut for [page.mainFrame().url()](#frameurl)

#### page.viewport()
- returns: <[Object]>
  - `width` <[number]> page width in pixels.
  - `height` <[number]> page height in pixels.
  - `deviceScaleFactor` <[number]> Specify device scale factor (can be though of as dpr). Defaults to `1`.
  - `isMobile` <[boolean]> Whether the `meta viewport` tag is taken into account. Defaults to `false`.
  - `hasTouch`<[boolean]> Specifies if viewport supports touch events. Defaults to `false`
  - `isLandscape` <[boolean]> Specifies if viewport is in landscape mode. Defaults to `false`.

#### page.waitFor(selectorOrFunctionOrTimeout[, options[, ...args]])
- `selectorOrFunctionOrTimeout` <[string]|[number]|[function]> A [selector], predicate or timeout to wait for
- `options` <[Object]> Optional waiting parameters
- `...args` <...[Serializable]|[JSHandle]> Arguments to pass to  `pageFunction`
- returns: <[Promise]<[JSHandle]>> Promise which resolves to a JSHandle of the success value

This method behaves differently with respect to the type of the first parameter:
- if `selectorOrFunctionOrTimeout` is a `string`, then the first argument is treated as a [selector] to wait for and the method is a shortcut for [page.waitForSelector](#pagewaitforselectorselector-options)
- if `selectorOrFunctionOrTimeout` is a `function`, then the first argument is treated as a predicate to wait for and the method is a shortcut for [page.waitForFunction()](#pagewaitforfunctionpagefunction-options-args).
- if `selectorOrFunctionOrTimeout` is a `number`, then the first argument is treated as a timeout in milliseconds and the method returns a promise which resolves after the timeout
- otherwise, an exception is thrown

Shortcut for [page.mainFrame().waitFor(selectorOrFunctionOrTimeout[, options[, ...args]])](#framewaitforselectororfunctionortimeout-options-args).

#### page.waitForFunction(pageFunction[, options[, ...args]])
- `pageFunction` <[function]|[string]> Function to be evaluated in browser context
- `options` <[Object]> Optional waiting parameters
  - `polling` <[string]|[number]> An interval at which the `pageFunction` is executed, defaults to `raf`. If `polling` is a number, then it is treated as an interval in milliseconds at which the function would be executed. If `polling` is a string, then it can be one of the following values:
    - `raf` - to constantly execute `pageFunction` in `requestAnimationFrame` callback. This is the tightest polling mode which is suitable to observe styling changes.
    - `mutation` - to execute `pageFunction` on every DOM mutation.
  - `timeout` <[number]> maximum time to wait for in milliseconds. Defaults to `30000` (30 seconds).
- `...args` <...[Serializable]|[JSHandle]> Arguments to pass to  `pageFunction`
- returns: <[Promise]<[JSHandle]>> Promise which resolves when the `pageFunction` returns a truthy value. It resolves to a JSHandle of the truthy value.

The `waitForFunction` can be used to observe viewport size change:
```js
const puppeteer = require('puppeteer');

puppeteer.launch().then(async browser => {
  const page = await browser.newPage();
  const watchDog = page.waitForFunction('window.innerWidth < 100');
  page.setViewport({width: 50, height: 50});
  await watchDog;
  await browser.close();
});
```
Shortcut for [page.mainFrame().waitForFunction(pageFunction[, options[, ...args]])](#framewaitforfunctionpagefunction-options-args).

#### page.waitForNavigation(options)
- `options` <[Object]> Navigation parameters which might have the following properties:
  - `timeout` <[number]> Maximum navigation time in milliseconds, defaults to 30 seconds, pass `0` to disable timeout. The default value can be changed by using the [page.setDefaultNavigationTimeout(timeout)](#pagesetdefaultnavigationtimeouttimeout) method.
  - `waitUntil` <[string]|[Array]<[string]>> When to consider navigation succeeded, defaults to `load`. Given an array of event strings, navigation is considered to be successful after all events have been fired. Events can be either:
    - `load` - consider navigation to be finished when the `load` event is fired.
    - `domcontentloaded` - consider navigation to be finished when the `DOMContentLoaded` event is fired.
    - `networkidle0` - consider navigation to be finished when there are no more than 0 network connections for at least `500` ms.
    - `networkidle2` - consider navigation to be finished when there are no more than 2 network connections for at least `500` ms.
- returns: <[Promise]<[Response]>> Promise which resolves to the main resource response. In case of multiple redirects, the navigation will resolve with the response of the last redirect.

#### page.waitForSelector(selector[, options])
- `selector` <[string]> A [selector] of an element to wait for,
- `options` <[Object]> Optional waiting parameters
  - `visible` <[boolean]> wait for element to be present in DOM and to be visible, i.e. to not have `display: none` or `visibility: hidden` CSS properties. Defaults to `false`.
  - `hidden` <[boolean]> wait for element to not be found in the DOM or to be hidden, i.e. have `display: none` or `visibility: hidden` CSS properties. Defaults to `false`.
  - `timeout` <[number]> maximum time to wait for in milliseconds. Defaults to `30000` (30 seconds).
- returns: <[Promise]<[ElementHandle]>> Promise which resolves when element specified by selector string is added to DOM.

Wait for the `selector` to appear in page. If at the moment of calling
the method the `selector` already exists, the method will return
immediately. If the selector doesn't appear after the `timeout` milliseconds of waiting, the function will throw.

This method works across navigations:
```js
const puppeteer = require('puppeteer');

puppeteer.launch().then(async browser => {
  const page = await browser.newPage();
  let currentURL;
  page
    .waitForSelector('img')
    .then(() => console.log('First URL with image: ' + currentURL));
  for (currentURL of ['https://example.com', 'https://google.com', 'https://bbc.com'])
    await page.goto(currentURL);
  await browser.close();
});
```
Shortcut for [page.mainFrame().waitForSelector(selector[, options])](#framewaitforselectorselector-options).


### class: Keyboard

Keyboard provides an api for managing a virtual keyboard. The high level api is [`keyboard.type`](#keyboardtypetext-options), which takes raw characters and generates proper keydown, keypress/input, and keyup events on your page.

For finer control, you can use [`keyboard.down`](#keyboarddownkey-options), [`keyboard.up`](#keyboardupkey), and [`keyboard.sendCharacter`](#keyboardsendcharacterchar) to manually fire events as if they were generated from a real keyboard.

An example of holding down `Shift` in order to select and delete some text:
```js
await page.keyboard.type('Hello World!');
await page.keyboard.press('ArrowLeft');

await page.keyboard.down('Shift');
for (let i = 0; i < ' World'.length; i++)
  await page.keyboard.press('ArrowLeft');
await page.keyboard.up('Shift');

await page.keyboard.press('Backspace');
// Result text will end up saying 'Hello!'
```

An example of pressing `A`
```js
await page.keyboard.down('Shift');
await page.keyboard.press('KeyA');
await page.keyboard.up('Shift');
```

> **NOTE** On MacOS, keyboard shortcuts like `⌘ A` -> Select All do not work. See [#1313](https://github.com/GoogleChrome/puppeteer/issues/1313)

#### keyboard.down(key[, options])
- `key` <[string]> Name of key to press, such as `ArrowLeft`. See [USKeyboardLayout] for a list of all key names.
- `options` <[Object]>
  - `text` <[string]> If specified, generates an input event with this text.
- returns: <[Promise]>

Dispatches a `keydown` event.

If `key` is a single character and no modifier keys besides `Shift` are being held down, a `keypress`/`input` event will also generated. The `text` option can be specified to force an input event to be generated.

If `key` is a modifier key, `Shift`, `Meta`, `Control`, or `Alt`, subsequent key presses will be sent with that modifier active. To release the modifier key, use [`keyboard.up`](#keyboardupkey).

After the key is pressed once, subsequent calls to [`keyboard.down`](#keyboarddownkey-options) will have [repeat](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/repeat) set to true. To release the key, use [`keyboard.up`](#keyboardupkey).

> **NOTE** Modifier keys DO influence `keyboard.down`. Holding down `Shift` will type the text in upper case.

#### keyboard.press(key[, options])
- `key` <[string]> Name of key to press, such as `ArrowLeft`. See [USKeyboardLayout] for a list of all key names.
- `options` <[Object]>
  - `text` <[string]> If specified, generates an input event with this text.
  - `delay` <[number]> Time to wait between `keydown` and `keyup` in milliseconds. Defaults to 0.
- returns: <[Promise]>

If `key` is a single character and no modifier keys besides `Shift` are being held down, a `keypress`/`input` event will also generated. The `text` option can be specified to force an input event to be generated.

> **NOTE** Modifier keys DO effect `elementHandle.press`. Holding down `Shift` will type the text in upper case.

Shortcut for [`keyboard.down`](#keyboarddownkey-options) and [`keyboard.up`](#keyboardupkey).

#### keyboard.sendCharacter(char)
- `char` <[string]> Character to send into the page.
- returns: <[Promise]>

Dispatches a `keypress` and `input` event. This does not send a `keydown` or `keyup` event.

```js
page.keyboard.sendCharacter('嗨');
```

> **NOTE** Modifier keys DO NOT effect `keyboard.sendCharacter`. Holding down `Shift` will not type the text in upper case.

#### keyboard.type(text, options)
- `text` <[string]> A text to type into a focused element.
- `options` <[Object]>
  - `delay` <[number]> Time to wait between key presses in milliseconds. Defaults to 0.
- returns: <[Promise]>

Sends a `keydown`, `keypress`/`input`, and `keyup` event for each character in the text.

To press a special key, like `Control` or `ArrowDown`, use [`keyboard.press`](#keyboardpresskey-options).

```js
page.keyboard.type('Hello'); // Types instantly
page.keyboard.type('World', {delay: 100}); // Types slower, like a user
```

> **NOTE** Modifier keys DO NOT effect `keyboard.type`. Holding down `Shift` will not type the text in upper case.

#### keyboard.up(key)
- `key` <[string]> Name of key to release, such as `ArrowLeft`. See [USKeyboardLayout] for a list of all key names.
- returns: <[Promise]>

Dispatches a `keyup` event.

### class: Mouse

#### mouse.click(x, y, [options])
- `x` <[number]>
- `y` <[number]>
- `options` <[Object]>
  - `button` <[string]> `left`, `right`, or `middle`, defaults to `left`.
  - `clickCount` <[number]> defaults to 1. See [UIEvent.detail].
  - `delay` <[number]> Time to wait between `mousedown` and `mouseup` in milliseconds. Defaults to 0.
- returns: <[Promise]>

Shortcut for [`mouse.move`](#mousemovex-y-options), [`mouse.down`](#mousedownoptions) and [`mouse.up`](#mouseupoptions).

#### mouse.down([options])
- `options` <[Object]>
  - `button` <[string]> `left`, `right`, or `middle`, defaults to `left`.
  - `clickCount` <[number]> defaults to 1. See [UIEvent.detail].
- returns: <[Promise]>

Dispatches a `mousedown` event.

#### mouse.move(x, y, [options])
- `x` <[number]>
- `y` <[number]>
- `options` <[Object]>
  - `steps` <[number]> defaults to 1. Sends intermediate `mousemove` events.
- returns: <[Promise]>

Dispatches a `mousemove` event.

#### mouse.up([options])
- `options` <[Object]>
  - `button` <[string]> `left`, `right`, or `middle`, defaults to `left`.
  - `clickCount` <[number]> defaults to 1. See [UIEvent.detail].
- returns: <[Promise]>

Dispatches a `mouseup` event.

### class: Touchscreen

#### touchscreen.tap(x, y)
- `x` <[number]>
- `y` <[number]>
- returns: <[Promise]>

Dispatches a `touchstart` and `touchend` event.

### class: Tracing

You can use [`tracing.start`](#tracingstartoptions) and [`tracing.stop`](#tracingstop) to create a trace file which can be opened in Chrome DevTools or [timeline viewer](https://chromedevtools.github.io/timeline-viewer/).

```js
await page.tracing.start({path: 'trace.json'});
await page.goto('https://www.google.com');
await page.tracing.stop();
```

#### tracing.start(options)
- `options` <[Object]>
  - `path` <[string]> A path to write the trace file to. **required**
  - `screenshots` <[boolean]> captures screenshots in the trace.
  - `categories` <[Array]<[string]>> specify custom categories to use instead of default.
- returns: <[Promise]>

Only one trace can be active at a time per browser.

#### tracing.stop()
- returns: <[Promise]>

### class: Dialog

[Dialog] objects are dispatched by page via the ['dialog'](#event-dialog) event.

An example of using `Dialog` class:
```js
const puppeteer = require('puppeteer');

puppeteer.launch().then(async browser => {
  const page = await browser.newPage();
  page.on('dialog', async dialog => {
    console.log(dialog.message());
    await dialog.dismiss();
    await browser.close();
  });
  page.evaluate(() => alert('1'));
});
```

#### dialog.accept([promptText])
- `promptText` <[string]> A text to enter in prompt. Does not cause any effects if the dialog's `type` is not prompt.
- returns: <[Promise]> Promise which resolves when the dialog has been accepted.

#### dialog.defaultValue()
- returns: <[string]> If dialog is prompt, returns default prompt value. Otherwise, returns empty string.

#### dialog.dismiss()
- returns: <[Promise]> Promise which resolves when the dialog has been dismissed.

#### dialog.message()
- returns: <[string]> A message displayed in the dialog.

#### dialog.type()
- returns: <[string]> Dialog's type, can be one of `alert`, `beforeunload`, `confirm` or `prompt`.

### class: ConsoleMessage

[ConsoleMessage] objects are dispatched by page via the ['console'](#event-console) event.

#### consoleMessage.args()
- returns: <[Array]<[JSHandle]>>

#### consoleMessage.text()
- returns: <[string]>

#### consoleMessage.type()
- returns: <[string]>

One of the following values: `'log'`, `'debug'`, `'info'`, `'error'`, `'warning'`, `'dir'`, `'dirxml'`, `'table'`, `'trace'`, `'clear'`, `'startGroup'`, `'startGroupCollapsed'`, `'endGroup'`, `'assert'`, `'profile'`, `'profileEnd'`, `'count'`, `'timeEnd'`.

### class: Frame

At every point of time, page exposes its current frame tree via the [page.mainFrame()](#pagemainframe) and [frame.childFrames()](#framechildframes) methods.

[Frame] object's lifecycle is controlled by three events, dispatched on the page object:
- ['frameattached'](#event-frameattached) - fired when the frame gets attached to the page. A Frame can be attached to the page only once.
- ['framenavigated'](#event-framenavigated) - fired when the frame commits navigation to a different URL.
- ['framedetached'](#event-framedetached) - fired when the frame gets detached from the page.  A Frame can be detached from the page only once.

An example of dumping frame tree:

```js
const puppeteer = require('puppeteer');

puppeteer.launch().then(async browser => {
  const page = await browser.newPage();
  await page.goto('https://www.google.com/chrome/browser/canary.html');
  dumpFrameTree(page.mainFrame(), '');
  await browser.close();

  function dumpFrameTree(frame, indent) {
    console.log(indent + frame.url());
    for (let child of frame.childFrames())
      dumpFrameTree(child, indent + '  ');
  }
});
```

#### frame.$(selector)
- `selector` <[string]> Selector to query page for
- returns: <[Promise]<?[ElementHandle]>> Promise which resolves to ElementHandle pointing to the frame element.

The method queries frame for the selector. If there's no such element within the frame, the method will resolve to `null`.

#### frame.$$(selector)
- `selector` <[string]> Selector to query page for
- returns: <[Promise]<[Array]<[ElementHandle]>>> Promise which resolves to ElementHandles pointing to the frame elements.

The method runs `document.querySelectorAll` within the frame. If no elements match the selector, the return value resolve to `[]`.

#### frame.$$eval(selector, pageFunction[, ...args])
- `selector` <[string]> A [selector] to query frame for
- `pageFunction` <[function]> Function to be evaluated in browser context
- `...args` <...[Serializable]|[JSHandle]> Arguments to pass to `pageFunction`
- returns: <[Promise]<[Serializable]>> Promise which resolves to the return value of `pageFunction`

This method runs `document.querySelectorAll` within the frame and passes it as the first argument to `pageFunction`.

If `pageFunction` returns a [Promise], then `frame.$$eval` would wait for the promise to resolve and return its value.

Examples:
```js
const divsCounts = await frame.$$eval('div', divs => divs.length);
```

#### frame.$eval(selector, pageFunction[, ...args])
- `selector` <[string]> A [selector] to query frame for
- `pageFunction` <[function]> Function to be evaluated in browser context
- `...args` <...[Serializable]|[JSHandle]> Arguments to pass to `pageFunction`
- returns: <[Promise]<[Serializable]>> Promise which resolves to the return value of `pageFunction`

This method runs `document.querySelector` within the frame and passes it as the first argument to `pageFunction`. If there's no element matching `selector`, the method throws an error.

If `pageFunction` returns a [Promise], then `frame.$eval` would wait for the promise to resolve and return its value.

Examples:
```js
const searchValue = await frame.$eval('#search', el => el.value);
const preloadHref = await frame.$eval('link[rel=preload]', el => el.href);
const html = await frame.$eval('.main-container', e => e.outerHTML);
```

#### frame.$x(expression)
- `expression` <[string]> Expression to [evaluate](https://developer.mozilla.org/en-US/docs/Web/API/Document/evaluate).
- returns: <[Promise]<[Array]<[ElementHandle]>>>

The method evluates the XPath expression.

#### frame.addScriptTag(options)
- `options` <[Object]>
  - `url` <[string]> Url of a script to be added.
  - `path` <[string]> Path to the JavaScript file to be injected into frame. If `path` is a relative path, then it is resolved relative to [current working directory](https://nodejs.org/api/process.html#process_process_cwd).
  - `content` <[string]> Raw JavaScript content to be injected into frame.
- returns: <[Promise]<[ElementHandle]>> which resolves to the added tag when the script's onload fires or when the script content was injected into frame.

Adds a `<script>` tag into the page with the desired url or content.

#### frame.addStyleTag(options)
- `options` <[Object]>
  - `url` <[string]> Url of the `<link>` tag.
  - `path` <[string]> Path to the CSS file to be injected into frame. If `path` is a relative path, then it is resolved relative to [current working directory](https://nodejs.org/api/process.html#process_process_cwd).
  - `content` <[string]> Raw CSS content to be injected into frame.
- returns: <[Promise]<[ElementHandle]>> which resolves to the added tag when the stylesheet's onload fires or when the CSS content was injected into frame.

Adds a `<link rel="stylesheet">` tag into the page with the desired url or a `<style type="text/css">` tag with the content.

#### frame.childFrames()
- returns: <[Array]<[Frame]>>

#### frame.content()
- returns: <[Promise]<[String]>>

Gets the full HTML contents of the frame, including the doctype.

#### frame.evaluate(pageFunction, ...args)
- `pageFunction` <[function]|[string]> Function to be evaluated in browser context
- `...args` <...[Serializable]|[JSHandle]> Arguments to pass to  `pageFunction`
- returns: <[Promise]<[Serializable]>> Promise which resolves to function return value

If the function, passed to the `frame.evaluate`, returns a [Promise], then `frame.evaluate` would wait for the promise to resolve and return its value.

If the function passed into `frame.evaluate` returns a non-[Serializable] value, then `frame.evaluate` resolves to `undefined`.

```js
const result = await frame.evaluate(() => {
  return Promise.resolve(8 * 7);
});
console.log(result); // prints "56"
```

A string can also be passed in instead of a function.

```js
console.log(await frame.evaluate('1 + 2')); // prints "3"
```

[ElementHandle] instances can be passed as arguments to the `frame.evaluate`:
```js
const bodyHandle = await frame.$('body');
const html = await frame.evaluate(body => body.innerHTML, bodyHandle);
await bodyHandle.dispose();
```

#### frame.executionContext()
- returns: <[Promise]<[ExecutionContext]>> Execution context associated with this frame.

#### frame.isDetached()
- returns: <[boolean]>

Returns `true` if the frame has been detached, or `false` otherwise.

#### frame.name()
- returns: <[string]>

Returns frame's name attribute as specified in the tag.

If the name is empty, returns the id attribute instead.

> **NOTE** This value is calculated once when the frame is created, and will not update if the attribute is changed later.

#### frame.parentFrame()
- returns: <?[Frame]> Returns parent frame, if any. Detached frames and main frames return `null`.

#### frame.select(selector, ...values)
- `selector` <[string]> A [selector] to query frame for
- `...values` <...[string]> Values of options to select. If the `<select>` has the `multiple` attribute, all values are considered, otherwise only the first one is taken into account.
- returns: <[Promise]<[Array]<[string]>>> Returns an array of option values that have been successfully selected.

Triggers a `change` and `input` event once all the provided options have been selected.
If there's no `<select>` element matching `selector`, the method throws an error.

```js
frame.select('select#colors', 'blue'); // single selection
frame.select('select#colors', 'red', 'green', 'blue'); // multiple selections
```

#### frame.setContent(html)
- `html` <[string]> HTML markup to assign to the page.
- returns: <[Promise]>

#### frame.title()
- returns: <[Promise]<[string]>> Returns page's title.

#### frame.url()
- returns: <[string]>

Returns frame's url.

#### frame.waitFor(selectorOrFunctionOrTimeout[, options[, ...args]])
- `selectorOrFunctionOrTimeout` <[string]|[number]|[function]> A [selector], predicate or timeout to wait for
- `options` <[Object]> Optional waiting parameters
- `...args` <...[Serializable]|[JSHandle]> Arguments to pass to  `pageFunction`
- returns: <[Promise]<[JSHandle]>> Promise which resolves to a JSHandle of the success value

This method behaves differently with respect to the type of the first parameter:
- if `selectorOrFunctionOrTimeout` is a `string`, then the first argument is treated as a [selector] to wait for and the method is a shortcut for [frame.waitForSelector](#framewaitforselectorselector-options)
- if `selectorOrFunctionOrTimeout` is a `function`, then the first argument is treated as a predicate to wait for and the method is a shortcut for [frame.waitForFunction()](#framewaitforfunctionpagefunction-options-args).
- if `selectorOrFunctionOrTimeout` is a `number`, then the first argument is treated as a timeout in milliseconds and the method returns a promise which resolves after the timeout
- otherwise, an exception is thrown


#### frame.waitForFunction(pageFunction[, options[, ...args]])
- `pageFunction` <[function]|[string]> Function to be evaluated in browser context
- `options` <[Object]> Optional waiting parameters
  - `polling` <[string]|[number]> An interval at which the `pageFunction` is executed, defaults to `raf`. If `polling` is a number, then it is treated as an interval in milliseconds at which the function would be executed. If `polling` is a string, then it can be one of the following values:
    - `raf` - to constantly execute `pageFunction` in `requestAnimationFrame` callback. This is the tightest polling mode which is suitable to observe styling changes.
    - `mutation` - to execute `pageFunction` on every DOM mutation.
  - `timeout` <[number]> maximum time to wait for in milliseconds. Defaults to `30000` (30 seconds).
- `...args` <...[Serializable]|[JSHandle]> Arguments to pass to  `pageFunction`
- returns: <[Promise]<[JSHandle]>> Promise which resolves when the `pageFunction` returns a truthy value. It resolves to a JSHandle of the truthy value.

The `waitForFunction` can be used to observe viewport size change:
```js
const puppeteer = require('puppeteer');

puppeteer.launch().then(async browser => {
  const page = await browser.newPage();
  const watchDog = page.mainFrame().waitForFunction('window.innerWidth < 100');
  page.setViewport({width: 50, height: 50});
  await watchDog;
  await browser.close();
});
```

#### frame.waitForSelector(selector[, options])
- `selector` <[string]> A [selector] of an element to wait for,
- `options` <[Object]> Optional waiting parameters
  - `visible` <[boolean]> wait for element to be present in DOM and to be visible, i.e. to not have `display: none` or `visibility: hidden` CSS properties. Defaults to `false`.
  - `hidden` <[boolean]> wait for element to not be found in the DOM or to be hidden, i.e. have `display: none` or `visibility: hidden` CSS properties. Defaults to `false`.
  - `timeout` <[number]> maximum time to wait for in milliseconds. Defaults to `30000` (30 seconds).
- returns: <[Promise]<[ElementHandle]>> Promise which resolves when element specified by selector string is added to DOM.

Wait for the `selector` to appear in page. If at the moment of calling
the method the `selector` already exists, the method will return
immediately. If the selector doesn't appear after the `timeout` milliseconds of waiting, the function will throw.

This method works across navigations:
```js
const puppeteer = require('puppeteer');

puppeteer.launch().then(async browser => {
  const page = await browser.newPage();
  let currentURL;
  page.mainFrame()
    .waitForSelector('img')
    .then(() => console.log('First URL with image: ' + currentURL));
  for (currentURL of ['https://example.com', 'https://google.com', 'https://bbc.com'])
    await page.goto(currentURL);
  await browser.close();
});
```

### class: ExecutionContext

The class represents a context for JavaScript execution. Examples of JavaScript contexts are:
- each [frame](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) has a separate execution context
- all kind of [workers](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API) have their own contexts

#### executionContext.evaluate(pageFunction, ...args)
- `pageFunction` <[function]|[string]> Function to be evaluated in `executionContext`
- `...args` <...[Serializable]|[JSHandle]> Arguments to pass to `pageFunction`
- returns: <[Promise]<[Serializable]>> Promise which resolves to function return value

If the function, passed to the `executionContext.evaluate`, returns a [Promise], then `executionContext.evaluate` would wait for the promise to resolve and return its value.

```js
const executionContext = page.mainFrame().executionContext();
const result = await executionContext.evaluate(() => Promise.resolve(8 * 7));
console.log(result); // prints "56"
```

A string can also be passed in instead of a function.

```js
console.log(await executionContext.evaluate('1 + 2')); // prints "3"
```

[JSHandle] instances can be passed as arguments to the `executionContext.evaluate`:
```js
const oneHandle = await executionContext.evaluateHandle(() => 1);
const twoHandle = await executionContext.evaluateHandle(() => 2);
const result = await executionContext.evaluate((a, b) => a + b, oneHandle, twoHandle);
await oneHandle.dispose();
await twoHandle.dispose();
console.log(result); // prints '3'.
```

#### executionContext.evaluateHandle(pageFunction, ...args)
- `pageFunction` <[function]|[string]> Function to be evaluated in the `executionContext`
- `...args` <...[Serializable]|[JSHandle]> Arguments to pass to `pageFunction`
- returns: <[Promise]<[JSHandle]>> Resolves to the return value of `pageFunction`

If the function, passed to the `executionContext.evaluateHandle`, returns a [Promise], then `executionContext.evaluteHandle` would wait for the promise to resolve and return its value.

```js
const context = page.mainFrame().executionContext();
const aHandle = await context.evaluateHandle(() => Promise.resolve(self));
aHandle; // Handle for the global object.
```

A string can also be passed in instead of a function.

```js
const aHandle = await context.evaluateHandle('1 + 2'); // Handle for the '3' object.
```

[JSHandle] instances can be passed as arguments to the `executionContext.evaluateHandle`:
```js
const aHandle = await context.evaluateHandle(() => document.body);
const resultHandle = await context.evaluateHandle(body => body.innerHTML, aHandle);
console.log(await resultHandle.jsonValue()); // prints body's innerHTML
await aHandle.dispose();
await resultHandle.dispose();
```

#### executionContext.queryObjects(prototypeHandle)
- `prototypeHandle` <[JSHandle]> A handle to the object prototype.
- returns: <[JSHandle]> A handle to an array of objects with this prototype

The method iterates JavaScript heap and finds all the objects with the given prototype.

```js
// Create a Map object
await page.evaluate(() => window.map = new Map());
// Get a handle to the Map object prototype
const mapPrototype = await page.evaluateHandle(() => Map.prototype);
// Query all map instances into an array
const mapInstances = await page.queryObjects(mapPrototype);
// Count amount of map objects in heap
const count = await page.evaluate(maps => maps.length, mapInstances);
await mapInstances.dispose();
await mapPrototype.dispose();
```

### class: JSHandle

JSHandle represents an in-page JavaScript object. JSHandles can be created with the [page.evaluateHandle](#pageevaluatehandlepagefunction-args) method.

```js
const windowHandle = await page.evaluateHandle(() => window);
// ...
```

JSHandle prevents references JavaScript objects from garbage collection unless the handle is [disposed](#jshandledispose). JSHandles are auto-disposed when their origin frame gets navigated or the parent context gets destroyed.

JSHandle instances can be used as arguments in [`page.$eval()`](#pageevalselector-pagefunction-args), [`page.evaluate()`](#pageevaluatepagefunction-args) and [`page.evaluateHandle`](#pageevaluatehandlepagefunction-args) methods.

#### jsHandle.asElement()
- returns: <?[ElementHandle]>

Returns either `null` or the object handle itself, if the object handle is an instance of [ElementHandle].

#### jsHandle.dispose()
- returns: <[Promise]> Promise which resolves when the object handle is successfully disposed.

The `jsHandle.dispose` method stops referencing the element handle.

#### jsHandle.executionContext()
- returns: [ExecutionContext]

Returns execution context the handle belongs to.

#### jsHandle.getProperties()
- returns: <[Promise]<[Map]<[string], [JSHandle]>>>

The method returns a map with property names as keys and JSHandle instances for the property values.

```js
const handle = await page.evaluateHandle(() => ({window, document}));
const properties = await handle.getProperties();
const windowHandle = properties.get('window');
const documentHandle = properties.get('document');
await handle.dispose();
```

#### jsHandle.getProperty(propertyName)
- `propertyName` <[string]> property to get
- returns: <[Promise]<[JSHandle]>>

Fetches a single property from the referenced object.

#### jsHandle.jsonValue()
- returns: <[Promise]<[Object]>>

Returns a JSON representation of the object. If the object has a
[`toJSON`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify#toJSON()_behavior)
function, it **will not be called**.

> **NOTE** The method will return an empty JSON if the referenced object is not stringifiable. It will throw an error if the object has circular references.

### class: ElementHandle

> **NOTE** Class [ElementHandle] extends [JSHandle].

ElementHandle represents an in-page DOM element. ElementHandles can be created with the [page.$](#pageselector) method.

```js
const puppeteer = require('puppeteer');

puppeteer.launch().then(async browser => {
  const page = await browser.newPage();
  await page.goto('https://google.com');
  const inputElement = await page.$('input[type=submit]');
  await inputElement.click();
  // ...
});
```

ElementHandle prevents DOM element from garbage collection unless the handle is [disposed](#elementhandledispose). ElementHandles are auto-disposed when their origin frame gets navigated.

ElementHandle instances can be used as arguments in [`page.$eval()`](#pageevalselector-pagefunction-args) and [`page.evaluate()`](#pageevaluatepagefunction-args) methods.

#### elementHandle.$(selector)
- `selector` <[string]> A [selector] to query element for
- returns: <[Promise]<?[ElementHandle]>>

The method runs `element.querySelector` within the page. If no element matches the selector, the return value resolve to `null`.

#### elementHandle.$$(selector)
- `selector` <[string]> A [selector] to query element for
- returns: <[Promise]<[Array]<[ElementHandle]>>>

The method runs `element.querySelectorAll` within the page. If no elements match the selector, the return value resolve to `[]`.

#### elementHandle.$x(expression)
- `expression` <[string]> Expression to [evaluate](https://developer.mozilla.org/en-US/docs/Web/API/Document/evaluate).
- returns: <[Promise]<?[ElementHandle]>> Promise which resolves to ElementHandle pointing to the frame element.

The method evluates the XPath expression relative to the elementHandle. If there's no such element, the method will resolve to `null`.

#### elementHandle.asElement()
- returns: <[elementhandle]>

#### elementHandle.boundingBox()
- returns: <[Promise]<?[Object]>>
    - x <[number]> the x coordinate of the element in pixels.
    - y <[number]> the y coordinate of the element in pixels.
    - width <[number]> the width of the element in pixels.
    - height <[number]> the height of the element in pixels.

This method returns the bounding box of the element (relative to the main frame), or `null` if the element is not visible.

#### elementHandle.click([options])
- `options` <[Object]>
  - `button` <[string]> `left`, `right`, or `middle`, defaults to `left`.
  - `clickCount` <[number]> defaults to 1. See [UIEvent.detail].
  - `delay` <[number]> Time to wait between `mousedown` and `mouseup` in milliseconds. Defaults to 0.
- returns: <[Promise]> Promise which resolves when the element is successfully clicked. Promise gets rejected if the element is detached from DOM.

This method scrolls element into view if needed, and then uses [page.mouse](#pagemouse) to click in the center of the element.
If the element is detached from DOM, the method throws an error.

#### elementHandle.dispose()
- returns: <[Promise]> Promise which resolves when the element handle is successfully disposed.

The `elementHandle.dispose` method stops referencing the element handle.

#### elementHandle.executionContext()
- returns: [ExecutionContext]

#### elementHandle.focus()
- returns: <[Promise]>

Calls [focus](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/focus) on the element.

#### elementHandle.getProperties()
- returns: <[Promise]<[Map]<[string], [JSHandle]>>>

The method returns a map with property names as keys and JSHandle instances for the property values.

```js
const listHandle = await page.evaluateHandle(() => document.body.children);
const properties = await listHandle.getProperties();
const children = [];
for (const property of properties.values()) {
  const element = property.asElement();
  if (element)
    children.push(element);
}
children; // holds elementHandles to all children of document.body
```

#### elementHandle.getProperty(propertyName)
- `propertyName` <[string]> property to get
- returns: <[Promise]<[JSHandle]>>

Fetches a single property from the objectHandle.

#### elementHandle.hover()
- returns: <[Promise]> Promise which resolves when the element is successfully hovered.

This method scrolls element into view if needed, and then uses [page.mouse](#pagemouse) to hover over the center of the element.
If the element is detached from DOM, the method throws an error.

#### elementHandle.jsonValue()
- returns: <[Promise]<[Object]>>

Returns a JSON representation of the object. The JSON is generated by running [`JSON.stringify`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify) on the object in page and consequent [`JSON.parse`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/parse) in puppeteer.

> **NOTE** The method will throw if the referenced object is not stringifiable.

#### elementHandle.press(key[, options])
- `key` <[string]> Name of key to press, such as `ArrowLeft`. See [USKeyboardLayout] for a list of all key names.
- `options` <[Object]>
  - `text` <[string]> If specified, generates an input event with this text.
  - `delay` <[number]> Time to wait between `keydown` and `keyup` in milliseconds. Defaults to 0.
- returns: <[Promise]>

Focuses the element, and then uses [`keyboard.down`](#keyboarddownkey-options) and [`keyboard.up`](#keyboardupkey).

If `key` is a single character and no modifier keys besides `Shift` are being held down, a `keypress`/`input` event will also be generated. The `text` option can be specified to force an input event to be generated.

> **NOTE** Modifier keys DO effect `elementHandle.press`. Holding down `Shift` will type the text in upper case.

#### elementHandle.screenshot([options])
- `options` <[Object]> Same options as in [page.screenshot](#pagescreenshotoptions).
- returns: <[Promise]<[Buffer]>> Promise which resolves to buffer with captured screenshot.

This method scrolls element into view if needed, and then uses [page.screenshot](#pagescreenshotoptions) to take a screenshot of the element.
If the element is detached from DOM, the method throws an error.

#### elementHandle.tap()
- returns: <[Promise]> Promise which resolves when the element is successfully tapped. Promise gets rejected if the element is detached from DOM.

This method scrolls element into view if needed, and then uses [touchscreen.tap](#touchscreentapx-y) to tap in the center of the element.
If the element is detached from DOM, the method throws an error.

#### elementHandle.toString()
- returns: <[string]>

#### elementHandle.type(text[, options])
- `text` <[string]> A text to type into a focused element.
- `options` <[Object]>
  - `delay` <[number]> Time to wait between key presses in milliseconds. Defaults to 0.
- returns: <[Promise]>

Focuses the element, and then sends a `keydown`, `keypress`/`input`, and `keyup` event for each character in the text.

To press a special key, like `Control` or `ArrowDown`, use [`elementHandle.press`](#elementhandlepresskey-options).

```js
elementHandle.type('Hello'); // Types instantly
elementHandle.type('World', {delay: 100}); // Types slower, like a user
```

An example of typing into a text field and then submitting the form:
```js
const elementHandle = await page.$('input');
await elementHandle.type('some text');
await elementHandle.press('Enter');
```

#### elementHandle.uploadFile(...filePaths)
- `...filePaths` <...[string]> Sets the value of the file input these paths. If some of the  `filePaths` are relative paths, then they are resolved relative to [current working directory](https://nodejs.org/api/process.html#process_process_cwd).
- returns: <[Promise]>

This method expects `elementHandle` to point to an [input element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input).

### class: Request

Whenever the page sends a request, the following events are emitted by puppeteer's page:
- ['request'](#event-request) emitted when the request is issued by the page.
- ['response'](#event-response) emitted when/if the response is received for the request.
- ['requestfinished'](#event-requestfinished) emitted when the response body is downloaded and the request is complete.

If request fails at some point, then instead of 'requestfinished' event (and possibly instead of 'response' event), the  ['requestfailed'](#event-requestfailed) event is emitted.

If request gets a 'redirect' response, the request is successfully finished with the 'requestfinished' event, and a new request is  issued to a redirected url.

#### request.abort([errorCode])
- `errorCode` <[string]> Optional error code. Defaults to `failed`, could be
  one of the following:
  - `aborted` - An operation was aborted (due to user action)
  - `accessdenied` - Permission to access a resource, other than the network, was denied
  - `addressunreachable` - The IP address is unreachable. This usually means
    that there is no route to the specified host or network.
  - `connectionaborted` - A connection timed out as a result of not receiving an ACK for data sent.
  - `connectionclosed` - A connection was closed (corresponding to a TCP FIN).
  - `connectionfailed` - A connection attempt failed.
  - `connectionrefused` - A connection attempt was refused.
  - `connectionreset` - A connection was reset (corresponding to a TCP RST).
  - `internetdisconnected` - The Internet connection has been lost.
  - `namenotresolved` - The host name could not be resolved.
  - `timedout` - An operation timed out.
  - `failed` - A generic failure occurred.
- returns: <[Promise]>

Aborts request. To use this, request interception should be enabled with `page.setRequestInterception`.
Exception is immediately thrown if the request interception is not enabled.

#### request.continue([overrides])
- `overrides` <[Object]> Optional request overwrites, which can be one of the following:
  - `url` <[string]> If set, the request url will be changed
  - `method` <[string]> If set changes the request method (e.g. `GET` or `POST`)
  - `postData` <[string]> If set changes the post data of request
  - `headers` <[Object]> If set changes the request HTTP headers
- returns: <[Promise]>

Continues request with optional request overrides. To use this, request interception should be enabled with `page.setRequestInterception`.
Exception is immediately thrown if the request interception is not enabled.

#### request.failure()
- returns: <?[Object]> Object describing request failure, if any
  - `errorText` <[string]> Human-readable error message, e.g. `'net::ERR_FAILED'`.

The method returns `null` unless this request was failed, as reported by
`requestfailed` event.

Example of logging all failed requests:

```js
page.on('requestfailed', request => {
  console.log(request.url + ' ' + request.failure().errorText);
});
```

#### request.frame()
- returns: <?[Frame]> A matching [Frame] object, or `null` if navigating to error pages.

#### request.headers()
- returns: <[Object]> An object with HTTP headers associated with the request. All header names are lower-case.

#### request.method()
- returns: <[string]> Request's method (GET, POST, etc.)

#### request.postData()
- returns: <[string]> Request's post body, if any.

#### request.resourceType()
- returns: <[string]>

Contains the request's resource type as it was perceived by the rendering engine.
ResourceType will be one of the following: `document`, `stylesheet`, `image`, `media`, `font`, `script`, `texttrack`, `xhr`, `fetch`, `eventsource`, `websocket`, `manifest`, `other`.

#### request.respond(response)
- `response` <[Object]> Response that will fulfill this request
  - `status` <[number]> Response status code, defaults to `200`.
  - `headers` <[Object]> Optional response headers
  - `contentType` <[string]> If set, equals to setting `Content-Type` response header
  - `body` <[Buffer]|[string]> Optional response body
- returns: <[Promise]>

Fulfills request with given response. To use this, request interception should
be enabled with `page.setRequestInterception`. Exception is thrown if
request interception is not enabled.

An example of fulfilling all requests with 404 responses:

```js
await page.setRequestInterception(true);
page.on('request', request => {
  request.respond({
    status: 404,
    contentType: 'text/plain',
    body: 'Not Found!'
  });
});
```

> **NOTE** Mocking responses for dataURL requests is not supported.
> Calling `request.respond` for a dataURL request is a noop.

#### request.response()
- returns: <?[Response]> A matching [Response] object, or `null` if the response has not been received yet.

#### request.url()
- returns: <[string]> URL of the request.

### class: Response

[Response] class represents responses which are received by page.

#### response.buffer()
- returns: <Promise<[Buffer]>> Promise which resolves to a buffer with response body.

#### response.headers()
- returns: <[Object]> An object with HTTP headers associated with the response. All header names are lower-case.

#### response.json()
- returns: <Promise<[Object]>> Promise which resolves to a JSON representation of response body.

This method will throw if the response body is not parsable via `JSON.parse`.

#### response.ok()
- returns: <[boolean]>

Contains a boolean stating whether the response was successful (status in the range 200-299) or not.

#### response.request()
- returns: <[Request]> A matching [Request] object.

#### response.status()
- returns: <[number]>

Contains the status code of the response (e.g., 200 for a success).

#### response.text()
- returns: <[Promise]<[string]>> Promise which resolves to a text representation of response body.

#### response.url()
- returns: <[string]>

Contains the URL of the response.

### class: Target

#### target.createCDPSession()
- returns: <[Promise]<[CDPSession]>>

Creates a Chrome Devtools Protocol session attached to the target.

#### target.page()
- returns: <[Promise]<?[Page]>>

If the target is not of type `"page"`, returns `null`.

#### target.type()
- returns: <[string]>

Identifies what kind of target this is. Can be `"page"`, `"service_worker"`, or `"other"`.

#### target.url()
- returns: <[string]>


### class: CDPSession

* extends: [`EventEmitter`](https://nodejs.org/api/events.html#events_class_eventemitter)

The `CDPSession` instances are used to talk raw Chrome Devtools Protocol:
- protocol methods can be called with `session.send` method.
- protocol events can be subscribed to with `session.on` method.

Documentation on DevTools Protocol can be found here: [DevTools Protocol Viewer](https://chromedevtools.github.io/devtools-protocol/).

```js
const client = await page.target().createCDPSession();
await client.send('Animation.enable');
await client.on('Animation.animationCreated', () => console.log('Animation created!'));
const response = await client.send('Animation.getPlaybackRate');
console.log('playback rate is ' + response.playbackRate);
await client.send('Animation.setPlaybackRate', {
  playbackRate: response.playbackRate / 2
});
```

#### cdpSession.detach()
- returns: <[Promise]>

Detaches session from target. Once detached, session won't emit any events and can't be used
to send messages.

#### cdpSession.send(method[, params])
- `method` <[string]> protocol method name
- `params` <[Object]> Optional method parameters
- returns: <[Promise]<[Object]>>


### class: Coverage

Coverage gathers information about parts of JavaScript and CSS that were used by the page.

An example of using JavaScript and CSS coverage to get percentage of initially
executed code:

```js
// Enable both JavaScript and CSS coverage
await Promise.all([
  page.startJSCoverage(),
  page.startCSSCoverage()
]);
// Navigate to page
await page.goto('https://example.com');
// Disable both JavaScript and CSS coverage
const [jsCoverage, cssCoverage] = await Promise.all([
  page.stopJSCoverage(),
  page.stopCSSCoverage(),
]);
let totalBytes = 0;
let usedBytes = 0;
const coverage = [].concat(jsCoverage, cssCoverage);
for (const entry of coverage) {
  totalBytes += entry.text.length;
  for (const range of entry.ranges)
    usedBytes += range.end - range.start - 1;
}
console.log(`Bytes used: ${usedBytes / totalBytes * 100}%`);
```

#### coverage.startCSSCoverage(options)
- `options` <[Object]>  Set of configurable options for coverage
  - `resetOnNavigation` <[boolean]> Whether to reset coverage on every navigation. Defaults to `true`.
- returns: <[Promise]> Promise that resolves when coverage is started

#### coverage.startJSCoverage(options)
- `options` <[Object]>  Set of configurable options for coverage
  - `resetOnNavigation` <[boolean]> Whether to reset coverage on every navigation. Defaults to `true`.
- returns: <[Promise]> Promise that resolves when coverage is started

#### coverage.stopCSSCoverage()
- returns: <[Promise]<[Array]<[Object]>>> Promise that resolves to the array of coverage reports for all stylesheets
  - `url` <[string]> StyleSheet URL
  - `text` <[string]> StyleSheet content
  - `ranges` <[Array]<[Object]>> StyleSheet ranges that were used. Ranges are sorted and non-overlapping.
    - `start` <[number]> A start offset in text, inclusive
    - `end` <[number]> An end offset in text, exclusive

> **NOTE** CSS Coverage doesn't include dynamically injected style tags without sourceURLs.


#### coverage.stopJSCoverage()
- returns: <[Promise]<[Array]<[Object]>>> Promise that resolves to the array of coverage reports for all non-anonymous scripts
  - `url` <[string]> Script URL
  - `text` <[string]> Script content
  - `ranges` <[Array]<[Object]>> Script ranges that were executed. Ranges are sorted and non-overlapping.
    - `start` <[number]> A start offset in text, inclusive
    - `end` <[number]> An end offset in text, exclusive

> **NOTE** JavaScript Coverage doesn't include anonymous scripts; however, scripts with sourceURLs are
reported.


[Array]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array "Array"
[boolean]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#Boolean_type "Boolean"
[Buffer]: https://nodejs.org/api/buffer.html#buffer_class_buffer "Buffer"
[function]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function "Function"
[number]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#Number_type "Number"
[Object]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object "Object"
[Page]: #class-page "Page"
[Promise]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise "Promise"
[string]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#String_type "String"
[stream.Readable]: https://nodejs.org/api/stream.html#stream_class_stream_readable "stream.Readable"
[CDPSession]: #class-cdpsession  "CDPSession"
[Error]: https://nodejs.org/api/errors.html#errors_class_error "Error"
[Frame]: #class-frame "Frame"
[ConsoleMessage]: #class-consolemessage "ConsoleMessage"
[ChildProcess]: https://nodejs.org/api/child_process.html "ChildProcess"
[Coverage]: #class-coverage "Coverage"
[iterator]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols "Iterator"
[Response]: #class-response  "Response"
[Request]: #class-request  "Request"
[Browser]: #class-browser  "Browser"
[Body]: #class-body  "Body"
[Element]: https://developer.mozilla.org/en-US/docs/Web/API/element "Element"
[Keyboard]: #class-keyboard "Keyboard"
[Dialog]: #class-dialog  "Dialog"
[JSHandle]: #class-jshandle "JSHandle"
[ExecutionContext]: #class-executioncontext "ExecutionContext"
[Mouse]: #class-mouse "Mouse"
[Map]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map "Map"
[selector]: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors "selector"
[Tracing]: #class-tracing "Tracing"
[ElementHandle]: #class-elementhandle "ElementHandle"
[UIEvent.detail]: https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/detail "UIEvent.detail"
[Serializable]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify#Description "Serializable"
[Touchscreen]: #class-touchscreen "Touchscreen"
[Target]: #class-target "Target"
[USKeyboardLayout]: ../lib/USKeyboardLayout.js "USKeyboardLayout"
