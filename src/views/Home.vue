<template>
  <div class="home">
    <input type="text" v-model="addressid">
    <button @click="value">住所自動入力</button>
    <p>address:{{addressin}}</p>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data(){
    return{
      addressid:"",
      addressdata:"",
      addressin:""
    }
  },
  methods: {
    async value(){
          let address = await axios.get(
`https://apis.postcode-jp.com/api/v4/postcodes/${this.addressid}?apiKey=JxZe9Ap6Qz3QOsAQPIcs83DIk8JgGYa9UEFveTH`)
          this.addressin = JSON.stringify(address.data[0].allAddress)
          console.log(address)
    }
  },

}
</script>
