<template>
   <div class="row">
       <form action="">
         <div class="col-sm-8 col sm offset-2 xs col-md-6 col-md-offset-3 form-group">
                <label>Quote</label>
                <textarea class="form-control" rows="3" v-model="quoteModelBinding"></textarea>   
         </div>
         <div class="col-sm-8 col sm offset-2 xs col-md-6 col-md-offset-3 form-group">
                <button class="btn btn-primary" @click.prevent="createNew">Add Quote</button>
         </div>
        </form>
   </div> 
</template>

<script>

export default {
    data: function() {
        return {
            quoteModelBinding: ''
        }
    },
    methods: {
        createNew(){
            this.$emit('quoteAdded', this.quoteModelBinding);
            this.quoteModelBinding = '';
        }
    }
}
</script>

<style>

</style>


