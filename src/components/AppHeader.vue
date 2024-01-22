<script>
    export default {
        data() {
            return { 
                title: 'Ciao ragazzi' 
            }
        },
    }
    </script>

<template>
    <header class="main-title">
        <h1>
            <p>
                {{ title }}
            </p>
        </h1>
    </header>
</template>

<style lang="scss" scoped>
    h1{
        p{
            color: red;
            text-align: center;
        }
    }
</style>
