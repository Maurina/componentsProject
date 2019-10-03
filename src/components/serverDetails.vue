<template>
    <div>
  
                <h2>Server Details are currently not updated</h2>
                     <div class="mx-auto list-group-item cards" :key ="index" v-for="index in 5" max-width="344"> 
           
                  <h3 >  Server #{{ index }} </h3>
                  <h4> Server Status: {{ test }} </h4>
              
                </div>
           <button @click="resetStatus">Clear Status</button>
    </div>
</template>

<script>
import { eventBus } from '../main'
export default {
    props:{
        test: {
            type: String,
            required: true
        }
    },
    methods: {
        resetStatus(){
            this.test = "unknown"
        }
    },
    created() {
        eventBus.$on('testRun', (testRun) =>{
            this.test = testRun;
        })
    }
}
</script>

<style scoped>
div{
   margin: 5%;
 }
</style>