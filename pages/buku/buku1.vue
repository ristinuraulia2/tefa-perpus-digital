<template>
  <div class="container">
    <div class="row mt-4 d-flek justify-content-evenly">
      <div class="col-lg-4">
            <img src="~/assets/img/tere.jpeg" width="220px" height="340" class="cover" alt="cover">
          </div>
      <div class="col-4">
        <p>Judul Buku : Pulang</p>
        <p>Penulis : Tere Liye</p>
        <p>Penerbit : Republika Penerbit</p>
        <p>Tebal : 400 halaman</p>
        <p>Tahun Terbit : 2015</p>
      </div>
    </div>
    <div class="row mt-5">
      <h2>Sinopsis</h2>
      <p> Deskripsi novel Pulang mengisahkan petualangan hidup remaja berusia 15 tahun yang memiliki kemampuan hebat dalam berburu babi hutan. 
        Hal itu membuat Teuku Muda terkesan. Bapak tua itu kemudian membawanya ke kota untuk diasuh layaknya anak angkat. Tokoh utama dalam sinopsis novel Pulang bernama Bujang.</p>
      </div>

      <nuxt-link to="/buku">
        <button type="button" class="btn btn-dark mt-5">KEMBALI</button>
      </nuxt-link>
  </div>

</template>