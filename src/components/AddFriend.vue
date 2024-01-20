<template>
  <div>
    <form>
      <label for="name">Name </label>
      <input
        v-model="name"
        type="text"
        name="name"
        id="name"
        autocomplete="off"
      />
      <label for="phone"> Phone</label>
      <input
        v-model="phone"
        type="text"
        name="phone"
        id="phone"
        autocomplete="off"
      />
      <label for="email"> Email</label>
      <input
        v-model="email"
        type="text"
        name="email"
        id="email"
        autocomplete="off"
      />
      <label for="checkbox"> Favorite</label>
      <input
        v-model="isFavorite"
        type="checkbox"
        name="checkbox"
        id="checkbox"
      />
      <button @click="saveFriend">submit</button>
    </form>
  </div>
</template>

<script>
export default {
  name: "AddFriend",
  data() {
    return {
      name: "",
      phone: "",
      email: "",
      isFavorite: false,
      friend: {
        id: String,
        name: String,
        phone: String,
        email: String,
        isFavorite: Boolean,
      },
    };
  },
  methods: {
    saveFriend(e) {
      e.preventDefault();

      const friend = {
        name: this.name,
        phone: this.phone,
        email: this.email,
        isFavorite: this.isFavorite,
      };

      this.$emit("add-friend", friend);
      this.clearForm();
    },
    clearForm() {
      this.name = "";
      this.phone = "";
      this.email = "";
      this.isFavorite = false;
    },
  },
};
</script>

<style></style>
