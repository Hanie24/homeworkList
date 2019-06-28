<template>
  <div id="app" class="container">
    <div class="jumbotron">
      <heading :heading='title'></heading>
      <newtask :homeworks='homeworks'></newtask>
      <listhomeworks :homeworks='homeworks'></listhomeworks>
    </div>
  </div>
</template>

<script>
  import Heading from './titleComponent.vue'
  import Newtask from './newTaskComponent.vue'
  import Listhomeworks from './listHomeworksComponent.vue'
  export default {
    components: {
      Heading,
      Newtask, 
      Listhomeworks
    },
    data() {
      return {
        title: '-Lista de tareas-',
        homeworks: [
          {
            text: 'Generar banner',
            finish: false
          },
          {
            text: 'Generar mailing',
            finish: false
          },
          {
            text: 'Checklist mennen',
            finish: false
          }
        ],
      }
    }
  }
</script>

<style>

</style>