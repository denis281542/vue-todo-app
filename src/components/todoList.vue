<template>
    <div>
      <ul>
          <todoItem
            v-for="(todo, i) in todos"
            v-bind:index="i"
            v-bind:todo="todo" :key="todo.id"
            @remove-todo="removeTodo"
          />
      </ul>        
    </div>
</template>

<script>
import todoItem from '@/components/todoItem'
export default {
    props: ['todos'],
    components: {
        todoItem
    },
    methods: {
        removeTodo(id) {
            this.$emit('remove-todo', id)
        }
    }
}
</script>

<style scoped>
    ul {
        list-style: none;
        margin: 0;
        padding: 0;
    }
</style>