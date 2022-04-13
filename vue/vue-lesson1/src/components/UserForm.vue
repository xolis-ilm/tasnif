<template>
    <div class="row justify-content-center">
      <div class="col-7">
        <form @submit.prevent>
          <input v-model="user.name" type="text" class="form-control mb-3" placeholder="Ism..." />
          <input v-model="user.age" type="number" class="form-control" placeholder="Yosh..." />
          <input v-model="user.phone" type="number" class="form-control mt-3" placeholder="Tel raqam..."/>
        <button @click="createTodo" class="btn btn-success mt-5 float-end">Qo`shish</button>
      </form>
      </div>
    </div>
</template>

<script>
export default {
    name: 'UserForm',

    props: {
        users: {
            type: String,
            required: true
        }
    },

    data() {
        return {
            user: {
                name: "",
                age: "",
                phone: "",
            }
        }
    },
    methods: {
        createTodo(){
            this.user.id = this.users.length + 1
            this.$emit('addUser', this.user)

            this.user = {
                name: "",
                age: "",
                phone: "",
            }
        },
    },
}
</script>

<style scoped>

</style>