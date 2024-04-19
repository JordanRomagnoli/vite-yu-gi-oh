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
    <div class="card-col">
        <div class="card_frame">
            <img :src="card.card_images[0].image_url" :alt="card.name" class="w-100">
        </div>

        <div class="card_info px-2">
            <h3>
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
    width: calc(100% / 5 - 16px);
    padding: 0 30px;
    margin-bottom: 16px;
    margin-left: 8px;
    margin-right: 8px;
    background-color: rgb(242, 242, 242);
    padding: 8px;
    .card_frame{
    width: 100%;
    margin-bottom: 8px;
    }
    .card_info{
    min-height: 100px;
    display: flex;
    justify-content: start;
    align-items: start;
    flex-direction: column;
    text-align: start;

        h3{
        font-size: 1.2rem;
        color: black;
        margin: 0;
        font-weight: 600;
        }

        span{

        font-size: 0.9rem;
        color: gray;

        }

    }
}

    
    
    
</style>
