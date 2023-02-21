<script>
export default {
  data() {
    return {
      title: "Todo List",
      todoLists: [
        {id: 1, todo: "Do homework", isActive: true},
        {id: 2, todo: "Read a book", isActive: true},
      ],
    };
  },
  methods: {
    printTodo(event){
        const asd = this.todoLists.length + 1
        if(event.target.value == ""){
          alert("input can not nul!")
        }else{
          var data = {id: asd, todo: event.target.value}
          this.todoLists.push(data) 
        }
    },
    deleteTodo(todoData){
        this.todoLists = this.todoLists.filter(todo => todo.id != todoData.id)
    },
    isActive(todoData){
      console.log(todoData)
    }
},
};
</script>

<template>
  <div class="box">
    <div class="titleHead">
      <h1>{{ title }}</h1>
      <input type="text" class="todo-input" @keydown.enter="printTodo">
      <!-- <button class="addBtn">add todo</button> -->
    </div>
    <div class="todoBody">
      <ul>
        <li v-for="todoList in todoLists" :key="todoList.id" title="todoList.todo" class="li-list">
          <div class="li-list-left">
            <input type="checkbox" id="checkbox" v-model="todoList.isActive" @click="todoList.isActive = !todoList.isActive"/>
            <input type="text" v-model="todoList.todo" :placeholder="[[ todoList.todo ]]" class="body-input">
          </div>
           <div class="li-list-right">
            <button class="delete-btn" @click="deleteTodo(todoList)">delete todo</button>
           </div>
        </li>
      </ul>
    </div>
  </div>
</template>

<style>
.box {
  margin: 10px;
  background-color: #4d9900;
  margin: auto;
  width: 65%;
  border: 2px solid black;
  padding: 10px 10px 10px 10px;
}


.todo-input{
  font-size: 20px;
}

.titleHead {
  font-family: "Courier New", Courier, monospace;
  background-color: #b3cccc;
  border: 2px solid black;
  text-align: center;
  padding: 10px 10px 30px 10px;
  font-size: 20px;
}


.li-list  {
  font-size: 20px;
  display: flex;
  justify-content: space-between;
  margin: 15px 15px 15px 0px;
  flex: 1 1 auto;
  text-overflow: clip;
  
}


.li-list-left{
  display: flex;
  justify-content: flex-start;
  align-items: center;
  gap: 20px
}

button:hover{
  background-color: red;
  
}
delete-btn{
  height: 1.5rem;
}

.body-input{
  width: 50rem;
  height: 1.5rem;
  border: 3px solid black;
}
</style>