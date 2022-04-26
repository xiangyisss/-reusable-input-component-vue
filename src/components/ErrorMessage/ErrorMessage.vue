<template>
    <div>
        <p>{{message}}</p>
    </div>
</template>

<script setup lang="ts">
import { computed } from '@vue/reactivity';

const props = withDefaults(defineProps<{
    message: string
}>(), {
    message: 'This is default error message'
})

const message = computed(() => {
    return props.message === '' ? 'This is default error message' : props.message
})
</script>

<style scoped>

</style>