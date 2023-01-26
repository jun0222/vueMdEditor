<template>
  <div id="app">
    <div id="main">
      <mavon-editor v-model="value" language="ja" font-size="24px" />
    </div>
  </div>
</template>

<style scoped></style>

<script>
import Vue from "vue";
import mavonEditor from "mavon-editor";
import "mavon-editor/dist/css/index.css";
Vue.use(mavonEditor);

export default {
  name: "app",
  data() {
    return { value: "" };
  },
};
</script>
