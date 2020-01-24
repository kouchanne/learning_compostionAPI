<template>
  <div id="app">
    {{state.test}}
    {{refStr}}
    <Test message="てすとまる"></Test>
    <router-view />
  </div>
</template>

<script lang="ts">
import { createComponent, reactive, ref } from '@vue/composition-api'
import Test from './components/Test.vue'
export default createComponent ({
  components: {
    Test
  },
  setup() {
    const state = reactive<{
      test: string
    }>({
      test: "ほぎぃ"
    })
    const refStr = ref<string>("れふれふ")

    return {
      state,
      refStr
    }
  }
})
</script>
