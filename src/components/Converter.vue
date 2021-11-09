<template>
	<div class="converter">
		<h2>{{ coinA }} para {{ coinB }}</h2>
		<input type="text" v-model="valueCoinA" :placeholder="coinA">
		<input type="button" value="Converter" @click="convert">
		<h2>{{ valueCoinB }}</h2>
	</div>
</template>

<script>
	export default {
		name: 'Converter',
		props: ['coinA', 'coinB'],
		data() {
			return {
				valueCoinA: '',
				valueCoinB: 0,
			}
		},
		methods: {
			convert() {
				let fromTo =  `${this.coinA}_${this.coinB}`
				let url = "https://free.currconv.com/api/v7/convert?q=" + fromTo + "&compact=ultra&apiKey=94400c2ba950c8409bcc"

				fetch(url)
					.then(res => {
						return res.json()
					})
					.then(json => {
						let value = json[fromTo];
						this.valueCoinB = (value * parseFloat(this.valueCoinA)).toFixed(2)
					})
			}
		}
	}
</script>

<style scoped>
	.converter {
		max-width: 300px;
		padding: 20px;
		box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.16);
	}
</style>
