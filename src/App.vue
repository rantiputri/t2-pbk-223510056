<template>
  <div id="app">
    <div class="background">
      <h1 style="color: #2a668d; font-weight: bold;">Formulir Data Diri</h1>
      <form @submit.prevent="submitForm">
        <div>
          <label for="name" style="color: #2a668d;">Nama:</label>
          <input type="text" id="name" v-model="formData.name" required>
        </div>
        <div>
          <label for="birthdate" style="color: #2a668d;">Tanggal Lahir:</label>
          <input type="date" id="birthdate" v-model="formData.birthdate" required>
        </div>
        <div>
          <label style="color: #2a668d;">Jenis Kelamin:</label>
          <div>
            <input type="radio" id="male" value="Laki-laki" v-model="formData.gender">
            <label for="male" style="color: #2a668d;">Laki-laki</label>
          </div>
          <div>
            <input type="radio" id="female" value="Perempuan" v-model="formData.gender">
            <label for="female" style="color: #2a668d;">Perempuan</label>
          </div>
        </div>
        <button type="submit" style="background-color: #4b9bdd; color: white;">Kirim</button>
      </form>
      <div v-if="submitted" style="color: #2a668d; font-weight: bold;">
        <h2 style="font-weight: bold;">Data yang Dikirim:</h2>
        <p style="font-weight: bold;"><strong>Nama:</strong> {{ formData.name }}</p>
        <p style="font-weight: bold;"><strong>Tanggal Lahir:</strong> {{ formData.birthdate }}</p>
        <p style="font-weight: bold;"><strong>Jenis Kelamin:</strong> {{ formData.gender }}</p>
      </div>

      <!-- Tombol -->
      <button @click="resetForm" style="background-color: #4b9bdd; color: white;">Reset</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      formData: {
        name: '',
        birthdate: '',
        gender: ''
      },
      submitted: false
    };
  },
  methods: {
    submitForm() {
      // Lakukan sesuatu dengan data yang dikirim
      console.log("Data yang dikirim:", this.formData);
      // Set submitted menjadi true agar menampilkan data yang dikirim
      this.submitted = true;
    },
    resetForm() {
      // Reset nilai pada formulir
      this.formData.name = '';
      this.formData.birthdate = '';
      this.formData.gender = '';
      // Set submitted menjadi false untuk menyembunyikan data yang dikirim
      this.submitted = false;
    }
  }
}
</script>

<style>
.background {
  background-color: #f78f8f;
  padding: 20px;
  border-radius: 10px;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  color: #4b9bdd;
}

.form-container {
  margin-bottom: 20px;
}

.result-container {
  margin-top: 20px;
}

/* Tambahkan gaya sesuai kebutuhan */
</style>
