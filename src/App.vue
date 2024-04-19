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

        getResponse(){
            
            Axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0', {
                params:{
                    archetype: this.store.activeArc.length > 0 ? this.store.activeArc : null,
                }
            })
            .then((res) => {
                this.store.cardsList = res.data.data;
            })
            .catch((err)=>{
                this.store.cardsList = [];
            })
            .finally(()=>{
                this.loadingFlag = false;
            })
            
        }
    },
    created() {

        this.getResponse();

        Axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
        .then((res) => {
            
            for(let i = 0; i < res.data.length; i++){
                this.store.arcList.push(res.data[i].archetype_name)
            }
        })
    }
}
</script>

<template>

    <LoadingGif v-if="loadingFlag == true"/>

    <div v-else>
        <header>
            <AppHeader/>
         </header>

        <main>
            <AppMain @arcFilter="getResponse()"/>
        </main>

        <footer>
            <AppFooter/>
        </footer>
    </div>
    

</template>

<style lang="scss">

@import "bootstrap/scss/bootstrap";
</style>


