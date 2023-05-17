---
# try also 'default' to start simple
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://source.unsplash.com/collection/94734566/1920x1080
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: true
# some information about the slides, markdown enabled
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# persist drawings in exports and build
drawings:
  persist: false
# page transition
transition: slide-left
# use UnoCSS
css: unocss
---

# Some CSS write way test


---
layout: image-right
image: https://source.unsplash.com/collection/94734566/1920x1080
---

# Author: ajycc20


---
layout: default
---

# CSS 约定

* OOCSS——面向对象的CSS，由Nicole Sullivan创建。
* SMACSS——可扩展的、模块化CSS架构，由Jonathan Snook创建。
* BEM——块（Block）、元素（Element）和修饰符（Modifier），由Yandex公司提出。
* ITCSS——倒三角形CSS，由Harry Roberts创建。

---
layout: default
---

# CSS 书写方式

* style scoped in Vue.js
* CSS Modules
* CSS in JS
* CSS atomic like Windi CSS 、Tailwind CSS 、UnoCSS

---
layout: default
---

# CSS selector 优先级

|     |     |     |     |     |     |
| :---: | :---: | :---: | :---: | :---: | :---: |
|选择器|内联样式|ID|类|标签|标记|
| html body header h1 | 0 | 0 | 0 | 4 | 0,0,0,4 |
| body header.page-header h1 | 0 | 0 | 1 | 3 | 0,0,1,3 |
| .page-header .title | 0 | 0 | 2 | 0 | 0,0,2,0 |
| #page-title | 0 | 1 | 0 | 0 | 0,1,0,0 |
| `<span style="color:red">style="color:red"</span>` | 1 | 0 | 0 | 0 | 1,0,0,0 |

---
layout: end
---

