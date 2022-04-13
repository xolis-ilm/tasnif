<template>
  <table class="table">
    <thead>
      <tr>
        <th scope="col">#</th>
        <th scope="col">First</th>
        <th scope="col">Last</th>
        <th scope="col">Handle</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="item of users" v-bind:key="item.id">
        <th>{{ item.id }}</th>
        <td>{{ item.name }}</td>
        <td>{{ item.age }}</td>
        <td>{{ item.phone }}</td>
        <td>
          <button @click="$emit('delete', item.id)" class="btn btn-danger">
            Delete
          </button>
        </td>
      </tr>
    </tbody>
  </table>
</template>
<script>
export default {
    name: 'UserList',

    props: {
        users: {
            type: String,
            required: true
        }
    }
}
</script>

<style scoped>

</style>