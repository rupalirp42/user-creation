<template>
  <div class="main">
    <CreateUser
      :info="allUsers"
      @resetFromChild="resetParents"
      @submitFromChild="submitParents"
    />
    <AllUsers :info="allUsers" />
  </div>
</template>

<script>
import CreateUser from "./components/CreateUser.vue";
import AllUsers from "./components/AllUsers.vue";

export default {
  name: "App",
  components: {
    CreateUser,
    AllUsers,
  },
  data() {
    return {
      allUsers: [
        {
          name: "Rupali Patil",
          age: 26,
          city: "Pune",
          contact: 1236547891,
        },
        {
          name: "Sonali Patil",
          age: 28,
          city: "Mumbai",
          contact: 1236547781,
        },
      ],
    };
  },
  methods: {
    resetParents() {
      alert("Form Reset from parent.");
    },
    submitParents(param) {
      // alert("Form submit from parent.");
      this.allUsers = param;
    },
  },
};
</script>

<style>
body {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 96vh;
  width: 99vw;
}

.main {
  height: 350px;
  /* width: 800px; */
  display: flex;
  justify-content: center;
}
.head-2 {
  text-align: center;
  color: gray;
}
</style>
