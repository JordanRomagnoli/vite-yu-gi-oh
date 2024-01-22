<script>
    
    export default {
        data() {
            return { 
                 
            }
        },
        props: {
            card: Object,
            arc: {
                type: String,
                default: 'Not Found',
            },
        },
    }
    </script>

<template>
    <div class="card-col mb-4">
        <div class="card_frame">
            <img :src="card.card_images[0].image_url" :alt="card.name" class="w-100">
        </div>

        <div class="card_info text-center px-2 py-4 bg-warning">
            <h3 class="">
                {{ card.name }}
            </h3>

            <span>
                {{ arc }}
            </span>
        </div>
    </div>
</template>

<style lang="scss" scoped>

.card-col{
    width: calc(100% / 5);
    padding: 0 30px;
    .card_frame{
    width: 100%;
    }
    .card_info{
    height: 200px;

        h3{
        font-size: 1.35rem;
        color: white;
        }

        span{

        font-size: 1.15rem;

        }

    }
}

    
    
    
</style>
