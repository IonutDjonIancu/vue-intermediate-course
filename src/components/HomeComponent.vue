<template>
  <div>
    <h4>My friends</h4>
    <AddFriend @add-friend="addFriend"></AddFriend>
    <FriendContact
      :key="frnd.id"
      v-for="frnd in friends"
      :friend="frnd"
      @toggle-favorite="markFriendAsFavorite"
    ></FriendContact>
  </div>
</template>

<script>
import FriendContact from "./FriendContact.vue";
import AddFriend from "./AddFriend.vue";
export default {
  name: "HomeComponent",
  components: {
    FriendContact,
    AddFriend,
  },
  methods: {
    markFriendAsFavorite(friendId) {
      let friend = this.friends.find((f) => f.id === friendId);
      friend.isFavorite = !friend.isFavorite;
    },
    addFriend(friend) {
      friend.id = this.friends.length + 1;

      this.friends.push(friend);
    },
  },
  emits: ["toggle-favorite"],
  data() {
    return {
      friends: [
        {
          id: 1,
          name: "Mark",
          phone: "1234 5678 90",
          email: "manuel@gmail.com",
          isFavorite: true,
        },
        {
          id: 2,
          name: "Jane",
          phone: "1234 5678 91",
          email: "jane@gmail.com",
          isFavorite: false,
        },
      ],
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss"></style>
