<template lang="pug">
div
  p {{ name }} ({{ age }})
  p Triple score: {{ triple }}
  button(@click="onClickButton") Click Me!
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";

@Component
export default class SampleComponent extends Vue {
  name = "simochee";
  age = 21;
  score = 55;

  mounted() {
    // コンポーネントがマウントされたときの処理
    console.log("life cycle hook：mounted");
  }

  beforeDestroy() {
    // コンポーネントが破棄される直前の処理
    console.log("life cycle hook：beforeDestroy");
  }

  get triple() {
    return this.score * 3;
  }

  onClickButton() {
    alert("button pushed!");
  }
}
</script>