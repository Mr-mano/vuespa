<template>
  <div>
    <!--<user-list v-bind:data="users" v-bind:users-coming="usersWhoWillCome"></user-list>-->
    <router-view v-bind:data="users" v-bind:users-coming="usersWhoWillCome"></router-view>
    <div  v-for="user in usersWhoWillCome">
            Id : {{user.id}} - Email : {{user.email}}
    </div>
  </div>

</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      usersUrl: 'https://jsonplaceholder.typicode.com/users',
      users: [],
      usersWhoWillCome: []
    }
  },
  created: function() {
            axios.get(this.usersUrl)
                .then((response) => {
                    this.users = response.data;
                    //console.log(vm.users);
                })
        }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
