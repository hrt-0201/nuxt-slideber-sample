<template>
    <div>
        <div class="header-area"><Sakura /></div>
        <div class="contents-area">
        <div v-for="(post, index) in posts" :key="index">
            <Accordion001 :title=post.title :text=post.description :link=post.link :no=index />
        </div>
        </div>
    </div>
</template>

<script>
export default {
  async asyncData({ $axios }) {
    const params = {
      body: "usmart",
    };
    // 取得先のURL
    const url =
      "https://57u2y22k2j.execute-api.ap-northeast-1.amazonaws.com/dev/soongetrss";
    // リクエスト（Get）
    const response = await $axios.$post(url, params).catch(function (error) {
      // エラー時の処理を書く
      console.error("ERROR!");
      return { messages: "error" };
    });

    return {
      posts: response.slice(0, 20),
    };
  },

  data: () => {
    return {
      content: "",
    };
  },
  head: {
    link: [
    ],
  },
  computed: {},
  methods: {
    reload() {
      location.reload();
    },
  },
};
</script>

<style scoped>
.header-area {
    /* position: fixed; */
    z-index: 2;
}
.contents-area {
    z-index: 1;
    /* padding-top: 100px; */
}
</style>