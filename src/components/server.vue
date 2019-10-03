<template>
    <div> 
            <v-card class="mx-auto list-group-item cards" :key ="index" v-for="index in 5" max-width="344">
              <v-card-text>
                <div>
               
                  <h2>  Server #{{ index }} </h2>
                
                </div>
              </v-card-text>
              <v-card-actions>
                <v-btn @click="serverStatus" text color="teal accent-4"> 
                  Test
                </v-btn>
              </v-card-actions>
          
            </v-card>

    </div>
</template>

<script>
    import { eventBus } from '../main'
    export default {
        data: function(){
            return{
                test: "normal"
            }
        },
    methods: {
        serverStatus() {
            this.test = ["critical", ""]
            eventBus.$emit('testRun', this.test)
        }
    }
}
</script>

<style scoped>
.cards{
   margin: 5%;
 }
</style>