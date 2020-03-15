<template>
  <div class="container">
    <h1 class="title">#YukCuciTangan</h1>
    <p class="subtitle">Kenapa sih kita harus cuci tangan?</p>
    <br>
    <p class="subtitle"><i>Ya biar bersih lah badrun.</i> Iya kita juga paham segitu aja mah.
    Jadi kita disini untuk mengajak kalian semua untuk mencuci tangan sebagai langkah preventif penularan virus yang lagi naik daun, apalagi kalo bukan COVID-19.</p>
    <p class="subtitle">Nih kita kasih tau angka kasus COVID-19 di Indonesia</p>

    <div class="columns">
      <div class="column card">
        <header class="card-header is-danger">
        <p class="card-header-title">
          Confirmed
        </p>
        <a href="#" class="card-header-icon" aria-label="more options">
          <span class="icon">
            <i class="fas fa-angle-down" aria-hidden="true"></i>
          </span>
        </a>
        </header>
        <div class="card-content">
        <div class="content">
          <p>{{ data }}</p>
        </div>
        </div>
      </div>

      <div class="column card">
        <header class="card-header">
        <p class="card-header-title">
          Death
        </p>
        <a href="#" class="card-header-icon" aria-label="more options">
          <span class="icon">
            <i class="fas fa-angle-down" aria-hidden="true"></i>
          </span>
        </a>
        </header>
        <div class="card-content">
        <div class="content">
          <p>{{ death }}</p>
        </div>
        </div>
      </div>

      <div class="column card">
        <header class="card-header">
        <p class="card-header-title">
          Recovered
        </p>
        <a href="#" class="card-header-icon" aria-label="more options">
          <span class="icon">
            <i class="fas fa-angle-down" aria-hidden="true"></i>
          </span>
        </a>
        </header>
        <div class="card-content">
        <div class="content">
          <p>{{ recovered }}</p>
        </div>
        </div>
      </div>
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
          case: res.data
          }
      })
      .catch((e) => {
        console.log(e)
      })
  },
  data() {
    return {
    }
  },
  head: {
    title: '#YukCuciTangan',
    meta: [
      {  
      }
    ]}
}
</script>

<style>
.container {
  margin: 40px auto;
  min-height: 90vh;
  align-items: center;
  align-content: center;
  text-align: left;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 800;
  font-size: 80px;
  color: #000000;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 24px;
  color: #505050;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}

@media(max-width: 768px) {
  .container {
    margin: 60px 20px;
  }

  .title {
    font-size: 36px;
    font-weight: 900;
  }

  .subtitle {
    font-size: 18px;
  }
}
</style>
