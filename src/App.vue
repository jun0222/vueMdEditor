<template>
  <div id="app">
    <mavon-editor
      style="height: 100%"
      v-model="value"
      language="ja"
      :toolbars="toolbars"
      @save="save"
      font-size="32px"
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
        italic: false,
        header: true,
        underline: false,
        strikethrough: true,
        mark: false,
        superscript: false,
        subscript: false,
        quote: true,
        ol: false,
        ul: true,
        link: true,
        imagelink: false,
        code: true,
        table: true,
        fullscreen: false,
        readmodel: false,
        htmlcode: true,
        help: false,
        /* 1.3.5 */
        undo: true,
        redo: true,
        trash: false,
        save: true,
        /* 1.4.2 */
        navigation: false,
        /* 2.1.8 */
        alignleft: false,
        aligncenter: false,
        alignright: false,
        /* 2.2.1 */
        subfield: true,
        preview: false,
      },
    };
  },
  methods: {
    save: function () {
      var blob = new Blob([this.value], { type: "text/plain" });
      let link = document.createElement("a");
      const now = new Date();
      link.href = window.URL.createObjectURL(blob);
      link.download =
        now.toISOString().slice(0, 10).replace(/-/g, "") +
        now.getMinutes() +
        now.getSeconds() +
        ".md";
      link.click();
    },
  },
};
</script>
