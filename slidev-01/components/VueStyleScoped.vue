<template>
  <div flex flex-col justify-start items-center h-sm>
    <div flex>
      <div class="box-1 whitespace-nowrap relative left-16">这是box-1</div>
      <div>
        <pre>
          .box-1[{{ state.box1Property }}] {
            color: red;
          }
        </pre>
      </div>
    </div>
    <div v-click="1" flex>
      <div class="box-2 whitespace-nowrap relative left-16">这是box-2</div>
      <div>
        <pre>
          .box-2[{{ state.box2Property }}] {
            color: blue;
          }
        </pre>
      </div>
    </div>
  </div>
</template>
<script setup lang="ts">
import { reactive, onMounted } from 'vue'

const state = reactive({
  box1Property: 'data-',
  box2Property: 'data-',
})

onMounted(() => {
  const box1 = document.querySelector('.box-1') as HTMLElement
  const box2 = document.querySelector('.box-2') as HTMLElement
  state.box1Property += getProperty(box1)
  state.box2Property += getProperty(box2)
})

function getProperty(node: HTMLElement) {
  const property = Object.keys({ ...node?.dataset })[0]
  return property
}
</script>
<style scoped>
.box-1 {
  color: red;
}

.box-2 {
  color: blue;
}
</style>
