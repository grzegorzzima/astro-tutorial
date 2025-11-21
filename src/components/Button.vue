<template>
  <PrimeButton :label="title" icon="pi pi-check" @click="handleClick" severity="primary" />
  <InputText type="text" />
</template>

<script setup lang="ts">
import PrimeButton from 'primevue/button';
import InputText from 'primevue/inputtext';

interface Props {
  title: string
}

function say(message: string) {
  alert(message)
}

const props = defineProps<Props>()

const emit = defineEmits<{
  click: [event: MouseEvent]
}>()

const handleClick = (event: MouseEvent) => {
  say('Button clicked!')
  emit('click', event)
}
</script>