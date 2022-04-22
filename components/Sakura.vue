<template>
  <div class="sakura_area">
    <ul class="sakura">
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
@import url("https://fonts.googleapis.com/css2?family=M+PLUS+Rounded+1c:wght@100&display=swap");

.sakura_area {
  width: 100%;
  height: 100px;
  padding-top: 0px;
  overflow: hidden;
  background: linear-gradient(#00bfff, #fff);
}

.sakura {
  position: absolute;
  padding: 0;
  margin: 0;
  width: 100%;
  height: 100px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.sakura h1 {
  font-family: "M PLUS Rounded 1c", sans-serif;
  font-size: 2rem;
  color: #fff;
}
</style>