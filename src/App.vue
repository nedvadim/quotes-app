<template>
    <div class="container">
        <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes" ></app-header>
        <app-new-quote @QuoteWasAdded = "addQuote"></app-new-quote>
        <app-quote-grid :quotes="quotes" @quoteWasDeleted="deleteQuote"></app-quote-grid>
    </div>
</template>

<script>
    
    import Header from './components/Header.vue'
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
            'app-new-quote': NewQuote,
            'app-header': Header
        },
        methods:{
            addQuote(quote){
                if(this.quotes.length >= 10)
                {
                    return alert('No room for new quotes. Delete some of them to free space');
                }
                this.quotes.push(quote);
            }
            ,
            deleteQuote(index){
                this.quotes.splice(index, 1);
            }
        }
    }
</script>

<style>
</style>
