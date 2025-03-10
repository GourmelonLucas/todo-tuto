<template>
    <li>
        {{ todo.name }}
        <button @click="deleteTodo">Supprimer</button>
    </li>
</template>

<script setup lang="ts">
import { defineProps, defineEmits } from 'vue'

const props = defineProps<{ todo: { id: number, name: string, completed: boolean } }>()
const emit = defineEmits(['delete'])

// Emit the delete event with the todo's id
const deleteTodo = () => {
    emit('delete', props.todo.id)
}
</script>