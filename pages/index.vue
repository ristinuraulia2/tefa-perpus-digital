<template>
  <div class="container-fluid">
    <div class="row my-5">
      <div class="col-lg-6">
        <nuxt-link to="/pengunjung/tambah">
          <div class="card bg-pengunjung rounded-5">
            <div class="card-body">
              <h2>Pengunjung</h2>
            </div>
          </div>
        </nuxt-link>
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
    <h2>STATISTIK</h2>
    <div class="container-fluid">
        <div class="row justify-content-evenly rounded-5">
          <div class="col-5">
            <div class="raccing">
              <h2><strong>3</strong> Pengunjung</h2>
              </div>
            </div>
            <div class="col-5">
              <div class="raccing1">
                <h2><strong>180</strong>Buku</h2>
              </div>
            </div>
          </div>
        </div>
    </div>
</template>

<style scoped>
.card {
  height: 250px;
  box-shadow: 1px 1px 1px #424242;
}
.card.bg-pengunjung {
  background-image: url("../assets/img/bg-home-kunjungan.jpg");
  background-repeat: no-repeat;
  background-position: center center;
  background-size: cover;
}
.card.bg-buku {
  background: url("../assets/img/bg-home-cari-buku.jpg") no-repeat center center;
  background-size: cover;
}
</style>