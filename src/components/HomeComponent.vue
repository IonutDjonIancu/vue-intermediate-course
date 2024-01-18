<template>
  <div>
    <h4>My friends</h4>
    <ul>
      <FriendContact
        :key="friend.id"
        v-for="friend in friends"
        v-bind:friend="friend"
      ></FriendContact>
    </ul>
  </div>
</template>

<script>
import FriendContact from "./FriendContact.vue";
export default {
  name: "HomeComponent",
  components: {
    FriendContact,
  },
  data() {
    return {
      friends: [
        {
          id: 1,
          name: "Mark",
          phone: "1234 5678 90",
          email: "manuel@gmail.com",
        },
        {
          id: 2,
          name: "Jane",
          phone: "1234 5678 91",
          email: "jane@gmail.com",
        },
      ],
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss"></style>
