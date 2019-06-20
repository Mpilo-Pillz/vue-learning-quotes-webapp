<template>
   <div class="row">
       <app-quote v-for="quote in quotesProps">{{ quote }}</app-quote>
   </div> 
</template>

<script>
import Quote from './Quote.vue';
export default {
    props: ['quotesProps'],
    components: {
        appQuote: Quote
    }
}
</script>

<style>

</style>


