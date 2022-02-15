<template>
  <div class="chat-list" id="chat-list">
    <the-user-item v-for="(user, id) in sortedUserList" :user="user" :key="id" />
  </div>
</template>

<script>
import TheUserItem from "@/components/Sidebar/User-list/TheUserItem";
import {users} from "@/mocks/users";

export default {
  data() {
    return {
      users,
    }
  },
  components: {TheUserItem},
  computed: {
    sortedUserList() {
      const unread = [], others = []
      this.users.forEach(item => {
        if (item.newMess > 0) {
          unread.push(item)
        } else {
          others.push(item)
        }
      })
      return unread.concat(others)
    }
  }
}
</script>

<style>
.chat-list {
  height: 100vh;
  overflow: auto;
}
</style>