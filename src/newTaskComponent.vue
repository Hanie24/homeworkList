<template>
    <div class="input-group">
        <input type="text" 
        placeholder="Escribe una nueva tarea" 
        v-model='newHomework' 
        v-on:keyup.enter="addHomework" 
        class="form-control">
        <span class="input-group-btn">
            <button type="button" 
            class="btn btn-primary" 
            v-on:click='addHomework'>Agregar</button>
        </span>
    </div>
</template>

<script>
export default {
    data(){
        return {
            newHomework: ''
        }
    },
    props: ['homeworks'], 
    methods: {
        addHomework(){
            let text = this.newHomework.trim();
            if(text){
                this.homeworks.push({
                    text: text,
                    finish: false
                })
            }
            this.newHomework = '';
        }
    }
}
</script>

