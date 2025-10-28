<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'

const currentDate = ref(new Date())

let timer: number

onMounted(() => {
    timer = window.setInterval(() => {
        currentDate.value = new Date()
    }, 1000)
})

onUnmounted(() => {
    clearInterval(timer)
})
</script>

<template>
    <div class="date">
        {{ currentDate.toLocaleDateString() }}
        {{ currentDate.toLocaleTimeString() }}
    </div>
</template>

<style scoped>
.date {
    font-size: 14px;
    color: #666;
}
</style>
