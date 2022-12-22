<template>
  <div class="bg-warning" style="height: 100vh;">
    <div id="app" class="d-flex justify-content-center">
      <div>
        <input type="text" placeholder="Ketik nama anda..." ref="inputField" style="width: 50vh;"
          class="rounded mt-4 py-1" />
      </div>
    </div>
    <div class="d-flex justify-content-center mt-3">
      <button style="" type="button" class="bg-success border border-white py-1 px-2 text-white rounded" @click="handleShout" :disabled="message === '' ">Buat Profile Picture!</button>
    </div>
    <div class="d-flex justify-content-center" style="height: 50vh;">
      <div class="d-flex justify-content-center mt-5" v-if="shout === shout">
        <div style="background-color:aqua ; border: 21;" class="rounded-circle">
          <img :src="shout" fluid />
        </div>
      </div>
      <div v-else></div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      shout: '',
    };
  },
  methods: {
    handleShout() {
      const message = this.$refs.inputField.value;
      this.shout = `https://robohash.org/${message}`;
    },
  },
};
</script>