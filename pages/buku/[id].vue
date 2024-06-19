<template>
  <div class="container-fluid">
    <div class="row mt-4 d-flek justify-content-evenly">
      <div class="col-lg-4">
        <div class="card">
          <div class="card-body">
            <img src="~/assets/img/tere.jpeg" width="220px" height="340px" class="cover" alt="cover1">
          </div>
        </div>
      </div>
      <div class="col-4">
        <h5>Penulis: {{ buku.penulis }}</h5>
        <h5>Penerbit: {{ buku.penerbit }}</h5>
        <h5>Tahun terbit: {{ buku.tahun.terbit }}</h5>
      </div>
    </div>
    <div class="row mt-5">
      <h2>Sinopsis</h2>
      <p class="mt-3">Deskripsi novel Pulang mengisahkan petualangan hidup remaja berusia 15 tahun
          yang memiliki kemampuan hebat dalam berburu babi hutan. Hal itu membuat Teuku Muda terkesan. 
        Bapak tua itu kemudian membawanya ke kota untuk diasuh layaknya anak angkat.
        Tokoh utama dalam sinopsis novel Pulang bernama Bujang.</p>
    </div>
    <nuxt-link to="buku">
      <button type="button" class="btn btn-dark mt-5">Kembali</button>
    </nuxt-link>
  </div>
</template>
<style scoped>
</style>

<script setup>
const supabase = useSupabaseClient()
const route = useRoute()
const buku = ref([])

const getBookById = async () => {
  const { data, error } = await supabase.from('buku').select(`*,kategori(*)`)
  .eq('id', route.params.id)
  if(data) buku.value = data[0]
}

onMounted(() => {
  getBookById()
})
</script>
        
