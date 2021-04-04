<template>
	<div>
        <ul v-for="task in tasks" :key="task.id">
            <li class="flex items-center mb-3">
            	<Task @toggle-reminder="$emit('toggle-reminder', task.id)" @delete-task="$emit('delete-task', task.id)" :task="task" />
            </li>
        </ul>
    </div>	
</template>

<script>
import Task from "./Task.vue"

export default {
	name: 'Tasks',
	props: {
		tasks: Array
	},
	components: {
		Task
	},
	emits: ['delete-task', 'toggle-reminder']
}
</script>