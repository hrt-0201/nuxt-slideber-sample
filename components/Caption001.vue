<template>
<!-- 参考にしたサイト：https://saruwakakun.com/html-css/reference/h-design -->
    <h4>{{message}}</h4>
</template>

<script>
export default {
    props: ["message"],
    name: "Caption001",
}
</script>

<style scoped>
h4 {
  position: relative;/*相対位置*/
  padding-left: 1.2em;/*アイコン分のスペース*/
  line-height: 1.4;/*行高*/
  color: #7b6459;/*文字色*/
}

h4:before {
  font-family: "Font Awesome 5 Free";
  content: "\f1b0";/*アイコンのユニコード*/
  font-weight: 900;
  position: absolute;/*絶対位置*/
  font-size: 1em;/*サイズ*/
  left: 0;/*アイコンの位置*/
  top: 0;/*アイコンの位置*/
  color: #ff938b; /*アイコン色*/
}
</style>