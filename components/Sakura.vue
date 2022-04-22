<template>
  <div class="header_area">
    <ul class="header">
      <h1>Utsunomiya News</h1>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Sakura",
};
</script>

<style scoped>
.header_area {
  width: 100%;
  height: 100px;
  padding-top: 0px;
  overflow: hidden;
  background: linear-gradient(#00bfff, #fff);
}

.header {
  /* position: absolute;を設定するとボトムメニューが崩れるためコメントアウト */
  /* position: absolute; */
  padding: 0;
  margin: 0;
  width: 100%;
  height: 100px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.header h1 {
  font-family: "M PLUS Rounded 1c", sans-serif;
  font-size: 2rem;
  color: #fff;
}
</style>