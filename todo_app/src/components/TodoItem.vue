<template>
  <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
      <p>
          <input type="checkbox" v-on:change="markComplete">
          {{todo.title}}
          <button @click="$emit('del-todo', todo.id)" class="del">X</button>
      </p>
  </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: ['todo'],
    methods:{
        markComplete(){
            this.todo.completed = !this.todo.completed
        }
    }
}


</script>

<style scoped>
.todo-item{
    font-size: 43px;
    padding: 8px;
    background-color: aliceblue;
    border: 1px solid black;
}
.is-complete{
    text-decoration: line-through;
}
.del{
    width: 48px;
    height: 48px;
    border-radius: 50%;
    border: none;
    background-color: red;
    color: white;
    font-size: 1.2rem;
}
</style>