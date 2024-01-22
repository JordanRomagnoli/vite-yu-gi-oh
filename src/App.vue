<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppFooter from './components/AppFooter.vue';
import Axios from 'axios';
import { store } from './store.js';
import LoadingGif from './components/LoadingGif.vue';


export default {
    data() {
        return { 

            store,
            loadingFlag: true,
        }
    },
    components: {

        AppHeader,
        AppMain,
        AppFooter,
        LoadingGif,
    },
    created(){
        setTimeout(()=>{
            this.loadingFlag = false;
        }, 1500)
    },
    mounted() {
        Axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=15&offset=0')
        .then((res) => {
            this.store.cardsList = res.data.data;
            console.log(this.store.cardsList);
        })
    },
}
</script>

<template>

    <LoadingGif v-if="loadingFlag"/>

    <div v-else>
        <header>
            <AppHeader/>
         </header>

        <main>
            <AppMain/>
        </main>

        <footer>
            <AppFooter/>
        </footer>
    </div>
    
        
</template>

<style lang="scss">
@import "bootstrap/scss/bootstrap";
</style>
