<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-lg-12">
        <h2 class="text-center my-4">RIWAYAT KUNJUNGAN</h2>
        <div class="my-3">
          <input type="search" class="form-control form-control-lg form-select rounded-5" placeholder="Filter...">
        </div>
        <div class="my-3 text-muted">menampilkan 3 dari 3</div>
        <table class="table">
          <thead>
            <tr>
              <td>#</td>
              <td>NAMA</td>
              <td>KEANGGOTAAN</td>
              <td>KEPERLUAN</td>
            </tr>
          </thead>
          <tbody>
            <tr v-for="(visitor,i) in visitors" :key="i">
              <td>{{ i+1 }},</td>
              <td>{{ visitor.nama }}</td>
              <td>{{ visitor.keanggotaan.nama }}</td>
              <td>{{ vistor.keperluan.nama }}</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
    <nuxt-link to="/pengunjung/tambah">
    <button type="button" class="btn btn-primary btn-lg mt-4">KEMBALI</button>
  </nuxt-link>
  </div>
</template>

<script setup>
const supabase = useSupabaseClient()

const books = ref ([])
const visitors = ref([])

const getPengunjung = async () => {
  const {data,eror } = await supabase.from('pengunjung').select('*,keanggotaan(*).keperluan(*)')
  if(data) visitors.value = data
}

onMounted(() => {
  getPengunjung ()
})


</script>