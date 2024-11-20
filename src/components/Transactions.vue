<template>
<div class="grid grid-cols-[4fr_4fr_1fr] content-center items-center border py-2 px-2" v-for="(tran, index) in transactions" :key="tran.id">
    <div class=""> {{ tran.name }}</div>
    <div :class="{'text-red-600': tran.amount < 0}" class="text-right pe-3">{{ tran.amount }}</div>
    <button @click="handleClick(tran.id)" class="bg-rose-500 justify-end rounded-md text-white hover:bg-rose-700 px-1 py-1">Delete</button>
</div>
 </template>
 
 <script>
 export default {
   name: "Transactions",
   data() {
     return {
       
     }
   },
   props: ["transactions"],
   methods: {
    handleClick(id) {
        console.log(id),
      this.$emit("deleteTransaction", {
               id
      });
    },
  },
 };
 </script>
 
 <style></style>
 