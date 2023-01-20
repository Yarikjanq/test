<template>
  <div class="mx-auto w-[300px]">
    <input v-model="cheked" class="border-[1px] text-[40px] w-[100%] text-right h-[100px]" />
    <div class="grid grid-cols-4">
     
      <button  v-for="numbers in number" :key="numbers" 
      :class="{'text-blue-500': ['C','*','/','-','+', 'R','='].includes(numbers), 'bg-blue-600 text-white area' :['='].includes(numbers)}"
      class="text-center border-[1px] text-[40px]"
         @click="change(numbers)">{{ numbers }}
      </button >
      
    </div>
  </div>
</template>

<script>
import { ref } from "vue";
export default {
  props: {
    number: {
      required: true,
    },
  },
  setup(props) {
    const cheked = ref("");
    const change = (numbers) => {
     
    if (numbers === "%") {
        cheked.value /= 100;
        console.log(numbers);
        return
      }

      if (numbers === "R") {
        cheked.value = cheked.value.slice(0, -1);
   
        return
      }
      if(numbers === '='){
        cheked.value = eval(cheked.value)
        return
      }
      if(numbers === 'C'){
        cheked.value = ''
        return
      }
      cheked.value = cheked.value.toString()
      cheked.value += numbers
     
     
    };

    return {
      change,
      cheked,
    };
  },
};
</script>
<style>
.area{
    grid-area: 6 / 4 / 4 / 4;
}

</style>
