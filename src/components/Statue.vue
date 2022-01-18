<template>
  <div>
      <ul>
          <StatueItem
          v-for="todo in todos"
          v-bind:key="todo.person"
          :todo="todo"
          @todo-item-changed="Changed"
          />
      </ul>
  </div>
</template>

<script>
import StatueItem from './StatueItem.vue'
export default {
    props: ['todos'],
    components: {StatueItem},
    methods: {
        Changed(e) {
            this.$emit('todo-item-changed', e)
        }
    }

}
</script>

