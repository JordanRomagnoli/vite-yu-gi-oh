<script>
    export default {
        data() {
            return { 
                title: 'Questo è il footer' 
            }
        },
    }
    </script>

<template>
    <main class="main-title">
        <h1>
            {{ title }}
        </h1>
    </main>
</template>

<style lang="scss" scoped>
    h1{
        color: blue;
        text-align: center;
    }
</style>
