<template>
  <div>
    <h2>formulir</h2>
    <form @submit.prevent="submitForm">
      <label for="">Nama:</label>
      <input class="{'is-invalid' :isInvalidName}" type="text" name="nama" v-model="kontak.nama">
      <div v-if="isInvalidName" class="error-message">Nama Harus Di isi</div>
      <br>
      <label for="">Email:</label>
      <input class="{'is-invalid' :isInvalidEmail}" name="email" v-model="kontak.email">
      <div v-if="isInvalidEmail" class="error-message">Email Harus Di Isi</div>
      <br>
      <input type="submit" value="Simpan">
      <div id="input"></div>
    </form>
  <div v-if="showResult">
    nama : {{ name }} <br>
    email : {{ email }}
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
        email: '',
      },
      showResult: ref(false),
      name: ref(''),
      email: ref(''),
    };
  },
  computed: {
    isInvalidName() {
      return this.kontak.nama.length < 1;
    },
    isInvalidEmail() {
      return this.kontak.email.length < 1;
    }
  },




  methods: {
    submitForm() {
      this.name = this.kontak.nama;
      this.email = this.kontak.email;
      this.showResult = true;
      this.isInvalidEmail = false;
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