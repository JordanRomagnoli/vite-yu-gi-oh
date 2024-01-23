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
            loadingFlag: true,
            store,
        }
    },
    components: {

        AppHeader,
        AppMain,
        AppFooter,
        LoadingGif,
    },
    methods: {
        addOption(){
            for(let i = 0; i < this.store.cardsList.length; i++){
                if ((this.store.cardsList[i].archetype !== undefined) && (!this.store.selectArc.includes(this.store.cardsList[i].archetype))) {
                    this.store.selectArc.push(this.store.cardsList[i].archetype);
                    console.log(this.store.selectArc);
                }
            }
        }
    },  
    // created(){
    //     setTimeout(()=>{
    //         this.loadingFlag = false;
    //     }, 1500)
    // },
    created() {
        Axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=100&offset=0')
        .then((res) => {
            this.store.cardsList = res.data.data;
        })
    },
    updated(){
        this.addOption()
        
    },
}
</script>

<template>

    <LoadingGif v-if="store.cardsList.length < 15"/>

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
