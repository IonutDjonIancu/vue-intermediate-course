<template>
  <div>
    <li>
      <h4>{{ friend.name }}</h4>
      <button @click="toggleDetails">Show details</button>
      <ul>
        <li>Phone: {{ friend.phone }}</li>
        <li>Email: {{ friend.email }}</li>
      </ul>
    </li>
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
    friend: Object,
  },
  methods: {
    toggleDetails() {
      this.detailsAreVisible = !this.detailsAreVisible;
    },
  },
};
</script>

<style></style>
