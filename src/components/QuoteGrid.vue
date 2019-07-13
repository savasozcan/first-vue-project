<template>
  <div class="row">
   <quote v-for="(quote, index) in quotes" @click.native="deleteOne(index)">{{ quote }}</quote>
  </div>
</template>

<script>
import Quote from './Quote'

export default {
  methods: {
    deleteOne(index) {
      this.$emit('quoteDeleted', index)
    }
  },
  props: ['quotes'],
  components: {
    Quote: Quote
  }
}
</script>

<style>
  .panel-body {
      font-family: 'Russo One', sans-serif;
  }

  .panel {
      cursor: pointer;
      background-color: rgb(197, 48, 48);
      display: inline-block;
      padding: 40px 60px;
      border: 1px solid #000;
      box-shadow: 10px 10px 5px 0px rgba(0,0,0,0.75);
      transition: background-color .4s ease;
      margin: 50px 10px;
  }
  
  .panel:hover {
      background-color: rgb(207, 93, 93);
  }

</style>