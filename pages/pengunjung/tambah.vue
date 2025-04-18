<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-lg-12">
        <h2 class="text-center my-4">ISI BUKU PENGUNJUNG</h2>
        <form>
          <div class="mb-3">
            <input type="text" class="form-control-lg rounded-5" placeholder="NAMA....">
          </div>
          <div class="mb-3">
            <select class="form-control form-control-lg form-select rounded-5">
              <option value="">KEANGGOTAAN</option>
              <option value="Siswa">mahasiswa</option>
              <option value="Siswa">mahasiswa</option>
              <option value="Guru">Dosen</option>
              <option value="Staf">Staf</option>
              <option value="Umum">Umum</option>
            </select>
          </div>
          <div class="mb-3">
            <div class="row">
              <div class="col-md-4">
                <select class="form-control form-control-lg form-select rounded-5 mb-2">
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
              <div class="col-md4">
                <select class="form-control form-control-lg form-select rounded-5 mb-2">
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
                <select class="form-control form-control-lg form-select rounded-5 mb-2">
                  <option value="">KELAS</option>
                    <option value="A">A</option>
                    <option value="B">B</option>
                    <option value="C">C</option>
                    <option value="D">D</option>
                </select>
              </div>
            </div>
          </div>
          <div class="mb-3">
            <select class="form-control form-control-lg form-select rounded-5">
              <option value="">KEPERLUAN</option>
              <option value="baca">Baca Buku</option>
              <option value="pinjam">Pinjam Buku</option>
              <option value="kembalikan">Kembalikan Buku</option>
            </select>
          </div>
          <button type="submit" class="btn btn-dark btn-lg rounded-5 px-5">KIRIM</button>
        </form>
      </div>
    </div>
  </div>
</template>