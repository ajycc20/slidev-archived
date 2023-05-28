<template>
    <div class="box-blue" flex>
      <div relative left-16 :class="$style.blue">这是蓝色的</div>
      <div>
        <pre>
          .{{ state.box1Property }} {
            color: blue;
          }
        </pre>
      </div>
    </div>
    <div v-click="1" class="box-red" flex>
      <div relative left-16 :class="$style.red">这是红色的</div>
      <div>
        <pre>
          .{{ state.box2Property }} {
            color: red;
          }
        </pre>
      </div>
    </div>
</template>

<script setup lang="ts">
import { reactive, onMounted } from 'vue'

const state = reactive({
  box1Property: '',
  box2Property: '',
})

onMounted(() => {
  const box1 = document.querySelector('.box-blue')!.children[0]
  const box2 = document.querySelector('.box-red')!.children[0]
  
  state.box1Property = box1.className
  state.box2Property = box2.className
})

</script>

<style module>
.blue {
  color: blue;
}

.red {
  color: red;
}
</style>
