<template>
    <h1> Habit Page </h1>
    <Button variant="primary" @click="addHabit()"> Add Habit </Button>
    <div v-for="(habit, index) in habits">
        {{ habit }}
    </div>

    <Modal v-model="showModal">
        CHECK CHECK
    </Modal>
</template>

<script setup lang="ts">
import type { Habit } from '~/types/Habit';

const showModal = ref(false)
const habits = reactive<Habit[]>([])

function getHabit() {

}

const addHabit = () => {
    showModal.value = true
}

</script>