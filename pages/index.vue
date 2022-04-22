<template>
  <div class="container">
    <Slideshow />
    
    <h1>お店の最新のつぶやき</h1>
    <div v-for="comment in comments" :key="comment.update_date">
      <Balloon001 :store_image_url="comment.store_image_url" :store_name="comment.store_name" :comment="comment.comment" :update_date="comment.update_date" />
    </div>
    <div class="balloon-point">
      <Balloon003 />
    </div>
  </div>
</template>

<script>
export default {
    async asyncData({ $axios }) {
    const params = {
      OperationType: "COMMENT",
    };
    // 取得先のURL
    const url =
      "https://pjle7dwta5.execute-api.ap-northeast-1.amazonaws.com/APITest02/dynamodbctrl";
    // リクエスト（Post）
    const response = await $axios.$post(url, params).catch(function(error) {
        // エラー時の処理を書く
        console.log('ERROR!')
    });
    // 配列で返ってくるのでJSONにして返却
    // console.log(response);
    return {
      comments: response.Items,
    };
  },
}
</script>

<style scoped>
.container {
  width:100%;
  height: 100%;
}
.balloon-point {
  position: fixed;
  top: 70%;
  left: 50%;
}


</style>