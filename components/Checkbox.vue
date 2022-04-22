<template>
<!-- 参考にしたサイト：https://webdesignfacts.net/entry/checkboxes-css/#CSS1　ここの「ボタン風チェックボックスCSS」 -->
    <div class="container">
  <ul class="ks-cboxtags">
    <li><input type="checkbox" id="checkboxOne" value="Rainbow Dash"><label for="checkboxOne">体を動かす</label></li>
    <li><input type="checkbox" id="checkboxTwo" value="Cotton Candy"><label for="checkboxTwo">みんなでワイワイ</label></li>
    <li><input type="checkbox" id="checkboxThree" value="Rarity"><label for="checkboxThree">1人でしんみり</label></li>
    <li><input type="checkbox" id="checkboxFour" value="Moondancer"><label for="checkboxFour">まったり雰囲気</label></li>
    <li><input type="checkbox" id="checkboxFive" value="Surprise"><label for="checkboxFive">ちょいと背伸び</label></li>
    <li><input type="checkbox" id="checkboxSix" value="Twilight Sparkle"><label for="checkboxSix">子供の心を忘れたくない</label></li>
    <li><input type="checkbox" id="checkboxSeven" value="Fluttershy"><label for="checkboxSeven">気分は秋葉原</label></li>
  </ul>

</div>
</template>

<script>
export default {
    props: ["message"],
    name: "Checkbox"
}
</script>

<style scoped>
body,
html {
    margin: 0;
    padding: 0;
}

body {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 50vh;
    background: #FFEFBA;
    /* fallback for old browsers */
    background: -webkit-linear-gradient(to right, #FFFFFF, #FFEFBA);
    /* Chrome 10-25, Safari 5.1-6 */
    background: linear-gradient(to right, #FFFFFF, #FFEFBA);
    /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */

}

.container {
    max-width: 640px;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    font-size: 13px;
}

ul.ks-cboxtags {
    list-style: none;
    /* padding: 20px; */
}
ul.ks-cboxtags li{
  display: inline;
}
ul.ks-cboxtags li label{
    display: inline-block;
    background-color: rgba(255, 255, 255, .9);
    border: 2px solid rgba(139, 139, 139, .3);
    color: #adadad;
    border-radius: 25px;
    white-space: nowrap;
    margin: 3px 0px;
    -webkit-touch-callout: none;
    -webkit-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    user-select: none;
    -webkit-tap-highlight-color: transparent;
    transition: all .2s;
}

ul.ks-cboxtags li label {
    padding: 8px 12px;
    cursor: pointer;
}

ul.ks-cboxtags li label::before {
    display: inline-block;
    font-style: normal;
    font-variant: normal;
    text-rendering: auto;
    -webkit-font-smoothing: antialiased;
    font-family: "Font Awesome 5 Free";
    font-weight: 900;
    font-size: 12px;
    padding: 2px 6px 2px 2px;
    content: "\f067";
    transition: transform .3s ease-in-out;
}

ul.ks-cboxtags li input[type="checkbox"]:checked + label::before {
    content: "\f00c";
    transform: rotate(-360deg);
    transition: transform .3s ease-in-out;
}

ul.ks-cboxtags li input[type="checkbox"]:checked + label {
    border: 2px solid #1bdbf8;
    background-color: #12bbd4;
    color: #fff;
    transition: all .2s;
}

ul.ks-cboxtags li input[type="checkbox"] {
  display: absolute;
}
ul.ks-cboxtags li input[type="checkbox"] {
  position: absolute;
  opacity: 0;
}
ul.ks-cboxtags li input[type="checkbox"]:focus + label {
  border: 2px solid #e9a1ff;
}
</style>