<template>
    <button :class="buttonClass">
        <slot />
    </button>
</template>

<script setup lang="ts">

const allowedVariants = ['primary', 'secondary'] as const;

type ButtonVariant = typeof allowedVariants[number];

const props = defineProps<{
    type?: string;
    variant: ButtonVariant;
}>()

const buttonClass = computed(() => {
    return props.variant === 'primary' ? 'btn-primary' : 'btn-secondary'
});

</script>