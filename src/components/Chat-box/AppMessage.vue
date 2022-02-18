<template>
    <div>
        <div class="message to-me-message" v-if="message.type === 'text' && message.sender === 'to me'">
            {{ message.message }}
            <div class="message-date">{{ message.date }}</div>
        </div>
        <div class="message my-message" v-if="message.type === 'text'  && message.sender === 'me'">
            {{ message.message }}
            <div class="message-date">{{ message.date }}</div>
        </div>
        <div class="img-message my-message" v-if="message.type === 'image'">
            <img :src="message.url" class="message-img" alt="">
            <div class="message-date">{{ message.date }}</div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['message']
}
</script>

<style scoped>

.message-img {
    padding: 13px;
    width: 300px;
    height: 350px;
}
.img-message{
    max-width: max-content;
    margin-bottom: 10px;
    width: auto;
    min-width: 120px;
    border-radius: 8px;
    box-shadow: -1px 1px 3px 0 rgb(0 0 0 / 14%);
    color: black;
    position: relative;
}
.message {
    font-size: 18px;
    padding: 15px 14px;
    max-width: 50%;
    margin-bottom: 10px;
    width: auto;
    min-width: 120px;
    border-radius: 8px;
    box-shadow: -1px 1px 3px 0 rgb(0 0 0 / 14%);
    color: black;
    position: relative;
}


.message-date {
    font-size: 9px;
    font-weight: bolder;
    position: absolute;
    bottom: 5px;
    right: 5px;
}

.my-message {
    background-color: #86d286;
    margin-right: 0.5rem;
    margin-left: auto;
}


.to-me-message {
    background-color: white;
    margin-left: 0.5rem;
    margin-right: auto;

}

</style>