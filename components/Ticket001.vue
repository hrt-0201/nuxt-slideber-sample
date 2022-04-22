<template>
    <div class="ticket">
<div class="ticket-inner">
<div class="ticket-left">
<div style="line-height:1;">クーポン名</div>
<div class="ticket-code">{{item}}</div>
<div class="ticket-name">{{store}}</div>
</div>
<div class="ticket-right">
<div class="ticket-ppp">PRICE</div>
<div><i class="fas fa-yen-sign"></i>{{beforeprice}}</div>
<div style="font-size:135%;">↓</div>
<div class="ticket-price"><i class="fas fa-yen-sign"></i>{{afterprice}}</div>
</div>
</div>
</div>
</template>

<script>
export default {
    props: ["item", "store", "beforeprice", "afterprice"],
    name: "Ticket001",
}
</script>

<style scoped>
.ticket{
background:url('~/assets/image/p0055_m.jpg');
background-size:cover;
padding:0.3rem;
box-shadow:1px 1px 6px rgba(10,5,0,0.5);
color:#433;
max-width:480px;
border:1px solid rgba(30,5,0,0.12);
}
.ticket-inner{
padding:0 0.7rem;
display:flex;
justify-content:space-between;
align-items:center;
border:2px solid rgba(30,5,0,0.5);
border-radius:2px;
text-align:center;
}
.ticket-left{
width:65%;
border-right:1px dashed #976;
padding:0.7rem 1rem 0.7rem 0;
font-size:80%;
}
.ticket-code{
font-weight:bold;
font-size:1.8rem;
line-height:1.2;
padding-top: 10px;
}
.ticket-name{
border-top:1px solid #666;
padding:0.4em 0 0 0;
line-height:1.2;
font-size:1.2rem;
}
.ticket-right{
width:30%;
padding:0.7rem 0;
line-height:1.2;
}
.ticket-price{
font-weight:bold;
font-size:160%;
color: red;
}
.ticket-ppp{
border-bottom:1px solid #666;
padding-bottom:6px;
margin-bottom:6px;
}
</style>