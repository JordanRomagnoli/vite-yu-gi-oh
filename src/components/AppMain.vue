<script>
    import SingleCard from '../components/SingleCard.vue';
    import { store } from '../store';
    
    export default {
        data() {
            return { 

                store
            }
        },
        components: {
            SingleCard,
        }, 
    }
    </script>

<template>
    <div class="bg-warning p-5 ">
        <div class=" container-xl ">
            <div class=" w-25 mb-3">
                <select class="form-select" aria-label="Default select example">
                    <option value="1">Alien</option>
                </select>
            </div>  
            

            <div class="row p-5 bg-white g-0 ">
                <div class="col-12 p-3 bg-dark text-white fw-bold mb-2 rounded-1  ">
                    <span>Found {{ store.cardsList.length }} cards</span>
                </div>

                <SingleCard 
                v-for="(elem, i) in store.cardsList"
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
