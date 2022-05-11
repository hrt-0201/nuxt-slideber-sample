<template>
  <div class="container">
    <p>status：{{ status }}</p>
    <p>LINE ID：{{ lineId }}</p>
    <div class="title-area">
      <Title001 message="個人設定" />
    </div>
    <Caption001 message="性別" />
    <div class="radio-area01">
      <input
        class="visually-hidden"
        type="radio"
        name="fruits"
        id="man"
        value="man"
        v-on:change="onChangeGender"
      />
      <label for="man">男性</label>
      <input
        class="visually-hidden"
        type="radio"
        name="fruits"
        id="woman"
        value="woman"
        v-on:change="onChangeGender"
      />
      <label for="woman">女性</label>
      <input
        class="visually-hidden"
        type="radio"
        name="fruits"
        id="etc"
        value="etc"
        v-on:change="onChangeGender"
      />
      <label for="etc">その他</label>
      <input
        class="visually-hidden"
        type="radio"
        name="fruits"
        id="none"
        value="none"
        v-on:change="onChangeGender"
      />
      <label for="none">未回答</label>
    </div>
    <Caption001 message="年代" />
    <div class="radio-area02">
      <input
        class="visually-hidden01"
        type="radio"
        name="human"
        id="human10"
        value="human10"
        v-on:change="onChangeAge"
      />
      <label for="human10">10代</label>
      <input
        class="visually-hidden01"
        type="radio"
        name="human"
        id="human20"
        value="human20"
        v-on:change="onChangeAge"
      />
      <label for="human20">20代</label>
      <input
        class="visually-hidden01"
        type="radio"
        name="human"
        id="human30"
        value="human30"
        v-on:change="onChangeAge"
      />
      <label for="human30">30代</label>
      <input
        class="visually-hidden01"
        type="radio"
        name="human"
        id="humannone"
        value="humannone"
        v-on:change="onChangeAge"
      />
      <label for="humannone">未回答</label>
    </div>
    <Caption001 message="興味のある項目" />
    <Checkbox />
    <Caption001 message="プッシュ通知" />
    <div class="radio-area03">
      <input
        class="visually-hidden03"
        type="radio"
        name="notification"
        id="ok"
        value="ok"
        v-on:change="onChangeNotification"
      />
      <label for="ok">有</label>
      <input
        class="visually-hidden03"
        type="radio"
        name="notification"
        id="ng"
        value="ng"
        v-on:change="onChangeNotification"
      />
      <label for="ng">無</label>
    </div>
    <br />
    <br />
    <button @click="putData">更新</button>
    <br />
    <br />
    <button @click="deleteData">削除</button>
    <br />
    <br />
    <br />
    <br />
    <br />
    <br />
    <br />
    <br />
  </div>
</template>

<script>
export default {
  data() {
    return {
      lineId: null,
      status: null,
      gender: "",
      age: "",
      interest: "0",
      notification: "0",
    };
  },
  mounted() {
    liff
      .init({
        // TODO: Liff IDは環境変数にする
        liffId: "1656897353-XwmddGRK", // Use own liffId
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
  methods: {
    async putData() {
      const params = {
        OperationType: "PUT",
        Keys: {
          lineId: this.lineId,
          gender: this.gender,
          age: this.age,
          interest: this.interest,
          notification: this.notification,
        },
      };
      const url =
        "https://6gsnlj85d3.execute-api.ap-northeast-1.amazonaws.com/dev/userdbctrl";
      const res = await this.$axios.$post(url, params);
      console.log(res);
    },
    async deleteData() {
      const params = {
        OperationType: "DELETE",
        Keys: {
          lineId: this.lineId,
        },
      };
      // TODO: いったんコメントアウト
      // const url =
      //   "https://6gsnlj85d3.execute-api.ap-northeast-1.amazonaws.com/dev/userdbctrl";
      // const res = await this.$axios.$post(url, params);
      // console.log(res);
    },
    onChangeGender(event) {
      // クリックイベントでイベント発火
      console.log(event.target.value);
      // input type="radio"のvalueを取得して判定
      if (event.target.value === "man") {
        this.gender = "man";
      } else if (event.target.value === "woman") {
        this.gender = "woman";
      } else if (event.target.value === "etc") {
        this.gender = "etc";
      } else if (event.target.value === "none") {
        this.gender = "none";
      }
    },
    onChangeAge(event) {
      // クリックイベントでイベント発火
      console.log(event.target.value);
      // input type="radio"のvalueを取得して判定
      if (event.target.value === "human10") {
        this.age = "human10";
      } else if (event.target.value === "human20") {
        this.age = "human20";
      } else if (event.target.value === "human30") {
        this.age = "human30";
      } else if (event.target.value === "humannone") {
        this.age = "humannone";
      }
    },
    onChangeNotification(event) {
      // クリックイベントでイベント発火
      console.log(event.target.value);
      // input type="radio"のvalueを取得して判定
      if (event.target.value === "ok") {
        this.notification = "1";
      } else if (event.target.value === "ng") {
        this.notification = "0";
      }
    },
  },
};
</script>

<style scoped>
.container {
  width: 100%;
  height: 100%;
}
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
.visually-hidden01 {
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
.visually-hidden03 {
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