<template>
  <p>Edit the event here</p>
  <button @click="edit">Edit Me</button>
</template>

<script>
export default {
  props: ['id', 'event'],
  inject: ['GStore'],
  methods: {
    edit() {
      this.GStore.flashMessage = 'the data has been updated ' + this.event.title
      setTimeout(() => {
        this.GStore.flashMessage = ''
      }, 3000)

      this.$router.push({
        name: 'EventDetails',
        params: { id: this.event.id }
      })
    }
  }
}
</script>
