<template>
  <div class="container">
    <h1 class="title">#YukCuciTangan</h1>
    <p class="subtitle">Kenapa sih kita harus cuci tangan?</p>
    <p class="subtitle"><b><i>Ya biar bersih lah.</i></b></p>
    <p class="subtitle">Iya kita juga paham segitu aja mah.
    Jadi kita disini untuk mengajak kalian semua untuk mencuci tangan sebagai langkah preventif penularan virus yang lagi naik daun, apalagi kalo bukan COVID-19.</p>

    <br>
    <br>
    <p class="subtitle">Dengan melonjaknya angka kasus COVID-19 ini, masa iya kita masih belum sadar pentingnya cuci tangan? WHO pun sudah menyarankan mencuci tangan sebagai langkah pencegahan pertama penyebaran COVID-19, jadi <i><b>bukan pake masker</b></i> apalagi sampe <b><i>nimbun</i></b> ya temen-temen.</p>
    <p class="subtitle">Kebanyakan mungkin jarang mencuci tangan, mungkin juga ada beberapa diantara kita yang mencuci tangan hanya dengan air, dan mungkin juga masih banyak yang tidak mengerti cara mencuci tangan yang benar. Mencuci tangan dengan benar tentunya dapat mengurangi penyebaran bakteri dan virus.</p>
    <p class="subtitle">Untuk kalian yang belum tau cara mencuci tangan yang benar, tenang aja kita bakal kasih tau kok. Yuk belajar bareng cara cuci tangan yang benar. <b>Berikut tata caranya</b></p>
    <p class="subtitle"><b>1</b> Kalian harus basahi tangan kalian dengan air bersih<br>
                        <b>2</b> Ambil sabun secukupnya untuk permukaan tangan <br>
                        <b>3</b> Gosok deh tuh kedua telapak tangan <br>
                        <b>4</b> Sekarang giliran punggung tangan sama sela-sela jari yang digosok <br>
                        <b>5</b> Bersihin telapak tangan dengan kuku <br>
                        <b>6</b> Gosok kedua telapak tangan dengan air yang mengalir <br>
                        <b>7</b> Keringin tangan pake handuk atau tisu yang bersih. <br>
    </p>
    <p class="subtitle"><b><i>Gimana kalau gak ada air atau lagi diluar?</i></b> Cukup pakai <i><b>Handsanitizer</b></i>, gosok ditangan sampai cairannya hilang. Gak susah kan? Yuk jadikan cuci tangan sebagai kebiasaan kita dalam berkegiatan sehari-hari!</p>
    <p class="subtitle"><b><i>#YukCuciTangan!</i></b></p>

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

.footer {
  align-items: center;
  align-content: center;
  text-align: right;
  margin: 120px 0 0 0;
  background: white;
}

.links {
  padding-top: 15px;
}

.card-body {
  font-size: 65px;
  font-weight: 700;
}

.confirmed {
  color: #f8da2e;
}

.recovered {
  color: #07a142;
}

.deaths {
  color: #c20505;
}

.card {
  margin: 0.5rem;
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

  .card-body {
    font-size: 28;
  }

  .footer {
    text-align: center;
  }
}
</style>
