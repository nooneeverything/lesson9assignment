<template>
    <div>
        <!-- <div v-for="(country,id) in countries" :key="id">
            <h1>Name: {{  country.name.common }}</h1>
            <h2 v-if="country.capital">Capital: {{ country.capital[0] }}</h2>
            <img v-if="country.flags.png" :src="country.flags.png" :title="country.flags.alt" :alt="country.flags.alt"/>
            <hr>
        </div> -->
        <Card v-for="(country,id) in countries" :key="id"

            :countryName="country.name.common"
            :flag="country.flags.png"
            :lang="country.languages"
            :capital="country.capital"
            :currencies="country.currencies"
        ></Card>
    </div>
   
</template>
 
<script>
import Card from '~/components/Card.vue';
import axios from 'axios';

 
export default {
  components: {
    Card
  },
  data() {
    return {
      loading: true,
      countries: null,
      errored: false
    }
  },
  mounted () {
    axios
        .get('https://restcountries.com/v3.1/all')
        .then(response => this.countries = response.data)
        .catch(error => {
            this.errored = true
        })
        .finally(() => this.loading = false)
    }
 
}
</script>

<style>


</style>
 