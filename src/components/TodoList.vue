<template>
    <div>
        <div class="todo-list" v-for="todo in allTodos" :key="todo.id">
            <div class="todo-list-left">
                <div class="todo-title-wrapper">
                    <h1 v-bind:class="{'is-complete':todo.completed}">{{ todo.title }}</h1>
                </div>
            </div>
            <div class="todo-list-right">
                <div v-bind:class="{'is-complete':todo.completed}">
                    <div class="chekckbox-wrapper">
                        <el-checkbox></el-checkbox>
                    </div>
                </div>
            </div>
            <div class="toolbar-wrapper">
                <div class="check-btn">
                    <el-button type="success"  @click="completeTodo(todo)" icon="el-icon-check" circle></el-button>
                </div>
                <!-- <div class="edit-btn">
                    <el-button type="primary" icon="el-icon-edit" circle></el-button>
                </div> -->
                <div class="delete-btn">
                    <el-button type="danger" icon="el-icon-delete" @click="deleteTodo(todo.id)" circle></el-button>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
import { mapGetters, mapActions } from 'vuex'
export default {
  name: 'TodoList',
  methods: {
    ...mapActions(['fetchTodos', 'deleteTodo', 'updateTodo']),
    completeTodo(todo) {
      const updTodo = {
        id: todo.id,
        title: todo.title,
        completed: !todo.completed
      }
      this.updateTodo(updTodo)
    }
  },
  computed: mapGetters(['allTodos']),
}
</script>
<style lang="scss">
</style>
