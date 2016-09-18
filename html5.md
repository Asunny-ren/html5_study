# HTML5

https://developer.mozilla.org/zh-CN/docs/Web/Guide/HTML/HTML5

* 语义：能够让你更恰当地描述你的内容是什么。
* 连通性：能够让你和服务器之间通过创新的新技术方法进行通信。
* 离线&存储：能够让网页在客户端本地存储数据以及更高效地离线运行。
* 多媒体：使 video 和 audio 成为了在所有 Web 中的一等公民。
* 2D/3D 绘图&效果：提供了一个更加分化范围的呈现选择。
* 性能&集成：提供了非常显著的性能优化和更有效的计算机硬件使用。
* 设备访问Device Access：能够处理各种输入和输出设备。
* 样式设计：让作者们来创作更加复杂的主题吧！

## 语义

#### 节段
 * section：表示文档中的一个区域（或节），通常包含一个标题标签来标识每一个section
 * article：元素表示文档、页面、应用或网站中的独立结构，其意在成为可独立分配的或可复用的结构，如在发布中，它可能是论坛帖子、杂志或新闻文章、博客、用户提交的评论、交互式组件，或者其他独立的内容项目。
 * nav：HTML导航栏 (<nav>) 描绘一个含有多个超链接的区域，这个区域包含转到其他页面，或者页面内部其他部分的链接列表.
 * header：元素表示一组引导性的帮助，可能包含标题元素，也可以包含其他元素，像logo、分节头部、搜索表单等。
 * footer：元素表示最近一个章节内容或者根节点（sectioning root ）元素的页脚。一个页脚通常包含该章节作者、版权数据或者与文档相关的链接等信息。
 * aside：元素中连接到页面中其他部分的内容，被认为是独立于该内容的一部分并且可以被单独的拆分出来而不会使整体受影响。其通常表现为侧边栏或者被插入在该内容里。他们通常包含在工具条，例如来自词汇表的定义。也可能有其他类型的信息，例如相关的广告、笔者的传记、web 应用程序、个人资料信息，或在博客上的相关链接。
 * hgroup：代表一个段的标题。它规定了在文档轮廓里（the outline of the document ）的单一标题是它所属的隐式或显式部分的标题。

## 音频和视频
### audio
##### 属性

  * autoplay
   布尔属性；如果指定（即使值为"false"！）；指定后，音频会马上自动开始播放，不会停下来等着数据载入结束。

  * autobuffer 已废弃 Gecko 2.0
布尔属性；如果指定，音频将会自动开始加载。即使没有设置自动播放。直到媒体缓存满了或者全部音频文件加载完毕，即使是在首次进入时。该属性应该仅仅用在用户可能会选择播放的音频上；例如用户通过“播放音频”链接来到的一个页面。该属性已在Gecko 2.0 (Firefox 4 / Thunderbird 3.3 / SeaMonkey 2.1) 中移除，使用preload属性取而代之。

  * buffered
你可以通过该属性获取已缓冲的资源的时间段信息。该属性包含一个 TimeRanges 对象。

  * controls
如果设置了该属性，浏览器将提供一个包含声音，播放进度，播放暂停的控制面板，让用户可以控制音频的播放。

  * loop
布尔属性；如果指定，将循环播放音频。

  * mozCurrentSampleOffset
在音频播放时，表示相对于音频开始处的偏移量的一个数值。

  * muted
表示是否静音的布尔值。默认值为false，表示有声音。

  * played
一个TimeRanges 对象，表示所有已播放的音频片段。

  * preload
枚举属性，让开发者自行思考来示意浏览器使用何种加载方式以达到最好的用户体验。可以是以下属性之一：

  * none: 示意用户可能不会播放该音频，或者服务器希望节省带宽；换句话说，该音频不会被缓存；

  * metadata: 示意即使用户可能不会播放该音频，但获取元数据 (例如音频长度) 还是有必要的。

  * auto: 示意用户可能会播放音频；换句话说，如果有必要，整个音频都将被加载，即使用户不期望使用。
空字符串 : 等效于auto属性。
假如不设置，默认值就是浏览器定义的了（即，不同浏览器会选择自己的默认值）， 即使规范建议设置为 metadata.

 使用备注：
autoplay 属性优先于 preload 假如用户想自动播放视频，那么很明显浏览器需要下载视频。同时设置autoplay 和 preload属性在规范里是允许的。
规范没有强制浏览器去遵循该属性的值；这仅仅只是个提示。
src
嵌入的音频的URL。 该URL应遵从 HTTP access controls. 这是一个可选属性；你可以在audio元素中使用 <source> 元素来替代该属性指定嵌入的音频。
volume
音频播放的音量。值从0.0 (无声) 到 1.0 (最大声).
时间偏移量目前是指定为float类型的值，表示偏移的秒数。

备注： HTML 5 规范中，时间偏移量值的定义还没有完成，有可能会变更。

##### 事件
``` html
<!-- Simple audio playback -->
<audio src="http://developer.mozilla.org/@api/deki/files/2926/=AudioTest_(1).ogg" autoplay>
  Your browser does not support the <code>audio</code> element.
</audio>

<!-- Audio playback with captions -->
<audio src="foo.ogg">
  <track kind="captions" src="foo.en.vtt" srclang="en" label="English">
  <track kind="captions" src="foo.sv.vtt" srclang="sv" label="Svenska">
</audio>
```
使用source元素的audio元素

``` html
<audio controls="controls">
Your browser does not support the <code>audio</code> element.
<source src="foo.wav" type="audio/wav">
</audio>
```

### video

  * autoplay
 布尔属性；指定后，视频会马上自动开始播放，不会停下来等着数据载入结束。

  * autobuffer  
 布尔属性；指定后，视频会自动开始缓存，即使没有设置自动播放。该属性适用于视频被认为可能会播放（比如，用户导航到专门播放视频的页面，而不是那种嵌入视频还有其它内容的页面）。视频会一直缓存到媒体缓存满。
 实现备注： 虽然是HTML5规范的早期草案的一部分， autobuffer 属性在稍晚的版本被去掉了。 Gecko 2.0 和其它浏览器中已经移除了这个属性，而且有些浏览器中从未实现。规范定义了一个新的枚举属性， preload， 用不同的语法来取代 autobuffer 属性。 bug 548523

  * buffered
 这个属性可以读取到哪段时间范围内的媒体被缓存了。该属性包含了一个 TimeRanges 对象。

  * controls
 加上这个属性，Gecko 会提供用户控制，允许用户控制视频的播放，包括音量，跨帧，暂停/恢复播放。

  * crossorigin
 该枚举属性指明抓取相关图片是否必须用到CORS（跨域资源共享）。 支持CORS的资源 可在 canvas 元素中被重用，而不会被污染。允许的值如下：
 * anonymous
 跨域请求（即，使用 Origin: 的HTTP头）会被执行。但是不发送凭证（即，不发送cookie， X.509 证书或者 HTTP Basic 授权）。如果服务器不提供证书给源站点 (不设置 Access-Control-Allow-Origin: HTTP头)，图片会被 污染 并且它的使用会受限。
 * use-credentials
 跨域请求A cross-origin request (i.e. with Origin: HTTP header) 会被执行，且凭证会被发送 (即， 发送一个 cookie, 一个证书和HTTP Basic授权会被执行)。如果服务器不提供证书给源站点 (通过Access-Control-Allow-Credentials: HTTP 头)，图像会被 污染 且它的使用会受限。
 不加这个属性时，抓取资源不会走CORS请求(即，不会发送 Origin: HTTP 头)，保证其在 canvas 元素中使用时不会被污染。如果指定非法值，会被当作指定了枚举关键字 anonymous 一样使用。 查看 CORS 设置属性 获取更多信息。

  * height
 视频展示区域的高度，单位是CSS像素。

  * loop
 布尔属性；指定后，会在视频结尾的地方，自动返回视频开始的地方。

  * muted
 布尔属性，指明了视频里的音频的默认设置。设置后，音频会初始化为静音。默认值是false,意味着视频播放的时候音频也会播放 。

  * played
 一个 TimeRanges 对象，指明了视频已经播放的所有范围。

  * preload
 该枚举属性旨在告诉浏览器作者认为达到最佳的用户体验的方式是什么。可能是下列值之一：
 * none: 提示作者认为用户不需要查看该视频，服务器也想要最小化访问流量；换句话说就是提示浏览器该视频不需要缓存。
 * metadata: 提示尽管作者认为用户不需要查看该视频，不过抓取元数据（比如：长度）还是很合理的。
 * auto: 用户需要这个视频优先加载；换句话说就是提示：如果需要的话，可以下载整个视频，即使用户并不一定会用它。
 空字符串：也就代指 auto 值。
 假如不设置，默认值就是浏览器定义的了 （即，不同浏览器会选择自己的默认值），即使规范建议设置为 metadata。

 使用备注：
 autoplay 属性优先于 preload 假如用户想自动播放视频，那么很明显浏览器需要下载视频。同时设置autoplay 和 preload属性在规范里是允许的。
 规范没有强制浏览器去遵循该属性的值；这仅仅只是个提示。
 poster
 一个海报帧的URL，用于在用户播放或者跳帧之前展示。如果属性未指定，那么在第一帧可用之前什么都不会展示；之后第一帧就像海报帧一样展示。

  * src
 要嵌到页面的视频的URL。可选；你也可以使用video块内的 <source> 元素来指定需要嵌到页面的视频。

  * width
 视频显示区域的宽度，单位是CSS像素。
 时间偏移量目前是指定为float类型的值，表示偏移的秒数。

 备注： HTML 5 规范中，时间偏移量值的定义还没有完成，有可能会变更。


##### 事件

``` html
<!-- Simple video example -->
<video src="videofile.ogg" autoplay poster="posterimage.jpg">
  抱歉，您的浏览器不支持内嵌视频，不过不用担心，你可以 <a href="videofile.ogg">下载</a>
  并用你喜欢的播放器观看!
</video>

<!-- Video with subtitles -->
<video src="foo.ogg">
  <track kind="subtitles" src="foo.en.vtt" srclang="en" label="English">
  <track kind="subtitles" src="foo.sv.vtt" srclang="sv" label="Svenska">
</video>
<!--
第一个例子播放一个视频，视频一收到，允许播放的时候就会立马开始播放，而不会停下来直到下载更多内容。 图片 "posterimage.jpg" 会一直展示在视频区域，直到开始播放。

第二个例子允许用户选择不同的字幕。
-->
```
