<template>
  <div>
    <input :id="'acd-check1' + no" class="acd-check" type="checkbox" />
    <label class="acd-label" :for="'acd-check1' + no">{{title}}</label>
    <div class="acd-content">
      <p>{{text}}</p>
    </div>
  </div>
</template>

<script>
export default {
    props: ["title", "text", "no"],
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
  height: 50px;
  opacity: 1;
  padding: 10px;
  visibility: visible;
}
</style>