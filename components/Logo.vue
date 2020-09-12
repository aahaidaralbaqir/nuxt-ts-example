<template>
  <div>
  <ul>
    <li
      v-for="(todo,index) in todos"
      :key="index"
    >
      <input type="checkbox" :checked="todo.is_done" @click="handleDoneTodo(todo)">  {{ todo.title }}
    </li>
  </ul>
  <input type="text" v-model="title"/>
  <button @click="handleCreateTodo">Add</button>
  </div>
</template>
<script lang="ts">
import { Vue, Component, Watch } from "nuxt-property-decorator";
interface Todo {
  id: number
  title: string
  is_done: boolean
}
@Component
export default class Logo extends Vue {
  title: string = ''
  todos: Array<Todo> = [
    {
      id: 1,
      title: "Todo one",
      is_done: false
    }
  ]

  private handleCreateTodo(): void {
    this.todos = [...this.todos,  { id: this.todos.length + 1, title: this.title, is_done:  false }]
    this.title = ''
  }

  private handleDoneTodo(todo: Todo) {
    this.todos = this.todos.filter(item => item.id != todo.id)
  }

  @Watch("title")
  private onTitleChanged(newVal: string) {
    console.log(newVal)
  }
}
</script>
<style>
.NuxtLogo {
  animation: 1s appear;
  margin: auto;
}

@keyframes appear {
  0% {
    opacity: 0;
  }
}
</style>
