<template>
    <div class="container">
        <app-new-quote @quoteAdded="newQuote"></app-new-quote>
        <app-quote-grid :quotesProps="quotesArray"></app-quote-grid>
    </div>
</template>

<script>
    import QuoteGrid from './components/QuoteGrid.vue';
    import NewQuote from './components/NewQuote.vue';

    export default {
        data: function(){
            return {
                quotesArray: [
                    'This is a quote for display purposes'
                ],
                maxQuotes: 10
            }
        },
        methods: {  
            newQuote(quoteArg) {
                this.quotesArray.push(quoteArg)
            }
        },
        components: {
            appQuoteGrid: QuoteGrid,
            appNewQuote: NewQuote
        }
    }
</script>

<style>
</style>
