<template>
  <div class="text-center">
    <h1 class="mt-5">My Portfolio</h1>
    <br />
    <button
      @click="isAdmin = true"
      class=" btn btn-dark"
      :class="{ 'bg-warning': isAdmin }"
    >
      ADMIN
    </button>
    <button
      @click="isAdmin = false"
      class=" btn btn-dark"
      :class="{ 'bg-warning': !isAdmin }"
    >
      USER
    </button>
    <br /><br />
    <admin-view v-if="isAdmin" @createProject="addProject" />
    <user-view img="image" v-else />
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
    //should we put in here the information we want to get from the child? $event
  }
};
</script>

<style></style>
