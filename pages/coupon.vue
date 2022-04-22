<template>
    <div class="container">
        <div class="title-area">
        <Title001 message="クーポン" />
    </div>
        TODO:クーポンデザインが他で使われているものを流用したのでいじって別物にしたい、、、（著作権的に）
        <div class="ticket-design">
            <Ticket001 item="生ビール割引" store="ほげ民" beforeprice="1000" afterprice="500"/>
        </div>
        <div class="ticket-design">
            <Ticket001 item="串盛り割引" store="ほげ貴族" beforeprice="1500" afterprice="1000"/>
        </div>
        <div class="ticket-design">
            <Ticket001 item="森伊蔵１杯" store="ほげ中屋" beforeprice="1500" afterprice="無料!!"/>
        </div>
        <div class="ticket-design">
            <Ticket001 item="最初の１杯" store="バーhoge" beforeprice="1000" afterprice="無料!!"/>
        </div>
        <div class="ticket-design">
            <Ticket001 item="栃木和牛ステーキ" store="ほげステーキ" beforeprice="2000" afterprice="1500"/>
        </div>
        <div class="ticket-design">
            <Ticket001 item="アユの塩焼き" store="居酒屋ほげ" beforeprice="800" afterprice="500"/>
        </div>
        <br />
        <br />
        <br />
        <br />
        <br />
        <br />
    </div>
</template>

<style scoped>
.container {
  width:100%;
  height: 100%;
}
.ticket-design {
    padding: 10px;
}
</style>