<template>
  <div class="users">
    <h2 class="head-2">Users</h2>
    <div v-for="user in info" :key="user" class="user-info">
      {{ user.name }}, {{ user.age }}, {{ user.city }}, {{ user.contact }}
      <div class="button-class">
        <span
          ><img src="D:/frontEnd/vue/user-creation/src/assets/Edit.svg"
        /></span>
        <span
          ><img src="D:/frontEnd/vue/user-creation/src/assets/Delete.svg"
        /></span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "AllUsers",
  props: {
    info: Array,
  },
};
</script>

<style scoped>
.users {
  border: 1px solid black;
  border-radius: 5px;
  padding: 35px;
  overflow-y: auto;
}
.user-info {
  border: 1px solid black;
  padding: 5px;
  border-radius: 5px;
  margin-bottom: 10px;
}
.button-class {
  text-align: right;
}
</style>
