<template>
  <div class="mx-5">
    Title <br />
    <input v-model="title" style="width: 25rem;" />
    <br /><br /><!--this way the sync is bidirectional and reactive to any changes-->
    Image Url<br />
    <input v-model="image" style="width: 25rem;" /> <br /><br />
    Description<br />
    <input v-model="description" style="width: 50rem;" /> <br /><br />
    <button @click="handleSubmit" class=" btn btn-dark">SUBMIT</button>
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
