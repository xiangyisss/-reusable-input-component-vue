<template>
    <div>
        <input @input="$emit('update:modelValue', $event.target.value)"/>
        <ErrorMessageVue v-if="hasWarning && type === 'email' && isNotValidEmail " :message="props.message"/>
    </div>
</template>

<script setup lang="ts">
import ErrorMessageVue from '../ErrorMessage/ErrorMessage.vue';
import { computed } from '@vue/reactivity';

const props = withDefaults(defineProps<{
    modelValue?: string,
    type?: string,
    message?: string,
    hasWarning?: boolean
}>(), {
    type:'text',
    hasWarning: false,
    message: ''
})


const isNotValidEmail = computed(() => {
    const format =  /^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/
    return !props.modelValue?.match(format) && props.modelValue !== ''
})

</script>

<style scoped>

</style>