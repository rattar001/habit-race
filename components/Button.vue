<template>
    <button :class="buttonClass">
        <slot />
    </button>
</template>

<script setup lang="ts">

const props = defineProps({
    type: String,
    variant: {
        type: String,
        default: 'primary'
    }
});

const buttonClass = computed(() => {
    return props.variant === 'primary'
        ? 'bg-blue-500 hover:bg-blue-600 text-white py-2 px-4 rounded'
        : 'bg-gray-500 hover:bg-gray-600 text-white py-2 px-4 rounded';
});

</script>