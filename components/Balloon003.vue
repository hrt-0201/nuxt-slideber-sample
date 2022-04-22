<template>
  <!-- 参考にしたサイト：https://saruwakakun.com/html-css/reference/speech-bubble -->
  <!-- 点滅はここ：https://1-notes.com/flash-animation/ -->
  <div class="balloon3">HOT</div>
</template>

<script>
export default {
  name: "Balloon003",
};
</script>

<style scoped>
.balloon3 {
  position: relative;
  display: inline-block;
  margin: 1.5em 0;
  padding: 0 5px;
  width: 90px;
  height: 90px;
  line-height: 90px;
  text-align: center;
  color: #fff;
  font-size: 20px;
  font-weight: bold;
  background: #ffab3d;
  border-radius: 50%;
  box-sizing: border-box;
  animation: flash 1s linear infinite;
}

.balloon3:before {
  content: "";
  position: absolute;
  bottom: -25px;
  left: 50%;
  margin-left: -15px;
  border: 15px solid transparent;
  border-top: 15px solid #ffab3d;
  z-index: 0;
  animation: flash 1s linear infinite;
}

@keyframes flash {
  0% {
    opacity: 1;
  }

  50% {
    opacity: 0.2;
  }
  100% {
    opacity: 1;
  }
}
</style>