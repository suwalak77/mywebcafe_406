<script setup>
import { ref } from 'vue';

//ตัวแปร
const travel = ref("");
const money = ref(0);

//const travelList=ref(['ท่าช้าง','GoodViews','RiverSide','WarmUp','ตะวันแดง'])
const travelList=ref([
  {name:'ท่าช้าง', price:80 , size: {s:80, m: 150, l:120}},
  {name:'GoodViews', price:120 , size: {s:120, m: 180, l:250} },
  {name:'RiverSide', price:150 , size: {s:150, m: 190, l:300}},
  {name:'WarmUp', price:100 , size: {s:100, m: 200, l:500}},
  {name:'ตะวันแดง', price:90 , size: {s:90, m: 250, l:700}},
])

//function
</script>

<template>


<div class="container text-center">
  <div class="row">
    <div class="col">
      <div class="card" style="width: 18rem;">
  <img src="..." class="card-img-top" alt="...">
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
    </div>
  </div>
</div>

  <div>
    <button type="button" class="btn btn-primary">Primary</button>
    <div v-for="(i,index) in travelList" :key="index">
      {{ index +1 }}
        ชื่อ {{ i.name }} รูป {{ i.price }}
        size m = {{ i.size.m }}
        รูป แผนที่
    </div>




    <h1>ไปเที่ยวกันมั๊ย....</h1>
    <input type="radio" value="a" v-model="travel" />ภูเขา
    <input type="radio" value="b" v-model="travel" />ทะเล
    <br>
    จำนวนเงิน
    <input type="number" v-model="money" />
    <br />
    <p v-if="money < 100">อยู่บ้านนอน</p>
    <p v-else-if="money >= 100 && money < 100000000">ขึ้นรถไปเที่ยว</p>
    <p v-else>ขับเครื่องบินส่วนตัวไป</p>
    
    <!--ปุ่มเดินทาง  // ถ้าจำนวนเงิน < 50. ไม่ให้กดปุ่ม -->
    <button v-if="money < 50" type="" disabled>เดินทาง</button>
    <button v-else type="">เดินทาง</button>
    <div v-if="travel == 'a'" >ภาพภูเขา</div>
    <div v-else>ภาพทะเล</div>
  </div>
</template>