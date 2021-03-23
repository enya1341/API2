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
    }
  },
  methods: {
    async value(addressin){
          let address = await axios.get(`https://apis.postcode-jp.com/api/v4/${this.addressid}/addressdata?callback`)
          addressin = JSON.stringify(address)
    }
  },

}
</script>
