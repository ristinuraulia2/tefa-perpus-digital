<template>
    <div class="container-fluid">
      <div class="row">
        <div class="col-lg-12">
          <h2 class="text-center my-4">BUKU</h2>
              <div class="my-3">
                <input type ="search" class="form-control rounded-5" placeholder ="Mau baca apa hari ini?">
              </div>
                <div class="ny-3 text-muted">manampilkan 3 dari 3</div>
                <div class="row">
                  <div class="col-lg-2">
                    <div class="card mb-3">
                      <div class="card-body">
                        <nuxt-link to="/buku/buku3">
                        <img src="~/assets/img/buyya.jpeg" class="cover"  alt="cover 1">
                      </nuxt-link>
                      </div>
                    </div>
                  </div>
                  <div class="col-lg-2">
                    <div class="card mb-3">
                      <div class="card-body">
                        <nuxt-link to="/buku/buku1">
                          <img src="~/assets/img/tere.jpeg" class="cover"  alt="cover 2">
                        </nuxt-link>
                      </div>
                    </div>
                  </div>
                  <div class="col-lg-2">
                    <div class="card mb-3">
                      <div class="card-body">
                        <nuxt-link to="/buku/buku2">
                        <img src="~/assets/img/uhibbu.jpg" class="cover"  alt="cover 3">
                        </nuxt-link>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
      </template>
  
<script setup>

</script>

<script setup>
const supabase = useSupabaseClient()

</script>

<script setup>
const Supabase = useSupabaseClient()

const books = ref([])
</script>

<script setup>

const getBooks = async () => {
  const { data,eror } = await supabase.from('buku').select(`*, kategori(*)`)
  if(data) books.value = data
}
</script>

<script setup>

  onMounted(() => {
    getBooks()
  })
</script>

<div v-for="(book,i) in books" :key=""i class="col-lg-2">
  <div class="card mb-3">
    <div class="card-body">
      <img :src="book.cover" class="cover" alt="cover">
    </div>
  </div>
</div>
</script>

<form @submit.prevent="getBooks">
  <input v-model="keyword" type="search">
</form>

<script setup>

  const keyword = ref(**)

</script>

<script setup>

  const getBooks= async () => {
    const { data,error } await supabase.from 'buku'.select('*, kategori(*)')
    .ilike('judul', '%${keyword.value}%')
    id (data) books.value=data
  }
</script>

  <style scoped>
  .card-body {
    width: 100%;
    height: 20em;
    padding: 0;
}
  .cover {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: 30;
}
</style>