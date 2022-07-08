<template>
    <div>
        <form @submit.prevent>
            <h2>Creating post</h2>
            <input v-model="post.title" type="text" placeholder="Name">
            <input v-model="post.body" type="text" placeholder="Description">
            <my-button @click="addPost">Create post</my-button>
        </form>
    </div>
</template>

<script>
import MyButton from './UI/MyButton.vue';
    export default {
    data() {
        return {
            post: {
                title: "",
                body: "",
            }
        };
    },
    methods: {
        addPost() {
            this.$emit("create", this.post);
            this.post = {
                title: "",
                body: "",

            };
        },
    },
    components: { MyButton }
}
</script>

<style lang="scss" scoped>
    form input {
        padding: 20px;
        margin-right: 20px;
        border: 2px solid green;
        padding: 23px 40px;
        border: 0;
        background: #fff;
        border-radius: 40px;
        font-family: 'Poppins';
        font-weight: 400;
        font-size: 16px;
    }
</style>