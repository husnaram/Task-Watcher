<template>
    <form @submit="onSubmit" class="space-y-3 mb-10">
        <div>
            <label class="text-gray-700" for="task">Task</label>
            <input id="task" v-model="text" type="text" class="block w-full px-4 py-2 mt-1 text-gray-700 bg-white border border-gray-300 rounded-md  focus:border-blue-500 focus:outline-none focus:ring">
        </div>
        <div>
            <label class="text-gray-700" for="dayAndTime">Day & Time</label>
            <input id="dayAndTime" v-model="day" type="text" class="block w-full px-4 py-2 mt-1 text-gray-700 bg-white border border-gray-300 rounded-md focus:border-blue-500 focus:outline-none focus:ring">
        </div>
        <div class="flex items-center">
            <label class="text-gray-700 mr-4" for="setReminder">Set Reminder</label>
        	<input id="setReminder" v-model="reminder" type="checkbox" class="p-4 bg-white border border-gray-300 rounded-md focus:outline-none focus:ring">
        </div>
        <div>
            <button class="px-6 py-3 w-full leading-5 text-blue-gray-50 transition-colors duration-200 transform bg-blue-accent-200 rounded-md hover:bg-blue-accent-700 focus:outline-none focus:bg-gray-600">Save Task</button>
        </div>
    </form>
</template>
<script>
export default {
    name: 'AddTask',
    data() {
    	return {
    		text: '',
    		day: '',
    		reminder: false
    	}
    },
    methods: {
    	onSubmit(e) {
    		e.preventDefault()

    		if (!this.text) {
    			alert('Please add a task')
    			return
    		}

    		const newTask = {
    			text: this.text,
    			day: this.day,
    			reminder: this.reminder
    		}

    		this.$emit('add-task', newTask)

    		this.text = ''
    		this.day = ''
    		this.reminder = false
    	}
    }
}
</script>