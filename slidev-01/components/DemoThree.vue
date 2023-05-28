<template>
  <div id="container" class="container" flex justify-center items-center h-60>
    <header>
      <div>
        <p class="content" id="content">这里是最终的文本展示</p>
      </div>
    </header>
  </div>
</template>

<script setup lang="ts">

</script>

<style scoped>
#container header div .content {
  color: green;
}

#content {
  color:yellow;
}

div header div .content {
  color: red;
}

.container header div p {
  color: blue;
}
</style>
