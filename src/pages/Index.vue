<template>
  <q-page class="flex flex-center">

  <div class="row">
    <div class="col-12">
      <h1 class="text-center">P</h1>
      </div>
       <div class="col-12 text-center">
         <q-btn size="20px" color="amber" glossy label="start"  @click="linkclick"/>
         </div>
      </div>
    
 


  </q-page>
</template>

<script>
import login from '../components/form'


export default {
  name: 'PageIndex',
  components: {
      login 
  },
  methods:  {

        linkclick () {
            this.$router.push("/login")
        }
  }
  
  
}
</script>


