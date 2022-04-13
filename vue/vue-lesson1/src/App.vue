<template>
  <div class="container">
    <myheader />
    <h1 class="text-center mb-5 mt-5">Todo Project</h1>
      <user-form :users="users" @addUser="createTodo" />
      <user-list :users="users" @delete="deleteitem" />
  </div>
</template>

<script>
import myheader from './components/MyHeader'
import UserForm from './components/UserForm';
import UserList from './components/UserList';

export default {
  name: 'App',

  components: {
    myheader,
    UserList,
    UserForm,
    
  },
 
 
    data() {
    return {
      users: [
        { id: 1, name: "Sherali", age: 32, phone: 902263569 },
        { id: 2, name: "Botir", age: 32, phone: 936662244 },
        { id: 3, name: "Samandar", age: 32, phone: 915550055 },
        { id: 4, name: "Islom", age: 32, phone: 915890089 },
      ],
    }
  },
  methods: {

    createTodo(item){
      this.users.push(item)
    },
    deleteitem(id){
       this.users = this.users.filter(item => item.id !== id)
    }
  },
};
</script>

<style>
</style>