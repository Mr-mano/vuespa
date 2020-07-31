<template>
    <div>
        <h2>Détails de l'utilisateur {{this.$route.params.id}}</h2>
        <p><router-link to="/users">Retour</router-link></p>
    </div>
</template>

<script>
export default {
    name: 'user-details',
    props: ['usr'],
        methods:{
            acceptInvitation: function(){
                this.$emit('accept');
        }
    }
}

</script>

<style>

</style>