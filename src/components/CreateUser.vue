<template>
  <div class="create-user">
    <div>
      <h2 class="head-2">Create User</h2>
    </div>
    <div>
      <form>
        <div class="type-info">
          <label>Name:</label>
          <input type="text" name="name" v-model="newUser.name" />
        </div>
        <div class="type-info">
          <label>Age:</label>
          <input type="number" name="age" v-model="newUser.age" />
        </div>
        <div class="type-info">
          <label>City:</label>
          <input type="text" name="city" v-model="newUser.city" />
        </div>
        <div class="type-info">
          <label>Contact:</label>
          <input type="number" name="contact" v-model="newUser.contact" />
        </div>
        <div class="button-group">
          <input
            type="reset"
            value="Reset"
            class="my-button"
            @click="reset()"
          />
          <input
            type="submit"
            value="Submit"
            class="my-button"
            @click.prevent="submit()"
          />
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: "CreateUser",
  props: {
    info: Array,
  },
  data() {
    return {
      newUser: {
        name: "",
        age: null,
        city: "",
        contact: null,
      },
    };
  },
  methods: {
    reset() {
      // alert("Form Reset.");
      this.$emit("resetFromChild");
    },
    submit() {
      // alert("Form Submitted.");
      const newInfo = [...this.info];
      newInfo.push(this.newUser);
      this.$emit("submitFromChild", newInfo);
    },
  },
};
</script>

<style scoped>
.create-user {
  border: 1px solid black;
  border-radius: 5px;
  margin-right: 200px;
  padding: 50px;
}
.type-info {
  margin-bottom: 10px;
  width: 100%;
}
.button-group {
  margin-top: 30px;
  text-align: center;
}
.my-button {
  padding: 8px;
  border-radius: 15px;
}
</style>
