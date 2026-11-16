***

name: easyvideo

description: 用 EasyVideo 把视频做成网页（film.html + window.film）。当用户要出片、混剪、复刻、做动画 / 宣传片 / 讲解片、剪辑、检查、渲染导出 MP4，或要打开 EasyVideo 及其 Studio 时使用。



***

# EasyVideo

## 安装 CLI

一条命令，直接从 Release 上的 tarball 装 —— 不经过 npm registry，也不用自己装 Node / Chromium /ffmpeg：



```
npx -y https://github.com/EasyVideoAI/EasyVideoAI/releases/latest/download/easyvideo.tgz
```

如果 `npx` 不认这个地址（老版本 npm 会把 URL 当成命令名），改用：



```
npm i -g https://github.com/EasyVideoAI/EasyVideoAI/releases/latest/download/easyvideo.tgz
easyvideo
```

报 404 说明 tag 或资产名写错了 —— 去 Release 页面核对，不要换别的版本号乱试。

这个 tarball 必须是 npm 包（里面有 `package.json` 和 `bin/`）。运行时的 `.zip` 不能用这条命令装：只能解压后用里面自带的 `node.exe` 跑。

## 已经装过？

`easyvideo` 在 PATH 里就直接跑，不要重装，也不要顺手升级。

## 然后按它打印的手册做事

不带参数运行时，CLI 会打印完整手册：它自带哪些技能、一个片子怎么搭、媒体和 canvas 怎么用。动手前先读这次任务需要的那一章，需要时再跑一遍手册。

## 不要做



* 不要自己装 Node、Chromium、ffmpeg—— 运行时已经自带。

* 不要在同一个工程上同时跑两个 `render` / `look`，它们会抢 `.film/`。

* 不要删 `.film/`；改完页面要重渲，就用 `--fresh` 或换一个 `--out`。