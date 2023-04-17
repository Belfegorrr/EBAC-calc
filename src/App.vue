<script setup>
import { reactive } from "vue";

// import { createApp } from 'vue';

const estado = reactive({
  num1: 0,
  num2: 0,
  soma: "0",
  selected: 'Somar'
});

function operacao() {
    
  if( estado.selected === 'Somar'){
    estado.soma = parseInt(estado.num1) + parseInt(estado.num2);  
    console.log(estado.soma)
  } else if( estado.selected === 'Subtrair'){    
      estado.soma = parseInt(estado.num1) - parseInt(estado.num2);
      console.log(estado.soma)
  }else if( estado.selected === 'Multiplicar'){    
      estado.soma = parseInt(estado.num1) * parseInt(estado.num2);
      console.log(estado.soma)
  }else if( estado.selected === 'Dividir'){    
      estado.soma = parseInt(estado.num1) / (parseInt(estado.num2));
      console.log(estado.soma)
  }
}
</script>

<template>
  <hr />
  <section class="container">

    <h1>Resutlado: {{ estado.soma }}</h1>
    <label>Calculadora EBAC</label>
    <br />
    <input type="number" @change=" estado.num1 = $event.target.value" />
    <br />
    <input type="number" @change=" estado.num2 = $event.target.value" />
    <br /> 
    
    <select @change=" estado.selected = $event.target.value">    
      <option >Somar</option>
      <option >Subtrair</option>
      <option >Multiplicar</option>
      <option >Dividir</option>
    </select>
    <br />
    <button className="operacao" @click="operacao" >{{ estado.selected }}</button>
    <br />
  </section>

</template>

<style scoped>
 .container {
    width: 100%;
    height: 100hv;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    background-color: #eef105;
    color: #0f0f0f;
}

h1 {
    font-size: 50px;
    margin-top: 40px;
    margin-bottom: 60px;
}

label{
  font-size: 30px;
}
input{
  padding: 20px;
  font-size: 20px;
  text-align: center;
}
select {
  text-align: center;
  width: 200px;
}

button{
  border: none;
  padding: 10px;
  color: #050505;
  background-color: #f19f07;
  font-size: 20px;
  font-weight: bold;
}
</style>
