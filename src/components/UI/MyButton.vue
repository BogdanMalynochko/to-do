<template>
    <button class="button">
        <slot></slot>
    </button>
</template>

<script>
    
</script>

<style lang="scss" scoped>
     .button {
        padding: 20px;
        background: #ec6d5e;
        border-radius: 40px;
        color: #fff;
        padding: 13px 30px;
        text-align: center;
        display: inline-block;
        border: 0;
        cursor: pointer;
        transition: 0.4s all;
        font-family: 'Poppins';
        font-style: normal;
        font-weight: 600;
        font-size: 20px;
        line-height: 24px;
        letter-spacing: .1em;
        text-transform: uppercase;

        &:hover {
            color: #ec6d5e;
            background: #fff;
            transition: 0.4s all;
        }
    }
</style>