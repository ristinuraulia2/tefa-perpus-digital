<template>
  <div class="container">
    <div class="row mt-4 d-flek justify-content-evenly">
      <div class="col-lg-4">
            <img src="~/assets/img/buyya.jpeg" width="220px" height="340" class="cover" alt="cover">
          </div>
      <div class="col-4">
        <p>Judul Buku : Buya </p>
        <p>Penulis:Fuadi</p>
        <p>Penerbit : Falcon</p>
        <p>Kode Klasifikasi : 813</p>
        <p>Kode Buku :2 22016  </p>
      </div>
    </div>
    <div class="row mt-5">
      <h2>Sinopsis</h2>
      <p>Novel Buya Hamka karya Ahmad Fuadi bertemakan perjuangan dan religi, yang di mana novel ini bercerita tantang masa kecil Hamka yang merupakan anak dari seorang ulama
        hingga ia dewasa juga menjadi seorang ulama. Novel Buya Hamka juga bercerita tentang perjuangan Hamka pada masa revolusi dan penjajahan Jepang.</p>
        
      </div>

      <nuxt-link to="/buku">
        <button type="button" class="btn btn-dark mt-5">KEMBALI</button>
      </nuxt-link>
  </div>

</template>