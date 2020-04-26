<template>
    <div class="container">
        <h1 class="title">Kasus COVID-19 di Indonesia</h1>
        <p class="subtitle">#dirumahaja #yukcucitangan</p>

        <div class="columns">
        <div class="column card">
        <header class="card-header is-danger">
        <p class="card-header-title">
          Positif
        </p>
        <a href="#" class="card-header-icon" aria-label="more options">
          <span class="icon">
            <i class="fas fa-angle-down" aria-hidden="true"></i>
          </span>
        </a>
        </header>
        <div class="card-content">
        <div class="content">
          <p class="card-body confirmed">{{ result.confirmed.value }}</p>
        </div>
        </div>
      </div>

      <div class="column card">
        <header class="card-header">
        <p class="card-header-title">
          Meninggal
        </p>
        <a href="#" class="card-header-icon" aria-label="more options">
          <span class="icon">
            <i class="fas fa-angle-down" aria-hidden="true"></i>
          </span>
        </a>
        </header>
        <div class="card-content">
        <div class="content">
          <p class="card-body deaths">{{ result.deaths.value }}</p>
        </div>
        </div>
      </div>

      <div class="column card">
        <header class="card-header">
        <p class="card-header-title">
          Sembuh
        </p>
        <a href="#" class="card-header-icon" aria-label="more options">
          <span class="icon">
            <i class="fas fa-angle-down" aria-hidden="true"></i>
          </span>
        </a>
        </header>
        <div class="card-content">
        <div class="content">
          <p class="card-body recovered">{{ result.recovered.value }}</p>
        </div>
        </div>
      </div>
    </div>
    <p>Terakhir diperbarui pada {{ result.lastUpdate }}</p>
    <div class="footer">
      &copy; 2020 #YukCuciTangan 
      <br>
      Data dari API <a href="https://github.com/mathdroid">@mathdroid</a>
    </div>
    </div>

    
</template>

<script>
import axios from 'axios'

export default {
  components: {

  },
  asyncData ({ params, error }) {
    return axios.get(`https://covid19.mathdro.id/api/countries/Indonesia`)
      .then((res) => {
        return {
          result: res.data
          }
      })
      .catch((e) => {
        console.log(e)
      })
  },
  data() {
    return {
      result : {}
    }
  },
  head: {
    title: 'COVID-19 Indonesia Realtime Count',
    meta: [
      {  
      }
    ]}
}
</script>