<template>
  
    <div class="container">
        <img src="../assets/logo.png" alt="logo">
        <h1>Lotto Generator</h1>
    </div>
    <div class="container">
        <button @click="generate()">Generate Number</button>
    </div>
   <div class="container">
        <div class="output" v-for="digit in arrayNumber" :key="digit">
            {{ digit }}
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return {
            arrayNumber : []
        }
    },
    methods: {

       generate(){
            
            while(this.arrayNumber.length < 6){
                let digits = Math.floor((Math.random() * 41))+1;
                if(!this.arrayNumber.includes(digits)){
                    this.arrayNumber.push(digits);
                }
            }
            
        }

    }

}
</script>

<style scope>


    .container{
        display: flex;
        align-items: center;
        justify-content: center;
    }

    img{
        height: 50px;
    }

    button{
        padding: 10px;
    }
    .output{
        display: flex;
        align-items: center;
        justify-content: center;
        padding: 10px;
    }

    
</style>