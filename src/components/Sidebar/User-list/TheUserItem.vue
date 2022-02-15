<template>
  <div class="user-item" id="user-item">
    <div class="user-icon__wrapper">
      <img
          :src="user.icon"
          class="user-icon"
      />
      <div class="user-status" v-if="user.status !== 'offline'"></div>
    </div>
    <div class="user-nickname">{{ user.nickname }}</div>
    <div class="user-rigth-side">
      <div class="user-count" v-if="user.newMess !== 0">{{ user.newMess }}</div>
      <div class="user-date">{{ user.messages[user.messages.length - 1].date }}</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {}
  },
  props: ["user"]
}
</script>

<style scoped>
.user-item {
  cursor: pointer;
  position: relative;
  display: flex;
  align-items: center;
  padding: 10px;
}

.user-icon__wrapper {
  position: relative;
}

.user-icon {
  width: 45px;
  height: 45px;
  border-radius: 50%;
}

.user-nickname {
  user-select: none;
  color: #313030;
  font-weight: bolder;
  margin-left: 9px;
}

.user-count {
  position: absolute;
  top: 10px;
  right: 10px;
  padding: 1px;
  background-color: #237c23;
  min-width: 16px;
  min-height: 16px;
  border-radius: 50%;
  font-size: 12px;
  display: flex;
  justify-content: center;
  align-items: center;
  color: white;
}
.user-date {
  font-size: 12px;
  position: absolute;
  bottom: 20px;
  right: 10px;
  color: #9d9d9d;
}

.user-item:hover {
  background-color: #dadada;
}
.user-item:active {
  background-color: #e5e4e4;
}

</style>