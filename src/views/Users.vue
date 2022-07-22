<template>
   
    <table v-if="showUsers" class="table mt-5">
      <thead>
        <tr class="text-black">
          <th>#</th>
          <th scope="col">Name</th>
          <th scope="col">Surname</th>
          <th scope="col">Email</th>
        </tr>
      </thead>
      <tbody>
        <tr class="text-Black text-start" v-for="user of users" :key="user.id">
          <th scope="row">{{ user.id}}</th>
          <th scope="row">
            <span class="">
              {{ user.name }}
            </span>
          </th>
          <td class="POINT" style="width: 100px">
            {{user.surname}}
          </td>
          <td class="POINT" style="width: 100px">
            {{user.email}}
          </td>
          <td>

          </td>
        </tr>
      </tbody>
    </table>
       <!-- <button @click ="toggleShowUsers">
    <span v-if="showUsers">
        Hide books
    </span>
    <span v-else>
        Show books
    </span>
       </button>  -->
</template>

<script>
export default {
data(){
return{
  users: null,
  showUsers: true,
}
},
// FETCHING USERS
mounted(){
     fetch("http://localhost:4000/users")
    .then((res) => res.json())
    .then((data) => {
      console.log(data)
      this.users = data.usersdata;
    });
},
methods:{
    toggleShowUsers(){
        this.showUsers = !this.showUsers;
    },
}
}

</script>

<style scoped>
table{
width: 60%;
}
tr{
  margin-top: 200px !important;
}
button{
  margin-top:200px !important;
}
</style> 