<template>
  <p>Registration form here</p>
  <button @click="register">Register Me</button>
</template>

<script>
export default {
  props: ['id', 'event'],
  inject: ['GStore'],
  methods: {
    register() {
      //Assuming successful API call to register them
      this.GStore.flashMessage =
        'You are successfully registered for ' + this.event.title
      setTimeout(() => {
        // After 3 seconds remove it
        this.GStore.flashMessage = ''
      }, 3000) // 3000 is the minliseconds time countung down after message appear
      //Set a flash message to appear on the next page loaded which says

      this.$router.push({
        name: 'EventDetails',
        params: { id: this.event.id }
      })
    }
  }
}
</script>
