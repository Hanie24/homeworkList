<template>
  <div>
    <h2>{{ heading }}</h2>
    <h3>Tareas a realizar: {{ numberHomeworks }}</h3>
  </div>
</template>

<script>
  import { bus } from './main.js'
  export default {
    props: ['heading'],
    data(){
      return { 
        numberHomeworks: 0
      }
    },
    created(){
      bus.$on('toUpDateCounter', (numberHomeworks) => {
        this.numberHomeworks = numberHomeworks;
      })
    }
  }
    
</script>

