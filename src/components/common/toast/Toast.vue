<script>
export default {
  name: "Toast",
  data() {
    return {
      message: "",
      isShow: false
    }
  },
  methods: {
    show(message = '默认文字', duration = 2000) {
      this.isShow = true;
      this.message = message;
      setTimeout(() => {
        this.isShow = false;
        this.message = "";
      }, duration);
    }
  },
}
</script>

<template>
  <div class="toast">
    <div v-show="isShow">
      {{ message }}
    </div>
  </div>
</template>

<style scoped>
.toast {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  padding: 8px 10px;

  color: #fff;
  background-color: rgba(0, 0, 0, 0.75);

  z-index: 999;
}
</style>
