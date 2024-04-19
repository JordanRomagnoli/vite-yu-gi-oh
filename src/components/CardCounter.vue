<script>
    import {store} from '../store';

    export default {
        data() {
            return { 

                store,
            }
        },
    }
    </script>

<template>
    <div class="col-12 p-3">
        <span>Found {{ this.store.cardsList.length }} cards</span>
    </div>
</template>

<style lang="scss" scoped>
    div{

        margin-bottom: 32px;
        span{

            font-weight: 800;
            text-transform: uppercase;
            font-size: 1.5rem;
        }
    }
</style>
