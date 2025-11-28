<template>
  <div class="my-element">
    <p :style="textStyle">I am a custom element !</p>
    <p>v0.0.9</p>
    <p>{{ t }}</p>
  </div>
</template>

<script>
import prettyMilliseconds from "pretty-ms";
export default {
  setup() {
    const t = prettyMilliseconds(1337000000);
    return { t };
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
