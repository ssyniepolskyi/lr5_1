<template>
  <div class="stock">
    <div class="stock-item" v-for="value in stock" :key="value.stock">
      <div class="stock-item__info">
        <div class="stock-item__cover">
          <img :src="value.IMAGE" alt="Logo Company">
        </div>
        <h3 class="stock-item__title">
          {{value.SHORTNAME}}
          <span>{{value.NP}}</span>
          <span>{{value.ADRESS}}</span>
        </h3>
      </div>
      <span class="stock-item__erdpou">ЄРДПУ: {{value.KOD_EDRPOU }}</span>
    </div>
    
  </div>
  
</template>

<script lang="ts">
import axios from 'axios'

export default {
  name: 'Stocks',
  data(){
    return{
      stock: [],
      errors: [],
    }
  },
  created(){
    axios.get('src/components/data.json')
    .then(response =>{
      this.stock = response.data
      console.log(response)
    })
  }
} as any

</script>
