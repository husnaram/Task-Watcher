<template>
	<div @dblclick="$emit('toggle-reminder', task.id)" class="p-4 rounded bg-deep-purple-50 w-full flex items-center justify-between" :class="[task.reminder ? 'border-l-4 border-green-accent-400' : '']">
		<div>
			<h3 class="font-medium text-gray-800">{{ task.text }}</h3>
			<p class="text-sm text-gray-600">{{ task.day }}</p>
		</div>
		<button @click="$emit('delete-task', task.id)" class="font-bold text-red-500 cursor-pointer">
			<svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path></svg>
		</button>
	</div>
</template>

<script>
export default {
	name: 'Task',
	props: {
		task: Object
	}
}
</script>