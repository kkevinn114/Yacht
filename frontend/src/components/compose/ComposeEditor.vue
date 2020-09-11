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
        New Template
      </v-card-title>
      <!-- <v-card-text v-if="templates.length < 1">
        Consider adding templates crafted for Yacht: <br> https://raw.githubusercontent.com/SelfhostedPro/selfhosted_templates/yacht/Template/template.json
      </v-card-text> -->
      <v-card-text>
        <!-- <v-form ref="form" @submit.prevent="submit">
          <v-text-field
            label="Title"
            v-model="form.title"
            :rules="titleRules"
            required
          ></v-text-field>
          <v-text-field
            label="URL"
            v-model="form.url"
            :rules="urlRules"
            required
          ></v-text-field>
          <v-btn class="mr-4" type="submit" @click="submit">Submit</v-btn>
        </v-form> -->
      </v-card-text>
    </v-card>
  </div>
</template>

<script>
// import { mapActions, mapState } from "vuex";

export default {
  data: () => ({
    form: {
      title: "",
      url: "",
    },
    titleRules: [
      (value) => !!value || "Required.",
      (value) => {
        const valid =
          (value.trim() || "").length > 1 && (value.trim() || "").length < 256;
        return valid || "Length between 2 and 255 Characters.";
      },
    ],
  }),
};
</script>

<style lang="css" scoped></style>
