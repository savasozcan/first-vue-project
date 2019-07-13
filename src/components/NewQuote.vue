<template>
    <div class="row">
        <form>
            <div class="col-sm-8 col-sm-offset2 col-xs-12 col-md-6 col-md-offset-3 form-group">
                <label>Quote</label>
                <textarea class="form-control" rows="6" v-model="quote"></textarea>
            </div>
            <div class="col-sm-8 col-sm-offset2 col-xs-12 col-md-6 col-md-offset-3 form-group">
                <button class="btn btn-primary" @click.prevent="createNewQuote">Add Quote</button>
            </div>
        </form>
    </div>
</template>

<script>
export default {
   data: function() {
       return {
           quote: ''
       }
   },
   methods: {
       createNewQuote() {
           this.$emit('addNewQuote', this.quote)
           this.quote = ''
       }
   }
}
</script>

<style>
    
</style>