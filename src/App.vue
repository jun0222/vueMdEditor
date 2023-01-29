<template>
  <div id="app">
    <mavon-editor
      style="height: 100%"
      v-model="value"
      language="ja"
      :toolbars="toolbars"
    ></mavon-editor>
  </div>
</template>

<style scoped>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: auto;
  margin-top: 60px;
  width: 90vw;
  height: 90vh;
}
</style>

<script>
import Vue from "vue";
import mavonEditor from "mavon-editor";
import "mavon-editor/dist/css/index.css";
Vue.use(mavonEditor);

export default {
  name: "editor",
  data() {
    return {
      value: "",
      toolbars: {
        bold: true,
        italic: true,
        header: true,
        underline: true,
        strikethrough: true,
        mark: true,
        superscript: true,
        subscript: true,
        quote: true,
        ol: true,
        ul: true,
        link: true,
        imagelink: true,
        code: true,
        table: true,
        fullscreen: false,
        readmodel: false,
        htmlcode: true,
        help: false,
        /* 1.3.5 */
        undo: true,
        redo: true,
        trash: true,
        save: true,
        /* 1.4.2 */
        navigation: false,
        /* 2.1.8 */
        alignleft: true,
        aligncenter: true,
        alignright: true,
        /* 2.2.1 */
        subfield: false,
        preview: false,
      },
    };
  },
};
</script>
