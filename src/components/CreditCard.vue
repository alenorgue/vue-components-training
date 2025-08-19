<script setup>
import { computed } from 'vue';


const props = defineProps({
    type: {type:String, required:true},
   number: {type:String, required:true},
    expirationMonth: {type:Number, required: true},
    expirationYear: {type:Number, required: true},
    bank: {type:String, required: true},
    owner: {type:String, required: true},
    bgColor: {type:String, required: true},
    color: {type:String, required: true}
})

const encryptedNumber = computed(() => {
return '•••• •••• •••• ' + props.number.slice(-4);
});

</script>

<template>
 
    <div class="credit-card" :style="{ backgroundColor: bgColor, color: color }">
    <img
        v-if="type === 'Visa'"
        src="/visa.png"
        alt="Visa"
        style="width:60px; margin-bottom:10px; margin-left:auto;"
    />
    <img
        v-else-if="type === 'Master Card'"
        src="/master-card.svg"
        alt="Master Card"
        style="width:60px; margin-bottom:10px; margin-left: auto;"
    />
      <h2> {{ encryptedNumber }} </h2>
      <p> <strong> Expires </strong> {{ expirationMonth }}/{{ expirationYear }}   {{ bank }}</p>
       <p> {{ owner }}</p>
    </div>
 
</template>

<style scoped>

 .credit-card{
    width: 350px;
    height: 210px;
    background-color: #333;
    border-radius: 10px;
    padding: 20px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    color: white;
 }

</style>
