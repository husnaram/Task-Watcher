<template>
	<div class="flex items-center justify-between pb-6 mb-4 border-b">
        <div>
            <router-link to="/" class="text-2xl font-extrabold">{{ title }}</router-link>
        </div>
        <div>
        	<Button v-show="homePage" @btn-click="$emit('toggle-add-task')" :text="showAddTask ? 'Close' : 'Add Task'" :class="showAddTask ? 'bg-red-500 hover:bg-red-800' : 'bg-deep-purple-accent-400 hover:bg-deep-purple-accent-700'" />
        </div>
    </div>
</template>

<script>
import Button from "./Button";

export default {
	name: 'Header',
	props: {
		title: String,
		showAddTask: Boolean
	},
	components: {
		Button
	},
	computed: {
		homePage() {
			if (this.$route.path === '/') {
				return true
			} else {
				return false
			}
		}
	}
}
</script>