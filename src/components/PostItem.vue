<template>
    <div class="post">
        <h4><strong>Name: </strong>{{ post.title }}</h4>
        <h4><strong>Description: </strong>{{ post.body }}</h4>
        <div class="btn-block">
            <my-button @click="$emit('remove', post)">Remove</my-button>
        </div>
    </div>
</template>

<script>
import MyButton from './UI/MyButton.vue';
    export default {
    props: {
        post: {
            type: Object,
            required: true,
        }
    },
    components: { MyButton }
}
</script>

<style lang="scss" scoped>
    .post {
            text-align: center;
            padding: 15px;
            border: 2px solid #ec6d5e;
            margin-top: 15px;
            background-color: #fff;
            border-radius: 25px;
            width: 850px;
            margin: 0 auto;

        h4 {
            font-family: 'Poppins';
            font-weight: 400;
            margin: 0;
            margin-bottom: 15px;
            color: #454152;
            font-size: 18px;
        }
    }
</style>