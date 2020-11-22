<template>
  <div>
     <el-container>
      <el-main>
        <el-row class="custom-row">
          <el-col :span="6" :offset="9">
            <div class="todo-input-field-wrapper">
                <div class="el-input">
                  <input type="text" v-model="title" v-on:keyup.enter="onSubmit" autocomplete="off" placeholder="Add Todo.." class="el-input__inner">
                </div>
            </div>
          </el-col>
        </el-row>
        <el-row class="custom-row">
          <el-col :md="6" :sm="24" :offset="9">
            <div class="todo-list-wrapper">
              <TodoList/>
            </div>
          </el-col>
        </el-row>
      </el-main>
     </el-container>
  </div>
</template>

<script>
// @ is an alias to /src
import TodoList from '../components/TodoList'
import { mapActions } from 'vuex'
export default {
  name: 'Home',
  data () {
    return {
      title: '',
    }
  },
  components: {
    TodoList
  },
  methods: {
    ...mapActions(['addTodo']),
    onSubmit (e) {
      e.preventDefault()
      this.addTodo(this.title)
    }
  }
}
</script>
