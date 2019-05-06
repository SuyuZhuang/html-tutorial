# URL

URL 是“统一资源定位符”（Uniform Resource Locator）的首字母缩写，中文译为“网址”，表示各种资源在互联网上的地址。下面就是一个典型的 URL。

```html
https://www.example.com/path/index.html
```

这些资源通常是文件，比如网页文件、图像文件、媒体文件、脚本文件等等。只要知道了它们的 URL，才可能在互联网上获取它们。

互联网的所有资源，通常都有一个或多个 URL 与之对应。

## 组成

URL 由多个部分组成。比如，`https://www.example.com/path/index.html`这个 URL，就可以分解成下面几个部分。

（1）协议（scheme）

协议指的是，浏览器处理该 URL 所要使用的方法。上例就是`https://`的部分，表示使用 HTTPs 协议。

互联网支持多种协议，必须指明网址使用哪一种协议，默认是 HTTP 协议。现在，HTTP 的加密版 HTTPS 协议越来越常见了，提供了更高的安全性。浏览器根据协议，处理网址所指向的资源。

协议后面紧跟着一个冒号和两个斜杠。但是，`mailto`协议是一个例外，它后面只有一个冒号，比如`mailto:foo@example.com`。

（2）主机（host）

主机是资源所在的网站名或服务器的名字。上例的主机是`www.example.com`。

（3）路径（path）

路径是资源在主机的位置。比如，`/path/index.html`这个路径，指向`/path`目录下面的`index.html`文件。

有时，路径指的是一个目录，不会包含文件名，结尾可能有斜杠，也可能没有斜杠。比如`/foo`和`/foo/`都可以是目录。这时，服务器通常会默认跳转到该目录里面的`index.html`文件（即等同于请求`/foo/index.html`），但也可能有其他的处理方法（比如列出目录里面的所有文件），这取决于服务器的设置。

## 合法字符

URL 只能使用 ASCII 码的可打印字符。为了表示那些不在这个范围的字符，允许将字符转义，即在该字符十六进制的ASCII码之前加上一个百分号。举例来说，字符`a`的十六进制ASCII是`61`，因此`www.apple.com`又可以写成`www.%61pple.com`。

有些字符在URL中具有特殊含义，就不能用在路径名之中。

- `%` 转义字符
- `/` 路径分隔符
- `.` 路径组件
- `..` 路径组件
- `#` 锚点标识符
- `?` 表示参数字符串
- `&` 参数分隔符
- `:` 表示传输协议的分隔符

## 绝对 URL 和相对 URL

URL 分成两种：绝对 URL 和相对 URL。

绝对 URL 指的是，只靠 URL 本身就能确定资源的位置。这意味着，URL 必须带有资源的完整信息，包含协议、主机、路径等部分。

相对 URL 指的是，URL 不包含资源位置的全部信息，必须结合当前网页的位置，才能定位资源。比如，当前网页的 URL 是`https://www.example.com/path/index.html`，该网页上面有一个资源，指向`a.html`，这个就是相对 URL。因为只知道`a.html`，并不能定位资源，还要知道当前网页的 URL 才可以。经过转换，从相对 URL 可以得到绝对 URL `https://www.example.com/path/a.html`。

相对 URL 如果以斜杠（`/`）开头，就表示根目录。否则，必须以当前目录为起点，推算资源的位置。比如，`foo/bar.html`表示在当前目录的`foo`子目录里面的`bar.html`文件。

相对 URL 还可以使用两个特殊写法，表示位置。

- `.`：表示当前目录，比如`./a.html`（当前目录下的`a.html`文件）
- `..`：表示上级目录，比如`../a.html`（上级目录下的`a.html`文件）

这两个写法可以多个连用，比如`../../`表示上两级目录。