
第一个问题是字体配置问题
现在的Geist配置文件方式不是传统的类引入Geist或者GeistMono+GeistSans

原来应该是
```js
import { GeistSans， Geist_Mono } from "geist/font";

const Geist = GeistSans;

const geistMono = GeistMono({
  variable: "--font-geist-mono",
  subsets: ["latin"],
});
const geistSans = GeistSans({
  variable: "--font-geist-sans",
  subsets: ["latin"],
});
最后在调用的时候直接使用


```
应该修改为
```js
import { GeistSans } from "geist/font/sans";
import { GeistMono } from "geist/font/mono";

const geistSans = GeistSans.variable;

const geistMono = GeistMono.variable;
```