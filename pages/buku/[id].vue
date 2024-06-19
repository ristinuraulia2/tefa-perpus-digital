<template>
  <div class="container-fluid">
    <div class="row mt-4 d-flex justify-content-evenly">
      <div class="col-lg-4">
        <div class="card">
          <div class="card-body">
            <img :src="buku.cover" width="220px" height="340px" class="cover" alt="cover1">
          </div>
        </div>
      </div>
      <div class="col-4">
        <h5>Judul: {{ buku.judul }}</h5>
        <h5>Pengarang: {{ buku.pengarang }}</h5>
        <h5>Tahun terbit: {{ buku.tahun_terbit }}</h5>
        <h5>Rak: {{ buku.rak }}</h5>
      </div>
    </div>
    <div class="row mt-5">
      <h2>Sinopsis</h2>
      <p class="mt-3"> mengisahkan petualangan hidup remaja berusia 15 tahun yang memiliki kemampuan hebat dalam berburu babi hutan. 
        Hal itu membuat Teuku Muda terkesan. Bapak tua itu kemudian membawanya ke kota untuk diasuh layaknya anak angkat. Tokoh utama dalam sinopsis novel Pulang bernama Bujang.</p>
    </div>
    <nuxt-link to="/buku">
      <button type="button" class="btn btn-dark mt-5">Kembali</button>
    </nuxt-link>
  </div>
</template>

<style scoped>
.card {
  width: 255px;
  height: 370px;
  box-shadow: 1px 1px 10px #424242;
}
</style>

<script setup>
const supabase = useSupabaseClient()

const route = useRoute()
const buku = ref([])

const getBookById = async () => {
  const { data, error } = await supabase.from('buku').select(`*, kategori(*))`)
  .eq('id', route.params.id)
  if(data) buku.value = data[0]
}
</script>

<script setup>

onMounted(() => {
  getBookById()
})
</script>
<h2 class="text-start my-4">{{ buku.judul }}</h2>
<div class="row">
  <div class="col-md-3">
    <img src="buku.cover" class="cover" alt="cover buku">
  </div>
  <div class="col-md-6">
    <div class="badge bg-primary p-2">{{ buku.kategori }}</div>
    <ul class="list-group list-group-flush">
      <li class="list-group-item">Penulis: {{ buku.penulis }}</li>
      <li class="list-group-item">Penerbit: {{ buku.penerbit }}</li>
      <li class="list-group-item">{{ buku.deskripsi }}</li>
    </ul>
  </div>
</div>