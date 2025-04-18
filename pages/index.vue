<template>
  <div class="conten">
    <div class="container-fluid">
      <div class="row py-5">
        <div class="col-lg-6">
          <nuxt-link to="/pengunjung">
            <div class="card bg-pengunjung rounded-5">
              <div class="card-body">
                <h2>Pengunjung</h2>
              </div>
            </div>
          </nuxt-link>
      </div>
      </div>
  
      <div class="col-lg-6">
        <nuxt-link to="/buku">
          <div class="card bg-buku rounded-5">
            <div class="card-body">
              <h2>Cari Buku</h2>
            </div>
          </div>
        </nuxt-link>
      </div>
    </div>
  </div>
</template>

<style scoped>
.conten{
  background-color: #1291D8;
}
  .card {
    height: 250px;
    box-shadow: whitesmoke;
  }
  .card.bg-pengunjung {
    background-image: url('../assets/img/cari.png');
    background-repeat: no-repeat;
    background-position: center center;
    background-size: cover;
  }
  .card.bg-buku {
    background: url('../assets/img/kunjungan.png') no-repeat center center;
    background-size: cover;
  }
</style>