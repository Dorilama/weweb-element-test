<template>
  <div class="my-element">
    <p :style="textStyle">I am a custom element !</p>
    <p>v0.0.10</p>
    <p>{{ version }}</p>
  </div>
</template>

<script>
import { version } from "@instantdb/core";
export default {
  setup() {
    return { version };
  },
  props: {
    content: { type: Object, required: true },
  },
  computed: {
    textStyle() {
      return {
        color: this.content.textColor,
      };
    },
  },
};
</script>

<style lang="scss" scoped>
.my-element {
  p {
    font-size: 18px;
  }
}
</style>
