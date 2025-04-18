<template>
  <div class="conten">
  <div class="container-fluid">
    <div class="row">
      <div class="col-lg-12">
        <h2 class="text-center my-4">BUKU</h2>
        <div class="my-3">
          <input type="search" class="form-container rounded-5"  width="150px"     placeholder="Search">
        </div>
        <div class="my-3 text-muted">menampilkan 3 dari 3</div>
        <div class="row">
          <div class="col-lg-2" v-for="(buku, i) in books " :key="i">
            <div class="card mb-3 mt-4">
              <div class="card-body">
                <img :src="buku.cover" class="cover" :alt="buku.judul">
              </div>
            </div>
          </div>
        </div>
        <nuxt-link to="/" class="btn btn-back btn-lg rounded-5 px-5">Kembali</nuxt-link>
      </div>
    </div>
  </div>
  </div>
</template>

<script setup>



const supabase = useSupabaseClient()



const books = ref([])
const keyword = ref('')

const getBooks = async () => {
  const {data, error } = await supabase.from('buku').select('*,kategori(*)')
  .ilike('judul', `%${keyword.value}%`)
  if (data) books.value = data
}

onMounted(() => {
  getBooks()
})
</script>


<style scoped>
.btn-back{
  background-color: whitesmoke;
}

.conten{
  background-color: #1291D8;
}
.card-body{
  width: 100%;
  height: 20em;
  padding: 0;
}
.cover{
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: 0 30;
}
</style>