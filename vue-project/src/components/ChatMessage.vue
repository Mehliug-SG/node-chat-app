<script setup>
    defineProps({
        message: {
            type: Object,
            required: true
        }
    })
</script>

<template>
    <div class="flex">
        <img class="h-20 w-20 rounded-full" :src="message.user.avatarUrl" alt="avatar">
        {{ message.user.username }}
    </div>
</template>