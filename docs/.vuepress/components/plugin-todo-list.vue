<template>
  <v-md-editor
    v-model="text"
    left-toolbar="undo redo | todo-list"
    :theme="theme"
    height="500px"
  />
</template>

<script>
import VMdEditor from '../../../lib/base-editor';
import '../../../lib/style/base-editor.css';
import githubTheme from '../../../lib/theme/github.js';
import '../../../lib/theme/style/github.css';
import createTodoListPlugin from '../../../lib/plugins/todo-list/index';
import '../../../lib/plugins/todo-list/todo-list.css';

VMdEditor.use(createTodoListPlugin());

export default {
  components: {
    [VMdEditor.name]: VMdEditor,
  },
  data() {
    this.theme = githubTheme;

    return {
      text: '- [x] Task',
    };
  },
};
</script>