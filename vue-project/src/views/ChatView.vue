<script setup>

import {ref} from 'vue'
import ChatMessage from '@/components/ChatMessage.vue'
const messageText = ref('')
const messageList = ref([])

function addMessage(){

    messageList.value.push({
        text: messageText.value,
        date: new Date(),
        user:{
            username: "Gouillaime",
            avatarUrl: "https://tp-amenagements.fr/wp-btp-2019/wp-content/uploads/2020/04/tractopelle-Komatsu-WB97R-8_1-scaled.jpg",
        }
    })
    messageText.value = ''

}

</script>


<template>

    <div v-for="(message, index) in messageList" class="p-4 text-black" :key="index">
        <chat-message :message="message"></chat-message>
    </div>
    
    <div class="flex align-center p-4">
        
        <textarea v-model="messageText" name="message" id="message" rows="1" class="a"></textarea>
        <button @click="addMessage" class="p-2 bg-blue-600 rounded-md">Envoyer</button>
    </div>
</template>