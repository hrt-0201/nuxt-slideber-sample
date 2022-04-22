<template>
  <div>
    <div class="title-area">
        <Title001 message="個人設定" />
    </div>
    <Caption001 message="性別" />
    <div class="radio-area01">
      <input class="visually-hidden" type="radio" name="fruits" id="man" />
      <label for="man">男性</label>
      <input class="visually-hidden" type="radio" name="fruits" id="woman" />
      <label for="woman">女性</label>
      <input class="visually-hidden" type="radio" name="fruits" id="etc" />
      <label for="etc">その他</label>
      <input class="visually-hidden" type="radio" name="fruits" id="none" />
      <label for="none">未回答</label>
    </div>
    <Caption001 message="年代" />
    <div class="radio-area01">
      <input class="visually-hidden" type="radio" name="fruits" id="man" />
      <label for="man">10代</label>
      <input class="visually-hidden" type="radio" name="fruits" id="woman" />
      <label for="woman">20代</label>
      <input class="visually-hidden" type="radio" name="fruits" id="etc" />
      <label for="etc">30代</label>
      <input class="visually-hidden" type="radio" name="fruits" id="none" />
      <label for="none">未回答</label>
    </div>
    <Caption001 message="興味のある項目" />
    <Checkbox />
  </div>
</template>

<style scoped>
.title-area {
    padding-bottom: 20px;
}
label {
  position: relative;
  cursor: pointer;
  padding-left: 30px;
}

label::before,
label::after {
  content: "";
  display: block;
  border-radius: 50%;
  position: absolute;
  transform: translateY(-50%);
  top: 50%;
}

label::before {
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 50%;
  width: 20px;
  height: 20px;
  left: 5px;
}

label::after {
  background-color: #ddd;
  border-radius: 50%;
  opacity: 0;
  width: 16px;
  height: 16px;
  left: 7px;
}

input:checked + label::after {
  opacity: 1;
}

.visually-hidden {
  position: absolute;
  white-space: nowrap;
  border: 0;
  clip: rect(0 0 0 0);
  clip-path: inset(50%);
  overflow: hidden;
  height: 1px;
  width: 1px;
  margin: -1px;
  padding: 0;
}
</style>