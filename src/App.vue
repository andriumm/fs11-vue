<template>
  <div>
    <h1>Hello World</h1>
    <button @click="isAdmin = true" :class="{ 'bg-warning': isAdmin }">
      ADMIN
    </button>
    <button @click="isAdmin = false" :class="{ 'bg-warning': !isAdmin }">
      USER
    </button>
    <admin-view v-if="isAdmin" @createProject="addProject" />
    <user-view v-else />
  </div>
</template>

<script>
//we are linking the children with their parent app.vue
import AdminView from "./components/AdminView";
import UserView from "./components/UserView";

export default {
  // we have to include the components that are its children
  name: "app",
  components: {
    userView: UserView,
    adminView: AdminView
  },
  data() {
    // the data has to be a function that returns an object.
    return {
      isAdmin: true,
      allProjects: []
    };
  },
  methods: {
    addProject(project) {
      this.allProjects.push(project);
    }
  }
};
</script>

<style></style>

<!-- I don't see the:
 var app = new Vue({
  el: '#app',
  data: {
    message: 'Hello Vue!'
  }
}) -->
