<template>
  <div class="wrapper">
    <div class="container-fluid">
      <div class="row">
        <div class="col-lg-12">
          <h2 class="text-center my-4">ISI BUKU PENGUNJUNG</h2>

          <div class="col-6">
            <form @submit.prevent="KirimData">
              <div class="mb-3">
                <input v-model="form.nama" type="text" class="form-control form-control-lg rounded-5"
                  placeholder="NAMA...">
              </div>
              <div class="mb-3">
                <select v-model="form.keanggotaan" class="form-control form-control-lg from-select rounded-5">
                  <option value="">KEANGGOTAAN</option>
                  <option v-for="(member, i) in members" :key="i" :value="member.id">{{ member.nama }}</option>

                </select>
              </div>
              <div v-if="form.keanggotaan == '1'" class="row mb-3">
                <div class="col-md-4">
                  <select v-model="form.tingkat" class="form-control form-control-lg form-select rounded-5 mb-2">
                    <option value="">Semester</option>
                      <option value="1">1</option>
                      <option value="2">2</option>
                      <option value="3">3</option>
                      <option value="4">4</option>
                      <option value="5">5</option>
                      <option value="6">6</option>
                      <option value="7">7</option>
                      <option value="8">8</option>
                  </select>
                </div>
                <div class="col-md-4">
                  <select v-model="form.jurusan" class="form-control form-control-lg from-select rounded-5 mb-2">
                    <option value="">Prodi</option>
                    <option value="Pendidikan Bahasa Inggris">Pendidikan Bahasa Inggris</option>
                    <option value="Pendidikan Guru Sekolah Dasar">Pendidikan Guru Sekolah Dasar</option>
                    <option value="Managemen">Managemen</option>
                    <option value="Akuntansi">Akuntansi</option>
                    <option value="Agribisnis">Agribisnis</option>
                    <option value="Agroteknologi">Agroteknologi</option>
                    <option value="Peternakan">Peternakan</option>
                    <option value="Teknik Informatika">Teknik Informatika</option>
                    <option value="Farmasi">Farmasi</option>
                    <option value="Hukum">Hukum</option>
                  </select>
                </div>
                <div class="col-md-4">
                  <select v-model="form.kelas" class="form-control form-control-lg from-select rounded-5 mb-2">
                    <option value="">KELAS</option>
                    <option value="A">A</option>
                    <option value="B">B</option>
                    <option value="C">C</option>
                    <option value="D">D</option>
                  </select>
                </div>
                <div class="col-md-4">
                </div>
              </div>
              <div class="mb-3">
                <select v-model="form.keperluan" class="form-control form-control-lg from-select rounded-5">
                  <option value="">KEPERLUAN</option>
                  <option v-for="(item, i) in objectives" :key="i" :value="item.id">{{ item.nama }}</option>
                </select>
              </div>
              <!-- <NuxtLink to="pengunjung/riwayat">
                <button type="submit" class="btn btn-dark btn-lg rounded-5 px-5">KIRIM</button>
              </NuxtLink> -->
              <input type="submit" value="kirim" class="btn btn-dark btn-lg rounded-5 px-5">
            </form>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const supabase = useSupabaseClient()

const members = ref([])
const objectives = ref([])

const form = ref({
  nama: "",
  keanggotaan: "",
  tingkat: "",
  kelas: "",
  jurusan: "",
  keperluan: "",
})

const KirimData = async () => {
  const { error } = await supabase.from('pengunjung').insert([form.value])
  if (error) throw error
  else navigateTo('/pengunjung/riwayat')
}

const getKeanggotaan = async () => {
  const { data, error } = await supabase.from('keanggotaan').select('*')
  if (data) members.value = data
}

const getKeperluan = async () => {
  const { data, error } = await supabase.from('keperluan').select('*')
  if (data) objectives.value = data
}

onMounted(() => {
  getKeanggotaan()
  getKeperluan()
})
</script>

<style scoped>
.wrapper {
  background-color: rgb(14, 143, 194);
  background-size: cover;
  height: 100vh;
  width: 100%;
}
</style scoped>