<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppFooter from './components/AppFooter.vue';
import Axios from 'axios';
import { store } from './store.js';


export default {
    data() {
        return { 

            store,
        }
    },
    components: {

        AppHeader,
        AppMain,
        AppFooter
    },
    created() {
        Axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=15&offset=0')
        .then((res) => {
            this.store.cardsList = res.data.data;
            console.log(this.store.cardsList);
        })
    },
}
</script>

<template>

    <header>
        <AppHeader/>
    </header>

    <main>
        <AppMain/>
    </main>

    <footer>
        <AppFooter/>
    </footer>
        
</template>

<style lang="scss">
@import "bootstrap/scss/bootstrap";
</style>
