<template>
	<div>
		<h1>Galería de fotos</h1>

		<router-link :to="{name: 'fotos', params:{id: item}}" v-for="(item, index) of fotosarreglo" :key="index">
			<button>foto {{item}}</button>
		</router-link>
		<Foto></Foto>
		<button @click="home">Home</button>
		<button @click="anterior">Anterior</button>
		<button @click="siguiente">Siguiente</button>
	</div>
</template>

<script>
import Foto from '@/components/Foto.vue';
	export default{
		components:{
			Foto
		},
		data(){
			return{
				fotosarreglo: [1,2,3]
			}
		},
		methods:{
			home(){
				this.$router.push('/')
			},
			anterior(){
				this.$router.go(-1)
			},
			siguiente(){
				this.$router.go(1)
			}
		}
	}
</script>