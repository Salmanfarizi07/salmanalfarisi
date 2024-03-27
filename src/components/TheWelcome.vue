<!-- InputTextMultiple.vue -->
<template>
  <div>
    <label for="inputText">Masukkan Nama :  </label>
    <input type="text" id="inputText" v-model="currentInput">
    <button @click="addText">Simpan</button>
    <table v-if="texts.length > 0">
      <thead>
        <tr>
          <th>No</th>
          <th>Nama</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(text, index) in texts" :key="index">
          <td>{{ index + 1 }}</td>
          <td>{{ text }}</td>
        </tr>
      </tbody>
    </table>
    <p v-else><i>Belum ada data yang ditambahkan</i></p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentInput: '', 
      texts: []
    }
  },
  methods: {
    addText() {
      this.texts.push(this.currentInput);
      this.currentInput = '';
    }
  }
}
</script>
