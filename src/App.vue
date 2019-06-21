<template>
    <div class="container">
        <app-header :quoteCount="quotesArray.length" :quotesMax="maxQuotes"></app-header>
        <app-new-quote @quoteAdded="newQuote"></app-new-quote>
        <app-quote-grid :quotesProps="quotesArray" @quoteDeleted="deleteQuote"></app-quote-grid>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">
                    Info: click on a quote to delete it!
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import QuoteGrid from './components/QuoteGrid.vue';
    import NewQuote from './components/NewQuote.vue';
    import Header from './components/Header.vue';

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
                if(this.quotesArray.length >= this.maxQuotes) {
                    return alert('Maximum quotes entered. Please delete some to enter more!');  
                }
                console.log("This works");
                this.quotesArray.push(quoteArg)
            },
            deleteQuote(index) {
                console.log("Now this also works");
                this.quotesArray.splice(index, 1);
            }
        },
        components: {
            appQuoteGrid: QuoteGrid,
            appNewQuote: NewQuote,
            appHeader: Header
        }
    }
</script>

<style>
</style>
