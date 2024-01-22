<script>
    import SingleCard from '../components/SingleCard.vue';
    import { store } from '../store';
    
    export default {
        data() {
            return { 
                selectedArc: null,
                singleArc: [],
                store,
            }
        },
        components: {
            SingleCard,
        },
        methods: {
            filteredCards() {
                if (!this.selectedArc) {
                    return this.store.cardsList;
                } else {
                    return this.store.cardsList.filter((card) => card.archetype === this.selectedArc);
                }
            },
        },
    }
    </script>

<template>
    <div class="bg-warning p-5 ">
        <div class=" container-xl ">
            <div class=" w-25 mb-3">
                <select class="form-select" v-model="selectedArc" aria-label="Default select example">
                    <option value="">All</option>
                    <option v-for="(elem, i) in store.selectArc">{{elem}}</option>
                </select>
            </div>  
            

            <div class="row p-5 bg-white g-0 rounded-4">
                <div class="col-12 p-3 bg-dark text-white fw-bold mb-2 rounded-1  ">
                    <span>Found {{ store.cardsList.length }} cards</span>
                </div>

            
                <SingleCard 
                v-for="(elem, i) in filteredCards()"
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
