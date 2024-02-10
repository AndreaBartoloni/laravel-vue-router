

<script>
import { store } from "../store.js"
import ProjectListCard from '../components/ProjectListCard.vue';

export default {
    name:"ProjectList",
    components: {
        ProjectListCard
    },

    data(){
        return{
            store
        }
    }
}
</script>

<template>

    <section>
        <h1>Lista Vetture</h1>
        <ProjectListCard v-for="project in store.projectList" :key="project" :item="project" />
    </section>

</template>

<style scoped>

main {
	padding: 1rem;
}

</style>