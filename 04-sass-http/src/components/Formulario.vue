<template>
  <div>
    <form @submit.prevent="obtener">
    <div>
      <label>Moneda Nacional: </label>
      <select v-model="moneda" required >
        <option value="" disabled selected > Seleccione una Moneda... </option>
        <option>MXN</option>
        <option>USD</option>
        <option>EUR</option>
        
      </select>
    </div>
    <div>
      <label> Criptomoneda: </label>
      <select  v-model="cripto" required >
        <option value="" disabled selected >Seleccione una Criptomoneda...</option>

        <option>BTC</option>
        <option>ETH</option>
        <option>LTC</option>
        
      </select>
    </div>
  <div>
    <button type="submit">Cotizar</button>
  </div>

    </form>
  </div>
</template>

<script>
  /**Necesito obtener la información de moneda y de cripto */
export default {
data: () =>({
  moneda: "",
  cripto: "",
}),
methods: {
  obtener (){

    console.log(this.moneda, this.cripto);
  }
  
},

};
</script>
