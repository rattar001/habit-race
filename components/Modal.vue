<template>
    <div v-if="modelValue" class="modal" @click.self="closeModal">
        <div class="modal-content">
            <slot />
        </div>
    </div>
</template>

<script setup lang="ts">
import { defineProps, defineEmits } from 'vue'

const props = defineProps({
    modelValue: {
        type: Boolean,
        required: true,
    }
})

const emit = defineEmits(['update:modelValue'])

function closeModal() {
    emit('update:modelValue', false)
}
</script>