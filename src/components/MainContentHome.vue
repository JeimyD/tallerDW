<template>
  <div class="main">
      <section class="pokemones-grid">
        <div class="pokemones" v-for="pokemon in pokemones" :key="pokemon.id">
          <img :src="pokemon.imagen" alt="imagenes pokemon">
          <h2>{{ pokemon.nombre }}</h2>
          <p>{{ pokemon.type_name }}</p>
        </div>
      </section>
  </div>
</template>

<script>
  export default {
    name: 'PokemonesApi',

    data() {
      return {
        pokemones: [],
      };
    },

    created() {
      this.getAllPokemones();
    },

    methods: {
      async getAllPokemones() {
        const pokemonApi = 'https://cobuses.com.co/APIV2/model/pokemon.php?dato=getallpokemon';
        try {
          const response = await this.axios.get(pokemonApi);
          this.pokemones = response.data;
          
        } catch (error) {
          console.log("No consumiste el API pendeja");
        }
      },
    },
  };
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .pokemones-grid{
    display: flex;
    flex-direction: row;  
    justify-content: space-around;
  }

  img{
    height: 125px;
    width: 125px;
    object-fit: cover;
  }
</style>
