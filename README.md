# 攀山快答 · 教师改编版

一个可以直接拿去改的华文词语游戏。90 秒，看词语选释义，答对往上爬一格，答错扣三秒。

改成你自己单元的词语，**只需要改一个文件，不需要会编码，也不需要注册任何账号**。

原版是「词山学海」里的攀山快答。这个版本是为了让老师改而重写的：一个 HTML 文件，三张图，没有任何外部依赖。

---

## 三步改成你自己的

### 1. 下载

点这个页面右上角绿色的 **Code** 按钮 → **Download ZIP** → 解压。

### 2. 改词语

解压出来的文件夹里，用记事本（Windows）或「文本编辑」（Mac）打开 **`my-words.js`**。

只改这一段就好：

```js
const UNIT_NAME = "中三 单元一";     // 单元名称，会显示在开始画面
const SECONDS   = 90;                // 每局几秒

const VOCAB = [
  { word: "维护", def: "保持、保障，使不受破坏" },
  { word: "策略", def: "为了达到某个目标而定下的计划或方法" },
  // 照这个格式往下加，别忘了行尾的逗号
];
```

三条规则：

1. 每一行都是 `{ word: "词语", def: "释义" },`
2. 行尾要有逗号 `,`
3. 至少 4 个词语才跑得起来，建议 8 个以上

**错误答案不用你写。** 程序会自动从你其他词语的释义里抓三个当干扰项，所以你的词语越多，题目越有挑战性。

### 3. 打开来玩

双击 `index.html`，就在浏览器里跑起来了。

改了词语之后，回到浏览器按刷新（Mac 是 `Cmd + R`，Windows 是 `Ctrl + R`）就能看到新的。

---

## 想让学生也能玩？

上面三步做出来的是你电脑上的版本。想变成一个可以发给学生的网址，就要把它放上 GitHub Pages：

1. 在这个页面右上角点 **Fork**，取一个自己的 repo 名字
2. 进你自己那个 repo → **Settings** → **Pages**
3. Source 选 **Deploy from a branch**，分支选 **main**，文件夹选 **/ (root)** → **Save**
4. 在 GitHub 网页上直接点开 `my-words.js` → 点铅笔图标 → 改词语 → **Commit changes**
5. 等一两分钟，打开 `https://你的用户名.github.io/你的repo名/`

这个网址就可以发给学生了。免费，不限人数，没有广告。

---

## 常见问题

**打开是一片空白 / 出现「词语表好像有点问题」**

页面会直接告诉你第几行写错了。九成是这三样之一：行尾少了逗号、引号少了一边、大括号少了一边。照着提示改，刷新就好。

**Mac 上用「文本编辑」打开会不会弄坏文件？**

`my-words.js` 是纯文本文件，「文本编辑」会正常打开，不会有问题。（`index.html` 才要小心，但你不需要动它。）

**GitHub Pages 打开是 404**

刚开启 Pages 要等一到两分钟才生效。等一下，然后强制刷新（Mac `Cmd + Shift + R`，Windows `Ctrl + F5`）。

**学校网络打不开 GitHub**

有些学校的网络会挡。用手机热点，或者回家再弄。前面「三步改成你自己的」那条路完全不需要网络。

**词语很多会不会太慢？**

不会。几百个词语都没问题，程序每次只抽一个。

---

## 想换个头像？

`art/climber.png` 是一张 6 格并排的动作图。你可以用 ChatGPT 或其他 AI 绘图工具生成一张新的，换掉它就行。

生成的时候要说清楚这几点，不然做出来的图对不上：

- **6 格横向并排**，每一格宽高相同
- 角色**朝右**
- 六个动作依序是：站立 · 走 A · 走 B · 爬 A · 爬 B · 举手庆祝
- 背景用**纯洋红色 `#FF00FF`**（之后去背用），或者直接出透明背景的 PNG
- **不要有任何文字、字母、数字或标志**

换好之后，把文件命名为 `climber.png`，放回 `art/` 文件夹，刷新就看得到。

如果新图的格子宽高比跟原来不一样，到 `index.html` 的 `.climber` 那几行把 `width` 和 `height` 调一下就好。

---

## 出处

原版「攀山快答」是[词山学海](https://btvssclunit.github.io/VocabSummit)的一部分。

这个教师改编版由 [Chun Kai Xin 郑凯欣](https://kaixinbuilds.github.io) 为「2026 AI in Sec CL NLC」工作坊重写，MIT 许可，欢迎自由改编，保留署名即可。

`art/` 里的图片一并提供给老师教学与改编使用。你也完全可以换成自己的。

做出来了？欢迎让我看看。

---

# VocabClimb Starter (English)

A Chinese vocabulary climbing game that teachers can adapt without writing code.
90 seconds, match the word to its meaning, climb one ledge per correct answer, lose three seconds per mistake.

**To make it yours:** download the ZIP, open `my-words.js` in any plain text editor, replace the word list, and open `index.html`. Nothing to install, no account, no build step. Wrong answers are generated automatically from your other entries.

To give students a link, fork this repo and switch on GitHub Pages under Settings → Pages (branch `main`, folder `/ (root)`).

Adapted from 攀山快答 in [VocabSummit](https://btvssclunit.github.io/VocabSummit). MIT licensed. Art assets included for teaching use and adaptation.
