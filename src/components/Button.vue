<template>
	<button @click="onClick()" class="inline-flex items-center justify-center w-full px-6 py-2 font-medium tracking-wide text-blue-gray-50 transition duration-200 rounded shadow-md focus:shadow-outline focus:outline-none">
		{{ text }}
	</button>
</template>

<script>
export default {
	name: 'Button',
	props: {
		text: String
	},
	methods: {
		onClick() {
			this.$emit('btn-click')
		}
	}
}	
</script>