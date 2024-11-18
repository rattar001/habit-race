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

<style scoped lang="postcss">
.modal {
    @apply fixed inset-0 bg-black/50 flex items-center justify-center;
}

.modal-content {
    @apply bg-white p-6 rounded-lg shadow-lg max-w-md w-full;
}
</style>