<template>
     <div class="post-wrapper" v-if="posts.length > 0">
        <post-item v-for="post in posts" :post="post" @remove="$emit('remove', post)"></post-item>
     </div>
     <h2 v-else>The to do list is empty</h2>
</template>

<script>
import PostItem from './PostItem.vue';
    export default {
    props: {
        posts: {
            type: Array,
            required: true
        }
    },
    components: { PostItem }
}
</script>

<style lang="scss" scoped>
    .post-wrapper {
        padding-top: 30px;
        display: flex;
        flex-direction: column;
        gap: 30px;
    }
</style>