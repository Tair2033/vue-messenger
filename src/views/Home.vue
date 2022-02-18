<template>
    <div class="messenger-app">
        <the-sidebar :users="sortedUserList" @userItemAction="getSelectedUser"/>
        <the-default-box v-if="$store.state.defaultBox"/>
        <the-chat-box
            v-if="!$store.state.defaultBox"
            :selectedUser="selectedUser"
        />
    </div>
</template>

<script>
import {users} from "/public/mocks/users";
import TheSidebar from "@/components/Sidebar/TheSidebar";
import TheDefaultBox from "@/components/Chat-box/TheDefaultBox";
import TheChatBox from "@/components/Chat-box/TheChatBox";

export default {
    data() {
        return {
            users,
            selectedUser: {}
        }
    },
    name: 'Home',
    components: {TheChatBox, TheDefaultBox, TheSidebar},
    methods: {
        getSelectedUser(user) {
            this.selectedUser = user;
        }
    },
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

<style scoped>
.messenger-app {
    position: fixed;
    height: 100vh;
    width: 100vw;
    top: 0px;
    left: 0px;
    display: flex;
    flex-direction: row;
}
</style>
