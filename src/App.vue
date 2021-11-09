<template>
	<div id="app">
		<div class="line">
			<Converter coin-a="USD" coin-b="BRL"/>
			<Converter coin-a="BRL" coin-b="USD"/>
		</div>
		<div class="line">
			<Converter coin-a="CAD" coin-b="BRL"/>
			<Converter coin-a="BRL" coin-b="CAD"/>
		</div>
		<div class="line">
			<Converter coin-a="EUR" coin-b="BRL"/>
			<Converter coin-a="BRL" coin-b="EUR"/>
		</div>
	</div>
</template>

<script>
	import Converter from '@/components/Converter.vue'

	export default {
		name: "App",
		components: {
			Converter,
		}
	}
</script>

<style scoped>
	:root {
		font-size: 10px;
	}

	#app {
		width: 90rem;
		margin: 6rem auto;
	}

	.line {
		display: flex;
		justify-content: space-around;
		margin: 2.4rem 0;
	}
</style>
