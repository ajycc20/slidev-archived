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
title: CSS 书写建议及选择器使用简介
---

# CSS 书写建议及选择器使用简介

---
layout: center
---

# CSS 书写方式

---
layout: two-cols
---

# style scoped in Vue.js

```vue{2,7-9|3,10-12|all}
<template>
  <div class="box-1">这是box1</div>
  <div class="box-2">这是box2</div>
</template>

<style scoped>
.box-1 {
  color: red;
}
.box-2 {
  color: blue;
}
</style>
```
::right::

# Renderer
<br />

<VueStyleScoped></VueStyleScoped>

---
layout: two-cols
---

# CSS Modules in Vue.js

```vue{2,7-9|3,10-12|all}
<template>
  <div :class="$style.blue">这是蓝色的</div>
  <div :class="$style.red">这是红色的</div>
</template>

<style module>
.blue {
  color: blue;
}
.red {
  color: red;
}
</style>
```

::right::

# Renderer
<br />
<VueStyleModule></VueStyleModule>


---
layout: two-cols
---
# Atomic CSS

```vue
<template>
  <div 
    flex
    overflow-hidden
    justify-center
    items-center
    h-40 w-40
    border="~ 4 dashed black"
  >
    <div class="w-20 h-40 bg-blue"></div>
    <div class="w-20 h-40 bg-red"></div>
  </div>
</template>
```

::right::

# Renderer
<br />
<VueStyleAtom v-click></VueStyleAtom>

<!-- CSS atomic like Windi CSS 、Tailwind CSS 、UnoCSS -->

---
layout: center
---

# CSS selector 优先级及使用推荐

---
layout: two-cols
---

# Demo 1

```vue
<template>
  <div>
    <header>
      <div>
        <p>这里是最终的文本展示</p>
      </div>
    </header>
  </div>
</template>

<style scoped>
div header div p {
  color: red;
}
header div p {
  color: blue;
}
</style>
```

::right::

# Playground

<DemoOne v-click></DemoOne>

---
layout: two-cols
---

# Demo 2

```vue
<template>
  <div class="container">
    <header>
      <div>
        <p>这里是最终的文本展示</p>
      </div>
    </header>
  </div>
</template>

<style scoped>
div header div p {
  color: blue;
}
.container header div p {
  color: red;
}
</style>
```

::right::

# Playground

<DemoTwo v-click></DemoTwo>

---
layout: two-cols
---

# Demo 3

```vue
<template>
  <div id="container" class="container">
    <header>
      <div>
        <p class="content" id="content">这里是最终的文本展示</p>
      </div>
    </header>
  </div>
</template>
<style scoped>
#container header div .content {
  color: green;
}
#content {
  color: yellow;
}
div header div .content {
  color: red;
}
.container header div p {
  color: blue;
}
</style>
```

::right::

<DemoThree v-click></DemoThree>

---
layout: two-cols
---

# Demo 4

```vue
<template>
  <div id="container" class="container">
    <header>
      <div>
        <p style="color:pink" class="content" id="content">这里是最终的文本展示</p>
      </div>
    </header>
  </div>
</template>
<style scoped>
#container header div .content {
  color: green;
}
#content {
  color: yellow;
}
div header div .content #content {
  color: red;
}
.container header div #content {
  color: blue;
}
</style>

```

::right::

# Playground

<DemoFour v-click></DemoFour>

---
layout: default
---

# CSS selector 优先级

|     |     |     |     |     |     |
| :---: | :---: | :---: | :---: | :---: | :---: |
|选择器|内联样式|ID|类/属性/伪类|标签/伪元素|标记|
| div header div p | 0 | 0 | 0 | 4 | 0,0,0,4 |
| .container header div p | 0 | 0 | 1 | 3 | 0,0,1,3 |
| .container header div .content | 0 | 0 | 2 | 0 | 0,0,2,2 |
| #container header div #content | 0 | 1 | 0 | 0 | 0,2,0,0 |
| `<span style="color:red">style="color:red"</span>` | 1 | 0 | 0 | 0 | 1,0,0,0 |

---
layout: end
---

