<template>
  <div id="app">
    ほぎぃ
    {{state.test}}
  </div>
</template>

<script lang="ts">
import { createComponent, reactive } from '@vue/composition-api'
export default createComponent ({
  setup() {
    const state = reactive<{
      test: string
    }>({
      test: "ほぎぃ"
    })

    return {
      state
    }
  }
})
</script>
