<template>
  <div>
    <h2>FORMULIR</h2>
    <form @submit.prevent="submitForm">
      <label for="">Nama:</label>
      <input class="{'is-invalid' :isInvalidName}" type="text" name="nama" v-model="kontak.nama">
      <div v-if="isInvalidName" class="error-message"></div>
      <br>
      <label for="">Kelas:</label>
      <input class="{'is-invalid' :isInvalidKelas}" name="kelas" v-model="kontak.kelas">
      <div v-if="isInvalidKelas" class="error-message"></div>
      <br>
      <label for="">Alamat:</label>
      <input class="{'is-invalid' :isInvalidAlamat}" name="alamat" v-model="kontak.alamat">
      <div v-if="isInvalidAlamat" class="error-message"></div>
      <br>
      <label for="">Nilai Matematika:</label>
      <input class="{'is-invalid' :isInvalidNilaimtk}" type="number" name="nilaimtk" v-model="kontak.nilaimtk">
      <div v-if="isInvalidNilaimtk" class="error-message"></div>
      <br>
      <label for="">Nilai IPA:</label>
      <input class="{'is-invalid' :isInvalidNilaiipa}" type="number" name="nilaiipa" v-model="kontak.nilaiipa">
      <div v-if="isInvalidNilaiipa" class="error-message"></div>
      <br>
      <label for="">Nilai Bahasa Indo:</label>
      <input class="{'is-invalid' :isInvalidNilaibi}" type="number" name="nilaibi" v-model="kontak.nilaibi">
      <div v-if="isInvalidNilaiib" class="error-message"></div>
      <br>
      <input type="submit" value="Simpan">
      <div id="input"></div>
    </form>
  <div v-if="showResult">
    nama : {{ name }} <br>
    kelas : {{ kelas }} <br>
    alamat : {{ alamat }} <br>
    nilai mtk: {{ nilaimtk }} <br>
    nilai ipa: {{ nilaiipa }} <br>
    nilai bahasa indo: {{ nilaibi }} <br>
    total nilai: {{ nilaimtk + nilaiipa + nilaibi }} <br>
    status : {{ nilaimtk + nilaiipa + nilaibi >= 240 ? 'lulus' : 'tidak lulus' }}
  </div>
  </div>
</template>

<script>
import { ref } from 'vue'
export default {
  name: 'MyComponent',
  data() {
    return {
      kontak:
      {
        nama: '',
        kelas: '',
        alamat: '',
        nilaimtk: '',
        nilaiipa: '',
        nilaibi: '',
      },
      showResult: ref(false),
      name: ref(''),
      kelas: ref(''),
      alamat: ref(''),
      nilaimtk: ref(''),
      nilaiipa: ref(''),
      nilaibi: ref(''),
      total: 0,
      
    };
  },
  computed: {
    isInvalidName() {
      return this.kontak.nama.length < 1;
    },
    isInvalidKelas() {
      return this.kontak.kelas.length < 1;
    },
    isInvalidAlamat() {
      return this.kontak.alamat.length < 1;
    },
    isInvalidNilaimtk() {
      return this.kontak.nilaimtk.length < 1;
    },
    isInvalidNilaiipa() {
      return this.kontak.nilaiipa.length < 1;
    },
    isInvalidNilaibi() {
      return this.kontak.nilaibi.length < 1;
    }
  },




  methods: {
    submitForm() {
      this.name = this.kontak.nama;
      this.kelas = this.kontak.kelas;
      this.alamat = this.kontak.alamat;
      this.nilaimtk = this.kontak.nilaimtk;
      this.nilaiipa = this.kontak.nilaiipa;
      this.nilaibi = this.kontak.nilaibi;
      this.total = parseInt(this.nilaimtk) + parseInt(this.nilaiipa) + parseInt(this.nilaibi)
      this.showResult = true;
      this.isInvalidKelas = false;
      this.isInvalidName = false;
    },
  },
};

</script>

<style>
h1 {
  color: blue;
}

;

.error-message {
  color: red;
  margin-top: 5px;
}

.is-invalid {
  border-color: red;
}
</style>