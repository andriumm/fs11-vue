<template>
  <div>
    Title
    <input v-model="title" />
    <!--this way the sync is bidirectional and reactive to any changes-->
    <button @click="handleSubmit" class="btn btn dark">SUBMIT</button>
  </div>
</template>

<script>
export default {
  name: "AdminView",
  data() {
    return {
      title: "",
      image: "",
      description: ""
    };
  },
  methods: {
    handleSubmit() {
      this.$emit("createProject", {
        title: this.title,
        image: this.image,
        description: this.description
      });
    }
  }
};
</script>

<style></style>
