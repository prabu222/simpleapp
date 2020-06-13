<template>
  <div class="q-pa-md" style="max-width: 400px">

    <q-form
      @submit="onSubmit"
      @reset="onReset"
      class="q-gutter-md"
    >
      <q-input
        filled
        v-model="name"
        label="Email*"
        hint="alghaniprabu1@gmail.com"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Please type email']"
      />

      <q-input
        filled
        type="password"
        v-model="age"
        label="Password"
        lazy-rules
        
       :rules="[ val => val && val.length > 0 || 'Please type password']"
      />

      <q-toggle v-model="accept" label="I accept the license and terms" />

      <div>
        <q-btn @click="submitclick" label="Submit" type="submit" color="primary"/>
        <q-btn label="Reset" type="reset" color="primary" flat class="q-ml-sm" />
      </div>
    </q-form>

  </div>
</template>

<script>
export default {
  data () {
    return {
      name: null,
      age: null,

      accept: false
    }
  },

  methods: {

    submitclick () {
            this.$router.push("/homepage")
        },
    onSubmit () {
      if (this.accept !== true) {
        this.$q.notify({
          color: 'red-5',
          textColor: 'white',
          icon: 'warning',
          message: 'You need to accept the license and terms first'
        })
      }
      else {
        this.$q.notify({
          color: 'green-4',
          textColor: 'white',
          icon: 'cloud_done',
          message: 'Submitted'
        })
      }
    },

    onReset () {
      this.name = null
      this.age = null
      this.accept = false
    }
  }
}
</script>