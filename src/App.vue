<script setup>
import { ref } from 'vue';

let cantidadBoletas=0

const valorBoleta=5000

const totalPagar=ref(0)

const comprarBoletas =()=>{
  totalPagar.value= +cantidadBoletas*valorBoleta
  if(cantidadBoletas>5){
    let descuento= valorBoleta- valorBoleta*0.3
 
    totalPagar.value= +cantidadBoletas*descuento
    return 'Debes pagar: ' + totalPagar.value
  }else{
    return 'Debes pagar: ' + totalPagar.value
  }
}

</script>

<template>
 <div class="bg-slate-200 w-96 mx-auto py-4 px-6 rounded-md mt-8 shadow-md">
<label for="entradas">
  cantidad
</label>
<input id="entradas" name="entradas" type="number" class="rounded-md bg-slate-100 pl-1" v-model="cantidadBoletas">
<button class="ml-2 bg-blue-300 px-2 rounded-md hover:bg-blue-400 
hover:text-white" @click="comprarBoletas">
comprar
</button>
<p class="text-center mt-3 border-2 border-blue-300 w-3/6 bg-slate-400">
  {{ comprarBoletas() }}
</p>
 </div>
</template>

