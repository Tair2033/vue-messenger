<template>
    <div class="chat-box" id="chat-box">
        <div class="chat-head" id="chat-head">
            <div class="chat-head__iconwrapper">
                <img :src="selectedUser.icon"
                     id="chat-head__icon" alt=""/>
                <div class="user-status">
                </div>
            </div>
            <strong class="chat-head__nickname">{{ selectedUser.nickname }}</strong>
            <div class="chat-head__settings">&hellip;</div>
        </div>

        <div class="chat-wrapper" id="chat-wrapper">
            <div class="chat-mess" id="chat-mess" >
                <AppMessage
                    v-for="(message, id) in selectedUser.messages"
                    :key="id"
                    :message="message"
                />
            </div>
        </div>

        <div id="new-mess" class="new-mess">
            <div class="input-wrapper">
                  <textarea
                      name="new_message"
                      id="new-message-input"
                      placeholder="write message here (Ctrl+Enter to send)"
                      tabindex="1"
                      rows="2"
                      v-model="newMessage"
                      @keydown.enter="sendMessage"
                  ></textarea>

                <svg id="Capa_1" class="file" xmlns="http://www.w3.org/2000/svg"
                     width="40px" height="50px" viewBox="0 0 792 792" xml:space="preserve">
                    <g>
                        <path d="M306,150.48v459.36c0,0-6.696,96.408,91.476,96.408C486,706.248,486,609.84,486,609.84V126.72C486,126.72,486,0,360,0
                            S234,126.72,234,126.72v483.12c0,0,0,182.16,162,182.16s162-182.16,162-182.16V126.72c0-19.8-36-19.8-36,0v483.12
                            c0,0,13.104,146.16-126,146.16c-126,0-126-146.16-126-146.16V126.72c0,0,0-90.72,90-90.72s90,90.72,90,90.72v483.12
                            c0,0,0,56.809-52.524,56.809c-52.523,0-55.476-56.809-55.476-56.809V150.48C342,130.68,306,130.68,306,150.48z"/>
                    </g>
                    <g>
                    </g>
                    <g>
                    </g>
                    <g>
                    </g>
                    <g>
                    </g>
                    <g>
                    </g>
                    <g>
                    </g>
                    <g>
                    </g>
                    <g>
                    </g>
                    <g>
                    </g>
                    <g>
                    </g>
                    <g>
                    </g>
                    <g>
                    </g>
                    <g>
                    </g>
                    <g>
                    </g>
                    <g>
                    </g>
                </svg>

            </div>
            <div class="send-mess" id="send-mess" @click="sendMessage">&#10148;</div>
        </div>
    </div>
</template>

<script>
import AppMessage from "@/components/Chat-box/AppMessage";

export default {
    data() {
      return {
          newMessage: ''
      }
    },
    components: {AppMessage},
    props: ['selectedUser'],
    methods: {
        sendMessage() {
            this.selectedUser.messages.push({
                type: "text",
                message: this.newMessage.trim(),
                date: `${new Date().getDay()}.${new Date().getMonth()}.${new Date().getFullYear()}`,
                sender: "me"
            });
            this.newMessage = ''
        },
        scrollPosition() {
            const chatMess = document.getElementById('chat-mess')
            chatMess.scrollTo({
                top: chatMess.scrollHeight,
            } )
        }
    },
    updated() {
        this.scrollPosition()
    },
    beforeMount() {
        this.scrollPosition()
    }
}
</script>

<style scoped>
.chat-box {
    width: 100%;
}

.chat-wrapper {
    position: relative;
    flex-grow: 1;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    min-height: 0;
    overflow: hidden;
}

.chat-mess {
    flex-grow: 1;
    flex-direction: column;
    justify-content: flex-end;
    min-height: 0;
    background: url("https://phonoteka.org/uploads/posts/2021-06/thumbs/1623918367_26-phonoteka_org-p-pattern-prodazhi-krasivo-33.png") top;
    height: 70vh;
    opacity: 0.8;
    position: relative;
    padding: 1em 1em 1.5em;
    overflow-y: auto;
}

.chat-head {
    user-select: none;
    display: flex;
    align-items: center;
    position: relative;
    padding: 15px;
    border-bottom: 1px solid #d5d4d4;
    box-shadow: rgb(0 0 0 / 14%) 0px 0px 5px 2px;
}

img#chat-head__icon {
    width: 45px;
    height: 45px;
    border-radius: 50%;
}

.chat-head__nickname {
    margin-left: 23px;
}

.chat-head__settings {
    cursor: pointer;
    user-select: none;
    position: absolute;
    right: 15px;
    top: 15px;
    font-size: 25px;
    color: green;
    padding-bottom: 10px;
    padding-left: 7px;
    padding-right: 7px;
    border-radius: 50%;
}

.chat-head__nickname:hover {
    color: #602727;
    cursor: pointer;
}

.chat-head__settings:hover {
    background-color: #eae9e9;
}

.chat-head__settings:active {
    background-color: #d5d2d2;
}

.chat-head__iconwrapper {
    position: relative;
}

.user-status {
    position: absolute;
    bottom: 3px;
    right: 0px;
    width: 10px;
    height: 10px;
    border: 2px solid white;
    border-radius: 50%;
    background-color: #237c23;
}

.new-mess {
    display: flex;
    justify-content: space-between;
}


#new-message-input {
    max-height: 200px;
    min-height: 32px;
    width: 100%;
    max-width: 100%;
    border: 1px solid #c7c7c7;
    padding: 0.5rem 35px 0.5rem 0.5rem;
    margin: 5px;
    font-family: 'Lato', sans-serif;
    font-size: 16px;
    border-radius: 4px;
    transition: all .2s;
    color: #444;
}

#new-message-input:focus {
    outline-color: #6abd6a;
}

.send-mess {
    cursor: pointer;
    user-select: none;
    font-size: 35px;
    color: #444444;
    padding: 15px;
    margin-left: 20px;
}

.send-mess:hover {
    color: #6abd6a;
}

.input-wrapper {
    display: flex;
    position: relative;
    width: 100%;
}

.file {
    user-select: none;
    cursor: pointer;
    position: absolute;
    top: 10px;
    right: 10px;
    fill: #0e0c0c;
}

.file:hover {
    fill: #467c46;
}

.file:active {
    fill: #14b714;
}

</style>