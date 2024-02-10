<script>


import axios from 'axios'; //importo Axios
import { store } from "./store.js"; //state management
import HeaderMenu from './components/HeaderMenu.vue';

export default {
	components: {
		HeaderMenu
	},
	data() {
		return {
			store
		}
	},
	mounted() {
		this.getProjectList();
	},
	methods: {
		getProjectList(){
			axios.get(this.store.apiUrl + "cars").then(risultato => {
				console.log(risultato);
				this.store.projectList = risultato.data;
			}).catch(errore => {
				console.error(errore);
			});
		}

	}
}
</script>

<template>
	<HeaderMenu/>
	<router-view/>
</template>

<style lang="scss">
// importo il foglio di stile generale dell'applicazione, non-scoped
@use './styles/general.scss';
</style>

<style scoped lang="scss">
// importo variabili
// @use './styles/partials/variables' as *;

// ...qui eventuale SCSS di App.vue

</style>