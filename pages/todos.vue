<template>
  <div class="container">
    <div>
      <logo />
      <h1 class="title">
        Todo
      </h1>
      <div class="links">
        <nuxt-link to="/" class="button--green">
          Index
        </nuxt-link>
        <nuxt-link to="/about" class="button--grey">
          About
        </nuxt-link>
      </div>
    </div>
    <ul>
      <li v-for="todo in todos" :key="todo">
        <input type="checkbox" :checked="todo.done" @change="toggle(todo)" />
        <span :class="{ done: todo.done }">{{ todo.text }}</span>
      </li>
      <li>
        <input placeholder="What needs to be done?" @keyup.enter="addTodo" />
      </li>
    </ul>
  </div>
</template>

<script>
import { mapMutations } from 'vuex'

export default {
  computed: {
    todos() {
      return this.$store.state.todos.list
    }
  },
  methods: {
    addTodo(e) {
      this.$store.commit('todos/add', e.target.value)
      e.target.value = ''
    },
    ...mapMutations({
      toggle: 'todos/toggle'
    })
  }
}
</script>

<style>
.done {
  text-decoration: line-through;
}
</style>
