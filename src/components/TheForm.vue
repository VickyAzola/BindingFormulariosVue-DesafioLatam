<script>
export default {
  name: 'TheForm',
  data() {
    return {
      titulo: '',
      chipSRC: '',
      numero: '',
      fechaExp: '',
      propietario: '',
      tipoSRC: ''
    }
  }
}
</script>

<template>
    <div class="container">
      <form>
        <div class="flex-group">
          <label for="titulo">Título de la tarjeta: </label>
          <input 
            id="titulo" 
            v-model="titulo" 
            placeholder="Visa Classic Crédito" 
          />
        </div>

        <div class="flex-group">
          <label for="chip">Chip SRC: </label>
          <input 
            id="chip" 
            v-model="chipSRC" 
            placeholder="Ingresa una dirección de imágen"
          />
        </div>

        <div class="flex-group">
          <label for="numero">Número: </label>
          <input 
            id="numero" 
            v-model="numero" 
            type="number" 
            placeholder="000 000 000 000"
          />
        </div>

        <div class="flex-group">
          <label for="fechaExp">Fecha de expiración: </label>
          <input id="fechaExp" v-model="fechaExp" type="date" />
        </div>

        <div class="flex-group">
          <label for="propietario">Propietario: </label>
          <input id="propietario" v-model="propietario" placeholder="Ingresa tu nombre"/>
        </div>

        <div class="flex-group">
          <label for="tipo">Tipo de tarjeta SRC: </label>
          <input id="tipo" v-model="tipoSRC" placeholder="Ingresa una dirección de imágen"/>
        </div>
      </form>

      <div class="carnet">
        <h3>{{ titulo }}</h3>
        <img width="40" :src="chipSRC" alt="" />
        <div>
          <h2>{{ numero }}</h2>
          <span v-if="fechaExp">Fecha Exp: <b>{{ fechaExp }}</b></span>
        </div>
        <footer>
          <span>{{ propietario }}</span>
          <img :src="tipoSRC" width="60" />
        </footer>
      </div>
    </div>
</template>

<style scoped>
.container {
  min-height: 100vh;
  display: grid;
  margin-inline: 5rem;
  grid-template-columns: 1fr 1fr;
  place-content: center;
}

form {
  margin-inline: auto;
  min-width: 25rem;
  padding: 18px;
  border-radius: 20px;
  border: ridge 1px;
  box-shadow: 1px 1px 1px 1px gray;
  font-weight: bold;
  display: flex;
  flex-direction: column;
  gap: 15px;
  justify-content: center;
}

.flex-group {
  display: flex;
  flex-direction: column;
}

.flex-group label {
  margin-bottom: .5rem;
}

.flex-group input {
  padding: .5rem;
  border: 1px solid rgb(168, 168, 168);
  border-radius: .3rem;
}

.carnet {
  margin-block: auto;
  width: 400px;
  height: 230px;
  background: #1c1a1e;
  color: white;
  border-radius: 20px;
  padding: 20px;
  box-shadow: 0 0 10px 2px black;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

h3 {
  font-size: 20px;
}

h2 {
  font-size: 30px;
  letter-spacing: 10px;
  margin-bottom: 15px;
  text-shadow: 0 0 1px gold;
  font-family: Times;
}

b {
  font-size: 16px;
}

footer {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  font-weight: bold;
  font-size: 18px;
  text-transform: uppercase;
  font-style: italic;
}
</style>
