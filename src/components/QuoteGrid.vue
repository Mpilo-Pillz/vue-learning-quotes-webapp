<template>
   <div class="row">
       <app-quote v-for="(quote, index) in quotesProps" @click.native="deleteQuote(index)">{{ quote }}</app-quote>
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

</style>


