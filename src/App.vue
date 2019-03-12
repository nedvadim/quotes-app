<template>
    <div class="container">
        <app-quote-grid :quotes="quotes"></app-quote-grid>
    </div>
</template>

<script>
    
    import QuoteGrid from './components/QuoteGrid.vue';

    export default {
        data: function(){
            return{
                quotes: [
                    'The very first quote out there.',
                    'Another one.'
                ],
                maxQuotes: 10
            };
        },
        components:{
            'app-quote-grid': QuoteGrid
        }
    }
</script>

<style>
</style>
