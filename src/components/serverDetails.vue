<template>
    <div>
   <v-card class="mx-auto list-group-item cards" >
         <v-card-text>
                <h2>Server Details</h2>
                     <div class="mx-auto list-group-item cards" max-width="344"> 
           
                  <h3 >  Server #{{ id }} </h3>
                  <h4> Server Status: {{ test }} </h4>
              
                </div>
           <v-btn @click="resetStatus" text color="teal accent-4">Clear Status</v-btn>
         </v-card-text>
   </v-card>
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
    data: function () {
        return {
            id:0
        }
    },
    methods: {
        resetStatus(){
            this.test = ""
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