<template>
    <div class="chat-box" id="chat-box">
        <div class="starting-chat">
            <img src="img/chat-placeholder.svg" class="started-img" alt=""/>
            <h1>Hi!</h1>
            <h2>Select a chat to start messaging.</h2>
        </div>
    </div>
</template>

<script>
export default {}
</script>

<style scoped>
.chat-box {
    width: 100%;
}

.starting-chat {
    text-align: center;
}

img.started-img {
    width: 100%;
    max-width: 500px;
}
</style>