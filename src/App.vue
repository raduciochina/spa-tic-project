<template>
  <div class="container">
    <UserHeader @show-add-user="toggleAddUser()" title="User Management" :showAddUser = "showAddUser"/>
    <div v-if="showAddUser">
      <AddUser @add-user='addUser'/>
    </div>
    <Users @delete-user="deleteUser" :users="users" />
  </div>
</template>

<script>
import UserHeader from './components/UserHeader.vue';
import Users from './components/Users.vue';
import AddUser from './components/AddUser.vue';

export default {
  name: 'App',
  components: {
    UserHeader,
    Users,
    AddUser,
  },
  data() {
    return {
      users: [],
      showAddUser: false,
    };
  },
  methods: {
    toggleAddUser() {
      this.showAddUser = !this.showAddUser;
    },
    addUser(user) {
      this.users.push(user);
    },
    deleteUser(id) {
      if(confirm("Are you sure?")) {
        this.users = this.users.filter(user => user.id !== id);
      }
    },
  },

  created() {
    this.users =  [
        { 
          id: 1,
          name: 'Nicu de la Cazanesti',
          email: 'nicucazanesti@gmail.com',
          password: '123456',
        },
        {
          id: 2,
          name: 'Mihai Bendeac',
          email: 'mihigh@gmail.com',
          password: '123456',
          creditCards:[
            {
              id: 1,
              name: 'Visa',
              number: '123456789',
              expirationDate: '12/12/2021',
              cvv: '123',
            },
            {
              id: 2,
              name: 'Mastercard',
              number: '123456789',
              expirationDate: '12/12/2021',
              cvv: '123',
            },
          ]
        },
        {
          id: 3,
          name: 'Marcel Popescu',
          email: 'marcelino@gmail.com',
          password: '123456',
        },
      ]
  }
}

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.container{
  max-width: 800px;
  margin: 0 auto;
}


</style>
