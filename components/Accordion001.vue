<template>
<!-- 参考にしたページ：https://webdesignday.jp/inspiration/technique/css/5316/ -->
  <div>
    <input :id="'acd-check1' + no" class="acd-check" type="checkbox" />
    <label class="acd-label" :for="'acd-check1' + no"
      ><div class="title-design">{{ title }}</div></label
    >
    <div class="acd-content">
      <div class="news-text" style="max-width: 400px;">{{ text }}</div>
      <a :href="link" class="news-link"
        ><i class="fas fa-newspaper"></i> 記事の続きはこちらから</a
      >
    </div>
  </div>
</template>

<script>
export default {
  props: ["title", "text", "link", "no"],
  name: "Accordion001",
};
</script>

<style scoped>
.acd-check {
  display: none;
}
.acd-label {
  background: #75fa7c;
  color: rgb(0, 0, 0);
  display: block;
  margin-bottom: 1px;
  padding: 10px;
  position: relative;
}
.title-design {
  max-width: 300px;
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}
.news-text {
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-line-clamp: 3;
  overflow: hidden;
}
.news-link {
  right: 5px;
}
.acd-label:after {
  background: #287703;
  box-sizing: border-box;
  color: #fff;
  content: "\f067";
  display: block;
  font-family: "Font Awesome 5 Free";
  font-weight: 900;
  height: 45px;
  padding: 10px 20px;
  position: absolute;
  right: 0;
  top: 0px;
}
.acd-content {
  border: 1px solid #333;
  display: block;
  height: 0;
  opacity: 0;
  padding: 0 10px;
  transition: 0.5s;
  visibility: hidden;
}
.acd-check:checked + .acd-label:after {
  content: "\f068";
}
.acd-check:checked + .acd-label + .acd-content {
  height: 150px;
  opacity: 1;
  padding: 10px;
  visibility: visible;
}
</style>