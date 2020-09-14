<template lang="html">
  <div class="template-form component">
    <v-card>
      <!-- <v-fade-transition>
        <v-progress-linear
          indeterminate
          v-if="isLoading"
          color="primary"
          bottom
        />
      </v-fade-transition> -->
      <v-card-title>
        New Compose Template
      </v-card-title>
      <v-form>
        <editor
          v-model="content"
          @init="editorInit"
          lang="yaml"
          theme="twilight"
          :height="windowHeight"
          :width="windowWidth"
          class="editor"
        ></editor>
      </v-form>
    </v-card>
  </div>
</template>

<script>
// import { mapActions, mapState } from "vuex";

export default {
  data() {
    return{
      content: null,
      windowHeight: window.innerHeight - 200,
      windowWidth: window.innerWidth - 80,
    }
  },
  components: {
    editor: require("vue2-ace-editor"),
  },
  methods: {
    editorInit() {
      require("brace/mode/yaml");
      require("brace/theme/twilight");
    },
  },
};
</script>

<style lang="css">
.ace_gutter {
  z-index: 1;
}
.ace_gutter-active-line{
  z-index: 1;
}
</style>
