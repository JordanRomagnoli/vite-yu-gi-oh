<script>
    export default {
        data() {
            return { 
                 
            }
        },
    }
    </script>

<template>
    <div class="loading">
        <img src="../assets/img/Spin-1s-200px.gif" alt="">
    </div>
</template>

<style lang="scss" scoped>
    .loading{
        z-index: 1;
        background-color: white;
        height: 100vh;
        width: 100vw;
        display: flex;
        justify-content: center;
        align-items: center;

        img{
            width: 80px;
            height: 80px;
        }
    };
</style>
