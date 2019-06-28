<template>
    <ul class="list-group">
        <li class="list-group-item" 
        v-for='(homework, i) of homeworks' 
        v-bind:class="{finish: homework.finish}">
            {{homework.text}}
            <span class="pull-right">
                <button type="button" 
                class="btn btn-success btn-sm glyphicon glyphicon-ok" 
                v-on:click="homework.finish = !homework.finish"></button>
            </span>
            <span class="pull-right">
                <button type="button" 
                class="btn btn-danger btn-sm glyphicon glyphicon-remove" 
                v-on:click="clear(i)"></button>
            </span>
        </li>
    </ul>
</template>

<script>
export default {
    props: ['homeworks'],
    methods:{
        clear(i){
            this.homeworks.splice(i, 1);
        }
    }
}
</script>

<style scoped>
    .finish{
    color: #7a7a7a;
    text-decoration: line-through;
    }
</style>

