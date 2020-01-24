<template>
  <div class="test">
    コンポーネントのテスト
    {{hoge}}
  </div>
</template>
<script lang="ts">
type Props = {
  message: String
}
import { createComponent, reactive, ref } from '@vue/composition-api'
export default createComponent({
  props: {
    message: {
      type: String,
      default: "default messageですよ"
    }
  },
  setup(props: Props) {
    const hoge = ref<string>(props.message)

    return {
      hoge
    }
  }
})
</script>