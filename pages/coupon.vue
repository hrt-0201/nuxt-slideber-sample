<template>
    <div>
        クーポンのページです
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
    </div>
</template>

<style scoped>
.ticket-design {
    padding: 10px;
}
</style>