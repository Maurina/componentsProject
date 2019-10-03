<template>
    <div> 
            <v-card class="mx-auto list-group-item cards" :key ="index" v-for="index in 5" max-width="344">
              <v-card-text>
                <div>
                  <ul class="list-group">
                    server #{{ index }}
                  </ul>
                </div>
              </v-card-text>
              <v-card-actions>
                <v-btn text color="teal accent-4"> 
                  Learn More
                </v-btn>
              </v-card-actions>
          
            </v-card>

    </div>
</template>

<script>
export default {
    
}
</script>

<style scoped>
.cards{
   margin: 5%;
 }
</style>