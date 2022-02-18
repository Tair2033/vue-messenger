<template>
  <div class="sidebar" id="sidebar">
    <the-brand/>
    <authed-user v-if="$store.state.auth && $store.state.authedUserSection"/>
    <the-search/>
    <app-user-list :users="users" @userItemAction="getSelectedUser"/>
  </div>
</template>

<script>
import TheBrand from "@/components/Sidebar/TheBrand";
import AuthedUser from "@/components/Sidebar/TheAuthedUser";
import TheSearch from "@/components/Sidebar/TheSearch";
import AppUserList from "@/components/Sidebar/User-list/TheUserList";

export default {
  components: {TheSearch, AuthedUser, TheBrand, AppUserList},
  props: ['users'],
  methods:{
    getSelectedUser(user) {
      this.$emit('userItemAction', user)
    }
  }
}
</script>

<style scoped>
.sidebar {
  box-shadow: rgba(0, 0, 0, 0.14) 0px 0px 5px 2px;
  display: flex;
  flex-direction: column;
  width: 280px;
  min-width: 280px;
  position: relative;
  z-index: 2;
}


</style>