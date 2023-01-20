<template>
   
        
    <div class="max-w-full h-[800px] flex items-center">
          
       
    
       
            <FormButton :number="numbers" 
            />

                
      

    
   

    </div>
</template>

<script>
import { ref } from 'vue';
import FormButton from "@/components/FormButton.vue";
export default{
    components:{
        FormButton,
     
    },
    
    setup(){


const numbers = ['C', '/', '*', 'R', 7, 8, 9, '-', 4, 5, 6, '+', 1, 2, 3, '=', '%', 0, '.']

    return{
        
        numbers,
        

    }
    
}

}



</script>