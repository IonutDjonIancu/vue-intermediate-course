<template>
  <div>
    <h4>{{ friend.name }} {{ friend.isFavorite ? "(*)" : "" }}</h4>
    <button @click="toggleDetails">
      {{ detailsAreVisible ? "Colapse" : "Expand" }}
    </button>
    <button @click="toggleFavorite">Favorite</button>
    <ul v-if="detailsAreVisible">
      <li>Phone: {{ friend.phone }}</li>
      <li>Email: {{ friend.email }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "FriendComponent",
  data() {
    return {
      detailsAreVisible: false,
    };
  },
  props: {
    friend: {
      id: String,
      name: String,
      phone: String,
      email: String,
      isFavorite: Boolean,
    },
  },
  methods: {
    toggleDetails() {
      this.detailsAreVisible = !this.detailsAreVisible;
    },
    toggleFavorite() {
      this.$emit("toggle-favorite", this.friend.id);
    },
  },
};
</script>

<style></style>
