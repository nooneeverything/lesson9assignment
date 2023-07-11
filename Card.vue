<template>
    <div class="card">
        <div class="card-top">
            <img :src="flag" alt="alt text" v-bind:class="{'img': border }" @click="toggle"/>
        </div>
        <div class="card-bottom">
            <div class="name">
            Name: {{ countryName }}
            </div>
            Languages:
            <span class="lang" v-for="l in lang">
            {{ l }},
            </span> 
            <div v-if="capital"> Capital: {{ capital[0] }} </div>
            <span class="currencies" v-for="(currency,key) in currencies">
            Currencies: {{ currency.name }} <span v-if="key +1 < currencies.length">, </span>
            </span>
        </div>
    </div>
</template>   

<script>
 import { bordermixin } from '../mixins/bordermixin.js' 
    export default {
        props: {
            countryName: null,
            flag: null,
            lang: null,
            capital: null,
            currencies: null,
        },    
        data() {
            return {


            }
        },
        mixins: [ 
            bordermixin
        ],
    }
</script>

<style>

.img {
    border: 3px solid orange;
}
</style> 