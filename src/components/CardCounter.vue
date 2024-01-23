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
    <div class="col-12 p-3 bg-dark text-white fw-bold mb-2 rounded-1 ">
        <span>Found {{ this.store.cardsList.length }} cards</span>
    </div>
</template>

<style lang="scss" scoped>

</style>
