<template>
    <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
        <p> <input type="checkbox" v-on:click="markComplete" v-bind:class="clicked">
            {{todo.title}}
            <button @click="$emit('del-todo', todo.id)" class="del">x</button>
        </p>
    </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: ["todo"],
    methods: {
        markComplete() {
            this.todo.completed = !this.todo.completed;
        }, 
        balledHard() {
            if(condition) {
                alert("You are officially a baller!");
            }
        }
    }
}
</script>

<style scoped>
      .todo-item {
          font-family:'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
    background: #f4f4f4;
    padding: 10px;
    border-bottom: 1px #ccc dotted;
  }
  .is-complete {
    text-decoration: line-through;
  }
  .del {
    background: #ff0000;
    color: #fff;
    border: none;
    padding: 5px 9px;
    border-radius: 50%;
    cursor: pointer;
    float: right;
  }
</style>