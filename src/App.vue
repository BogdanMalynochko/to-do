<template>
    <my-dialog v-model:show="dialogVisible">
        <post-form @create="addPost"></post-form>
    </my-dialog>
    <h1>To do List</h1>
    <div class="btn-block">
        <my-button @click="showDialog">Create post</my-button>
        <my-button @click="fetchPosts">Get server posts</my-button>
    </div>
    <post-list :posts="posts" @remove="removePost"></post-list>
</template>

<script>
    import PostList from "./components/PostList";
    import PostForm from "./components/PostForm";
    import MyDialog from "./components/UI/MyDialog.vue";
    import MyButton from "./components/UI/MyButton.vue";
    import axios from 'axios';

    export default {
            components: {
            PostForm,
            PostList,   
            MyDialog,
            MyButton
        },
            data () {
                return {
                    posts: [],
                    dialogVisible: false,
                }
            }, 
            methods : {
                addPost (post) {
                    this.posts.push(post);
                    this.dialogVisible = false;
                },
                removePost (post) {
                    this.posts.splice(this.posts.indexOf(post), 1);
                },
                showDialog () {
                    this.dialogVisible = true;
                },
                async fetchPosts() {
                    try {
                        const response = await axios.get('https://jsonplaceholder.typicode.com/posts?_limit=10');
                        this.posts = response.data;
                    } catch (e) {
                        alert('ERROR');
                    }
                }
            },
            // mounted() {
            //     this.fetchPosts();
            // }
    }
</script>

<style lang="scss">
    #app {
        margin: 0 auto;
        padding: 0;
        box-sizing: border-box;
        max-width: 1440px;

        h1, h2 {
            text-align: center;
            font-family: 'Poppins';
            font-size: 45px;
            font-weight: 600;
        }

        h2 {
            text-align: center;
            font-size: 30px;
            font-weight: 400;
        }

        .btn-block {
            display: flex;
            justify-content: center;
            gap: 30px;
        }
    }
</style>