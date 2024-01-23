<script>
    import SingleCard from '../components/SingleCard.vue';
    import { store } from '../store';
    
    export default {
        data() {
            return { 
                
                store,
            }
        },
        components: {
            SingleCard,
        },
        methods: {
            changeActiveArc(newArc){
                this.store.activeArc = newArc;
            }
        },
    }
    </script>

<template>
    <div class="bg-warning p-5 ">
        <div class=" container-xl ">
            <div class=" w-25 mb-3">
                <select class="form-select" name="type" v-model="store.activeArc" @click="$emit('arcFilter')" aria-label="Default select example">
                    <option value="">All</option>
                    <option name="type" v-for="(elem, i) in store.arcList" :value="elem" @click="changeActiveArc(value)" :key="i">{{elem}}</option>
                </select>
            </div>  
            

            <div class="row p-5 bg-white g-0 rounded-4">
                <div class="col-12 p-3 bg-dark text-white fw-bold mb-2 rounded-1 ">
                    <span>Found {{ this.store.cardsList.length }} cards</span>
                </div>

            
                <SingleCard 
                v-for="(elem, i) in this.store.cardsList"
                :key="i"
                :card="elem"
                :arc="elem.archetype"
                />
                
                
                
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use "../assets/scss/main.scss" as *;
</style>
