<template>
  <div id="app">
    <img src="./assets/logo.png">
    <h1>Todos</h1>
    <new-todo @handleNewItem="addNewItem"></new-todo>
    <todo-list :itemlist="itemlist" @handleRemoveItem="removeItem"></todo-list>
  </div>
</template>





<script>
import NewTodo from './components/NewTodo'
import TodoList from './components/TodoList'

const itemlist = [
  {id: '1', name:'test1', complete: true},
  {id: '2', name:'test2', complete: false},
  {id: '3', name:'test3', complete: false},
  {id: '4', name:'test4', complete: false},
  {id: '5', name:'test5', complete: false}
]

export default {
  data(){
    return {
      itemlist: itemlist
    }
  },
  methods: {
    addNewItem: function (newitem) {
      this.itemlist.push({id:newitem+(new Date()), name:newitem, complete: false})
    },
    removeItem: function (itemid) {
      this.itemlist = this.itemlist.filter(({id: id}) => id!==itemid)
    }
  },
  components: {
    NewTodo,
    TodoList
  }
}
</script>






<style scoped>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }

  body {
    background-color: #22923b;
  }

  h1 {
    color: #dc6e76;
  }
</style>
