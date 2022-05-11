<template>
  <div class="container">
    <Slideshow />

    <div class="line-info">
      <p>status：{{ status }}</p>
      <p>LINE ID：{{ lineId }}</p>
    </div>

  <ul>
    <li v-for="todo in todos" :key="todo.text">
      <input :checked="todo.done" @change="toggle(todo)" type="checkbox">
      <span :class="{ done: todo.done }">{{ todo.text }}</span>
    </li>
    <li><input @keyup.enter="addTodo" placeholder="What needs to be done?"></li>
  </ul>

    <h1>お店の最新のつぶやき</h1>
    <div v-for="comment in comments" :key="comment.update_date">
      <Balloon001
        :store_image_url="comment.store_image_url"
        :store_name="comment.store_name"
        :comment="comment.comment"
        :update_date="comment.update_date"
      />
    </div>
    <div class="balloon-point">
      <Balloon003 />
    </div>
  </div>
</template>

<script>
import { mapMutations } from 'vuex'

export default {
  async asyncData({ $axios }) {
    const params = {
      OperationType: "COMMENT",
    };
    // 取得先のURL
    const url =
      "https://pjle7dwta5.execute-api.ap-northeast-1.amazonaws.com/APITest02/dynamodbctrl";
    // リクエスト（Post）
    const response = await $axios.$post(url, params).catch(function (error) {
      // エラー時の処理を書く
      console.log("ERROR!");
    });
    // 配列で返ってくるのでJSONにして返却
    // console.log(response);
    return {
      comments: response.Items,
    };
  },
  data() {
    return {
      lineId: null,
      status: null,
    };
  },
  mounted() {
    // if (!this.canUseLIFF()) {
    //   return
    // }

    liff
      .init({
        // TODO: Liff IDは環境変数にする
        liffId: "1657084401-YLk3zQKz", // Use own liffId
      })
      .then(() => {
        // start to use LIFF's api
        this.status = "success!!!!";
        // ID Tokenを取得する
        const idToken = liff.getIDToken();
        console.log(idToken);
        this.lineId = idToken;
      })
      .catch((err) => {
        console.log(err);
      });
  },
  computed: {
    todos () {
      return this.$store.state.todo.list
    }
  },
  methods: {
    addTodo (e) {
      this.$store.commit('todo/add', e.target.value)
      e.target.value = ''
    },
    ...mapMutations({
      toggle: 'todo/toggle'
    })
  }
};
</script>

<style scoped>
.container {
  width: 100%;
  height: 100%;
}
.line-info {
  width:350px;
}
.line-info p {
  font-size: 0.5rem;
}
.balloon-point {
  position: fixed;
  top: 70%;
  left: 50%;
}
</style>