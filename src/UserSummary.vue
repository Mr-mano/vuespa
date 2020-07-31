<template>
    <div class="user-summary">
        Id: {{usr.id}}, Ville: {{usr.address.city}}, CP: {{usr.address.zipcode}}, email: <router-link v-bind:to="/users/ + usr.id">{{usr.email}}</router-link>
        <button v-on:click="acceptInvitation">Accepter</button>
    </div>

</template>

<script>
export default {
    name: 'user-summary',
    props: ['usr'],
        methods:{
            acceptInvitation: function(){
                this.$emit('accept');
        }
    }
}
</script>

<style>
.user-summary{
    border: 2px solid grey;
    margin: 10px;
    padding: 15px;
    width: 250px;
}
</style>