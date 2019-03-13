<template>
    <div class="container">
        <app-new-quote @QuoteWasAdded = "AddQuote"></app-new-quote>
        <app-quote-grid :quotes="quotes"></app-quote-grid>
    </div>
</template>

<script>
    
    import QuoteGrid from './components/QuoteGrid.vue';
    import NewQuote from './components/NewQuote.vue';

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
            'app-quote-grid': QuoteGrid,
            'app-new-quote': NewQuote
        },
        methods:{
            AddQuote(quote){
                this.quotes.push(quote);
            }
        }
    }
</script>

<style>
</style>
