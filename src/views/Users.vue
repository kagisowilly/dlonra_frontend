<template>
   <div class="myTable">
    <table class="table mt-5">
      <thead>
        <tr class="text-black text-start">
          <th>#</th>
          <th scope="col">Name</th>
          <th scope="col">Surname</th>
          <th scope="col">Email</th>
        </tr>
      </thead>
      <tbody>
        <tr class="text-white text-start" v-for="user of users" :key="user.id">
          <th scope="row">{{ user.id}}</th>
          <td scope="row">
            <span class="">
              {{ user.name }}
            </span>
          </td>
          <td class="POINT" style="width: 100px">
            {{user.surname}}
          </td>
          <td class="POINT" style="width: 100px">
           {{user.email}}
          </td>
        </tr>
      </tbody>
    </table>    
   </div>
       <button @click ="getUsers">
        Show Users
       </button> 
</template>

<script>
export default {
data(){
return{
  users: null,
}
},
// FETCHING USERS
methods:{
      getUsers(){
      fetch("https://dlonra-academy.herokuapp.com/users")
    .then((res) => res.json())
    .then((data) => {
      console.log(data)
      this.users = data.usersdata;
    });   
  }
}
}
</script>

<style scoped>
table{
width: 60%;

}
.myTable{
  display: flex;
  align-items: center;
  min-height: 85vh;
}
button{
    background-color: #ffc801;
  border-radius: 20px;
}

@media all and (max-width: 800px) {
  td{
    font-size: 13px !important;
  }
  button{
  margin-bottom:50px !important;

}  
}
</style> 