<template>
    <div class="chat-list" id="chat-list">
        <app-user-item v-for="(user, id) in users" :user="user" :key="id" @userItemAction="getSelectedUser"/>
    </div>
</template>

<script>
import AppUserItem from "@/components/Sidebar/User-list/AppUserItem";

export default {
    data() {
        return {}
    },
    props: ['users'],
    components: {AppUserItem},
    methods: {
        getSelectedUser(user) {
            this.$emit('userItemAction', user)
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