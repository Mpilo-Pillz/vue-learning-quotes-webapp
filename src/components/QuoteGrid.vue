<template>
   <!-- <div class="row">
       <app-quote v-for="(quote, index) in quotesProps" >{{ quote }}</app-quote>
   </div>  -->

   <div class="row">
       <app-quote 
       v-for="(quote, index) in quotesProps"
       v-bind:key="(quote, index)">{{ quote }}

           <hr>
           <button class="btn btn-danger deleteQuoteButton" @click="deleteQuote(index)">Delete Quote</button>

       </app-quote>
   </div> 
</template>

<script>
import Quote from './Quote.vue';
export default {
    props: ['quotesProps'],
    components: {
        appQuote: Quote
    },
    methods: {
        deleteQuote(index) {
            this.$emit('quoteDeleted', index);
        }
    }
}
</script>

<style>
    .deleteQuoteButton {
        font-family: Arial, Helvetica, sans-serif;
    }
</style>


