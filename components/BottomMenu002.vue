<template>
  <div class="container">
    <ul class="bottom-menu">
      <li>
        <!--　↓↓項目1. ホーム 　＃の部分にホームのURLを入れる -->
        <a href="/">
          <i class="far fa-paper-plane"></i><br />
          <span class="mini-text">ホーム</span>
        </a>
      </li>

      <li class="menu-width-max">
        <!-- ↓↓項目2. おすすめ　すぐ下の"＃"はそのまま -->
        <a href="/news">
          <i class="fas fa-comments"></i><br />
          <span class="mini-text">ニュース</span>
        </a>

        <!-- 下の"#"の部分におすすめ"記事URL"とタイトル等を入れる -->
        <!-- 今のところ使い道がないのでコメントアウト -->
        <!-- <ul class="menu-second-level">
          <li><a href="#">タイトル１</a></li>
          <li><a href="#">タイトル２</a></li>
          <li><a href="#">タイトル３</a></li>
          <li><a href="#">タイトル４</a></li>
          <li><a href="#">タイトル５</a></li>
        </ul> -->
      </li>
      <li>
        <!-- ↓↓項目3.　-->
        <a href="/coupon">
          <i class="fas fa-barcode"></i><br />
          <span class="mini-text">クーポン</span>
        </a>
      </li>
      <li>
        <!-- ↓↓項目4.　-->
        <a href="/admin">
          <i class="far fa-address-card"></i><br />
          <span class="mini-text">個人設定</span>
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "BottomMenu002",
};
</script>

<style scoped>
/*========================
　smartphone　bottom menu
　========================*/

.mini-text {
  font-size: 10px;
} /*文字大きさ*/

ul.bottom-menu {
  position: fixed;
  left: 0;
  bottom: 0;
  width: 100%;
  height: 60px; /*高さ*/
  margin: 0;
  padding: 0;
  background-color: #f5f5f5; /*背景色*/
  border-top: 2px solid #808080; /*バーの上の線*/
  border-bottom: 2px solid #808080; /*バーの下の線*/
  z-index: 30;
}

ul.bottom-menu li {
  float: left;
  width: 25%;
  background-color: #f5f5f5; /*背景色*/
  list-style-type: none;
  text-align: center;
  font-size: 25px; /*アイコンのサイズ*/
}

.bottom-menu li a {
  display: block;
  color: #808080; /*アイコン＆文字の色*/
  padding-top: 10px;
  padding-bottom: 5px;
  line-height: 10px;
  text-decoration: none;
}

.bottom-menu li a:hover {
  color: #a9a9a9; /*マウスオーバー時の色*/
}

/* === 展開メニュー === */

ul.menu-second-level {
  visibility: hidden;
  opacity: 0;
  z-index: 1;
}

ul.menu-second-level li a {
  border-top: 1px dashed #a9a9a9; /*展開の枠点線*/
  font-size: 15px; /*展開メニューの文字サイズ*/
  line-height: 30px; /*文字の縦幅*/
}

.menu-second-level li a:hover {
  height: 100%;
  background: lightgrey; /*マウスオーバーの色*/
}

li.menu-width-max ul.menu-second-level {
  position: absolute;
  bottom: 47px; /*高さ*/
  left: 0;
  box-sizing: border-box;
  width: 100%;
  padding: 0;
}

li.menu-width-max:hover ul.menu-second-level {
  bottom: 47px; /*高さ*/
  visibility: visible;
  opacity: 1;
}

li.menu-width-max ul.menu-second-level li {
  float: left;
  width: 100%;
  border: none;
}
</style>