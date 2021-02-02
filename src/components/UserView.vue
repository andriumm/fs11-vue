<template>
  <!-- //we will have to add another div to be able to include more code -->
  <!-- -->
  <div class="mx-5">
    User View <img :src="img" />
    <!--space to add the pic-->
  </div>
</template>

<script>
export default {
  name: "UserView",
  props: ["img"]
};
</script>

<style></style>
