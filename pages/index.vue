<template>
    <v-container>
        <post-form v-if="me" />
    <div>
        <post-card v-for="p in mainPosts" :key="p.id" :post="p" />
    </div>
    </v-container>
</template>


<script>
import PostCard from '~/components/PostCard.vue'
import PostForm from '~/components/PostForm.vue'

export default{
    components:{
        PostCard,
        PostForm
    },
    computed:{
        me(){
            return this.$store.state.users.me
        },
        mainPosts(){
            return this.$store.state.posts.mainPosts
        }
    }
}
</script>

<style>

</style>