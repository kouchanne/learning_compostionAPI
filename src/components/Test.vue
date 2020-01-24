<template>
  <div class="test">
    コンポーネントのテスト
    {{state.path}}
    {{state.message}}
  </div>
</template>
<script lang="ts">
type Props = {
  message: String
}
import { createComponent, reactive, ref, SetupContext } from '@vue/composition-api'
export default createComponent({
  props: {
    message: {
      type: String,
      default: "default messageですよ"
    }
  },
  setup(props: Props, context: SetupContext) {
    // context で 今まで $vue で直接触ってたやつをスコープ状態にして参照するようになった
    const route = context.root.$route.path
    const state = reactive<{
      path: String,
      message: String
    }>({
      path: route,
      message: props.message
    })

    return {
      state
    }
  }
})
</script>